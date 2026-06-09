# PCPStorageProviderKey::LoadFromContainer(uchar)

- ea: `0x180015ac0`
- end: `0x1800187cc`
- name: `?LoadFromContainer@PCPStorageProviderKey@@IEAAJE@Z`
- size: `11532`
- prototype: `__int64 __fastcall(PCPStorageProviderKey *this, char)`
- caller_count: `2`
- callee_count: `32`
- tags: `file_ops, registry_config`

## callers

- `0x1800159f0`
- `0x180018e20`

## callees

- `0x18000f240`
- `0x18000f858`
- `0x180011554`
- `0x1800133c4`
- `0x1800138e0`
- `0x180014a60`
- `0x1800157c0`
- `0x180015ac0`
- `0x1800187d4`
- `0x180018874`
- `0x1800188bc`
- `0x180018924`
- `0x180018994`
- `0x180018a94`
- `0x18001add0`
- `0x1800212f0`
- `0x180029a20`
- `0x180049b30`
- `0x18004da4c`
- `0x180052290`
- `0x1800528d0`
- `0x180059b4c`
- `0x180061b6c`
- `0x1800768a0`
- `0x180076998`
- `0x1800769bc`
- `0x180076fca`
- `0x180077034`
- `0x18007704c`
- `0x1800801c8`
- `0x1800c2ce0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015e24`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001602b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001626e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001643b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016487`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016567`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800166e7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016726`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016804`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800168e8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016b4e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800179bc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015e24`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001602b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001626e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001643b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016487`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016567`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800166e7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016726`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016804`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800168e8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180016b4e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800179bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017af2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017af2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017fd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017fd5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015b8a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015b8a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001785b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001785b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180017798`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180017798`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015b4e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015bbf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015b4e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015bbf`
- `CRYPT32!CryptUnprotectData` at `0x180016964`
- `CRYPT32!CryptUnprotectData` at `0x180016964`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall PCPStorageProviderKey::LoadFromContainer(PCPStorageProviderKey *this, char a2)
{
  char v2; // r15
  unsigned int v4; // edi
  char *i; // rbx
  const char *v6; // r9
  unsigned int LastError; // ebx
  tlv *v8; // rdx
  unsigned __int8 *v9; // rcx
  void *v10; // rcx
  unsigned __int8 *v11; // rcx
  unsigned __int8 *v12; // rcx
  unsigned __int8 *v13; // rcx
  const unsigned __int16 *v14; // rdx
  unsigned __int8 *v15; // rax
  unsigned __int8 *v16; // rcx
  tlv *v18; // rdx
  unsigned __int8 *v19; // rcx
  unsigned __int8 *v20; // rcx
  unsigned __int8 *v21; // rcx
  unsigned __int8 *v22; // rcx
  unsigned __int8 *v23; // rcx
  const struct std::nothrow_t *v24; // rdx
  unsigned __int8 *v25; // rcx
  unsigned __int8 *v26; // rcx
  unsigned __int8 *v27; // rcx
  unsigned int v28; // r12d
  __int64 v29; // rcx
  int v30; // edx
  const struct std::nothrow_t *v31; // rdx
  const wchar_t *v32; // rax
  tlv *v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rax
  unsigned __int64 v36; // r9
  const struct std::nothrow_t *v37; // rdx
  unsigned __int64 v38; // rdi
  unsigned __int64 v39; // rbx
  unsigned __int16 *v40; // rax
  const struct std::nothrow_t *v41; // rdx
  unsigned __int16 *v42; // rsi
  tlv *v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // rdx
  unsigned __int64 v46; // rdi
  unsigned int v47; // eax
  unsigned __int64 v48; // r15
  __int64 v49; // r12
  tlv *v50; // rcx
  void *v51; // rcx
  unsigned __int8 *v52; // rcx
  void *v53; // rcx
  size_t v54; // rdi
  void *v55; // rax
  const struct std::nothrow_t *v56; // rdx
  void *v57; // rbx
  void *v58; // rcx
  tlv *v59; // rdi
  unsigned int v60; // edx
  __int64 v61; // rax
  __int64 v62; // rcx
  unsigned __int64 v63; // r14
  unsigned int v64; // eax
  unsigned __int64 v65; // rsi
  __int64 v66; // r12
  unsigned int v67; // ebx
  void *v68; // rax
  const struct std::nothrow_t *v69; // rdx
  void *v70; // r15
  tlv *v71; // rsi
  __int64 v72; // rcx
  __int64 v73; // rdx
  size_t v74; // rdi
  unsigned int v75; // eax
  size_t v76; // rbx
  __int64 v77; // r12
  unsigned __int64 v78; // rcx
  unsigned __int64 v79; // rbx
  void *v80; // rax
  __int64 v81; // rcx
  void *v82; // rdi
  tlv *v83; // rbx
  void *v84; // r9
  __int64 v85; // rcx
  __int64 v86; // rdx
  unsigned __int64 v87; // rdi
  unsigned int v88; // eax
  unsigned __int64 v89; // r14
  __int64 v90; // r15
  const struct std::nothrow_t *v91; // rdx
  void *v92; // rcx
  unsigned __int8 *v93; // rcx
  void *v94; // rcx
  unsigned __int8 *v95; // rcx
  unsigned int v96; // edi
  unsigned __int8 *v97; // rax
  const struct std::nothrow_t *v98; // rdx
  unsigned __int8 *v99; // rbx
  unsigned __int8 *v100; // rcx
  tlv *v101; // r14
  __int64 v102; // rax
  __int64 v103; // rcx
  unsigned __int64 v104; // rsi
  unsigned int v105; // eax
  unsigned __int64 v106; // rdi
  __int64 v107; // r12
  void **v108; // rcx
  int v109; // edi
  TpmObject *v110; // rsi
  __int64 (__fastcall *v111)(TpmObject *, _QWORD, const wchar_t *, __int64 *); // rax
  int v112; // ebx
  void (__fastcall ***v113)(_QWORD, __int64); // rcx
  int v114; // eax
  int Property; // eax
  unsigned int v116; // ebx
  void *v117; // rax
  __int64 v118; // rcx
  __int64 v119; // rdx
  unsigned int v120; // eax
  tlv *v121; // rbx
  void *v122; // rcx
  unsigned __int8 *v123; // rcx
  void *v124; // rcx
  unsigned __int8 *v125; // rcx
  DWORD v126; // edi
  unsigned __int8 *v127; // rax
  const struct std::nothrow_t *v128; // rdx
  unsigned __int8 *v129; // rbx
  unsigned __int8 *v130; // rcx
  unsigned __int8 *v131; // rcx
  void *v132; // rcx
  unsigned __int8 *v133; // rcx
  void *v134; // rcx
  tlv *v135; // rbx
  void *v136; // rcx
  unsigned __int8 *v137; // rcx
  void *v138; // rcx
  unsigned __int8 *v139; // rcx
  unsigned int v140; // edi
  unsigned __int8 *v141; // rax
  unsigned __int8 *v142; // rbx
  const struct std::nothrow_t *v143; // rdx
  int v144; // eax
  void *v145; // rcx
  unsigned __int8 *v146; // rcx
  void *v147; // rcx
  void *v148; // rcx
  unsigned __int8 *v149; // rcx
  void *v150; // rcx
  unsigned __int8 *v151; // rcx
  tlv *v152; // rbx
  void *v153; // rcx
  unsigned __int8 *v154; // rcx
  void *v155; // rcx
  unsigned __int8 *v156; // rcx
  int v157; // eax
  const struct std::nothrow_t *v158; // rdx
  void *v159; // rcx
  unsigned __int8 *v160; // rcx
  void *v161; // rcx
  unsigned __int8 *v162; // rcx
  __int64 v163; // rdx
  const struct std::nothrow_t *v164; // rdx
  const struct std::nothrow_t *v165; // rdx
  tlv *v166; // rdi
  void *v167; // rcx
  unsigned __int8 *v168; // rcx
  void *v169; // rcx
  unsigned __int8 *v170; // rcx
  const struct std::nothrow_t *v171; // rdx
  void *v172; // rcx
  unsigned __int8 *v173; // rcx
  void *v174; // rcx
  unsigned __int8 *v175; // rcx
  void (__fastcall ***v176)(_QWORD, __int64); // rcx
  void *v177; // rcx
  unsigned __int8 *v178; // rcx
  void *v179; // rcx
  __int64 v180; // rdx
  const struct std::nothrow_t *v181; // rdx
  void *v182; // rcx
  unsigned __int8 *v183; // rcx
  void *v184; // rcx
  unsigned __int8 *v185; // rcx
  __int64 v186; // rdx
  const struct std::nothrow_t *v187; // rdx
  const struct std::nothrow_t *v188; // rdx
  void *v189; // rcx
  unsigned __int8 *v190; // rcx
  void *v191; // rcx
  unsigned __int8 *v192; // rcx
  __int64 v193; // rdx
  const struct std::nothrow_t *v194; // rdx
  const struct std::nothrow_t *v195; // rdx
  tlv *v196; // rdi
  void *v197; // rcx
  unsigned __int8 *v198; // rcx
  void *v199; // rcx
  unsigned __int8 *v200; // rcx
  void *v201; // rcx
  unsigned __int8 *v202; // rcx
  void *v203; // rcx
  __int64 v204; // rdx
  __int64 v205; // rcx
  void *v206; // rcx
  unsigned __int8 *v207; // rcx
  void *v208; // rcx
  __int64 v209; // rdx
  const struct std::nothrow_t *v210; // rdx
  const struct std::nothrow_t *v211; // rdx
  void *v212; // rcx
  unsigned __int8 *v213; // rcx
  void *v214; // rcx
  unsigned __int8 *v215; // rcx
  void *v216; // rcx
  unsigned __int8 *v217; // rcx
  void *v218; // rcx
  unsigned __int8 *v219; // rcx
  DWORD FileSize; // eax
  const char *v221; // r9
  unsigned __int64 v222; // r14
  void *v223; // rax
  void *v224; // rdi
  unsigned __int8 *v225; // rcx
  void *v226; // rcx
  unsigned __int8 *v227; // rcx
  const char *v228; // r9
  tlv *v229; // rax
  const struct std::nothrow_t *v230; // rdx
  tlv *v231; // rbx
  void *v232; // rcx
  unsigned __int8 *v233; // rcx
  void *v234; // rcx
  unsigned __int8 *v235; // rcx
  void *v236; // rdi
  const struct std::nothrow_t *v237; // rdx
  void *v238; // rcx
  void *v239; // rax
  void *v240; // rcx
  _DWORD *v241; // rcx
  const struct std::nothrow_t *v242; // rdx
  tlv *v243; // rdi
  void *v244; // rcx
  unsigned __int8 *v245; // rcx
  void *v246; // rcx
  unsigned __int8 *v247; // rcx
  int Data; // edi
  unsigned __int8 *v249; // rcx
  void *v250; // rcx
  const struct std::nothrow_t *v251; // rdx
  void *v252; // rcx
  unsigned __int8 *v253; // rcx
  void *v254; // rcx
  __int64 unique; // rax
  const struct std::nothrow_t *v256; // rdx
  void *v257; // rcx
  tlv *v258; // rbx
  void *v259; // rcx
  unsigned __int8 *v260; // rcx
  void *v261; // rcx
  unsigned __int8 *v262; // rcx
  const struct std::nothrow_t *v263; // rdx
  void *v264; // rcx
  unsigned __int8 *v265; // rcx
  void *v266; // rcx
  unsigned __int8 *v267; // rcx
  __int64 v268; // rax
  const struct std::nothrow_t *v269; // rdx
  void *v270; // rcx
  const struct std::nothrow_t *v271; // rdx
  void *v272; // rcx
  unsigned __int8 *v273; // rcx
  void *v274; // rcx
  unsigned __int8 *v275; // rcx
  const struct std::nothrow_t *v276; // rdx
  tlv *v277; // rbx
  void *v278; // rcx
  unsigned __int8 *v279; // rcx
  void *v280; // rcx
  unsigned __int8 *v281; // rcx
  const struct std::nothrow_t *v282; // rdx
  DATA_BLOB *v283; // rcx
  __int64 cbData; // r8
  BYTE *pbData; // rdx
  tlv *v286; // rbx
  void *v287; // rcx
  unsigned __int8 *v288; // rcx
  void *v289; // rcx
  unsigned __int8 *v290; // rcx
  const struct std::nothrow_t *v291; // rdx
  void *v292; // rcx
  const struct std::nothrow_t *v293; // rdx
  unsigned __int8 *v294; // rcx
  void *v295; // rcx
  unsigned __int8 *v296; // rcx
  unsigned __int8 *v297; // rcx
  bool v298; // zf
  const struct std::nothrow_t *v299; // rdx
  void *v300; // rcx
  unsigned __int8 *v301; // rcx
  void *v302; // rcx
  unsigned __int8 *v303; // rcx
  const struct std::nothrow_t *v304; // rdx
  void *v305; // rcx
  unsigned __int8 *v306; // rcx
  void *v307; // rcx
  unsigned __int8 *v308; // rcx
  const struct std::nothrow_t *v309; // rdx
  void *v310; // rcx
  unsigned __int8 *v311; // rcx
  void *v312; // rcx
  unsigned __int8 *v313; // rcx
  const struct std::nothrow_t *v314; // rdx
  const struct std::nothrow_t *v315; // rdx
  tlv *v316; // rbx
  void *v317; // rcx
  unsigned __int8 *v318; // rcx
  void *v319; // rcx
  unsigned __int8 *v320; // rcx
  const struct std::nothrow_t *v321; // rdx
  void *v322; // rcx
  unsigned __int8 *v323; // rcx
  void *v324; // rcx
  unsigned __int8 *v325; // rcx
  const struct std::nothrow_t *v326; // rdx
  int v327; // eax
  const char *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *v332; // [rsp+40h] [rbp-C0h] BYREF
  size_t Size; // [rsp+48h] [rbp-B8h] BYREF
  void *v334; // [rsp+50h] [rbp-B0h]
  unsigned __int8 *v335; // [rsp+58h] [rbp-A8h] BYREF
  void *Src; // [rsp+60h] [rbp-A0h]
  tlv *v337; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 **v338; // [rsp+70h] [rbp-90h]
  unsigned int *v339; // [rsp+78h] [rbp-88h]
  char v340; // [rsp+80h] [rbp-80h]
  unsigned int v341; // [rsp+88h] [rbp-78h]
  __int64 v342; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v343; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v344; // [rsp+9Ch] [rbp-64h] BYREF
  _BYTE v345[24]; // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall ***v346)(_QWORD, __int64); // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v347; // [rsp+C0h] [rbp-40h]
  DATA_BLOB *p_pDataIn; // [rsp+C8h] [rbp-38h] BYREF
  DATA_BLOB *p_pDataOut; // [rsp+D0h] [rbp-30h]
  char v350; // [rsp+D8h] [rbp-28h]
  DWORD NumberOfBytesRead; // [rsp+E0h] [rbp-20h] BYREF
  int v352; // [rsp+E4h] [rbp-1Ch] BYREF
  __int64 v353; // [rsp+E8h] [rbp-18h] BYREF
  void *v354; // [rsp+F0h] [rbp-10h] BYREF
  void *v355; // [rsp+F8h] [rbp-8h] BYREF
  DATA_BLOB pDataIn; // [rsp+100h] [rbp+0h] BYREF
  DATA_BLOB pDataOut; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v358; // [rsp+120h] [rbp+20h]
  __int64 v359; // [rsp+128h] [rbp+28h] BYREF
  char v360; // [rsp+130h] [rbp+30h]
  _BYTE v361[88]; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  char v363; // [rsp+1A0h] [rbp+A0h] BYREF
  char v364; // [rsp+1A8h] [rbp+A8h]
  char v365; // [rsp+1B0h] [rbp+B0h]
  __int64 v366; // [rsp+1B8h] [rbp+B8h]

  v364 = a2;
  v2 = a2;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v345, L"PCPStorageProviderKey::LoadFromContainer", 1);
  v332 = 0;
  v344 = 0;
  v338 = &v332;
  v339 = &v344;
  v340 = 1;
  v334 = 0;
  v335 = 0;
  v4 = 0;
  for ( i = (char *)CreateFileW((LPCWSTR)this + 44, 0x80000000, 1u, 0, 3u, 0x80u, 0);
        i == (char *)-1LL;
        i = (char *)CreateFileW((LPCWSTR)this + 44, 0x80000000, 1u, 0, 3u, 0x80u, 0) )
  {
    if ( GetLastError() != 32 )
      break;
    if ( v4 >= 6 )
      break;
    Sleep(dword_1800DBB78[v4++]);
  }
  v342 = (__int64)i;
  if ( (unsigned __int64)(i - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1185,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  v6);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
    v9 = v335;
    v335 = 0;
    if ( v9 )
      operator delete(v9, v8);
    v10 = v334;
    v334 = 0;
    if ( v10 )
      operator delete(v10, v8);
    if ( v340 )
    {
      v340 = 0;
      v11 = *v338;
      if ( *v338 )
      {
        v8 = (tlv *)*v339;
        if ( *v339 )
        {
          do
          {
            *v11++ = 0;
            v8 = (tlv *)((char *)v8 - 1);
          }
          while ( v8 );
        }
      }
    }
LABEL_17:
    v13 = v332;
    v332 = 0;
    goto LABEL_36;
  }
  FileSize = GetFileSize(i, 0);
  v222 = FileSize;
  if ( FileSize == -1 )
  {
    Data = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1189,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
             v221);
    CloseHandle(i);
    v249 = v335;
    v335 = 0;
    if ( v249 )
      operator delete(v249, v24);
    v250 = v334;
    v334 = 0;
    if ( v250 )
      operator delete(v250, v24);
    if ( v340 )
    {
      v340 = 0;
      v25 = *v338;
      if ( *v338 )
      {
        v24 = (const struct std::nothrow_t *)*v339;
        if ( *v339 )
        {
          do
          {
            *v25++ = 0;
            v24 = (const struct std::nothrow_t *)((char *)v24 - 1);
          }
          while ( v24 );
        }
      }
    }
    goto LABEL_44;
  }
  v223 = operator new[](FileSize, (const struct std::nothrow_t *)&std::nothrow);
  v224 = v223;
  if ( v223 )
    memset_0(v223, 0, (unsigned int)v222);
  else
    v224 = 0;
  Src = v224;
  if ( !v224 )
  {
    Src = 0;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
    v225 = v335;
    v335 = 0;
    if ( v225 )
      operator delete(v225, v18);
    v226 = v334;
    v334 = 0;
    if ( v226 )
      operator delete(v226, v18);
    if ( v340 )
    {
      v340 = 0;
      v227 = *v338;
      if ( *v338 )
      {
        v18 = (tlv *)*v339;
        if ( *v339 )
        {
          do
          {
            *v227++ = 0;
            v18 = (tlv *)((char *)v18 - 1);
          }
          while ( v18 );
        }
      }
    }
LABEL_435:
    v20 = v332;
    v332 = 0;
    goto LABEL_26;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(i, v224, v222, &NumberOfBytesRead, 0) )
  {
    Data = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1192,
             (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
             v228);
    v252 = Src;
    Src = 0;
    if ( v252 )
      operator delete(v252, v251);
    CloseHandle(i);
    v253 = v335;
    v335 = 0;
    if ( v253 )
      operator delete(v253, v24);
    v254 = v334;
    v334 = 0;
    if ( v254 )
      operator delete(v254, v24);
    if ( v340 )
    {
      v340 = 0;
      v27 = *v338;
      if ( *v338 )
      {
        v24 = (const struct std::nothrow_t *)*v339;
        if ( *v339 )
        {
          do
          {
            *v27++ = 0;
            v24 = (const struct std::nothrow_t *)((char *)v24 - 1);
          }
          while ( v24 );
        }
      }
    }
LABEL_44:
    v26 = v332;
    v332 = 0;
LABEL_45:
    if ( v26 )
      operator delete(v26, v24);
    KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v345);
    return (unsigned int)Data;
  }
  wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(i);
  v342 = -1;
  v229 = (tlv *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v231 = v229;
  if ( v229 )
  {
    *((_QWORD *)v229 + 1) = 0;
    tlv::Clear(v229);
  }
  else
  {
    v231 = 0;
  }
  v337 = v231;
  if ( !v231 )
  {
    v337 = 0;
    v232 = Src;
    Src = 0;
    if ( v232 )
      operator delete(v232, v230);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
    v233 = v335;
    v335 = 0;
    if ( v233 )
      operator delete(v233, v18);
    v234 = v334;
    v334 = 0;
    if ( v234 )
      operator delete(v234, v18);
    if ( v340 )
    {
      v340 = 0;
      v235 = *v338;
      if ( *v338 )
      {
        v18 = (tlv *)*v339;
        if ( *v339 )
        {
          do
          {
            *v235++ = 0;
            v18 = (tlv *)((char *)v18 - 1);
          }
          while ( v18 );
          v20 = v332;
          v332 = 0;
          goto LABEL_26;
        }
      }
    }
    goto LABEL_435;
  }
  v236 = Src;
  tlv::Clear(v231);
  v238 = (void *)*((_QWORD *)v231 + 1);
  if ( v238 )
  {
    operator delete(v238, v237);
    *((_QWORD *)v231 + 1) = 0;
  }
  v239 = operator new[](v222, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)v231 + 1) = v239;
  if ( !v239 )
  {
    LastError = -2147024888;
    goto LABEL_462;
  }
  memset_0(v239, 0, v222);
  *((_DWORD *)v231 + 1) = v222;
  if ( (_DWORD)v222 )
  {
    v240 = (void *)*((_QWORD *)v231 + 1);
    if ( v240 )
    {
      if ( v236 )
      {
        memcpy_0(v240, v236, v222);
        goto LABEL_459;
      }
      memset_0(v240, 0, v222);
    }
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
LABEL_459:
  v241 = (_DWORD *)*((_QWORD *)v231 + 1);
  if ( *v241 != 1347636048 || *(_DWORD *)((char *)v241 + *((unsigned int *)v231 + 1) - 4) != 1347636048 )
  {
    tlv::Clear(v231);
    LastError = -2146893819;
LABEL_462:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1198,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)LastError,
      (int)dwCreationDisposition);
    v243 = v337;
    v337 = 0;
    if ( v243 )
    {
      tlv::Release(v243);
      operator delete(v243, (const struct std::nothrow_t *)0x18);
    }
    v244 = Src;
    Src = 0;
    if ( v244 )
      operator delete(v244, v242);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
    v245 = v335;
    v335 = 0;
    if ( v245 )
      operator delete(v245, v8);
    v246 = v334;
    v334 = 0;
    if ( v246 )
      operator delete(v246, v8);
    if ( v340 )
    {
      v340 = 0;
      v247 = *v338;
      if ( *v338 )
      {
        v8 = (tlv *)*v339;
        if ( *v339 )
        {
          do
          {
            *v247++ = 0;
            v8 = (tlv *)((char *)v8 - 1);
          }
          while ( v8 );
        }
      }
    }
    goto LABEL_17;
  }
  *(_DWORD *)v231 = 4;
  v28 = 0;
  v341 = 0;
  LOBYTE(v366) = 0;
  v347 = 0;
  v365 = 0;
  v343 = 0;
  LODWORD(Size) = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_63:
        v33 = v337;
        v14 = (const unsigned __int16 *)*(unsigned int *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1));
        if ( (_DWORD)v14 == 1347636048 )
        {
          *((_DWORD *)this + 176) = -1;
          if ( v2 )
          {
            v363 = 0;
            v352 = 0;
            v108 = (void **)(*((_QWORD *)this + 6) + 136LL);
            if ( !*v108 )
            {
              v327 = ProviderOpenAlgorithmProvider(v108, v14, 0);
              LastError = v327;
              if ( v327 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x128C,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)(unsigned int)v327,
                  (int)dwCreationDisposition);
                wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
                v322 = Src;
                Src = 0;
                if ( v322 )
                  operator delete(v322, v321);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
                v323 = v335;
                v335 = 0;
                if ( v323 )
                  operator delete(v323, v8);
                v324 = v334;
                v334 = 0;
                if ( v324 )
                  operator delete(v324, v8);
                if ( !v340 )
                  goto LABEL_35;
                v340 = 0;
                v325 = *v338;
                if ( !*v338 )
                  goto LABEL_35;
                v8 = (tlv *)*v339;
                if ( !*v339 )
                  goto LABEL_35;
                do
                {
                  *v325++ = 0;
                  v8 = (tlv *)((char *)v8 - 1);
                }
                while ( v8 );
                v13 = v332;
                v332 = 0;
                goto LABEL_36;
              }
            }
            v109 = (int)v332;
            v110 = *(TpmObject **)(*((_QWORD *)this + 6) + 136LL);
            KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v361, L"ProviderImportKeyPair", 1);
            v346 = 0;
            TpmObject::LockProvider(v110);
            v111 = *(__int64 (__fastcall **)(TpmObject *, _QWORD, const wchar_t *, __int64 *))(*(_QWORD *)v110 + 1144LL);
            v358 = &v346;
            v359 = 0;
            v360 = 1;
            v112 = v111(v110, 0, L"OpaqueKeyBlob", &v359);
            if ( v360 )
            {
              v113 = (void (__fastcall ***)(_QWORD, __int64))*v358;
              *v358 = v359;
              if ( v113 )
                (**v113)(v113, 1);
            }
            TpmObject::UnLockProvider(v110);
            v114 = PcpFromHResult(v112);
            LastError = v114;
            if ( v114 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x17E,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcprovider.cpp",
                (const char *)(unsigned int)v114,
                v109);
              v176 = v346;
              v346 = 0;
              if ( v176 )
                (**v176)(v176, 1);
              KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v361);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1295,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)LastError,
                dwCreationDispositiona);
              wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
              v177 = Src;
              Src = 0;
              if ( v177 )
                operator delete(v177, v8);
              v178 = v335;
              v335 = 0;
              if ( v178 )
                operator delete(v178, v8);
              v179 = v334;
              v334 = 0;
              if ( v179 )
                operator delete(v179, v8);
              if ( !v340 )
                goto LABEL_35;
              v340 = 0;
              v22 = *v338;
              if ( !*v338 )
                goto LABEL_35;
              v8 = (tlv *)*v339;
              if ( !*v339 )
                goto LABEL_35;
              do
              {
                *v22++ = 0;
                v8 = (tlv *)((char *)v8 - 1);
              }
              while ( v8 );
              v13 = v332;
              v332 = 0;
              goto LABEL_36;
            }
            *((_QWORD *)this + 96) = v346;
            v346 = 0;
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v361);
            Property = ProviderGetProperty(*((_QWORD *)this + 96), 44, &v363);
            LastError = Property;
            if ( Property < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x129A,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)(unsigned int)Property,
                (int)&v352);
              wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
              v216 = Src;
              Src = 0;
              if ( v216 )
                operator delete(v216, v8);
              v217 = v335;
              v335 = 0;
              if ( v217 )
                operator delete(v217, v8);
              v218 = v334;
              v334 = 0;
              if ( v218 )
                operator delete(v218, v8);
              if ( !v340 )
                goto LABEL_35;
              v340 = 0;
              v219 = *v338;
              if ( !*v338 )
                goto LABEL_35;
              v8 = (tlv *)*v339;
              if ( !*v339 )
                goto LABEL_35;
              do
              {
                *v219++ = 0;
                v8 = (tlv *)((char *)v8 - 1);
              }
              while ( v8 );
              v13 = v332;
              v332 = 0;
              goto LABEL_36;
            }
            if ( v363 )
              *((_DWORD *)this + 180) = 3;
            if ( v365 )
            {
              v144 = ProviderSetProperty(*((_QWORD *)this + 96), 102, v335, v347);
              LastError = v144;
              if ( v144 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x12A7,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)(unsigned int)v144,
                  (int)&v352);
                wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
                v145 = Src;
                Src = 0;
                if ( v145 )
                  operator delete(v145, v8);
                v146 = v335;
                v335 = 0;
                if ( v146 )
                  operator delete(v146, v8);
                v147 = v334;
                v334 = 0;
                if ( v147 )
                  operator delete(v147, v8);
                if ( !v340 )
                  goto LABEL_35;
                v340 = 0;
                v23 = *v338;
                if ( !*v338 )
                  goto LABEL_35;
                v8 = (tlv *)*v339;
                if ( !*v339 )
                  goto LABEL_35;
                do
                {
                  *v23++ = 0;
                  v8 = (tlv *)((char *)v8 - 1);
                }
                while ( v8 );
                v13 = v332;
                v332 = 0;
                goto LABEL_36;
              }
            }
            if ( (_BYTE)v366 )
            {
              v157 = ProviderSetProperty(*((_QWORD *)this + 96), 103, v334, v28);
              LastError = v157;
              if ( v157 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x12B1,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)(unsigned int)v157,
                  (int)&v352);
                wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
                v159 = Src;
                Src = 0;
                if ( v159 )
                  operator delete(v159, v158);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
                v160 = v335;
                v335 = 0;
                if ( v160 )
                  operator delete(v160, v8);
                v161 = v334;
                v334 = 0;
                if ( v161 )
                  operator delete(v161, v8);
                if ( !v340 )
                  goto LABEL_35;
                v340 = 0;
                v162 = *v338;
                if ( !*v338 )
                  goto LABEL_35;
                v8 = (tlv *)*v339;
                if ( !*v339 )
                  goto LABEL_35;
                do
                {
                  *v162++ = 0;
                  v8 = (tlv *)((char *)v8 - 1);
                }
                while ( v8 );
                v13 = v332;
                v332 = 0;
                goto LABEL_36;
              }
            }
            *((_BYTE *)this + 708) = 1;
          }
          *((_BYTE *)this + 700) = 1;
          v50 = v337;
          v337 = 0;
          if ( v50 )
            tlv::`scalar deleting destructor'(v50, (unsigned int)v14);
          v51 = Src;
          Src = 0;
          if ( v51 )
            operator delete(v51, (const struct std::nothrow_t *)v14);
          v52 = v335;
          v335 = 0;
          if ( v52 )
            operator delete(v52, (const struct std::nothrow_t *)v14);
          v53 = v334;
          v334 = 0;
          if ( v53 )
            operator delete(v53, (const struct std::nothrow_t *)v14);
          if ( v340 )
          {
            v340 = 0;
            v15 = *v338;
            if ( *v338 )
            {
              v14 = (const unsigned __int16 *)*v339;
              if ( *v339 )
              {
                do
                {
                  *v15++ = 0;
                  v14 = (const unsigned __int16 *)((char *)v14 - 1);
                }
                while ( v14 );
              }
            }
          }
          v16 = v332;
          v332 = 0;
          if ( v16 )
            operator delete(v16, (const struct std::nothrow_t *)v14);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v345);
          return 0;
        }
        v343 = *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1));
        v34 = *(unsigned int *)v337;
        v35 = *((_QWORD *)v337 + 1);
        v36 = *(unsigned int *)(v34 + v35 + 4);
        LODWORD(Size) = *(_DWORD *)(v34 + v35 + 4);
        *((_DWORD *)this + 176) = (_DWORD)v14;
        if ( (_DWORD)v14 != 33554436 )
          break;
        v38 = ((v36 + 1) >> 1) + 1;
        v39 = 2 * v38;
        if ( !is_mul_ok(v38, 2u) )
          v39 = -1;
        v40 = (unsigned __int16 *)operator new[](v39, (const struct std::nothrow_t *)&std::nothrow);
        v42 = v40;
        if ( !v40 )
        {
          v135 = v337;
          v337 = 0;
          if ( v135 )
          {
            tlv::Release(v135);
            operator delete(v135, (const struct std::nothrow_t *)0x18);
          }
          v136 = Src;
          Src = 0;
          if ( v136 )
            operator delete(v136, v41);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
          v137 = v335;
          v335 = 0;
          if ( v137 )
            operator delete(v137, v18);
          v138 = v334;
          v334 = 0;
          if ( v138 )
            operator delete(v138, v18);
          if ( v340 )
          {
            v340 = 0;
            v139 = *v338;
            if ( *v338 )
            {
              v18 = (tlv *)*v339;
              if ( *v339 )
              {
                do
                {
                  *v139++ = 0;
                  v18 = (tlv *)((char *)v18 - 1);
                }
                while ( v18 );
              }
            }
          }
          goto LABEL_25;
        }
        memset_0(v40, 0, v39);
        memset_0(v42, 0, 2 * v38);
        v43 = v337;
        if ( *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1)) == 1347636048 )
        {
          LastError = -2147024858;
          v163 = 171;
LABEL_304:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v163,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tlv.cpp",
            (const char *)LastError,
            (int)dwCreationDisposition);
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x11F7,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)LastError,
            (int)"Failed to get TLV_ALGID.",
            dwFlagsAndAttributes);
          operator delete(v42, v164);
          v166 = v337;
          v337 = 0;
          if ( v166 )
          {
            tlv::Release(v166);
            operator delete(v166, (const struct std::nothrow_t *)0x18);
          }
          v167 = Src;
          Src = 0;
          if ( v167 )
            operator delete(v167, v165);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
          v168 = v335;
          v335 = 0;
          if ( v168 )
            operator delete(v168, v8);
          v169 = v334;
          v334 = 0;
          if ( v169 )
            operator delete(v169, v8);
          if ( !v340 )
            goto LABEL_35;
          v340 = 0;
          v170 = *v338;
          if ( !*v338 )
            goto LABEL_35;
          v8 = (tlv *)*v339;
          if ( !*v339 )
            goto LABEL_35;
          do
          {
            *v170++ = 0;
            v8 = (tlv *)((char *)v8 - 1);
          }
          while ( v8 );
          v13 = v332;
          v332 = 0;
          goto LABEL_36;
        }
        v343 = *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1));
        v44 = *(unsigned int *)v337;
        v45 = *((_QWORD *)v337 + 1);
        v46 = *(unsigned int *)(v44 + v45 + 4);
        if ( !(_DWORD)Size )
        {
          LODWORD(Size) = *(_DWORD *)(v44 + v45 + 4);
          goto LABEL_56;
        }
        if ( (unsigned int)Size < (unsigned int)v46 )
        {
          LastError = -2146893784;
          v163 = 180;
          goto LABEL_304;
        }
        v47 = v44 + 8;
        *(_DWORD *)v337 = v44 + 8;
        if ( (_DWORD)v46 )
        {
          v48 = (unsigned int)Size;
          v49 = v45 + v47;
          if ( v49 && (unsigned int)Size >= v46 )
          {
            memcpy_0(v42, (const void *)(v45 + v47), (unsigned int)v46);
            goto LABEL_54;
          }
          memset_0(v42, 0, (unsigned int)Size);
          if ( v49 )
          {
            if ( v48 < v46 )
            {
              *(_DWORD *)_o__errno() = 34;
              goto LABEL_53;
            }
          }
          else
          {
            *(_DWORD *)_o__errno() = 22;
LABEL_53:
            invalid_parameter_noinfo();
          }
LABEL_54:
          v28 = v341;
          v2 = v364;
        }
        LODWORD(Size) = v46;
        *(_DWORD *)v43 += v46;
LABEL_56:
        v29 = 0;
        do
        {
          v30 = aRsa[v29++];
          v31 = (const struct std::nothrow_t *)(v30 - (unsigned int)v42[v29 - 1]);
        }
        while ( !(_DWORD)v31 && v29 != 4 );
        if ( (_DWORD)v31 )
        {
          if ( !wcscmp_0(L"RSA_SIGN", v42) )
          {
            v32 = L"RSA_SIGN";
          }
          else if ( !wcscmp_0(L"ECDSA", v42) )
          {
            v32 = L"ECDSA";
          }
          else if ( !wcscmp_0(L"ECDH", v42) )
          {
            v32 = L"ECDH";
          }
          else
          {
            if ( wcscmp_0(L"HMAC-SHA256", v42) )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x120F,
                (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                (const char *)0x80090020LL,
                (int)"TLV Alg ID unknown. AlgId: %ls",
                (const char *)v42);
              operator delete(v42, v314);
              v316 = v337;
              v337 = 0;
              if ( v316 )
              {
                tlv::Release(v316);
                operator delete(v316, (const struct std::nothrow_t *)0x18);
              }
              v317 = Src;
              Src = 0;
              if ( v317 )
                operator delete(v317, v315);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
              v318 = v335;
              v335 = 0;
              if ( v318 )
                operator delete(v318, v293);
              v319 = v334;
              v334 = 0;
              if ( v319 )
                operator delete(v319, v293);
              if ( v340 )
              {
                v340 = 0;
                v320 = *v338;
                if ( *v338 )
                {
                  v293 = (const struct std::nothrow_t *)*v339;
                  if ( *v339 )
                  {
                    do
                    {
                      *v320++ = 0;
                      v293 = (const struct std::nothrow_t *)((char *)v293 - 1);
                    }
                    while ( v293 );
                  }
                }
              }
LABEL_581:
              v297 = v332;
              v298 = v332 == 0;
              v332 = 0;
              if ( !v298 )
                operator delete(v297, v293);
              KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v345);
              return 2148073504LL;
            }
            v32 = L"HMAC-SHA256";
          }
        }
        else
        {
          v32 = L"RSA";
        }
        *((_QWORD *)this + 89) = v32;
        operator delete(v42, v31);
      }
      if ( (_DWORD)v14 != 0x2000000 )
        break;
      operator delete(*((void **)this + 10), (const struct std::nothrow_t *)v14);
      *((_QWORD *)this + 10) = 0;
      v78 = (((unsigned __int64)(unsigned int)Size + 1) >> 1) + 1;
      v79 = 2 * v78;
      if ( !is_mul_ok(v78, 2u) )
        v79 = -1;
      v80 = operator new[](v79, (const struct std::nothrow_t *)&std::nothrow);
      v82 = v80;
      if ( !v80 )
      {
        v18 = v337;
        v337 = 0;
        if ( v18 )
          wistd::default_delete<tlv>::operator()(v81, v18);
        v148 = Src;
        Src = 0;
        if ( v148 )
          operator delete(v148, v18);
        v149 = v335;
        v335 = 0;
        if ( v149 )
          operator delete(v149, v18);
        v150 = v334;
        v334 = 0;
        if ( v150 )
          operator delete(v150, v18);
        if ( v340 )
        {
          v340 = 0;
          v151 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v151++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
        goto LABEL_25;
      }
      memset_0(v80, 0, v79);
      *((_QWORD *)this + 10) = v82;
      memset_0(v82, 0, (unsigned int)Size + 2LL);
      v83 = v337;
      if ( *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1)) == 1347636048 )
      {
        LastError = -2147024858;
        v193 = 171;
LABEL_368:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v193,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tlv.cpp",
          (const char *)LastError,
          (int)dwCreationDisposition);
        operator delete(*((void **)this + 10), v194);
        *((_QWORD *)this + 10) = 0;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x11AC,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)LastError,
          (int)"Failed to get TLV_KEYNAME.",
          dwFlagsAndAttributes);
        v196 = v337;
        v337 = 0;
        if ( v196 )
        {
          tlv::Release(v196);
          operator delete(v196, (const struct std::nothrow_t *)0x18);
        }
        v197 = Src;
        Src = 0;
        if ( v197 )
          operator delete(v197, v195);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v198 = v335;
        v335 = 0;
        if ( v198 )
          operator delete(v198, v8);
        v199 = v334;
        v334 = 0;
        if ( v199 )
          operator delete(v199, v8);
        if ( !v340 )
          goto LABEL_35;
        v340 = 0;
        v200 = *v338;
        if ( !*v338 )
          goto LABEL_35;
        v8 = (tlv *)*v339;
        if ( !*v339 )
          goto LABEL_35;
        do
        {
          *v200++ = 0;
          v8 = (tlv *)((char *)v8 - 1);
        }
        while ( v8 );
        v13 = v332;
        v332 = 0;
        goto LABEL_36;
      }
      v84 = (void *)*((_QWORD *)this + 10);
      v343 = *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1));
      v85 = *(unsigned int *)v337;
      v86 = *((_QWORD *)v337 + 1);
      v87 = *(unsigned int *)(v85 + v86 + 4);
      if ( (_DWORD)Size )
      {
        if ( !v84 )
        {
          LastError = -2146893785;
          v193 = 179;
          goto LABEL_368;
        }
        if ( (unsigned int)Size < (unsigned int)v87 )
        {
          LastError = -2146893784;
          v193 = 180;
          goto LABEL_368;
        }
        v88 = v85 + 8;
        *(_DWORD *)v337 = v85 + 8;
        if ( (_DWORD)v87 )
        {
          v89 = (unsigned int)Size;
          v90 = v86 + v88;
          if ( !v90 || (unsigned int)Size < v87 )
          {
            memset_0(v84, 0, (unsigned int)Size);
            if ( v90 )
            {
              if ( v89 >= v87 )
              {
LABEL_175:
                v2 = v364;
                goto LABEL_176;
              }
              *(_DWORD *)_o__errno() = 34;
            }
            else
            {
              *(_DWORD *)_o__errno() = 22;
            }
            invalid_parameter_noinfo();
            goto LABEL_175;
          }
          memcpy_0(v84, (const void *)(v86 + v88), (unsigned int)v87);
          v2 = v364;
          LODWORD(Size) = v87;
          *(_DWORD *)v83 += v87;
        }
        else
        {
LABEL_176:
          LODWORD(Size) = v87;
          *(_DWORD *)v83 += v87;
        }
      }
      else
      {
        LODWORD(Size) = *(_DWORD *)(v85 + v86 + 4);
      }
    }
    if ( (unsigned int)v14 <= 0x2000000 )
      break;
LABEL_69:
    *(_DWORD *)v33 += 4;
    *(_DWORD *)v33 += *(_DWORD *)(*(unsigned int *)v33 + *((_QWORD *)v33 + 1)) + 4;
  }
  v37 = (const struct std::nothrow_t *)(unsigned int)((_DWORD)v14 - 16777218);
  switch ( (int)v37 )
  {
    case 0:
      if ( !v2 )
        goto LABEL_69;
      unique = wil::make_unique_nothrow<unsigned char [0]>(&v354, (unsigned int)Size);
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(&v332, unique);
      v257 = v354;
      v354 = 0;
      if ( v257 )
        operator delete(v257, v256);
      if ( !v332 )
      {
        v258 = v337;
        v337 = 0;
        if ( v258 )
        {
          tlv::Release(v258);
          operator delete(v258, (const struct std::nothrow_t *)0x18);
        }
        v259 = Src;
        Src = 0;
        if ( v259 )
          operator delete(v259, v256);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v260 = v335;
        v335 = 0;
        if ( v260 )
          operator delete(v260, v18);
        v261 = v334;
        v334 = 0;
        if ( v261 )
          operator delete(v261, v18);
        if ( v340 )
        {
          v340 = 0;
          v262 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v262++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
        goto LABEL_25;
      }
      v344 = Size;
      Data = tlv::GetData(v337, &v343, &v344, v332);
      if ( Data < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x11BA,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)(unsigned int)Data,
          (int)"Failed to get TLV_PCPKEYBLOB.",
          dwFlagsAndAttributes);
        v277 = v337;
        v337 = 0;
        if ( v277 )
        {
          tlv::Release(v277);
          operator delete(v277, (const struct std::nothrow_t *)0x18);
        }
        v278 = Src;
        Src = 0;
        if ( v278 )
          operator delete(v278, v276);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v279 = v335;
        v335 = 0;
        if ( v279 )
          operator delete(v279, v24);
        v280 = v334;
        v334 = 0;
        if ( v280 )
          operator delete(v280, v24);
        if ( v340 )
        {
          v340 = 0;
          v281 = *v338;
          if ( *v338 )
          {
            v24 = (const struct std::nothrow_t *)*v339;
            if ( *v339 )
            {
              do
              {
                *v281++ = 0;
                v24 = (const struct std::nothrow_t *)((char *)v24 - 1);
              }
              while ( v24 );
            }
          }
        }
        goto LABEL_497;
      }
      *((_DWORD *)this + 188) |= 1u;
      goto LABEL_63;
    case 1:
      if ( !v2 )
        goto LABEL_69;
      v96 = Size;
      v97 = (unsigned __int8 *)operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
      v99 = v97;
      if ( v97 )
        memset_0(v97, 0, v96);
      else
        v99 = 0;
      v100 = v332;
      v332 = v99;
      if ( v100 )
      {
        operator delete(v100, v98);
        v99 = v332;
      }
      if ( !v99 )
      {
        v121 = v337;
        v337 = 0;
        if ( v121 )
        {
          tlv::Release(v121);
          operator delete(v121, (const struct std::nothrow_t *)0x18);
        }
        v122 = Src;
        Src = 0;
        if ( v122 )
          operator delete(v122, v98);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v123 = v335;
        v335 = 0;
        if ( v123 )
          operator delete(v123, v18);
        v124 = v334;
        v334 = 0;
        if ( v124 )
          operator delete(v124, v18);
        if ( v340 )
        {
          v340 = 0;
          v125 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v125++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
        goto LABEL_25;
      }
      v344 = Size;
      v101 = v337;
      if ( *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1)) == 1347636048 )
      {
        LastError = -2147024858;
        v204 = 171;
        goto LABEL_391;
      }
      v343 = *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1));
      v102 = *(unsigned int *)v337;
      v103 = *((_QWORD *)v337 + 1);
      v104 = *(unsigned int *)(v102 + v103 + 4);
      if ( (_DWORD)Size )
      {
        if ( (unsigned int)Size < (unsigned int)v104 )
        {
          LastError = -2146893784;
          v204 = 180;
LABEL_391:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v204,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tlv.cpp",
            (const char *)LastError,
            (int)dwCreationDisposition);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11CC,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)LastError,
            dwCreationDispositionb);
          v8 = v337;
          v337 = 0;
          if ( v8 )
            wistd::default_delete<tlv>::operator()(v205, v8);
          v206 = Src;
          Src = 0;
          if ( v206 )
            operator delete(v206, v8);
          v207 = v335;
          v335 = 0;
          if ( v207 )
            operator delete(v207, v8);
          v208 = v334;
          v334 = 0;
          if ( v208 )
            operator delete(v208, v8);
          if ( v340 )
          {
            v340 = 0;
            v12 = *v338;
            if ( *v338 )
            {
              v8 = (tlv *)*v339;
              if ( *v339 )
              {
                do
                {
                  *v12++ = 0;
                  v8 = (tlv *)((char *)v8 - 1);
                }
                while ( v8 );
              }
            }
          }
          goto LABEL_17;
        }
        v105 = v102 + 8;
        *(_DWORD *)v337 = v105;
        if ( !(_DWORD)v104 )
          goto LABEL_207;
        v106 = v344;
        v107 = v103 + v105;
        if ( v107 && v344 >= v104 )
        {
          memcpy_0(v99, (const void *)(v103 + v105), v104);
LABEL_206:
          v28 = v341;
LABEL_207:
          v344 = v104;
          *(_DWORD *)v101 += v104;
          v99 = v332;
          LODWORD(v104) = v344;
          v2 = v364;
          goto LABEL_208;
        }
        memset_0(v99, 0, v344);
        if ( v107 )
        {
          if ( v106 >= v104 )
            goto LABEL_206;
          *(_DWORD *)_o__errno() = 34;
        }
        else
        {
          *(_DWORD *)_o__errno() = 22;
        }
        invalid_parameter_noinfo();
        goto LABEL_206;
      }
      v344 = *(_DWORD *)(v102 + v103 + 4);
LABEL_208:
      *(&pDataIn.cbData + 1) = 0;
      pDataIn.cbData = v104;
      pDataIn.pbData = v99;
      pDataOut = 0;
      p_pDataIn = &pDataIn;
      p_pDataOut = &pDataOut;
      v350 = 1;
      if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
      {
        Data = wil::details::in1diag3::Return_GetLastErrorMsg(
                 retaddr,
                 (void *)0x11E2,
                 (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                 "Failed to get TLV_PROTECTEDPCPKEYBLOB.",
                 dwCreationDisposition);
        if ( v350 )
        {
          v350 = 0;
          p_pDataIn->pbData = 0;
          p_pDataIn->cbData = 0;
          v283 = p_pDataOut;
          cbData = p_pDataOut->cbData;
          pbData = p_pDataOut->pbData;
          if ( p_pDataOut->cbData )
          {
            do
            {
              *pbData++ = 0;
              --cbData;
            }
            while ( cbData );
            v283 = p_pDataOut;
          }
          LocalFree(v283->pbData);
          p_pDataOut->pbData = 0;
          p_pDataOut->cbData = 0;
        }
        v286 = v337;
        v337 = 0;
        if ( v286 )
        {
          tlv::Release(v286);
          operator delete(v286, (const struct std::nothrow_t *)0x18);
        }
        v287 = Src;
        Src = 0;
        if ( v287 )
          operator delete(v287, v282);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v288 = v335;
        v335 = 0;
        if ( v288 )
          operator delete(v288, v24);
        v289 = v334;
        v334 = 0;
        if ( v289 )
          operator delete(v289, v24);
        if ( v340 )
        {
          v340 = 0;
          v290 = *v338;
          if ( *v338 )
          {
            v24 = (const struct std::nothrow_t *)*v339;
            if ( *v339 )
            {
              do
              {
                *v290++ = 0;
                v24 = (const struct std::nothrow_t *)((char *)v24 - 1);
              }
              while ( v24 );
            }
          }
        }
LABEL_497:
        v26 = v332;
        v332 = 0;
        goto LABEL_45;
      }
      v344 = pDataOut.cbData;
      v126 = pDataOut.cbData;
      v127 = (unsigned __int8 *)operator new[](pDataOut.cbData, (const struct std::nothrow_t *)&std::nothrow);
      v129 = v127;
      if ( v127 )
        memset_0(v127, 0, v126);
      else
        v129 = 0;
      v130 = v332;
      v332 = v129;
      if ( v130 )
        operator delete(v130, v128);
      v131 = v332;
      if ( !v332 )
      {
        if ( v350 )
        {
          v350 = 0;
          lambda_ee9bf1c1c3f01db3bb6f0e4961eb48bc_::operator()(&p_pDataIn);
        }
        v18 = v337;
        v337 = 0;
        if ( v18 )
          wistd::default_delete<tlv>::operator()(v131, v18);
        v132 = Src;
        Src = 0;
        if ( v132 )
          operator delete(v132, v18);
        v133 = v335;
        v335 = 0;
        if ( v133 )
          operator delete(v133, v18);
        v134 = v334;
        v334 = 0;
        if ( v134 )
          operator delete(v134, v18);
        if ( v340 )
        {
          v340 = 0;
          v19 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v19++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
        goto LABEL_25;
      }
      if ( v344 )
      {
        if ( pDataOut.pbData )
        {
          memcpy_0(v332, pDataOut.pbData, v344);
        }
        else
        {
          memset_0(v332, 0, v344);
          *(_DWORD *)_o__errno() = 22;
          invalid_parameter_noinfo();
        }
      }
      if ( v350 )
      {
        v350 = 0;
        lambda_ee9bf1c1c3f01db3bb6f0e4961eb48bc_::operator()(&p_pDataIn);
      }
      goto LABEL_63;
    case 3:
      *((_DWORD *)this + 164) = 0;
      operator delete(*((void **)this + 83), v37);
      *((_QWORD *)this + 83) = 0;
      wil::make_unique_nothrow<unsigned char [0]>(&v353, (unsigned int)Size);
      if ( !v353 )
      {
        v353 = 0;
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v264 = Src;
        Src = 0;
        if ( v264 )
          operator delete(v264, v263);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v265 = v335;
        v335 = 0;
        if ( v265 )
          operator delete(v265, v18);
        v266 = v334;
        v334 = 0;
        if ( v266 )
          operator delete(v266, v18);
        if ( v340 )
        {
          v340 = 0;
          v267 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v267++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
        goto LABEL_25;
      }
      *((_QWORD *)this + 83) = v353;
      v353 = 0;
      *((_DWORD *)this + 164) = Size;
      LastError = tlv::GetData(v337, &v343, (unsigned int *)&Size, *((unsigned __int8 **)this + 83));
      if ( (LastError & 0x80000000) == 0 )
        goto LABEL_63;
      operator delete(*((void **)this + 83), v326);
      *((_QWORD *)this + 83) = 0;
      *((_DWORD *)this + 164) = 0;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1248,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)LastError,
        (int)"Failed to get TLV_KEYCERTIFICATION.",
        dwFlagsAndAttributes);
      wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
      v305 = Src;
      Src = 0;
      if ( v305 )
        operator delete(v305, v304);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
      v306 = v335;
      v335 = 0;
      if ( v306 )
        operator delete(v306, v8);
      v307 = v334;
      v334 = 0;
      if ( v307 )
        operator delete(v307, v8);
      if ( !v340 )
        goto LABEL_35;
      v340 = 0;
      v308 = *v338;
      if ( !*v338 )
        goto LABEL_35;
      v8 = (tlv *)*v339;
      if ( !*v339 )
        goto LABEL_35;
      do
      {
        *v308++ = 0;
        v8 = (tlv *)((char *)v8 - 1);
      }
      while ( v8 );
      v13 = v332;
      v332 = 0;
      goto LABEL_36;
    case 4:
      *((_DWORD *)this + 162) = 0;
      operator delete(*((void **)this + 80), v37);
      *((_QWORD *)this + 80) = 0;
      v67 = Size;
      v68 = operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
      v70 = v68;
      if ( !v68 )
      {
        v152 = v337;
        v337 = 0;
        if ( v152 )
        {
          tlv::Release(v152);
          operator delete(v152, (const struct std::nothrow_t *)0x18);
        }
        v153 = Src;
        Src = 0;
        if ( v153 )
          operator delete(v153, v69);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v154 = v335;
        v335 = 0;
        if ( v154 )
          operator delete(v154, v18);
        v155 = v334;
        v334 = 0;
        if ( v155 )
          operator delete(v155, v18);
        if ( v340 )
        {
          v340 = 0;
          v156 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v156++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
        goto LABEL_25;
      }
      memset_0(v68, 0, v67);
      *((_QWORD *)this + 80) = v70;
      *((_DWORD *)this + 162) = Size;
      v71 = v337;
      if ( *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1)) == 1347636048 )
      {
        LastError = -2147024858;
        v186 = 171;
        goto LABEL_356;
      }
      v343 = *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1));
      v72 = *(unsigned int *)v337;
      v73 = *((_QWORD *)v337 + 1);
      v74 = *(unsigned int *)(v72 + v73 + 4);
      if ( !(_DWORD)Size )
      {
        LODWORD(Size) = *(_DWORD *)(v72 + v73 + 4);
        v2 = v364;
        goto LABEL_63;
      }
      if ( (unsigned int)Size < (unsigned int)v74 )
      {
        LastError = -2146893784;
        v186 = 180;
LABEL_356:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v186,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tlv.cpp",
          (const char *)LastError,
          (int)dwCreationDisposition);
        operator delete(*((void **)this + 80), v187);
        *((_QWORD *)this + 80) = 0;
        *((_DWORD *)this + 162) = 0;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x121F,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)LastError,
          (int)"Failed to get TLV_CERTIFICATE.",
          dwFlagsAndAttributes);
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v189 = Src;
        Src = 0;
        if ( v189 )
          operator delete(v189, v188);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v190 = v335;
        v335 = 0;
        if ( v190 )
          operator delete(v190, v8);
        v191 = v334;
        v334 = 0;
        if ( v191 )
          operator delete(v191, v8);
        if ( v340 )
        {
          v340 = 0;
          v192 = *v338;
          if ( *v338 )
          {
            v8 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v192++ = 0;
                v8 = (tlv *)((char *)v8 - 1);
              }
              while ( v8 );
            }
          }
        }
        goto LABEL_35;
      }
      v75 = v72 + 8;
      *(_DWORD *)v337 = v72 + 8;
      if ( !(_DWORD)v74 )
        goto LABEL_117;
      v76 = (unsigned int)Size;
      v77 = v73 + v75;
      if ( v77 && (unsigned int)Size >= v74 )
      {
        memcpy_0(v70, (const void *)(v73 + v75), v74);
        goto LABEL_116;
      }
      goto LABEL_112;
    case 5:
      *((_QWORD *)this + 77) = 0;
      *((_DWORD *)this + 158) = 0;
      operator delete(*((void **)this + 78), v37);
      *((_QWORD *)this + 78) = 0;
      v140 = Size;
      v141 = (unsigned __int8 *)operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
      v142 = v141;
      if ( !v141 )
      {
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v201 = Src;
        Src = 0;
        if ( v201 )
          operator delete(v201, v18);
        v202 = v335;
        v335 = 0;
        if ( v202 )
          operator delete(v202, v18);
        v203 = v334;
        v334 = 0;
        if ( v203 )
          operator delete(v203, v18);
        if ( v340 )
        {
          v340 = 0;
          v21 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v21++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
        goto LABEL_25;
      }
      memset_0(v141, 0, v140);
      *((_QWORD *)this + 78) = v142;
      *((_DWORD *)this + 158) = Size;
      LastError = tlv::GetData(v337, &v343, (unsigned int *)&Size, v142);
      if ( (LastError & 0x80000000) != 0 )
      {
        operator delete(*((void **)this + 78), v143);
        *((_QWORD *)this + 78) = 0;
        *((_DWORD *)this + 158) = 0;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x122F,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)LastError,
          (int)"Failed to get TLV_UIPOLICY.",
          dwFlagsAndAttributes);
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v300 = Src;
        Src = 0;
        if ( v300 )
          operator delete(v300, v299);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v301 = v335;
        v335 = 0;
        if ( v301 )
          operator delete(v301, v8);
        v302 = v334;
        v334 = 0;
        if ( v302 )
          operator delete(v302, v8);
        if ( v340 )
        {
          v340 = 0;
          v303 = *v338;
          if ( *v338 )
          {
            v8 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v303++ = 0;
                v8 = (tlv *)((char *)v8 - 1);
              }
              while ( v8 );
              v13 = v332;
              v332 = 0;
              goto LABEL_36;
            }
          }
        }
LABEL_35:
        v13 = v332;
        v332 = 0;
        goto LABEL_36;
      }
      if ( (unsigned int)(*((_DWORD *)this + 158) - 1) <= 0x12 )
      {
        operator delete(*((void **)this + 78), v143);
        *((_QWORD *)this + 78) = 0;
        *((_DWORD *)this + 158) = 0;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1237,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)0x80090020LL,
          (int)"TLV UI Policy malformed.",
          dwFlagsAndAttributes);
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v292 = Src;
        Src = 0;
        if ( v292 )
          operator delete(v292, v291);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v294 = v335;
        v335 = 0;
        if ( v294 )
          operator delete(v294, v293);
        v295 = v334;
        v334 = 0;
        if ( v295 )
          operator delete(v295, v293);
        if ( v340 )
        {
          v340 = 0;
          v296 = *v338;
          if ( *v338 )
          {
            v293 = (const struct std::nothrow_t *)*v339;
            if ( *v339 )
            {
              do
              {
                *v296++ = 0;
                v293 = (const struct std::nothrow_t *)((char *)v293 - 1);
              }
              while ( v293 );
            }
          }
        }
        goto LABEL_581;
      }
      *((_QWORD *)this + 77) = *((_QWORD *)this + 78);
      goto LABEL_63;
    case 6:
      v268 = wil::make_unique_nothrow<unsigned char [0]>(&v355, v36);
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(&v335, v268);
      v270 = v355;
      v355 = 0;
      if ( v270 )
        operator delete(v270, v269);
      if ( !v335 )
      {
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v272 = Src;
        Src = 0;
        if ( v272 )
          operator delete(v272, v271);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v273 = v335;
        v335 = 0;
        if ( v273 )
          operator delete(v273, v18);
        v274 = v334;
        v334 = 0;
        if ( v274 )
          operator delete(v274, v18);
        if ( v340 )
        {
          v340 = 0;
          v275 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v275++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
        goto LABEL_25;
      }
      v347 = Size;
      LastError = tlv::GetData(v337, &v343, (unsigned int *)&Size, v335);
      if ( (LastError & 0x80000000) == 0 )
      {
        v365 = 1;
        goto LABEL_63;
      }
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1254,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
        (const char *)LastError,
        (int)"Failed to get TLV_AIKCERTIFICATION.",
        dwFlagsAndAttributes);
      wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
      v310 = Src;
      Src = 0;
      if ( v310 )
        operator delete(v310, v309);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
      v311 = v335;
      v335 = 0;
      if ( v311 )
        operator delete(v311, v8);
      v312 = v334;
      v334 = 0;
      if ( v312 )
        operator delete(v312, v8);
      if ( !v340 )
        goto LABEL_35;
      v340 = 0;
      v313 = *v338;
      if ( !*v338 )
        goto LABEL_35;
      v8 = (tlv *)*v339;
      if ( !*v339 )
        goto LABEL_35;
      do
      {
        *v313++ = 0;
        v8 = (tlv *)((char *)v8 - 1);
      }
      while ( v8 );
      v13 = v332;
      v332 = 0;
LABEL_36:
      if ( v13 )
        operator delete(v13, v8);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v345);
      return LastError;
    case 7:
      v54 = v36;
      v55 = operator new[](v36, (const struct std::nothrow_t *)&std::nothrow);
      v57 = v55;
      if ( v55 )
        memset_0(v55, 0, v54);
      else
        v57 = 0;
      v58 = v334;
      v334 = v57;
      if ( v58 )
      {
        operator delete(v58, v56);
        v57 = v334;
      }
      if ( !v57 )
      {
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v92 = Src;
        Src = 0;
        if ( v92 )
          operator delete(v92, v91);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v93 = v335;
        v335 = 0;
        if ( v93 )
          operator delete(v93, v18);
        v94 = v334;
        v334 = 0;
        if ( v94 )
          operator delete(v94, v18);
        if ( v340 )
        {
          v340 = 0;
          v95 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v95++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
LABEL_25:
        v20 = v332;
        v332 = 0;
LABEL_26:
        if ( v20 )
          operator delete(v20, v18);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v345);
        return 2147942408LL;
      }
      v59 = v337;
      v60 = *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1));
      if ( v60 == 1347636048 )
      {
        LastError = -2147024858;
        v180 = 171;
LABEL_344:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v180,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tlv.cpp",
          (const char *)LastError,
          (int)dwCreationDisposition);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1261,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)LastError,
          (int)"Failed to get TLV_IDBINDING.",
          dwFlagsAndAttributes);
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v182 = Src;
        Src = 0;
        if ( v182 )
          operator delete(v182, v181);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v183 = v335;
        v335 = 0;
        if ( v183 )
          operator delete(v183, v8);
        v184 = v334;
        v334 = 0;
        if ( v184 )
          operator delete(v184, v8);
        if ( !v340 )
          goto LABEL_35;
        v340 = 0;
        v185 = *v338;
        if ( !*v338 )
          goto LABEL_35;
        v8 = (tlv *)*v339;
        if ( !*v339 )
          goto LABEL_35;
        do
        {
          *v185++ = 0;
          v8 = (tlv *)((char *)v8 - 1);
        }
        while ( v8 );
        v13 = v332;
        v332 = 0;
        goto LABEL_36;
      }
      v28 = Size;
      v341 = Size;
      v343 = v60;
      v61 = *(unsigned int *)v337;
      v62 = *((_QWORD *)v337 + 1);
      v63 = *(unsigned int *)(v61 + v62 + 4);
      if ( (_DWORD)Size )
      {
        if ( (unsigned int)Size < (unsigned int)v63 )
        {
          LastError = -2146893784;
          v180 = 180;
          goto LABEL_344;
        }
        v64 = v61 + 8;
        *(_DWORD *)v337 = v64;
        if ( !(_DWORD)v63 )
          goto LABEL_144;
        v65 = (unsigned int)Size;
        v66 = v62 + v64;
        if ( !v66 || (unsigned int)Size < v63 )
        {
          memset_0(v57, 0, (unsigned int)Size);
          if ( v66 )
          {
            if ( v65 >= v63 )
              goto LABEL_143;
            *(_DWORD *)_o__errno() = 34;
          }
          else
          {
            *(_DWORD *)_o__errno() = 22;
          }
          invalid_parameter_noinfo();
          goto LABEL_143;
        }
        memcpy_0(v57, (const void *)(v62 + v64), (unsigned int)v63);
LABEL_143:
        v28 = v341;
LABEL_144:
        LODWORD(Size) = v63;
        *(_DWORD *)v59 += v63;
        v2 = v364;
        LOBYTE(v366) = 1;
      }
      else
      {
        LODWORD(Size) = *(_DWORD *)(v61 + v62 + 4);
        LOBYTE(v366) = 1;
      }
      goto LABEL_63;
    case 8:
      *((_DWORD *)this + 174) = 0;
      operator delete(*((void **)this + 86), v37);
      *((_QWORD *)this + 86) = 0;
      v116 = Size;
      v117 = operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
      v70 = v117;
      if ( !v117 )
      {
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v172 = Src;
        Src = 0;
        if ( v172 )
          operator delete(v172, v171);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v173 = v335;
        v335 = 0;
        if ( v173 )
          operator delete(v173, v18);
        v174 = v334;
        v334 = 0;
        if ( v174 )
          operator delete(v174, v18);
        if ( v340 )
        {
          v340 = 0;
          v175 = *v338;
          if ( *v338 )
          {
            v18 = (tlv *)*v339;
            if ( *v339 )
            {
              do
              {
                *v175++ = 0;
                v18 = (tlv *)((char *)v18 - 1);
              }
              while ( v18 );
            }
          }
        }
        goto LABEL_25;
      }
      memset_0(v117, 0, v116);
      *((_QWORD *)this + 86) = v70;
      *((_DWORD *)this + 174) = Size;
      v71 = v337;
      if ( *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1)) == 1347636048 )
      {
        LastError = -2147024858;
        v209 = 171;
LABEL_403:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v209,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tlv.cpp",
          (const char *)LastError,
          (int)dwCreationDisposition);
        operator delete(*((void **)this + 86), v210);
        *((_QWORD *)this + 86) = 0;
        *((_DWORD *)this + 174) = 0;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1271,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)LastError,
          (int)"Failed to get TLV_PLATFORMCLAIM.",
          dwFlagsAndAttributes);
        wistd::unique_ptr<tlv,wistd::default_delete<tlv>>::~unique_ptr<tlv,wistd::default_delete<tlv>>(&v337);
        v212 = Src;
        Src = 0;
        if ( v212 )
          operator delete(v212, v211);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v342);
        v213 = v335;
        v335 = 0;
        if ( v213 )
          operator delete(v213, v8);
        v214 = v334;
        v334 = 0;
        if ( v214 )
          operator delete(v214, v8);
        if ( !v340 )
          goto LABEL_35;
        v340 = 0;
        v215 = *v338;
        if ( !*v338 )
          goto LABEL_35;
        v8 = (tlv *)*v339;
        if ( !*v339 )
          goto LABEL_35;
        do
        {
          *v215++ = 0;
          v8 = (tlv *)((char *)v8 - 1);
        }
        while ( v8 );
        v13 = v332;
        v332 = 0;
        goto LABEL_36;
      }
      v343 = *(_DWORD *)(*(unsigned int *)v337 + *((_QWORD *)v337 + 1));
      v118 = *(unsigned int *)v337;
      v119 = *((_QWORD *)v337 + 1);
      v74 = *(unsigned int *)(v118 + v119 + 4);
      if ( (_DWORD)Size )
      {
        if ( (unsigned int)Size < (unsigned int)v74 )
        {
          LastError = -2146893784;
          v209 = 180;
          goto LABEL_403;
        }
        v120 = v118 + 8;
        *(_DWORD *)v337 = v118 + 8;
        if ( (_DWORD)v74 )
        {
          v76 = (unsigned int)Size;
          v77 = v119 + v120;
          if ( v77 && (unsigned int)Size >= v74 )
          {
            memcpy_0(v70, (const void *)(v119 + v120), (unsigned int)v74);
          }
          else
          {
LABEL_112:
            memset_0(v70, 0, v76);
            if ( v77 )
            {
              if ( v76 >= v74 )
                goto LABEL_116;
              *(_DWORD *)_o__errno() = 34;
            }
            else
            {
              *(_DWORD *)_o__errno() = 22;
            }
            invalid_parameter_noinfo();
          }
LABEL_116:
          v28 = v341;
        }
LABEL_117:
        LODWORD(Size) = v74;
        *(_DWORD *)v71 += v74;
        v2 = v364;
        goto LABEL_63;
      }
      LODWORD(Size) = *(_DWORD *)(v118 + v119 + 4);
      v2 = v364;
      goto LABEL_63;
    default:
      goto LABEL_69;
  }
}

```

