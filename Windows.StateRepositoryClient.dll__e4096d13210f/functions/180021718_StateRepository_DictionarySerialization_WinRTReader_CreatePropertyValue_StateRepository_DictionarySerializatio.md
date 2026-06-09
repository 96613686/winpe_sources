# StateRepository::DictionarySerialization::WinRTReader::CreatePropertyValue(StateRepository::DictionarySerialization::DataType,uint,unsigned __int64,void const *,RoVariant &)

- ea: `0x180021718`
- end: `0x18002347d`
- name: `?CreatePropertyValue@WinRTReader@DictionarySerialization@StateRepository@@AEAAJW4DataType@23@I_KPEBXAEAVRoVariant@@@Z`
- size: `7525`
- prototype: `__int64 __fastcall(StateRepository::DictionarySerialization::WinRTReader *, int, unsigned int, unsigned __int64, unsigned int *sourceString, unsigned __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180023910`

## callees

- `0x180002980`
- `0x180002e50`
- `0x180003d04`
- `0x1800075e4`
- `0x180009420`
- `0x18000b348`
- `0x18000c2e4`
- `0x18000c58c`
- `0x1800191a4`
- `0x180021594`
- `0x180021668`
- `0x18002169c`
- `0x180021718`
- `0x180023484`
- `0x180023860`
- `0x180026030`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002227b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002227b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023233`

## string_xrefs

- `0x180021768`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180021a56`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180021af1`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180022220`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180022290`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x1800224a9`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180022538`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180022d6c`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180022ea1`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180022f10`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180023282`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x18002333d`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180023372`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x18002344d`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180023468`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DictionarySerialization::WinRTReader::CreatePropertyValue(
        StateRepository::DictionarySerialization::WinRTReader *a1,
        int a2,
        unsigned int a3,
        unsigned __int64 a4,
        unsigned int *sourceString,
        unsigned __int64 a6)
{
  const unsigned __int16 *v6; // rsi
  unsigned __int64 v8; // r15
  __int64 v11; // rdx
  unsigned int IsAvailable; // edi
  __int64 v13; // rdx
  __int64 *v15; // r12
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // r14d
  struct IInspectableVtbl *v22; // rbx
  int v23; // edi
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rax
  struct IInspectableVtbl *v28; // rbx
  int v29; // edi
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rax
  struct IInspectableVtbl *v33; // rbx
  int v34; // edi
  int v35; // eax
  char v36; // cl
  __int64 v37; // rax
  struct IInspectableVtbl *v38; // rbx
  int v39; // edi
  int v40; // eax
  unsigned int v41; // esi
  __int64 v42; // rax
  struct IInspectableVtbl *v43; // rbx
  int v44; // edi
  int v45; // eax
  __int128 v46; // xmm0
  __int64 v47; // rax
  int v48; // eax
  unsigned __int64 v49; // rsi
  struct IInspectableVtbl *v50; // rbx
  int v51; // edi
  int v52; // eax
  int v53; // ebx
  int v54; // ebx
  int v55; // ebx
  __int64 v56; // rdx
  __int64 v57; // rax
  struct IInspectableVtbl *v58; // rbx
  int v59; // edi
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rax
  struct IInspectableVtbl *v63; // rbx
  int v64; // edi
  int v65; // eax
  __int64 v66; // rdx
  __int64 v67; // rax
  struct IInspectableVtbl *v68; // rbx
  int v69; // edi
  int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // rax
  struct IInspectableVtbl *v73; // rbx
  int v74; // edi
  int v75; // eax
  __int128 v76; // xmm0
  __int64 v77; // rax
  int v78; // eax
  unsigned __int64 v79; // rsi
  struct IInspectableVtbl *v80; // rbx
  int v81; // edi
  int v82; // eax
  int v83; // ebx
  int v84; // ebx
  int v85; // ebx
  int v86; // ebx
  int v87; // ebx
  int v88; // ebx
  int v89; // ebx
  int v90; // ebx
  __int64 v91; // rdx
  __int64 v92; // rax
  struct IInspectableVtbl *v93; // rbx
  int v94; // edi
  int v95; // eax
  __int64 v96; // rdx
  __int64 v97; // rax
  struct IInspectableVtbl *v98; // rbx
  int v99; // edi
  int v100; // eax
  __int64 v101; // rdx
  __int64 v102; // rax
  struct IInspectableVtbl *v103; // rbx
  int v104; // edi
  int v105; // eax
  __int64 v106; // rax
  struct IInspectableVtbl *v107; // rbx
  int v108; // edi
  int v109; // eax
  __int64 v110; // rdx
  __int64 v111; // rax
  struct IInspectableVtbl *v112; // rbx
  int v113; // edi
  int v114; // eax
  UINT32 v115; // edx
  int v116; // eax
  HRESULT v117; // ebx
  __int64 v118; // rdx
  __int64 v119; // rax
  struct IInspectableVtbl *v120; // rbx
  int v121; // edi
  int v122; // eax
  __int64 v123; // rdx
  __int64 v124; // rax
  struct IInspectableVtbl *v125; // rbx
  int v126; // edi
  int v127; // eax
  __int64 v128; // rax
  struct IInspectableVtbl *v129; // rbx
  int v130; // edi
  int v131; // eax
  int v132; // eax
  __int64 v133; // r9
  __int64 v134; // rdx
  __int64 v135; // rax
  int v136; // r14d
  struct IInspectableVtbl *v137; // rbx
  int v138; // edi
  int v139; // eax
  int v140; // ebx
  int v141; // ebx
  int v142; // ebx
  int v143; // ebx
  __int64 v144; // rax
  struct IInspectableVtbl *v145; // rbx
  int v146; // edi
  int v147; // eax
  __int64 v148; // rax
  struct IInspectableVtbl *v149; // rbx
  int v150; // edi
  int v151; // eax
  __int64 v152; // rax
  struct IInspectableVtbl *v153; // rbx
  int v154; // edi
  int v155; // eax
  __int64 v156; // rax
  struct IInspectableVtbl *v157; // rbx
  int v158; // edi
  int v159; // eax
  __int64 v160; // rax
  struct IInspectableVtbl *v161; // rbx
  int v162; // edi
  int v163; // eax
  __int64 v164; // rax
  struct IInspectableVtbl *v165; // rbx
  int v166; // edi
  int v167; // eax
  int v168; // ebx
  int v169; // ebx
  int v170; // ebx
  __int64 v171; // rax
  struct IInspectableVtbl *v172; // rbx
  int v173; // edi
  int v174; // eax
  __int64 v175; // rax
  struct IInspectableVtbl *v176; // rbx
  int v177; // edi
  int v178; // eax
  __int64 v179; // rax
  struct IInspectableVtbl *v180; // rbx
  int v181; // edi
  int v182; // eax
  __int64 v183; // rax
  struct IInspectableVtbl *v184; // rbx
  int v185; // edi
  int v186; // eax
  __int64 v187; // rax
  struct IInspectableVtbl *lpVtbl; // rbx
  int v189; // edi
  int v190; // eax
  int v191; // ebx
  int v192; // ebx
  int v193; // ebx
  int v194; // ebx
  int v195; // ebx
  int v196; // ebx
  int v197; // ebx
  int v198; // ebx
  unsigned __int64 v199; // rax
  _QWORD *v200; // rbx
  HSTRING v201; // rax
  unsigned __int64 v202; // rdi
  HSTRING v203; // rax
  struct IInspectable **v204; // r9
  unsigned __int64 v205; // rdx
  __int64 v206; // rdx
  __int64 v207; // rdx
  unsigned __int64 i; // r14
  __int64 v209; // rcx
  __int64 v210; // rax
  unsigned __int64 v211; // rdi
  __int64 v212; // rcx
  __int64 v213; // rax
  __int64 v214; // rax
  __int64 v215; // rax
  __int64 v216; // rax
  __int64 v217; // rax
  struct IInspectableVtbl *v218; // rbx
  int v219; // edi
  int v220; // eax
  unsigned __int64 v221; // rax
  HSTRING_HEADER *v222; // rbx
  unsigned __int64 v223; // rax
  HSTRING *v224; // rdi
  unsigned __int64 v225; // rdx
  unsigned __int64 v226; // r13
  __int64 v227; // r10
  HRESULT StringReference; // eax
  __int64 v229; // r9
  __int64 v230; // rdx
  __int64 v231; // rax
  int v232; // r12d
  struct IInspectableVtbl *v233; // rsi
  int v234; // r14d
  int v235; // eax
  __int64 v236; // rax
  struct IInspectableVtbl *v237; // rbx
  int v238; // edi
  int v239; // eax
  int v240; // [rsp+20h] [rbp-59h]
  int v241; // [rsp+20h] [rbp-59h]
  struct IInspectable v242; // [rsp+30h] [rbp-49h] BYREF
  int v243; // [rsp+38h] [rbp-41h]
  struct IInspectable *v244[2]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int64 v245; // [rsp+50h] [rbp-29h] BYREF
  struct IInspectable *v246; // [rsp+58h] [rbp-21h] BYREF
  HSTRING string; // [rsp+60h] [rbp-19h] BYREF
  struct IInspectable *v248; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  v6 = (const unsigned __int16 *)sourceString;
  v8 = a3;
  IsAvailable = StateRepository::DictionarySerialization::WinRTReader::EnsurePropertyValueStaticsIsAvailable(a1);
  if ( (IsAvailable & 0x80000000) != 0 )
  {
    v13 = 198;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)IsAvailable,
      v240);
    return IsAvailable;
  }
  v15 = *(__int64 **)a1;
  if ( a2 > 21 )
  {
    if ( a2 <= 33 )
    {
      if ( a2 == 33 )
      {
        if ( a4 != 4 * v8 )
        {
          v19 = 445;
          goto LABEL_36;
        }
        v244[0] = (struct IInspectable *)a6;
        v187 = *v15;
        v244[1] = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v187 + 264))(
                v15,
                (unsigned int)v8,
                sourceString,
                &v244[1]);
        RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
        lpVtbl = v242.lpVtbl;
        v189 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v190 = *(_DWORD *)(a6 + 8);
        v242.lpVtbl = *(struct IInspectableVtbl **)a6;
        *(_QWORD *)a6 = lpVtbl;
        *(_DWORD *)(a6 + 8) = v189;
        v243 = v190;
        RoVariant::~RoVariant((RoVariant *)&v242);
        if ( v21 < 0 )
        {
          v25 = 446;
          goto LABEL_40;
        }
      }
      else if ( a2 > 28 )
      {
        v168 = a2 - 29;
        if ( v168 )
        {
          v169 = v168 - 1;
          if ( v169 )
          {
            v170 = v169 - 1;
            if ( v170 )
            {
              if ( v170 != 1 )
                return 2154233861LL;
              if ( a4 != 16 * v8 )
              {
                v19 = 438;
                goto LABEL_36;
              }
              v244[0] = (struct IInspectable *)a6;
              v171 = *v15;
              v244[1] = 0;
              v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v171 + 352))(
                      v15,
                      (unsigned int)v8,
                      sourceString,
                      &v244[1]);
              RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
              v172 = v242.lpVtbl;
              v173 = v243;
              v242.lpVtbl = 0;
              v243 = 0;
              RoVariant::~RoVariant((RoVariant *)&v242);
              v174 = *(_DWORD *)(a6 + 8);
              v242.lpVtbl = *(struct IInspectableVtbl **)a6;
              *(_QWORD *)a6 = v172;
              *(_DWORD *)(a6 + 8) = v173;
              v243 = v174;
              RoVariant::~RoVariant((RoVariant *)&v242);
              if ( v21 < 0 )
              {
                v25 = 439;
                goto LABEL_40;
              }
            }
            else
            {
              if ( a4 != 8 * v8 )
              {
                v19 = 430;
                goto LABEL_36;
              }
              v244[0] = (struct IInspectable *)a6;
              v175 = *v15;
              v244[1] = 0;
              v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v175 + 336))(
                      v15,
                      (unsigned int)v8,
                      sourceString,
                      &v244[1]);
              RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
              v176 = v242.lpVtbl;
              v177 = v243;
              v242.lpVtbl = 0;
              v243 = 0;
              RoVariant::~RoVariant((RoVariant *)&v242);
              v178 = *(_DWORD *)(a6 + 8);
              v242.lpVtbl = *(struct IInspectableVtbl **)a6;
              *(_QWORD *)a6 = v176;
              *(_DWORD *)(a6 + 8) = v177;
              v243 = v178;
              RoVariant::~RoVariant((RoVariant *)&v242);
              if ( v21 < 0 )
              {
                v25 = 431;
                goto LABEL_40;
              }
            }
          }
          else
          {
            if ( a4 != 8 * v8 )
            {
              v19 = 422;
              goto LABEL_36;
            }
            v244[0] = (struct IInspectable *)a6;
            v179 = *v15;
            v244[1] = 0;
            v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v179 + 248))(
                    v15,
                    (unsigned int)v8,
                    sourceString,
                    &v244[1]);
            RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
            v180 = v242.lpVtbl;
            v181 = v243;
            v242.lpVtbl = 0;
            v243 = 0;
            RoVariant::~RoVariant((RoVariant *)&v242);
            v182 = *(_DWORD *)(a6 + 8);
            v242.lpVtbl = *(struct IInspectableVtbl **)a6;
            *(_QWORD *)a6 = v180;
            *(_DWORD *)(a6 + 8) = v181;
            v243 = v182;
            RoVariant::~RoVariant((RoVariant *)&v242);
            if ( v21 < 0 )
            {
              v25 = 423;
              goto LABEL_40;
            }
          }
        }
        else
        {
          if ( a4 != 4 * v8 )
          {
            v19 = 415;
            goto LABEL_36;
          }
          v244[0] = (struct IInspectable *)a6;
          v183 = *v15;
          v244[1] = 0;
          v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v183 + 232))(
                  v15,
                  (unsigned int)v8,
                  sourceString,
                  &v244[1]);
          RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
          v184 = v242.lpVtbl;
          v185 = v243;
          v242.lpVtbl = 0;
          v243 = 0;
          RoVariant::~RoVariant((RoVariant *)&v242);
          v186 = *(_DWORD *)(a6 + 8);
          v242.lpVtbl = *(struct IInspectableVtbl **)a6;
          *(_QWORD *)a6 = v184;
          *(_DWORD *)(a6 + 8) = v185;
          v243 = v186;
          RoVariant::~RoVariant((RoVariant *)&v242);
          if ( v21 < 0 )
          {
            v25 = 416;
            goto LABEL_40;
          }
        }
      }
      else if ( a2 == 28 )
      {
        if ( a4 != 2 * v8 )
        {
          v19 = 408;
          goto LABEL_36;
        }
        v244[0] = (struct IInspectable *)a6;
        v164 = *v15;
        v244[1] = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v164 + 216))(
                v15,
                (unsigned int)v8,
                sourceString,
                &v244[1]);
        RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
        v165 = v242.lpVtbl;
        v166 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v167 = *(_DWORD *)(a6 + 8);
        v242.lpVtbl = *(struct IInspectableVtbl **)a6;
        *(_QWORD *)a6 = v165;
        *(_DWORD *)(a6 + 8) = v166;
        v243 = v167;
        RoVariant::~RoVariant((RoVariant *)&v242);
        if ( v21 < 0 )
        {
          v25 = 409;
          goto LABEL_40;
        }
      }
      else
      {
        v140 = a2 - 22;
        if ( v140 )
        {
          v141 = v140 - 2;
          if ( v141 )
          {
            v142 = v141 - 1;
            if ( v142 )
            {
              v143 = v142 - 1;
              if ( v143 )
              {
                if ( v143 != 1 )
                  return 2154233861LL;
                if ( a4 != 16 * v8 )
                {
                  v19 = 401;
                  goto LABEL_36;
                }
                v244[0] = (struct IInspectable *)a6;
                v144 = *v15;
                v244[1] = 0;
                v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v144 + 312))(
                        v15,
                        (unsigned int)v8,
                        sourceString,
                        &v244[1]);
                RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
                v145 = v242.lpVtbl;
                v146 = v243;
                v242.lpVtbl = 0;
                v243 = 0;
                RoVariant::~RoVariant((RoVariant *)&v242);
                v147 = *(_DWORD *)(a6 + 8);
                v242.lpVtbl = *(struct IInspectableVtbl **)a6;
                *(_QWORD *)a6 = v145;
                *(_DWORD *)(a6 + 8) = v146;
                v243 = v147;
                RoVariant::~RoVariant((RoVariant *)&v242);
                if ( v21 < 0 )
                {
                  v25 = 402;
                  goto LABEL_40;
                }
              }
              else
              {
                if ( a4 != 8 * v8 )
                {
                  v19 = 394;
                  goto LABEL_36;
                }
                v244[0] = (struct IInspectable *)a6;
                v148 = *v15;
                v244[1] = 0;
                v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v148 + 272))(
                        v15,
                        (unsigned int)v8,
                        sourceString,
                        &v244[1]);
                RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
                v149 = v242.lpVtbl;
                v150 = v243;
                v242.lpVtbl = 0;
                v243 = 0;
                RoVariant::~RoVariant((RoVariant *)&v242);
                v151 = *(_DWORD *)(a6 + 8);
                v242.lpVtbl = *(struct IInspectableVtbl **)a6;
                *(_QWORD *)a6 = v149;
                *(_DWORD *)(a6 + 8) = v150;
                v243 = v151;
                RoVariant::~RoVariant((RoVariant *)&v242);
                if ( v21 < 0 )
                {
                  v25 = 395;
                  goto LABEL_40;
                }
              }
            }
            else
            {
              if ( a4 != 8 * v8 )
              {
                v19 = 387;
                goto LABEL_36;
              }
              v244[0] = (struct IInspectable *)a6;
              v152 = *v15;
              v244[1] = 0;
              v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v152 + 320))(
                      v15,
                      (unsigned int)v8,
                      sourceString,
                      &v244[1]);
              RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
              v153 = v242.lpVtbl;
              v154 = v243;
              v242.lpVtbl = 0;
              v243 = 0;
              RoVariant::~RoVariant((RoVariant *)&v242);
              v155 = *(_DWORD *)(a6 + 8);
              v242.lpVtbl = *(struct IInspectableVtbl **)a6;
              *(_QWORD *)a6 = v153;
              *(_DWORD *)(a6 + 8) = v154;
              v243 = v155;
              RoVariant::~RoVariant((RoVariant *)&v242);
              if ( v21 < 0 )
              {
                v25 = 388;
                goto LABEL_40;
              }
            }
          }
          else
          {
            if ( a4 != 2 * v8 )
            {
              v19 = 379;
              goto LABEL_36;
            }
            v244[0] = (struct IInspectable *)a6;
            v156 = *v15;
            v244[1] = 0;
            v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v156 + 280))(
                    v15,
                    (unsigned int)v8,
                    sourceString,
                    &v244[1]);
            RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
            v157 = v242.lpVtbl;
            v158 = v243;
            v242.lpVtbl = 0;
            v243 = 0;
            RoVariant::~RoVariant((RoVariant *)&v242);
            v159 = *(_DWORD *)(a6 + 8);
            v242.lpVtbl = *(struct IInspectableVtbl **)a6;
            *(_QWORD *)a6 = v157;
            *(_DWORD *)(a6 + 8) = v158;
            v243 = v159;
            RoVariant::~RoVariant((RoVariant *)&v242);
            if ( v21 < 0 )
            {
              v25 = 380;
              goto LABEL_40;
            }
          }
        }
        else
        {
          if ( a4 != v8 )
          {
            v19 = 372;
            goto LABEL_36;
          }
          v244[0] = (struct IInspectable *)a6;
          v160 = *v15;
          v244[1] = 0;
          v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v160 + 288))(
                  v15,
                  (unsigned int)v8,
                  sourceString,
                  &v244[1]);
          RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
          v161 = v242.lpVtbl;
          v162 = v243;
          v242.lpVtbl = 0;
          v243 = 0;
          RoVariant::~RoVariant((RoVariant *)&v242);
          v163 = *(_DWORD *)(a6 + 8);
          v242.lpVtbl = *(struct IInspectableVtbl **)a6;
          *(_QWORD *)a6 = v161;
          *(_DWORD *)(a6 + 8) = v162;
          v243 = v163;
          RoVariant::~RoVariant((RoVariant *)&v242);
          if ( v21 < 0 )
          {
            v25 = 373;
            goto LABEL_40;
          }
        }
      }
      return 0;
    }
    v191 = a2 - 34;
    if ( !v191 )
    {
      if ( a4 != 8 * v8 )
      {
        v19 = 453;
        goto LABEL_36;
      }
      v244[0] = (struct IInspectable *)a6;
      v236 = *v15;
      v244[1] = 0;
      v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v236 + 344))(
              v15,
              (unsigned int)v8,
              sourceString,
              &v244[1]);
      RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
      v237 = v242.lpVtbl;
      v238 = v243;
      v242.lpVtbl = 0;
      v243 = 0;
      RoVariant::~RoVariant((RoVariant *)&v242);
      v239 = *(_DWORD *)(a6 + 8);
      v242.lpVtbl = *(struct IInspectableVtbl **)a6;
      *(_QWORD *)a6 = v237;
      *(_DWORD *)(a6 + 8) = v238;
      v243 = v239;
      RoVariant::~RoVariant((RoVariant *)&v242);
      if ( v21 < 0 )
      {
        v25 = 454;
        goto LABEL_40;
      }
      return 0;
    }
    v192 = v191 - 1;
    if ( v192 )
    {
      v193 = v192 - 1;
      if ( !v193 )
      {
        if ( a4 != 8 * v8 )
        {
          v19 = 502;
          goto LABEL_36;
        }
        v244[0] = (struct IInspectable *)a6;
        v217 = *v15;
        v244[1] = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v217 + 328))(
                v15,
                (unsigned int)v8,
                sourceString,
                &v244[1]);
        RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
        v218 = v242.lpVtbl;
        v219 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v220 = *(_DWORD *)(a6 + 8);
        v242.lpVtbl = *(struct IInspectableVtbl **)a6;
        *(_QWORD *)a6 = v218;
        *(_DWORD *)(a6 + 8) = v219;
        v243 = v220;
        RoVariant::~RoVariant((RoVariant *)&v242);
        if ( v21 < 0 )
        {
          v25 = 503;
          goto LABEL_40;
        }
        return 0;
      }
      v194 = v193 - 1;
      if ( v194 )
      {
        v195 = v194 - 1;
        if ( v195 )
        {
          v196 = v195 - 1;
          if ( v196 )
          {
            v197 = v196 - 1;
            if ( v197 )
            {
              v198 = v197 - 1;
              if ( v198 )
              {
                if ( v198 != 1 )
                  return 2154233861LL;
                v199 = 8 * v8;
                if ( !is_mul_ok(v8, 8u) )
                  v199 = -1;
                v200 = operator new[](v199, (const struct std::nothrow_t *)&std::nothrow);
                if ( !v200 )
                {
                  IsAvailable = -2147024882;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x220,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
                    (const char *)0x8007000ELL,
                    v240);
                  operator delete(0);
                  return IsAvailable;
                }
                v201 = 0;
                v202 = 0;
                if ( (_DWORD)v8 )
                {
                  while ( 1 )
                  {
                    v203 = v201 + 1;
                    v248 = 0;
                    v245 = 0;
                    v204 = (struct IInspectable **)&v200[v202];
                    *v204 = 0;
                    string = v203;
                    if ( (unsigned __int64)v203 > a4 )
                    {
                      v207 = 553;
                      goto LABEL_216;
                    }
                    if ( *(_DWORD *)v6 > 0x100000u )
                    {
                      v207 = 555;
                      goto LABEL_216;
                    }
                    v205 = *(unsigned int *)v6;
                    if ( (unsigned __int64)v203 + v205 > a4 )
                    {
                      v207 = 559;
                      goto LABEL_216;
                    }
                    v242.lpVtbl = (struct IInspectableVtbl *)(v6 + 2);
                    v41 = StateRepository::DictionarySerialization::WinRTReader::Deserialize(
                            (StateRepository::DictionarySerialization::WinRTReader *)&v248,
                            v205,
                            (unsigned int *)v6 + 1,
                            v204,
                            &v245);
                    if ( (v41 & 0x80000000) != 0 )
                      break;
                    string = (HSTRING)((char *)string + v245);
                    if ( (unsigned __int64)string > a4 )
                    {
                      v207 = 573;
LABEL_216:
                      v41 = -2140733435;
                      goto LABEL_217;
                    }
                    v6 = (const unsigned __int16 *)((char *)v242.lpVtbl + v245);
                    wil::com_ptr_t<Windows::Foundation::IPropertyValueStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IPropertyValueStatics,wil::err_returncode_policy>(&v248);
                    v201 = string;
                    if ( ++v202 >= v8 )
                      goto LABEL_206;
                  }
                  for ( i = 0; i < v202; ++i )
                  {
                    v209 = v200[i];
                    if ( !v209 )
                      wil::details::in1diag3::_FailFast_Hr(
                        retaddr,
                        (void *)0x235,
                        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
                        (const char *)0x8000FFFFLL,
                        v240);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v209 + 16LL))(v209);
                  }
                  v207 = 568;
LABEL_217:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v207,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
                    (const char *)v41,
                    v240);
                  wil::com_ptr_t<Windows::Foundation::IPropertyValueStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IPropertyValueStatics,wil::err_returncode_policy>(&v248);
                }
                else
                {
LABEL_206:
                  if ( v201 == (HSTRING)a4 )
                  {
                    v244[0] = (struct IInspectable *)a6;
                    v210 = *v15;
                    v244[1] = 0;
                    v41 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *, struct IInspectable **))(v210 + 304))(
                            v15,
                            (unsigned int)v8,
                            v200,
                            &v244[1]);
                    RoVariant::Attach((RoVariant *)a6, v244[1]);
                    if ( (v41 & 0x80000000) == 0 )
                    {
                      v211 = 0;
                      if ( (_DWORD)v8 )
                      {
                        do
                        {
                          v212 = v200[v211];
                          if ( !v212 )
                            wil::details::in1diag3::_FailFast_Hr(
                              retaddr,
                              (void *)0x244,
                              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
                              (const char *)0x8000FFFFLL,
                              v240);
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v212 + 16LL))(v212);
                          ++v211;
                        }
                        while ( v211 < v8 );
                      }
                      operator delete(v200);
                      return 0;
                    }
                    v206 = 577;
                  }
                  else
                  {
                    v41 = -2140733435;
                    v206 = 576;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v206,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
                    (const char *)v41,
                    v240);
                }
                operator delete(v200);
                return v41;
              }
              return 2147500033LL;
            }
            if ( a4 != 8 * v8 )
            {
              v19 = 530;
              goto LABEL_36;
            }
            v244[0] = (struct IInspectable *)a6;
            v213 = *v15;
            v244[1] = 0;
            v117 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v213 + 256))(
                     v15,
                     (unsigned int)v8,
                     sourceString,
                     &v244[1]);
            RoVariant::Attach((RoVariant *)a6, v244[1]);
            if ( v117 >= 0 )
              return 0;
            v118 = 531;
          }
          else
          {
            if ( a4 != 4 * v8 )
            {
              v19 = 523;
              goto LABEL_36;
            }
            v244[0] = (struct IInspectable *)a6;
            v214 = *v15;
            v244[1] = 0;
            v117 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v214 + 240))(
                     v15,
                     (unsigned int)v8,
                     sourceString,
                     &v244[1]);
            RoVariant::Attach((RoVariant *)a6, v244[1]);
            if ( v117 >= 0 )
              return 0;
            v118 = 524;
          }
        }
        else
        {
          if ( a4 != 2 * v8 )
          {
            v19 = 516;
            goto LABEL_36;
          }
          v244[0] = (struct IInspectable *)a6;
          v215 = *v15;
          v244[1] = 0;
          v117 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v215 + 224))(
                   v15,
                   (unsigned int)v8,
                   sourceString,
                   &v244[1]);
          RoVariant::Attach((RoVariant *)a6, v244[1]);
          if ( v117 >= 0 )
            return 0;
          v118 = 517;
        }
      }
      else
      {
        if ( a4 != v8 )
        {
          v19 = 509;
          goto LABEL_36;
        }
        v244[0] = (struct IInspectable *)a6;
        v216 = *v15;
        v244[1] = 0;
        v117 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, unsigned int *, struct IInspectable **))(v216 + 208))(
                 v15,
                 (unsigned int)v8,
                 sourceString,
                 &v244[1]);
        RoVariant::Attach((RoVariant *)a6, v244[1]);
        if ( v117 >= 0 )
          return 0;
        v118 = 510;
      }
LABEL_107:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v118,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)(unsigned int)v117,
        v240);
      return (unsigned int)v117;
    }
    v221 = 24 * v8;
    if ( !is_mul_ok(v8, 0x18u) )
      v221 = -1;
    v222 = (HSTRING_HEADER *)operator new[](v221, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v222 )
    {
      IsAvailable = -2147024882;
      v13 = 465;
      goto LABEL_3;
    }
    v223 = 8 * v8;
    if ( !is_mul_ok(v8, 8u) )
      v223 = -1;
    v224 = (HSTRING *)operator new[](v223, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v224 )
    {
      IsAvailable = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)0x8007000ELL,
        v240);
      operator delete(v222);
      return IsAvailable;
    }
    v225 = 0;
    v226 = 0;
    v245 = 0;
    if ( (_DWORD)v8 )
    {
      while ( v226 + 4 <= a4 )
      {
        v227 = *(unsigned int *)v6;
        if ( (unsigned int)v227 > 0x100000 )
        {
          v230 = 477;
          goto LABEL_263;
        }
        v242.lpVtbl = (struct IInspectableVtbl *)*(unsigned int *)v6;
        v226 += v227 + 4;
        if ( v226 > a4 )
        {
          v230 = 484;
          goto LABEL_263;
        }
        string = (HSTRING)(v6 + 2);
        StringReference = WindowsCreateStringReference(
                            (PCWSTR)((unsigned __int64)(v6 + 2) & -(__int64)((_DWORD)v227 != 0)),
                            (unsigned int)v227 >> 1 != 0 ? ((unsigned int)v227 >> 1) - 1 : 0,
                            &v222[v225],
                            &v224[v225]);
        v41 = StringReference;
        if ( StringReference < 0 )
        {
          v229 = (unsigned int)StringReference;
          v230 = 488;
          goto LABEL_264;
        }
        v225 = v245 + 1;
        v245 = v225;
        if ( v225 >= v8 )
          goto LABEL_266;
        v6 = (const unsigned __int16 *)((char *)v242.lpVtbl + (unsigned __int64)string);
      }
      v230 = 475;
    }
    else
    {
LABEL_266:
      if ( v226 == a4 )
      {
        v244[0] = (struct IInspectable *)a6;
        v231 = *v15;
        v244[1] = 0;
        v232 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING *, struct IInspectable **))(v231 + 296))(
                 v15,
                 (unsigned int)v8,
                 v224,
                 &v244[1]);
        RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
        v233 = v242.lpVtbl;
        v234 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v235 = *(_DWORD *)(a6 + 8);
        v242.lpVtbl = *(struct IInspectableVtbl **)a6;
        *(_QWORD *)a6 = v233;
        *(_DWORD *)(a6 + 8) = v234;
        v243 = v235;
        RoVariant::~RoVariant((RoVariant *)&v242);
        if ( v232 >= 0 )
        {
          operator delete(v224);
          operator delete(v222);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EF,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
          (const char *)(unsigned int)v232,
          v240);
        v41 = v232;
LABEL_265:
        operator delete(v224);
        operator delete(v222);
        return v41;
      }
      v230 = 494;
    }
LABEL_263:
    v41 = -2140733435;
    v229 = 2154233861LL;
LABEL_264:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v230,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)v229,
      v240);
    goto LABEL_265;
  }
  if ( a2 == 21 )
  {
    string = 0;
    v248 = 0;
    v245 = 0;
    v132 = StateRepository::DictionarySerialization::WinRTReader::Deserialize(
             (StateRepository::DictionarySerialization::WinRTReader *)&string,
             a4,
             sourceString,
             &v248,
             &v245);
    v41 = v132;
    if ( v132 >= 0 )
    {
      if ( v245 == a4 )
      {
        v244[0] = (struct IInspectable *)a6;
        v135 = *v15;
        v244[1] = 0;
        v136 = (*(__int64 (__fastcall **)(__int64 *, struct IInspectable *, struct IInspectable **))(v135 + 152))(
                 v15,
                 v248,
                 &v244[1]);
        RoVariant::RoVariant((RoVariant *)&v242, v244[1], 1, 1);
        v137 = v242.lpVtbl;
        v138 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v139 = *(_DWORD *)(a6 + 8);
        v242.lpVtbl = *(struct IInspectableVtbl **)a6;
        *(_QWORD *)a6 = v137;
        *(_DWORD *)(a6 + 8) = v138;
        v243 = v139;
        RoVariant::~RoVariant((RoVariant *)&v242);
        if ( v136 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v248);
          wil::com_ptr_t<Windows::Foundation::IPropertyValueStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IPropertyValueStatics,wil::err_returncode_policy>(&string);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16C,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
          (const char *)(unsigned int)v136,
          v241);
        v41 = v136;
LABEL_125:
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v248);
        wil::com_ptr_t<Windows::Foundation::IPropertyValueStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IPropertyValueStatics,wil::err_returncode_policy>(&string);
        return v41;
      }
      v41 = -2140733435;
      v134 = 363;
      v133 = 2154233861LL;
    }
    else
    {
      v133 = (unsigned int)v132;
      v134 = 362;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v134,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)v133,
      v241);
    goto LABEL_125;
  }
  if ( a2 > 11 )
  {
    v83 = a2 - 12;
    if ( !v83 )
    {
      if ( a4 != 4 )
      {
        v19 = 285;
        goto LABEL_36;
      }
      v245 = a6;
      v128 = *v15;
      v246 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v128 + 112))(v15, v11, &v246);
      RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
      v129 = v242.lpVtbl;
      v130 = v243;
      v242.lpVtbl = 0;
      v243 = 0;
      RoVariant::~RoVariant((RoVariant *)&v242);
      v131 = *(_DWORD *)(a6 + 8);
      v244[0] = *(struct IInspectable **)a6;
      *(_QWORD *)a6 = v129;
      *(_DWORD *)(a6 + 8) = v130;
      LODWORD(v244[1]) = v131;
      RoVariant::~RoVariant((RoVariant *)v244);
      if ( v21 < 0 )
      {
        v25 = 286;
        goto LABEL_40;
      }
      return 0;
    }
    v84 = v83 - 1;
    if ( !v84 )
    {
      if ( a4 != 8 )
      {
        v19 = 293;
        goto LABEL_36;
      }
      v123 = *(_QWORD *)sourceString;
      v245 = a6;
      v124 = *v15;
      v246 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v124 + 192))(v15, v123, &v246);
      RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
      v125 = v242.lpVtbl;
      v126 = v243;
      v242.lpVtbl = 0;
      v243 = 0;
      RoVariant::~RoVariant((RoVariant *)&v242);
      v127 = *(_DWORD *)(a6 + 8);
      v244[0] = *(struct IInspectable **)a6;
      *(_QWORD *)a6 = v125;
      *(_DWORD *)(a6 + 8) = v126;
      LODWORD(v244[1]) = v127;
      RoVariant::~RoVariant((RoVariant *)v244);
      if ( v21 < 0 )
      {
        v25 = 294;
        goto LABEL_40;
      }
      return 0;
    }
    v85 = v84 - 1;
    if ( v85 )
    {
      v86 = v85 - 1;
      if ( !v86 )
      {
        if ( a4 != 8 )
        {
          v19 = 320;
          goto LABEL_36;
        }
        v110 = *(_QWORD *)sourceString;
        v245 = a6;
        v111 = *v15;
        v246 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v111 + 176))(v15, v110, &v246);
        RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
        v112 = v242.lpVtbl;
        v113 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v114 = *(_DWORD *)(a6 + 8);
        v244[0] = *(struct IInspectable **)a6;
        *(_QWORD *)a6 = v112;
        *(_DWORD *)(a6 + 8) = v113;
        LODWORD(v244[1]) = v114;
        RoVariant::~RoVariant((RoVariant *)v244);
        if ( v21 < 0 )
        {
          v25 = 321;
          goto LABEL_40;
        }
        return 0;
      }
      v87 = v86 - 1;
      if ( !v87 )
      {
        if ( a4 != 1 )
        {
          v19 = 327;
          goto LABEL_36;
        }
        LOBYTE(v11) = *(_BYTE *)sourceString;
        v245 = a6;
        v106 = *v15;
        v246 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v106 + 56))(v15, v11, &v246);
        RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
        v107 = v242.lpVtbl;
        v108 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v109 = *(_DWORD *)(a6 + 8);
        v244[0] = *(struct IInspectable **)a6;
        *(_QWORD *)a6 = v107;
        *(_DWORD *)(a6 + 8) = v108;
        LODWORD(v244[1]) = v109;
        RoVariant::~RoVariant((RoVariant *)v244);
        if ( v21 < 0 )
        {
          v25 = 328;
          goto LABEL_40;
        }
        return 0;
      }
      v88 = v87 - 1;
      if ( !v88 )
      {
        if ( a4 != 2 )
        {
          v19 = 334;
          goto LABEL_36;
        }
        v101 = *(unsigned __int16 *)sourceString;
        v245 = a6;
        v102 = *v15;
        v246 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v102 + 72))(v15, v101, &v246);
        RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
        v103 = v242.lpVtbl;
        v104 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v105 = *(_DWORD *)(a6 + 8);
        v244[0] = *(struct IInspectable **)a6;
        *(_QWORD *)a6 = v103;
        *(_DWORD *)(a6 + 8) = v104;
        LODWORD(v244[1]) = v105;
        RoVariant::~RoVariant((RoVariant *)v244);
        if ( v21 < 0 )
        {
          v25 = 335;
          goto LABEL_40;
        }
        return 0;
      }
      v89 = v88 - 1;
      if ( !v89 )
      {
        if ( a4 != 4 )
        {
          v19 = 341;
          goto LABEL_36;
        }
        v96 = *sourceString;
        v245 = a6;
        v97 = *v15;
        v246 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v97 + 88))(v15, v96, &v246);
        RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
        v98 = v242.lpVtbl;
        v99 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v100 = *(_DWORD *)(a6 + 8);
        v244[0] = *(struct IInspectable **)a6;
        *(_QWORD *)a6 = v98;
        *(_DWORD *)(a6 + 8) = v99;
        LODWORD(v244[1]) = v100;
        RoVariant::~RoVariant((RoVariant *)v244);
        if ( v21 < 0 )
        {
          v25 = 342;
          goto LABEL_40;
        }
        return 0;
      }
      v90 = v89 - 1;
      if ( !v90 )
      {
        if ( a4 != 8 )
        {
          v19 = 348;
          goto LABEL_36;
        }
        v91 = *(_QWORD *)sourceString;
        v245 = a6;
        v92 = *v15;
        v246 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v92 + 104))(v15, v91, &v246);
        RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
        v93 = v242.lpVtbl;
        v94 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v95 = *(_DWORD *)(a6 + 8);
        v244[0] = *(struct IInspectable **)a6;
        *(_QWORD *)a6 = v93;
        *(_DWORD *)(a6 + 8) = v94;
        LODWORD(v244[1]) = v95;
        RoVariant::~RoVariant((RoVariant *)v244);
        if ( v21 < 0 )
        {
          v25 = 349;
          goto LABEL_40;
        }
        return 0;
      }
      if ( v90 != 1 )
        return 2154233861LL;
      return 2147500033LL;
    }
    v115 = 0;
    string = 0;
    if ( a4 )
    {
      v116 = StringCchLengthW((const unsigned __int16 *)sourceString, a4 >> 1, (unsigned __int64 *)&string);
      if ( v116 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
          (const char *)(unsigned int)v116,
          v240);
        v19 = 303;
        goto LABEL_36;
      }
      v115 = (unsigned int)string;
      if ( a4 != 2LL * (_QWORD)string + 2 )
      {
        v19 = 304;
        goto LABEL_36;
      }
    }
    else
    {
      v6 = &dword_18002C434;
    }
    string = 0;
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    v117 = WindowsCreateStringReference(v6, v115, &hstringHeader, &string);
    if ( v117 >= 0 )
    {
      v245 = a6;
      v119 = *v15;
      v246 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, struct IInspectable **))(v119 + 144))(v15, string, &v246);
      RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
      v120 = v242.lpVtbl;
      v121 = v243;
      v242.lpVtbl = 0;
      v243 = 0;
      RoVariant::~RoVariant((RoVariant *)&v242);
      v122 = *(_DWORD *)(a6 + 8);
      v244[0] = *(struct IInspectable **)a6;
      *(_QWORD *)a6 = v120;
      *(_DWORD *)(a6 + 8) = v121;
      LODWORD(v244[1]) = v122;
      RoVariant::~RoVariant((RoVariant *)v244);
      if ( v21 < 0 )
      {
        v25 = 313;
        goto LABEL_40;
      }
      return 0;
    }
    v118 = 312;
    goto LABEL_107;
  }
  if ( a2 == 11 )
  {
    if ( a4 != 16 )
    {
      v19 = 278;
      goto LABEL_36;
    }
    v76 = *(_OWORD *)sourceString;
    v245 = a6;
    v77 = *v15;
    v246 = 0;
    *(_OWORD *)v244 = v76;
    v78 = (*(__int64 (__fastcall **)(__int64 *, struct IInspectable **, struct IInspectable **))(v77 + 200))(
            v15,
            v244,
            &v246);
    v79 = v245;
    v21 = v78;
    RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
    v80 = v242.lpVtbl;
    v81 = v243;
    v242.lpVtbl = 0;
    v243 = 0;
    RoVariant::~RoVariant((RoVariant *)&v242);
    v82 = *(_DWORD *)(v79 + 8);
    v244[0] = *(struct IInspectable **)v79;
    *(_QWORD *)v79 = v80;
    *(_DWORD *)(v79 + 8) = v81;
    LODWORD(v244[1]) = v82;
    RoVariant::~RoVariant((RoVariant *)v244);
    if ( v21 < 0 )
    {
      v25 = 279;
      goto LABEL_40;
    }
    return 0;
  }
  if ( a2 > 6 )
  {
    v53 = a2 - 7;
    if ( v53 )
    {
      v54 = v53 - 1;
      if ( v54 )
      {
        v55 = v54 - 1;
        if ( v55 )
        {
          if ( v55 != 1 )
            return 2154233861LL;
          if ( a4 != 8 )
          {
            v19 = 270;
            goto LABEL_36;
          }
          v56 = *(_QWORD *)sourceString;
          v245 = a6;
          v57 = *v15;
          v246 = 0;
          v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v57 + 184))(v15, v56, &v246);
          RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
          v58 = v242.lpVtbl;
          v59 = v243;
          v242.lpVtbl = 0;
          v243 = 0;
          RoVariant::~RoVariant((RoVariant *)&v242);
          v60 = *(_DWORD *)(a6 + 8);
          v244[0] = *(struct IInspectable **)a6;
          *(_QWORD *)a6 = v58;
          *(_DWORD *)(a6 + 8) = v59;
          LODWORD(v244[1]) = v60;
          RoVariant::~RoVariant((RoVariant *)v244);
          if ( v21 < 0 )
          {
            v25 = 271;
            goto LABEL_40;
          }
        }
        else
        {
          if ( a4 != 8 )
          {
            v19 = 262;
            goto LABEL_36;
          }
          v61 = *(_QWORD *)sourceString;
          v245 = a6;
          v62 = *v15;
          v246 = 0;
          v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v62 + 96))(v15, v61, &v246);
          RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
          v63 = v242.lpVtbl;
          v64 = v243;
          v242.lpVtbl = 0;
          v243 = 0;
          RoVariant::~RoVariant((RoVariant *)&v242);
          v65 = *(_DWORD *)(a6 + 8);
          v244[0] = *(struct IInspectable **)a6;
          *(_QWORD *)a6 = v63;
          *(_DWORD *)(a6 + 8) = v64;
          LODWORD(v244[1]) = v65;
          RoVariant::~RoVariant((RoVariant *)v244);
          if ( v21 < 0 )
          {
            v25 = 263;
            goto LABEL_40;
          }
        }
      }
      else
      {
        if ( a4 != 4 )
        {
          v19 = 255;
          goto LABEL_36;
        }
        v66 = *sourceString;
        v245 = a6;
        v67 = *v15;
        v246 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v67 + 80))(v15, v66, &v246);
        RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
        v68 = v242.lpVtbl;
        v69 = v243;
        v242.lpVtbl = 0;
        v243 = 0;
        RoVariant::~RoVariant((RoVariant *)&v242);
        v70 = *(_DWORD *)(a6 + 8);
        v244[0] = *(struct IInspectable **)a6;
        *(_QWORD *)a6 = v68;
        *(_DWORD *)(a6 + 8) = v69;
        LODWORD(v244[1]) = v70;
        RoVariant::~RoVariant((RoVariant *)v244);
        if ( v21 < 0 )
        {
          v25 = 256;
          goto LABEL_40;
        }
      }
    }
    else
    {
      if ( a4 != 2 )
      {
        v19 = 248;
        goto LABEL_36;
      }
      v71 = *(unsigned __int16 *)sourceString;
      v245 = a6;
      v72 = *v15;
      v246 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v72 + 64))(v15, v71, &v246);
      RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
      v73 = v242.lpVtbl;
      v74 = v243;
      v242.lpVtbl = 0;
      v243 = 0;
      RoVariant::~RoVariant((RoVariant *)&v242);
      v75 = *(_DWORD *)(a6 + 8);
      v244[0] = *(struct IInspectable **)a6;
      *(_QWORD *)a6 = v73;
      *(_DWORD *)(a6 + 8) = v74;
      LODWORD(v244[1]) = v75;
      RoVariant::~RoVariant((RoVariant *)v244);
      if ( v21 < 0 )
      {
        v25 = 249;
        goto LABEL_40;
      }
    }
    return 0;
  }
  if ( a2 == 6 )
  {
    if ( a4 != 16 )
    {
      v19 = 241;
      goto LABEL_36;
    }
    v46 = *(_OWORD *)sourceString;
    v245 = a6;
    v47 = *v15;
    v246 = 0;
    *(_OWORD *)v244 = v46;
    v48 = (*(__int64 (__fastcall **)(__int64 *, struct IInspectable **, struct IInspectable **))(v47 + 160))(
            v15,
            v244,
            &v246);
    v49 = v245;
    v21 = v48;
    RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
    v50 = v242.lpVtbl;
    v51 = v243;
    v242.lpVtbl = 0;
    v243 = 0;
    RoVariant::~RoVariant((RoVariant *)&v242);
    v52 = *(_DWORD *)(v49 + 8);
    v244[0] = *(struct IInspectable **)v49;
    *(_QWORD *)v49 = v50;
    *(_DWORD *)(v49 + 8) = v51;
    LODWORD(v244[1]) = v52;
    RoVariant::~RoVariant((RoVariant *)v244);
    if ( v21 < 0 )
    {
      v25 = 242;
      goto LABEL_40;
    }
    return 0;
  }
  if ( !a2 )
  {
    if ( a4 )
    {
      v19 = 204;
      goto LABEL_36;
    }
    v245 = a6;
    v42 = *v15;
    v246 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, struct IInspectable **))(v42 + 48))(v15, &v246);
    RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
    v43 = v242.lpVtbl;
    v44 = v243;
    v242.lpVtbl = 0;
    v243 = 0;
    RoVariant::~RoVariant((RoVariant *)&v242);
    v45 = *(_DWORD *)(a6 + 8);
    v244[0] = *(struct IInspectable **)a6;
    *(_QWORD *)a6 = v43;
    *(_DWORD *)(a6 + 8) = v44;
    LODWORD(v244[1]) = v45;
    RoVariant::~RoVariant((RoVariant *)v244);
    if ( v21 < 0 )
    {
      v25 = 205;
      goto LABEL_40;
    }
    return 0;
  }
  v16 = a2 - 1;
  if ( !v16 )
  {
    v36 = *(_BYTE *)sourceString;
    if ( *(_BYTE *)sourceString >= 2u )
    {
      v19 = 211;
      goto LABEL_36;
    }
    if ( a4 != 1 )
    {
      v19 = 212;
      goto LABEL_36;
    }
    v245 = a6;
    v37 = *v15;
    LOBYTE(v11) = v36 != 0;
    v246 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v37 + 136))(v15, v11, &v246);
    RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
    v38 = v242.lpVtbl;
    v39 = v243;
    v242.lpVtbl = 0;
    v243 = 0;
    RoVariant::~RoVariant((RoVariant *)&v242);
    v40 = *(_DWORD *)(a6 + 8);
    v244[0] = *(struct IInspectable **)a6;
    *(_QWORD *)a6 = v38;
    *(_DWORD *)(a6 + 8) = v39;
    LODWORD(v244[1]) = v40;
    RoVariant::~RoVariant((RoVariant *)v244);
    if ( v21 < 0 )
    {
      v25 = 213;
      goto LABEL_40;
    }
    return 0;
  }
  v17 = v16 - 2;
  if ( !v17 )
  {
    if ( a4 != 2 )
    {
      v19 = 219;
      goto LABEL_36;
    }
    v31 = *(unsigned __int16 *)sourceString;
    v245 = a6;
    v32 = *v15;
    v246 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v32 + 128))(v15, v31, &v246);
    RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
    v33 = v242.lpVtbl;
    v34 = v243;
    v242.lpVtbl = 0;
    v243 = 0;
    RoVariant::~RoVariant((RoVariant *)&v242);
    v35 = *(_DWORD *)(a6 + 8);
    v244[0] = *(struct IInspectable **)a6;
    *(_QWORD *)a6 = v33;
    *(_DWORD *)(a6 + 8) = v34;
    LODWORD(v244[1]) = v35;
    RoVariant::~RoVariant((RoVariant *)v244);
    if ( v21 < 0 )
    {
      v25 = 220;
      goto LABEL_40;
    }
    return 0;
  }
  v18 = v17 - 1;
  if ( !v18 )
  {
    if ( a4 != 8 )
    {
      v19 = 227;
      goto LABEL_36;
    }
    v26 = *(_QWORD *)sourceString;
    v245 = a6;
    v27 = *v15;
    v246 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v27 + 168))(v15, v26, &v246);
    RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
    v28 = v242.lpVtbl;
    v29 = v243;
    v242.lpVtbl = 0;
    v243 = 0;
    RoVariant::~RoVariant((RoVariant *)&v242);
    v30 = *(_DWORD *)(a6 + 8);
    v244[0] = *(struct IInspectable **)a6;
    *(_QWORD *)a6 = v28;
    *(_DWORD *)(a6 + 8) = v29;
    LODWORD(v244[1]) = v30;
    RoVariant::~RoVariant((RoVariant *)v244);
    if ( v21 < 0 )
    {
      v25 = 228;
      goto LABEL_40;
    }
    return 0;
  }
  if ( v18 == 1 )
  {
    if ( a4 != 8 )
    {
      v19 = 234;
LABEL_36:
      v41 = -2140733435;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)0x80670005LL,
        v240);
      return v41;
    }
    v245 = a6;
    v20 = *v15;
    v246 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(v20 + 120))(v15, v11, &v246);
    RoVariant::RoVariant((RoVariant *)&v242, v246, 1, 1);
    v22 = v242.lpVtbl;
    v23 = v243;
    v242.lpVtbl = 0;
    v243 = 0;
    RoVariant::~RoVariant((RoVariant *)&v242);
    v24 = *(_DWORD *)(a6 + 8);
    v244[0] = *(struct IInspectable **)a6;
    *(_QWORD *)a6 = v22;
    *(_DWORD *)(a6 + 8) = v23;
    LODWORD(v244[1]) = v24;
    RoVariant::~RoVariant((RoVariant *)v244);
    if ( v21 < 0 )
    {
      v25 = 235;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)(unsigned int)v21,
        v240);
      return (unsigned int)v21;
    }
    return 0;
  }
  return 2154233861LL;
}

```