## disassembly

```asm
0x180015ac0  mov     [rsp-8+arg_8], dl
0x180015ac4  push    rbp
0x180015ac5  push    rbx
0x180015ac6  push    rsi
0x180015ac7  push    rdi
0x180015ac8  push    r12
0x180015aca  push    r13
0x180015acc  push    r14
0x180015ace  push    r15
0x180015ad0  lea     rbp, [rsp-58h]
0x180015ad5  sub     rsp, 158h
0x180015adc  movzx   r15d, dl
0x180015ae0  mov     r13, rcx
0x180015ae3  mov     r8b, 1; bool
0x180015ae6  lea     rdx, aPcpstorageprov_26; "PCPStorageProviderKey::LoadFromContaine"...
0x180015aed  lea     rcx, [rbp+90h+var_F4+4]; this
0x180015af1  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180015af6  nop
0x180015af7  xor     r12d, r12d
0x180015afa  mov     [rsp+190h+var_150], r12
0x180015aff  mov     dword ptr [rbp+90h+var_F4], r12d
0x180015b03  lea     rax, [rsp+190h+var_150]
0x180015b08  mov     [rsp+190h+var_120], rax
0x180015b0d  lea     rax, [rbp+90h+var_F4]
0x180015b11  mov     [rsp+190h+var_118], rax
0x180015b16  mov     [rbp+90h+var_110], 1
0x180015b1a  mov     [rsp+190h+var_140], r12
0x180015b1f  mov     [rsp+190h+var_138], r12
0x180015b24  mov     edi, r12d
0x180015b27  mov     [rsp+190h+hTemplateFile], r12; hTemplateFile
0x180015b2c  mov     dword ptr [rsp+190h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180015b34  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x180015b3c  xor     r9d, r9d; lpSecurityAttributes
0x180015b3f  mov     edx, 80000000h; dwDesiredAccess
0x180015b44  mov     r8d, 1; dwShareMode
0x180015b4a  lea     rcx, [r13+58h]; lpFileName
0x180015b4e  call    cs:__imp_CreateFileW
0x180015b55  nop     dword ptr [rax+rax+00h]
0x180015b5a  mov     rbx, rax
0x180015b5d  lea     r14, __ImageBase
0x180015b64  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015b68  jnz     short loc_180015BD4
0x180015b6a  call    cs:__imp_GetLastError
0x180015b71  nop     dword ptr [rax+rax+00h]
0x180015b76  cmp     eax, 20h ; ' '
0x180015b79  jnz     short loc_180015BD4
0x180015b7b  cmp     edi, 6
0x180015b7e  jnb     short loc_180015BD4
0x180015b80  mov     ecx, edi
0x180015b82  mov     ecx, ds:rva dword_1800DBB78[r14+rcx*4]; dwMilliseconds
0x180015b8a  call    cs:__imp_Sleep
0x180015b91  nop     dword ptr [rax+rax+00h]
0x180015b96  inc     edi
0x180015b98  mov     [rsp+190h+hTemplateFile], r12; hTemplateFile
0x180015b9d  mov     dword ptr [rsp+190h+dwFlagsAndAttributes], 80h; char *
0x180015ba5  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x180015bad  xor     r9d, r9d; lpSecurityAttributes
0x180015bb0  mov     edx, 80000000h; dwDesiredAccess
0x180015bb5  mov     r8d, 1; dwShareMode
0x180015bbb  lea     rcx, [r13+58h]; lpFileName
0x180015bbf  call    cs:__imp_CreateFileW
0x180015bc6  nop     dword ptr [rax+rax+00h]
0x180015bcb  mov     rbx, rax
0x180015bce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015bd2  jz      short loc_180015B6A
0x180015bd4  mov     [rbp+90h+var_100], rbx
0x180015bd8  lea     rax, [rbx-1]
0x180015bdc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015be0  jbe     loc_180017793
0x180015be6  mov     rcx, [rbp+98h]; this
0x180015bed  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180015bf4  mov     edx, 1185h; void *
0x180015bf9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015bfe  mov     ebx, eax
0x180015c00  lea     rcx, [rbp+90h+var_100]
0x180015c04  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180015c09  nop
0x180015c0a  mov     rcx, [rsp+190h+var_138]; void *
0x180015c0f  mov     [rsp+190h+var_138], r12
0x180015c14  test    rcx, rcx
0x180015c17  jz      short loc_180015C1F
0x180015c19  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c1e  nop
0x180015c1f  mov     rcx, [rsp+190h+var_140]; void *
0x180015c24  mov     [rsp+190h+var_140], r12
0x180015c29  test    rcx, rcx
0x180015c2c  jz      short loc_180015C34
0x180015c2e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c33  nop
0x180015c34  cmp     [rbp+90h+var_110], 0
0x180015c38  jz      short loc_180015C7F
0x180015c3a  mov     [rbp+90h+var_110], 0
0x180015c3e  mov     rax, [rsp+190h+var_120]
0x180015c43  mov     rcx, [rax]
0x180015c46  test    rcx, rcx
0x180015c49  jz      short loc_180015C7F
0x180015c4b  mov     rax, [rsp+190h+var_118]
0x180015c50  mov     edx, [rax]
0x180015c52  test    rdx, rdx
0x180015c55  jz      short loc_180015C7F
0x180015c57  mov     byte ptr [rcx], 0
0x180015c5a  lea     rcx, [rcx+1]
0x180015c5e  sub     rdx, 1
0x180015c62  jnz     short loc_180015C57
0x180015c64  jmp     short loc_180015C7F
0x180015c66  mov     rax, [rsp+190h+var_118]
0x180015c6b  mov     edx, [rax]
0x180015c6d  test    rdx, rdx
0x180015c70  jz      short loc_180015C7F
0x180015c72  mov     byte ptr [rcx], 0
0x180015c75  lea     rcx, [rcx+1]
0x180015c79  sub     rdx, 1
0x180015c7d  jnz     short loc_180015C72
0x180015c7f  mov     rcx, [rsp+190h+var_150]
0x180015c84  mov     [rsp+190h+var_150], r12
0x180015c89  jmp     loc_180015D73
0x180015c8e  mov     rcx, [rsp+190h+var_118]
0x180015c93  mov     edx, [rcx]
0x180015c95  test    rdx, rdx
0x180015c98  jz      short loc_180015CAD
0x180015c9a  nop     word ptr [rax+rax+00h]
0x180015ca0  mov     byte ptr [rax], 0
0x180015ca3  lea     rax, [rax+1]
0x180015ca7  sub     rdx, 1; struct std::nothrow_t *
0x180015cab  jnz     short loc_180015CA0
0x180015cad  mov     rcx, [rsp+190h+var_150]; void *
0x180015cb2  mov     [rsp+190h+var_150], r14
0x180015cb7  test    rcx, rcx
0x180015cba  jz      short loc_180015CC2
0x180015cbc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015cc1  nop
0x180015cc2  lea     rcx, [rbp+90h+var_F4+4]; this
0x180015cc6  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180015ccb  xor     eax, eax
0x180015ccd  add     rsp, 158h
0x180015cd4  pop     r15
0x180015cd6  pop     r14
0x180015cd8  pop     r13
0x180015cda  pop     r12
0x180015cdc  pop     rdi
0x180015cdd  pop     rsi
0x180015cde  pop     rbx
0x180015cdf  pop     rbp
0x180015ce0  retn
0x180015ce2  mov     rax, [rsp+190h+var_118]
0x180015ce7  mov     edx, [rax]
0x180015ce9  test    rdx, rdx
0x180015cec  jz      short loc_180015CFD
0x180015cee  xchg    ax, ax
0x180015cf0  mov     byte ptr [rcx], 0
0x180015cf3  lea     rcx, [rcx+1]
0x180015cf7  sub     rdx, 1; struct std::nothrow_t *
0x180015cfb  jnz     short loc_180015CF0
0x180015cfd  mov     rcx, [rsp+190h+var_150]; void *
0x180015d02  mov     [rsp+190h+var_150], r14
0x180015d07  test    rcx, rcx
0x180015d0a  jz      short loc_180015D12
0x180015d0c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015d11  nop
0x180015d12  lea     rcx, [rbp+90h+var_F4+4]; this
0x180015d16  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180015d1b  mov     eax, 80070008h
0x180015d20  jmp     short loc_180015CCD
0x180015d22  mov     rax, [rsp+190h+var_118]
0x180015d27  mov     edx, [rax]
0x180015d29  test    rdx, rdx
0x180015d2c  jz      short loc_180015CFD
0x180015d2e  xchg    ax, ax
0x180015d30  mov     byte ptr [rcx], 0
0x180015d33  lea     rcx, [rcx+1]
0x180015d37  sub     rdx, 1
0x180015d3b  jnz     short loc_180015D30
0x180015d3d  jmp     short loc_180015CFD
0x180015d3f  mov     rax, [rsp+190h+var_118]
0x180015d44  mov     edx, [rax]; struct std::nothrow_t *
0x180015d46  test    rdx, rdx
0x180015d49  jz      short loc_180015D69
0x180015d4b  nop     dword ptr [rax+rax+00h]
0x180015d50  mov     byte ptr [rcx], 0
0x180015d53  lea     rcx, [rcx+1]
0x180015d57  sub     rdx, 1
0x180015d5b  jnz     short loc_180015D50
0x180015d5d  mov     rcx, [rsp+190h+var_150]
0x180015d62  mov     [rsp+190h+var_150], r14
0x180015d67  jmp     short loc_180015D73
0x180015d69  mov     rcx, [rsp+190h+var_150]; void *
0x180015d6e  mov     [rsp+190h+var_150], r14
0x180015d73  test    rcx, rcx
0x180015d76  jz      short loc_180015D7E
0x180015d78  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015d7d  nop
0x180015d7e  lea     rcx, [rbp+90h+var_F4+4]; this
0x180015d82  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180015d87  mov     eax, ebx
0x180015d89  jmp     loc_180015CCD
0x180015d8e  mov     rax, [rsp+190h+var_118]
0x180015d93  mov     edx, [rax]
0x180015d95  test    rdx, rdx
0x180015d98  jz      short loc_180015D69
0x180015d9a  nop     word ptr [rax+rax+00h]
0x180015da0  mov     byte ptr [rcx], 0
0x180015da3  lea     rcx, [rcx+1]
0x180015da7  sub     rdx, 1
0x180015dab  jnz     short loc_180015DA0
0x180015dad  mov     rcx, [rsp+190h+var_150]
0x180015db2  mov     [rsp+190h+var_150], r14
0x180015db7  jmp     short loc_180015D73
0x180015db9  mov     rax, [rsp+190h+var_118]
0x180015dbe  mov     edx, [rax]
0x180015dc0  test    rdx, rdx
0x180015dc3  jz      short loc_180015DDD
0x180015dc5  nop     word ptr [rax+rax+00000000h]
0x180015dd0  mov     byte ptr [rcx], 0
0x180015dd3  lea     rcx, [rcx+1]
0x180015dd7  sub     rdx, 1; struct std::nothrow_t *
0x180015ddb  jnz     short loc_180015DD0
0x180015ddd  mov     rcx, [rsp+190h+var_150]; void *
0x180015de2  mov     [rsp+190h+var_150], r12
0x180015de7  test    rcx, rcx
0x180015dea  jz      short loc_180015DF2
0x180015dec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015df1  nop
0x180015df2  lea     rcx, [rbp+90h+var_F4+4]; this
0x180015df6  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180015dfb  mov     eax, edi
0x180015dfd  jmp     loc_180015CCD
0x180015e02  mov     rax, [rsp+190h+var_118]
0x180015e07  mov     edx, [rax]
0x180015e09  test    rdx, rdx
0x180015e0c  jz      short loc_180015DDD
0x180015e0e  xchg    ax, ax
0x180015e10  mov     byte ptr [rcx], 0
0x180015e13  lea     rcx, [rcx+1]
0x180015e17  sub     rdx, 1
0x180015e1b  jnz     short loc_180015E10
0x180015e1d  jmp     short loc_180015DDD
0x180015e1f  cmp     r15, rdi
0x180015e22  jnb     short loc_180015E3B
0x180015e24  call    cs:__imp__o__errno
0x180015e2b  nop     dword ptr [rax+rax+00h]
0x180015e30  mov     dword ptr [rax], 22h ; '"'
0x180015e36  call    _invalid_parameter_noinfo
0x180015e3b  mov     r12d, [rbp+90h+var_108]
0x180015e3f  movzx   r15d, [rbp+90h+arg_8]
0x180015e47  mov     dword ptr [rsp+190h+Size], edi
0x180015e4b  add     [rbx], edi
0x180015e4d  xor     r14d, r14d
0x180015e50  mov     rcx, r14
0x180015e53  lea     rbx, aRsa; "RSA"
0x180015e5a  nop     word ptr [rax+rax+00h]
0x180015e60  movzx   edx, word ptr [rbx+rcx*2]
0x180015e64  inc     rcx
0x180015e67  movzx   eax, word ptr [rsi+rcx*2-2]
0x180015e6c  sub     edx, eax; struct std::nothrow_t *
0x180015e6e  jnz     short loc_180015E76
0x180015e70  cmp     rcx, 4
0x180015e74  jnz     short loc_180015E60
0x180015e76  test    edx, edx
0x180015e78  jnz     loc_180018672
0x180015e7e  mov     rax, rbx
0x180015e81  mov     [r13+2C8h], rax
0x180015e88  mov     rcx, rsi; void *
0x180015e8b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015e90  jmp     short loc_180015EC0
0x180015e92  mov     dword ptr [rbx], 4
0x180015e98  xor     r14d, r14d
0x180015e9b  mov     r12d, r14d
0x180015e9e  mov     [rbp+90h+var_108], r14d
0x180015ea2  mov     byte ptr [rbp+90h+arg_18], r12b
0x180015ea9  mov     [rbp+90h+var_D0], r14d
0x180015ead  mov     [rbp+90h+arg_10], r12b
0x180015eb4  mov     [rbp+90h+var_F8], r14d
0x180015eb8  mov     dword ptr [rsp+190h+Size], r14d
0x180015ebd  nop     dword ptr [rax]
0x180015ec0  mov     r8, [rsp+190h+var_128]
0x180015ec5  mov     ecx, [r8]
0x180015ec8  mov     rax, [r8+8]
0x180015ecc  mov     edx, [rcx+rax]; unsigned __int16 *
0x180015ecf  cmp     edx, 50534B50h
0x180015ed5  jz      loc_180016042
0x180015edb  mov     [rbp+90h+var_F8], edx
0x180015ede  mov     ecx, [r8]
0x180015ee1  mov     rax, [r8+8]
0x180015ee5  mov     r9d, [rcx+rax+4]
0x180015eea  mov     dword ptr [rsp+190h+Size], r9d
0x180015eef  mov     [r13+2C0h], edx
0x180015ef6  cmp     edx, 2000004h
0x180015efc  jz      short loc_180015F52
0x180015efe  cmp     edx, 2000000h
0x180015f04  jz      loc_18001629F
0x180015f0a  ja      short def_180015F28; jumptable 0000000180015F28 default case, case 16777220
0x180015f0c  add     edx, 0FEFFFFFEh; switch 9 cases
0x180015f12  cmp     edx, 8
0x180015f15  ja      short def_180015F28; jumptable 0000000180015F28 default case, case 16777220
0x180015f17  lea     rcx, __ImageBase
0x180015f1e  mov     eax, ds:(jpt_180015F28 - 180000000h)[rcx+rdx*4]
0x180015f25  add     rax, rcx
0x180015f28  jmp     rax; switch jump
0x180015f2e  test    r15b, r15b; jumptable 0000000180015F28 case 16777219
0x180015f31  jnz     loc_18001649B
  ... truncated ...
```