## disassembly

```asm
0x180021718  mov     [rsp-8+arg_8], rbx
0x18002171d  push    rbp
0x18002171e  push    rsi
0x18002171f  push    rdi
0x180021720  push    r12
0x180021722  push    r13
0x180021724  push    r14
0x180021726  push    r15
0x180021728  lea     rbp, [rsp-17h]
0x18002172d  sub     rsp, 90h
0x180021734  mov     rax, cs:__security_cookie
0x18002173b  xor     rax, rsp
0x18002173e  mov     [rbp+47h+var_38], rax
0x180021742  mov     rsi, [rbp+47h+sourceString]
0x180021746  mov     r14, r9
0x180021749  mov     r15d, r8d
0x18002174c  mov     ebx, edx
0x18002174e  mov     r12, rcx
0x180021751  call    ?EnsurePropertyValueStaticsIsAvailable@WinRTReader@DictionarySerialization@StateRepository@@AEAAJXZ; StateRepository::DictionarySerialization::WinRTReader::EnsurePropertyValueStaticsIsAvailable(void)
0x180021756  xor     r13d, r13d
0x180021759  mov     edi, eax
0x18002175b  test    eax, eax
0x18002175d  jns     short loc_18002177E
0x18002175f  mov     edx, 0C6h; void *
0x180021764  mov     rcx, [rbp+4Fh]; this
0x180021768  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x18002176f  mov     r9d, edi; char *
0x180021772  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021777  mov     eax, edi
0x180021779  jmp     loc_18002257A
0x18002177e  mov     r12, [r12]
0x180021782  cmp     ebx, 15h
0x180021785  jg      loc_1800225A1
0x18002178b  jz      loc_18002245A
0x180021791  cmp     ebx, 0Bh
0x180021794  jg      loc_180021EBE
0x18002179a  jz      loc_180021E1E
0x1800217a0  cmp     ebx, 6
0x1800217a3  jg      loc_180021BA8
0x1800217a9  jz      loc_180021B08
0x1800217af  test    ebx, ebx
0x1800217b1  jz      loc_180021A48
0x1800217b7  sub     ebx, 1
0x1800217ba  jz      loc_18002199E
0x1800217c0  sub     ebx, 2
0x1800217c3  jz      loc_180021907
0x1800217c9  sub     ebx, 1
0x1800217cc  jz      loc_180021870
0x1800217d2  cmp     ebx, 1
0x1800217d5  jnz     loc_180022D34
0x1800217db  cmp     r14, 8
0x1800217df  jz      short loc_1800217EB
0x1800217e1  mov     edx, 0EAh
0x1800217e6  jmp     loc_180021A52
0x1800217eb  mov     rax, [rbp+47h+arg_28]
0x1800217ef  lea     r8, [rbp+47h+var_68]
0x1800217f3  movsd   xmm1, qword ptr [rsi]
0x1800217f7  mov     rcx, r12
0x1800217fa  mov     [rbp+47h+var_70], rax
0x1800217fe  mov     rax, [r12]
0x180021802  mov     [rbp+47h+var_68], r13
0x180021806  mov     rax, [rax+78h]
0x18002180a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002180f  mov     rdx, [rbp+47h+var_68]; struct IInspectable *
0x180021813  lea     rcx, [rbp+47h+var_90]; this
0x180021817  mov     rsi, [rbp+47h+var_70]
0x18002181b  mov     r9b, 1; bool
0x18002181e  mov     r8b, r9b; bool
0x180021821  mov     r14d, eax
0x180021824  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x180021829  mov     rbx, [rbp+47h+var_90]
0x18002182d  lea     rcx, [rbp+47h+var_90]; this
0x180021831  mov     edi, [rbp+47h+var_88]
0x180021834  mov     [rbp+47h+var_90], r13
0x180021838  mov     [rbp+47h+var_88], r13d
0x18002183c  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180021841  mov     rcx, [rsi]
0x180021844  mov     eax, [rsi+8]
0x180021847  mov     [rbp+47h+var_80], rcx
0x18002184b  lea     rcx, [rbp+47h+var_80]; this
0x18002184f  mov     [rsi], rbx
0x180021852  mov     [rsi+8], edi
0x180021855  mov     dword ptr [rbp+47h+var_80+8], eax
0x180021858  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18002185d  test    r14d, r14d
0x180021860  jns     loc_180022578
0x180021866  mov     edx, 0EBh
0x18002186b  jmp     loc_180021AED
0x180021870  cmp     r14, 8
0x180021874  jz      short loc_180021880
0x180021876  mov     edx, 0E3h
0x18002187b  jmp     loc_180021A52
0x180021880  mov     rax, [rbp+47h+arg_28]
0x180021884  lea     r8, [rbp+47h+var_68]
0x180021888  mov     rdx, [rsi]
0x18002188b  mov     rcx, r12
0x18002188e  mov     [rbp+47h+var_70], rax
0x180021892  mov     rax, [r12]
0x180021896  mov     [rbp+47h+var_68], r13
0x18002189a  mov     rax, [rax+0A8h]
0x1800218a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218a6  mov     rdx, [rbp+47h+var_68]; struct IInspectable *
0x1800218aa  lea     rcx, [rbp+47h+var_90]; this
0x1800218ae  mov     rsi, [rbp+47h+var_70]
0x1800218b2  mov     r9b, 1; bool
0x1800218b5  mov     r8b, r9b; bool
0x1800218b8  mov     r14d, eax
0x1800218bb  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x1800218c0  mov     rbx, [rbp+47h+var_90]
0x1800218c4  lea     rcx, [rbp+47h+var_90]; this
0x1800218c8  mov     edi, [rbp+47h+var_88]
0x1800218cb  mov     [rbp+47h+var_90], r13
0x1800218cf  mov     [rbp+47h+var_88], r13d
0x1800218d3  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800218d8  mov     rcx, [rsi]
0x1800218db  mov     eax, [rsi+8]
0x1800218de  mov     [rbp+47h+var_80], rcx
0x1800218e2  lea     rcx, [rbp+47h+var_80]; this
0x1800218e6  mov     [rsi], rbx
0x1800218e9  mov     [rsi+8], edi
0x1800218ec  mov     dword ptr [rbp+47h+var_80+8], eax
0x1800218ef  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800218f4  test    r14d, r14d
0x1800218f7  jns     loc_180022578
0x1800218fd  mov     edx, 0E4h
0x180021902  jmp     loc_180021AED
0x180021907  cmp     r14, 2
0x18002190b  jz      short loc_180021917
0x18002190d  mov     edx, 0DBh
0x180021912  jmp     loc_180021A52
0x180021917  mov     rax, [rbp+47h+arg_28]
0x18002191b  lea     r8, [rbp+47h+var_68]
0x18002191f  movzx   edx, word ptr [rsi]
0x180021922  mov     rcx, r12
0x180021925  mov     [rbp+47h+var_70], rax
0x180021929  mov     rax, [r12]
0x18002192d  mov     [rbp+47h+var_68], r13
0x180021931  mov     rax, [rax+80h]
0x180021938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002193d  mov     rdx, [rbp+47h+var_68]; struct IInspectable *
0x180021941  lea     rcx, [rbp+47h+var_90]; this
0x180021945  mov     rsi, [rbp+47h+var_70]
0x180021949  mov     r9b, 1; bool
0x18002194c  mov     r8b, r9b; bool
0x18002194f  mov     r14d, eax
0x180021952  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x180021957  mov     rbx, [rbp+47h+var_90]
0x18002195b  lea     rcx, [rbp+47h+var_90]; this
0x18002195f  mov     edi, [rbp+47h+var_88]
0x180021962  mov     [rbp+47h+var_90], r13
0x180021966  mov     [rbp+47h+var_88], r13d
0x18002196a  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18002196f  mov     rcx, [rsi]
0x180021972  mov     eax, [rsi+8]
0x180021975  mov     [rbp+47h+var_80], rcx
0x180021979  lea     rcx, [rbp+47h+var_80]; this
0x18002197d  mov     [rsi], rbx
0x180021980  mov     [rsi+8], edi
0x180021983  mov     dword ptr [rbp+47h+var_80+8], eax
0x180021986  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18002198b  test    r14d, r14d
0x18002198e  jns     loc_180022578
0x180021994  mov     edx, 0DCh
0x180021999  jmp     loc_180021AED
0x18002199e  mov     cl, [rsi]
0x1800219a0  cmp     cl, 2
0x1800219a3  jb      short loc_1800219AF
0x1800219a5  mov     edx, 0D3h
0x1800219aa  jmp     loc_180021A52
0x1800219af  cmp     r14, 1
0x1800219b3  jz      short loc_1800219BF
0x1800219b5  mov     edx, 0D4h
0x1800219ba  jmp     loc_180021A52
0x1800219bf  mov     rax, [rbp+47h+arg_28]
0x1800219c3  lea     r8, [rbp+47h+var_68]
0x1800219c7  mov     [rbp+47h+var_70], rax
0x1800219cb  test    cl, cl
0x1800219cd  mov     rax, [r12]
0x1800219d1  mov     rcx, r12
0x1800219d4  setnz   dl
0x1800219d7  mov     [rbp+47h+var_68], r13
0x1800219db  mov     rax, [rax+88h]
0x1800219e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219e7  mov     rdx, [rbp+47h+var_68]; struct IInspectable *
0x1800219eb  lea     rcx, [rbp+47h+var_90]; this
0x1800219ef  mov     rsi, [rbp+47h+var_70]
0x1800219f3  mov     r9b, 1; bool
0x1800219f6  mov     r8b, r9b; bool
0x1800219f9  mov     r14d, eax
0x1800219fc  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x180021a01  mov     rbx, [rbp+47h+var_90]
0x180021a05  lea     rcx, [rbp+47h+var_90]; this
0x180021a09  mov     edi, [rbp+47h+var_88]
0x180021a0c  mov     [rbp+47h+var_90], r13
0x180021a10  mov     [rbp+47h+var_88], r13d
0x180021a14  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180021a19  mov     rcx, [rsi]
0x180021a1c  mov     eax, [rsi+8]
0x180021a1f  mov     [rbp+47h+var_80], rcx
0x180021a23  lea     rcx, [rbp+47h+var_80]; this
0x180021a27  mov     [rsi], rbx
0x180021a2a  mov     [rsi+8], edi
0x180021a2d  mov     dword ptr [rbp+47h+var_80+8], eax
0x180021a30  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180021a35  test    r14d, r14d
0x180021a38  jns     loc_180022578
0x180021a3e  mov     edx, 0D5h
0x180021a43  jmp     loc_180021AED
0x180021a48  test    r14, r14
0x180021a4b  jz      short loc_180021A71
0x180021a4d  mov     edx, 0CCh; void *
0x180021a52  mov     rcx, [rbp+4Fh]; this
0x180021a56  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180021a5d  mov     esi, 80670005h
0x180021a62  mov     r9d, esi; char *
0x180021a65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021a6a  mov     eax, esi
0x180021a6c  jmp     loc_18002257A
0x180021a71  mov     rax, [rbp+47h+arg_28]
0x180021a75  lea     rdx, [rbp+47h+var_68]
0x180021a79  mov     [rbp+47h+var_70], rax
0x180021a7d  mov     rcx, r12
0x180021a80  mov     rax, [r12]
0x180021a84  mov     [rbp+47h+var_68], r13
0x180021a88  mov     rax, [rax+30h]
0x180021a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a91  mov     rdx, [rbp+47h+var_68]; struct IInspectable *
0x180021a95  lea     rcx, [rbp+47h+var_90]; this
0x180021a99  mov     rsi, [rbp+47h+var_70]
0x180021a9d  mov     r9b, 1; bool
0x180021aa0  mov     r8b, r9b; bool
0x180021aa3  mov     r14d, eax
0x180021aa6  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x180021aab  mov     rbx, [rbp+47h+var_90]
0x180021aaf  lea     rcx, [rbp+47h+var_90]; this
0x180021ab3  mov     edi, [rbp+47h+var_88]
0x180021ab6  mov     [rbp+47h+var_90], r13
0x180021aba  mov     [rbp+47h+var_88], r13d
0x180021abe  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180021ac3  mov     rcx, [rsi]
0x180021ac6  mov     eax, [rsi+8]
0x180021ac9  mov     [rbp+47h+var_80], rcx
0x180021acd  lea     rcx, [rbp+47h+var_80]; this
0x180021ad1  mov     [rsi], rbx
0x180021ad4  mov     [rsi+8], edi
0x180021ad7  mov     dword ptr [rbp+47h+var_80+8], eax
0x180021ada  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180021adf  test    r14d, r14d
0x180021ae2  jns     loc_180022578
0x180021ae8  mov     edx, 0CDh; void *
0x180021aed  mov     rcx, [rbp+4Fh]; this
0x180021af1  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180021af8  mov     r9d, r14d; char *
0x180021afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b00  mov     eax, r14d
0x180021b03  jmp     loc_18002257A
0x180021b08  cmp     r14, 10h
0x180021b0c  jz      short loc_180021B18
0x180021b0e  mov     edx, 0F1h
0x180021b13  jmp     loc_180021A52
0x180021b18  mov     rax, [rbp+47h+arg_28]
0x180021b1c  lea     r8, [rbp+47h+var_68]
0x180021b20  movups  xmm0, xmmword ptr [rsi]
0x180021b23  mov     [rbp+47h+var_70], rax
0x180021b27  lea     rdx, [rbp+47h+var_80]
0x180021b2b  mov     rax, [r12]
0x180021b2f  mov     rcx, r12
0x180021b32  mov     [rbp+47h+var_68], r13
0x180021b36  movdqu  xmmword ptr [rbp+47h+var_80], xmm0
0x180021b3b  mov     rax, [rax+0A0h]
0x180021b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b47  mov     rdx, [rbp+47h+var_68]; struct IInspectable *
0x180021b4b  lea     rcx, [rbp+47h+var_90]; this
0x180021b4f  mov     rsi, [rbp+47h+var_70]
0x180021b53  mov     r9b, 1; bool
0x180021b56  mov     r8b, r9b; bool
0x180021b59  mov     r14d, eax
0x180021b5c  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x180021b61  mov     rbx, [rbp+47h+var_90]
0x180021b65  lea     rcx, [rbp+47h+var_90]; this
0x180021b69  mov     edi, [rbp+47h+var_88]
0x180021b6c  mov     [rbp+47h+var_90], r13
0x180021b70  mov     [rbp+47h+var_88], r13d
0x180021b74  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180021b79  mov     rcx, [rsi]
0x180021b7c  mov     eax, [rsi+8]
0x180021b7f  mov     [rbp+47h+var_80], rcx
0x180021b83  lea     rcx, [rbp+47h+var_80]; this
0x180021b87  mov     [rsi], rbx
0x180021b8a  mov     [rsi+8], edi
0x180021b8d  mov     dword ptr [rbp+47h+var_80+8], eax
0x180021b90  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180021b95  test    r14d, r14d
0x180021b98  jns     loc_180022578
0x180021b9e  mov     edx, 0F2h
0x180021ba3  jmp     loc_180021AED
0x180021ba8  sub     ebx, 7
0x180021bab  jz      loc_180021D8A
0x180021bb1  sub     ebx, 1
0x180021bb4  jz      loc_180021CF7
  ... truncated ...
```
