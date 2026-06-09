# sqlite3Update

- ea: `0x18002f9a4`
- end: `0x180031187`
- name: `sqlite3Update`
- size: `6115`
- prototype: ``
- caller_count: `3`
- callee_count: `55`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001bc30`
- `0x1800595f8`
- `0x18008c1b4`

## callees

- `0x180006ac0`
- `0x180007a00`
- `0x18000b4bc`
- `0x18000b6a8`
- `0x18000db18`
- `0x180014464`
- `0x180015e80`
- `0x18002e290`
- `0x18002f9a4`
- `0x180031190`
- `0x1800311c0`
- `0x180031964`
- `0x180036430`
- `0x1800369e4`
- `0x180036d74`
- `0x180037774`
- `0x180038974`
- `0x18003b8a0`
- `0x18003be78`
- `0x18003bff4`
- `0x18003c4c4`
- `0x18003c5f4`
- `0x18003ceec`
- `0x18003d480`
- `0x18003da90`
- `0x18003e68c`
- `0x18003f960`
- `0x18004002c`
- `0x1800421bc`
- `0x180042260`
- `0x180042bb0`
- `0x180042c38`
- `0x180045374`
- `0x180078a68`
- `0x18007b620`
- `0x18007bd48`
- `0x18007c408`
- `0x18007c918`
- `0x18007cae0`
- `0x18007f6bc`
- `0x180081030`
- `0x180081cf4`
- `0x180081db4`
- `0x180082788`
- `0x1800828a0`
- `0x1800835c0`
- `0x180085478`
- `0x18008608c`
- `0x180086890`
- `0x18008b7d4`

## string_xrefs

- `0x18002fe41`: `cannot UPDATE generated column "%s"`
- `0x18003110d`: `rows updated`

## pseudocode

```c
__int64 __fastcall sqlite3Update(__int64 *a1, __int64 a2, int *a3, __int64 a4, int a5, char a6, char a7, __int64 a8)
{
  __int64 *v8; // rdi
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // r9
  __int64 v13; // rcx
  int *v14; // rbx
  __int64 v15; // r15
  char v16; // al
  int v17; // r9d
  int v18; // edx
  int v19; // r15d
  bool v20; // zf
  __int64 v21; // r11
  __int64 v22; // rcx
  int v23; // r10d
  int v24; // r8d
  int v25; // edx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rcx
  void *v31; // r15
  int v32; // r15d
  int i; // ecx
  __int64 v34; // rax
  char v35; // r14
  int v36; // r13d
  __int64 v37; // rbx
  char v38; // cl
  int *v39; // r9
  int j; // r14d
  __int64 v41; // r12
  const char *v42; // rcx
  int v43; // r12d
  __int64 v44; // r15
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rbx
  bool v48; // sf
  const char *v49; // r9
  __int64 v50; // rax
  int v51; // eax
  unsigned __int8 v52; // cl
  int v53; // r14d
  __int64 v54; // rdx
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // rbx
  int v58; // r13d
  __int64 v59; // rcx
  int v60; // r14d
  __int64 v61; // rcx
  void *v63; // r15
  __int64 v64; // rcx
  __int64 v65; // rax
  int *v66; // r14
  int v67; // eax
  __int64 v68; // rdx
  int *v69; // rbx
  __int64 v70; // r10
  int v71; // edx
  int v72; // r12d
  __int64 v73; // rax
  int v74; // ecx
  char v75; // al
  int v76; // eax
  unsigned int v77; // ebx
  __int64 v78; // r8
  int v79; // r9d
  int v80; // r13d
  int v81; // r8d
  unsigned int v82; // r12d
  __int16 v83; // ax
  __int64 v84; // rax
  signed __int64 v85; // rbx
  int v86; // r14d
  int v87; // eax
  __int64 *v88; // rcx
  int v89; // ecx
  __int16 v90; // cx
  int v91; // eax
  int v92; // ebx
  int v93; // r14d
  int v94; // eax
  __int64 v95; // rax
  __int64 *v96; // rax
  __int64 *v97; // rcx
  __int64 v98; // rdx
  __int64 v99; // r8
  int v100; // eax
  __int64 v101; // rcx
  unsigned int v102; // r14d
  __int64 v103; // rax
  unsigned int v104; // r12d
  int v105; // r14d
  unsigned int v106; // r15d
  int v107; // r8d
  _BYTE *v108; // rdx
  __int64 v109; // rdx
  __int64 v110; // r15
  int v111; // eax
  int v112; // r15d
  __int64 v113; // r13
  int v114; // r14d
  int v115; // r8d
  int v116; // ebx
  int v117; // r14d
  int v118; // eax
  int v119; // ebx
  int v120; // r14d
  int v121; // r14d
  signed int v122; // ebx
  int v123; // r12d
  int v124; // edx
  int v125; // r14d
  int v126; // ebx
  int v127; // eax
  signed int v128; // r8d
  int v129; // r15d
  unsigned int v130; // ebx
  signed int v131; // r14d
  __int64 v132; // rax
  __int64 v133; // rcx
  __int16 v134; // ax
  int v135; // r15d
  unsigned int v136; // ecx
  int v137; // ebx
  unsigned int v138; // r14d
  __int64 v139; // rax
  unsigned int v140; // eax
  int v141; // eax
  int v142; // ebx
  int v143; // eax
  unsigned int v144; // r14d
  __int64 v145; // rdi
  int v147; // [rsp+28h] [rbp-E0h]
  char v148; // [rsp+78h] [rbp-90h]
  char v149; // [rsp+78h] [rbp-90h]
  int v150; // [rsp+7Ch] [rbp-8Ch]
  char v151; // [rsp+80h] [rbp-88h]
  int v152; // [rsp+84h] [rbp-84h]
  int v153; // [rsp+88h] [rbp-80h]
  int v154; // [rsp+8Ch] [rbp-7Ch]
  int v155; // [rsp+90h] [rbp-78h]
  int v156; // [rsp+94h] [rbp-74h]
  int v157; // [rsp+98h] [rbp-70h]
  unsigned int v158; // [rsp+9Ch] [rbp-6Ch]
  unsigned int v159; // [rsp+9Ch] [rbp-6Ch]
  int v160; // [rsp+9Ch] [rbp-6Ch]
  int v161; // [rsp+A0h] [rbp-68h]
  unsigned int v162; // [rsp+A0h] [rbp-68h]
  __int64 Vdbe; // [rsp+A8h] [rbp-60h]
  unsigned int v164; // [rsp+B0h] [rbp-58h]
  unsigned int v165; // [rsp+B4h] [rbp-54h]
  __int64 v166; // [rsp+B8h] [rbp-50h]
  int v167; // [rsp+C0h] [rbp-48h]
  __int64 v168; // [rsp+C8h] [rbp-40h]
  __int16 v169; // [rsp+D0h] [rbp-38h]
  unsigned int v170; // [rsp+D4h] [rbp-34h]
  int v171; // [rsp+D8h] [rbp-30h] BYREF
  int v172; // [rsp+DCh] [rbp-2Ch]
  int v173; // [rsp+E0h] [rbp-28h]
  int v174; // [rsp+E4h] [rbp-24h]
  __int64 v175; // [rsp+E8h] [rbp-20h]
  __int64 v176; // [rsp+F0h] [rbp-18h]
  int v177; // [rsp+F8h] [rbp-10h]
  __int64 v178; // [rsp+100h] [rbp-8h]
  int v179; // [rsp+108h] [rbp+0h] BYREF
  int v180; // [rsp+10Ch] [rbp+4h]
  size_t Size; // [rsp+110h] [rbp+8h] BYREF
  void *v182; // [rsp+118h] [rbp+10h]
  __int64 v183; // [rsp+120h] [rbp+18h]
  int v184; // [rsp+128h] [rbp+20h]
  int v185; // [rsp+12Ch] [rbp+24h]
  int v186; // [rsp+130h] [rbp+28h]
  __int64 v187; // [rsp+138h] [rbp+30h]
  size_t v188; // [rsp+140h] [rbp+38h] BYREF
  __int64 *v189; // [rsp+148h] [rbp+40h]
  __int64 v190; // [rsp+150h] [rbp+48h]
  __int64 v191; // [rsp+158h] [rbp+50h]
  _OWORD v192[7]; // [rsp+160h] [rbp+58h] BYREF
  char v197; // [rsp+210h] [rbp+108h]
  char v198; // [rsp+218h] [rbp+110h]

  v8 = a1;
  v179 = 0;
  v9 = 0;
  v171 = 0;
  v187 = *a1;
  memset(v192, 0, 56);
  if ( *((_DWORD *)a1 + 12) )
    goto LABEL_336;
  v10 = sqlite3SrcListLookup(a1, a2);
  v176 = v10;
  v11 = v10;
  if ( !v10 )
    goto LABEL_336;
  if ( ((v158 = sqlite3SchemaToIndex(*v8, *(_QWORD *)(v10 + 96)), *(_QWORD *)(v11 + 88))
     || (v13 = *(_QWORD *)(*(_QWORD *)(v12 + 32) + 56LL)) != 0 && *(_QWORD *)(v13 + 64))
    && !*((_BYTE *)v8 + 229) )
  {
    v14 = a3;
    v15 = triggersReallyExist((_DWORD)v8, v11, 129, (_DWORD)a3, (__int64)&v179);
  }
  else
  {
    v14 = a3;
    v15 = 0;
  }
  v16 = *(_BYTE *)(v11 + 63);
  v175 = v15;
  v198 = v16;
  v152 = *(int *)a2 <= 1 ? 0 : *v14;
  if ( (unsigned int)sqlite3ViewGetColumnNames(v8, v11) || (unsigned int)sqlite3IsReadOnly(v8, v11, v15) )
    goto LABEL_336;
  v17 = *((_DWORD *)v8 + 13);
  v18 = v17;
  v150 = v17;
  v172 = v17;
  v19 = v17 + 1;
  *((_DWORD *)v8 + 13) = v17 + 1;
  v20 = *(_BYTE *)(v11 + 48) >= 0;
  v174 = v17 + 1;
  if ( v20 )
    v21 = 0;
  else
    v21 = sqlite3PrimaryKeyIndex(v11);
  v22 = *(_QWORD *)(v11 + 16);
  v23 = 0;
  v168 = v21;
  v184 = 0;
  if ( v22 )
  {
    v24 = v19;
    v25 = v19;
    do
    {
      v26 = v25;
      if ( v21 != v22 )
      {
        v25 = v24;
        v26 = v17;
      }
      ++v23;
      v17 = v26;
      v24 = v25 + 1;
      *((_DWORD *)v8 + 13) = ++v25;
      v22 = *(_QWORD *)(v22 + 40);
    }
    while ( v22 );
    v18 = v172;
    v184 = v23;
    v150 = v26;
  }
  if ( a8 )
  {
    v17 = *(_DWORD *)(a8 + 76);
    v150 = v17;
    v174 = *(_DWORD *)(a8 + 80);
    *((_DWORD *)v8 + 13) = v18;
  }
  v27 = v187;
  *(_DWORD *)(a2 + 76) = v17;
  v28 = v23;
  v29 = sqlite3DbMallocRawNN(v27, v23 + 4LL * (v23 + *(__int16 *)(v11 + 54) + 1) + 2);
  v166 = v29;
  v9 = v29;
  if ( !v29 )
    goto LABEL_336;
  v30 = *(__int16 *)(v11 + 54);
  Size = v28 + 1;
  v183 = v29 + 4 * v30;
  v31 = (void *)(v183 + 4 + 4 * v28);
  v182 = v31;
  memset_0(v31, 1, v28 + 1);
  *((_BYTE *)v31 + v28 + 1) = 0;
  v32 = 0;
  for ( i = 0; i < *(__int16 *)(v11 + 54); *(_DWORD *)(v9 + 4 * v34) = -1 )
    v34 = i++;
  *((_QWORD *)&v192[0] + 1) = a2;
  *(_OWORD *)((char *)&v192[1] + 8) = 0;
  *(_QWORD *)((char *)&v192[2] + 12) = 0;
  DWORD1(v192[3]) = 0;
  *(_QWORD *)&v192[0] = v8;
  *(_QWORD *)&v192[1] = a8;
  DWORD2(v192[2]) = 512;
  Vdbe = sqlite3GetVdbe(v8);
  if ( !Vdbe )
    goto LABEL_336;
  v178 = 0;
  v35 = 0;
  v167 = -1;
  v36 = 0;
  v151 = 0;
  v197 = 0;
  while ( 1 )
  {
    if ( v36 >= *a3 )
    {
      v190 = 0;
      v52 = v151 + v35;
      v20 = (*(_BYTE *)(v11 + 48) & 0x60) == 0;
      v189 = 0;
      v155 = 0;
      v164 = 0;
      v170 = 0;
      v185 = 0;
      v161 = 0;
      v149 = v151 + v35;
      if ( !v20 )
      {
        do
        {
          v53 = 0;
          if ( *(__int16 *)(v11 + 54) <= 0 )
            break;
          do
          {
            if ( *(int *)(v166 + 4LL * v53) < 0 )
            {
              v54 = *(_QWORD *)(v11 + 8) + 24LL * v53;
              if ( (*(_BYTE *)(v54 + 18) & 0x60) != 0 )
              {
                v55 = sqlite3ColumnExpr(v11, v54);
                if ( (unsigned int)sqlite3ExprReferencesUpdatedColumn(v55, v166) )
                {
                  *(_DWORD *)(v166 + 4LL * v53) = 99999;
                  v32 = 1;
                }
              }
            }
            ++v53;
          }
          while ( v53 < *(__int16 *)(v11 + 54) );
          v20 = v32 == 0;
          v32 = 0;
        }
        while ( !v20 );
        v32 = 0;
        v52 = v149;
      }
      *(_QWORD *)(a2 + 88) = (*(_BYTE *)(v11 + 63) != 1) - 1LL;
      v180 = v52;
      v56 = sqlite3FkRequired(v8, v11, v166, v52);
      v157 = v56;
      if ( a5 == 5 )
        v171 = 1;
      v57 = *(_QWORD *)(v11 + 16);
      v58 = 0;
      if ( v57 )
      {
        while ( 1 )
        {
          if ( v149
            || v56 > 1
            || v57 == v168
            || (v59 = *(_QWORD *)(v57 + 72)) != 0 && (unsigned int)sqlite3ExprReferencesUpdatedColumn(v59, v166) )
          {
            v60 = ++*((_DWORD *)v8 + 14);
            *((_DWORD *)v8 + 14) = v60 + *(unsigned __int16 *)(v57 + 96);
          }
          else
          {
            v60 = 0;
            while ( 1 )
            {
              if ( v32 >= *(unsigned __int16 *)(v57 + 94) )
                goto LABEL_93;
              v61 = *(__int16 *)(*(_QWORD *)(v57 + 8) + 2LL * v32);
              if ( (v61 & 0x8000u) != 0LL
                 ? sqlite3ExprReferencesUpdatedColumn(*(_QWORD *)(32LL * v32 + *(_QWORD *)(v57 + 80) + 8), v166)
                 : *(_DWORD *)(v166 + 4 * v61) >= 0 )
              {
                break;
              }
              ++v32;
            }
            v60 = ++*((_DWORD *)v8 + 14);
            *((_DWORD *)v8 + 14) = v60 + *(unsigned __int16 *)(v57 + 96);
            if ( a5 == 11 && *(_BYTE *)(v57 + 98) == 5 )
              v171 = 1;
          }
          if ( v60 )
          {
            v63 = v182;
          }
          else
          {
LABEL_93:
            v63 = v182;
            *((_BYTE *)v182 + v58 + 1) = 0;
          }
          v64 = v183;
          v65 = v58++;
          *(_DWORD *)(v183 + 4 * v65) = v60;
          v57 = *(_QWORD *)(v57 + 40);
          v56 = v157;
          if ( !v57 )
            break;
          v32 = 0;
        }
        v11 = v176;
      }
      else
      {
        v63 = v182;
        v64 = v183;
      }
      v66 = (int *)(v8 + 7);
      v67 = ++*((_DWORD *)v8 + 14);
      v191 = v58;
      *(_DWORD *)(v64 + 4LL * v58) = v67;
      if ( v171 )
        memset_0(v63, 1, Size);
      if ( !*((_BYTE *)v8 + 30) )
      {
        *(_DWORD *)(Vdbe + 200) |= 0x10u;
        v66 = (int *)(v8 + 7);
      }
      if ( v175 )
      {
        v69 = v66;
      }
      else
      {
        if ( !v157 )
        {
          v68 = 0;
          v69 = v66;
          goto LABEL_108;
        }
        v69 = (int *)(v8 + 7);
      }
      v68 = 1;
LABEL_108:
      sqlite3BeginWriteOperation(v8, v68, v158);
      v70 = 0;
      if ( *(_BYTE *)(v11 + 63) == 1 )
      {
        v72 = 0;
        goto LABEL_121;
      }
      v71 = *((_DWORD *)v8 + 14) + 1;
      v155 = v71;
      v72 = *(_DWORD *)(v183 + 4LL * v58);
      v161 = v72;
      *v66 = v71;
      if ( v151 )
      {
        v69 = v66;
      }
      else
      {
        v73 = v175;
        if ( !v175 && !v157 )
        {
          v74 = v71;
          goto LABEL_115;
        }
      }
      v74 = v71 + *(__int16 *)(v11 + 54);
      v185 = v71 + 1;
      v73 = v175;
      *v69 = v74;
LABEL_115:
      if ( v149 || v73 || v157 )
      {
        v71 = v74 + 1;
        *v69 = ++v74;
      }
      v164 = v71;
      v170 = v74 + 1;
      *v69 = v74 + *(__int16 *)(v11 + 54);
LABEL_121:
      v75 = v198;
      if ( v198 == 2 )
      {
        v190 = v8[47];
        v8[47] = *(_QWORD *)v11;
        v75 = 2;
        v189 = v8;
      }
      if ( !v152 )
      {
        if ( v75 == 2 )
          sqlite3MaterializeView((_DWORD)v8, v11, a4, 0, 0, v150);
        v76 = sqlite3ResolveExprNames(v192, a4);
        v70 = 0;
        if ( v76 )
          goto LABEL_333;
      }
      if ( *(_BYTE *)(v11 + 63) == 1 )
      {
        updateVirtualTable((_DWORD)v8, a2, v11, (_DWORD)a3, v178, v166, a4, a5);
        goto LABEL_333;
      }
      v77 = --*((_DWORD *)v8 + 17);
      v78 = a8;
      v186 = 0;
      v165 = v77;
      if ( (*(_QWORD *)(v187 + 48) & 0x100000000LL) != 0
        && !v8[23]
        && !*((_BYTE *)v8 + 30)
        && !*((_BYTE *)v8 + 227)
        && !a8 )
      {
        v79 = *((_DWORD *)v8 + 14) + 1;
        v186 = v79;
        *((_DWORD *)v8 + 14) = v79;
        sqlite3VdbeAddOp3(Vdbe, 71, 0, v79, 0);
        v78 = 0;
        v70 = 0;
      }
      if ( !v152 && *(char *)(v11 + 48) >= 0 )
      {
        v169 = 0;
        v156 = 0;
        v80 = 0;
        sqlite3VdbeAddOp3(Vdbe, 75, 0, v72, v155);
        v81 = *((_DWORD *)v8 + 13);
        v153 = v81;
        *((_DWORD *)v8 + 13) = v81 + 1;
        v159 = sqlite3VdbeAddOp3(Vdbe, 118, v81, 0, v72);
        v82 = v159;
        if ( !a8 )
          goto LABEL_138;
LABEL_176:
        v86 = 1;
        v176 = 0;
        v154 = 1;
        sqlite3ExprIfFalse(v8, a4, v77, 16);
        LODWORD(v85) = Size;
        v70 = 0;
        v177 = 0;
        v188 = Size;
        goto LABEL_177;
      }
      if ( v168 )
        v90 = *(_WORD *)(v168 + 94);
      else
        v90 = 0;
      v169 = v90;
      v80 = *((_DWORD *)v8 + 14) + 1;
      v156 = v152 + v90 + v80;
      *((_DWORD *)v8 + 14) = v156;
      if ( v78 )
      {
        v153 = 0;
        if ( !v152 )
        {
          v82 = 0;
          v159 = 0;
          goto LABEL_176;
        }
      }
      else
      {
        if ( v198 == 2 )
          v91 = *(__int16 *)(v11 + 54);
        else
          v91 = 0;
        v92 = v152 + v90 + v91;
        v93 = *((_DWORD *)v8 + 13);
        v153 = v93;
        *((_DWORD *)v8 + 13) = v93 + 1;
        if ( v168 )
          sqlite3VdbeAddOp3(Vdbe, 75, 0, v80, v90 + v80 - 1);
        v82 = sqlite3VdbeAddOp3(Vdbe, 118, v93, v92, 0);
        v159 = v82;
        v94 = v168;
        if ( v168 )
        {
          v95 = sqlite3KeyInfoOfIndex(v8, v168);
          if ( v95 )
          {
            *(_WORD *)(v95 + 8) = v92;
            sqlite3VdbeAppendP4(Vdbe, v95, 4294967288LL);
          }
          v94 = v168;
        }
        if ( !v152 )
        {
LABEL_138:
          v83 = 4;
          if ( !*((_BYTE *)v8 + 30)
            && !v175
            && !v157
            && !v149
            && !v171
            && (!a4 || (*(_DWORD *)(a4 + 4) & 0x400000) == 0) )
          {
            v83 = 12;
          }
          v84 = sqlite3WhereBegin((_DWORD)v8, a2, a4, 0, 0, 0, v83, v174);
          v70 = 0;
          v176 = v84;
          if ( !v84 )
            goto LABEL_333;
          v85 = *(_QWORD *)(v84 + 40);
          v86 = *(unsigned __int8 *)(v84 + 66);
          v87 = *(_DWORD *)(v84 + 68) & 1;
          v188 = v85;
          Size = v85;
          v154 = v86;
          v177 = v87;
          if ( v86 != 1 )
          {
            v88 = v8;
            if ( v8[22] )
              v88 = (__int64 *)v8[22];
            *((_BYTE *)v88 + 32) = 1;
            v89 = v150;
            if ( v86 == 2 && v85 >= 0 && HIDWORD(v85) != v150 && *((_BYTE *)v182 + HIDWORD(v85) - v172) )
            {
              v86 = 0;
              v154 = 0;
            }
LABEL_178:
            v20 = *(_BYTE *)(v11 + 48) >= 0;
            v173 = 0;
            if ( v20 )
            {
              sqlite3VdbeAddOp3(Vdbe, 135, v89, v155, 0);
              v70 = 0;
              if ( v86 )
              {
                if ( !v82 )
                {
LABEL_192:
                  v98 = v176;
                  goto LABEL_193;
                }
                sqlite3VdbeChangeToNoop(Vdbe, v82);
              }
              else
              {
                v99 = v183;
                v100 = *((_DWORD *)v8 + 14) + 1;
                v101 = v191;
                *((_DWORD *)v8 + 14) = v100;
                *(_DWORD *)(v99 + 4 * v101) = v100;
                sqlite3VdbeAddOp3(Vdbe, 128, v153, v161, v155);
              }
            }
            else
            {
              v102 = 0;
              if ( v169 > 0 )
              {
                do
                {
                  sqlite3ExprCodeGetColumnOfTable(
                    Vdbe,
                    v11,
                    v150,
                    *(__int16 *)(*(_QWORD *)(v168 + 8) + 2LL * v102),
                    v102 + v80);
                  ++v102;
                }
                while ( (int)v102 < v169 );
                LODWORD(v85) = v188;
                v70 = 0;
                v8 = a1;
                v82 = v159;
              }
              v86 = v154;
              if ( v154 )
              {
                if ( v82 )
                {
                  sqlite3VdbeChangeToNoop(Vdbe, v82);
                  v70 = 0;
                }
                v173 = v169;
                v156 = v80;
                goto LABEL_192;
              }
              v103 = sqlite3IndexAffinityStr(v187, v168);
              sqlite3VdbeAddOp4(Vdbe, 97, v80, v169, v156, v103, v169);
              sqlite3VdbeAddOp4Int(Vdbe, 138, v153, v156, v80, v169);
            }
            v70 = 0;
            goto LABEL_192;
          }
LABEL_177:
          v89 = v150;
          goto LABEL_178;
        }
        updateFromSelect((_DWORD)v8, v93, v94, (_DWORD)a3, a2, a4);
        v70 = 0;
        if ( v198 == 2 )
          v150 = v93;
      }
      v96 = (__int64 *)v8[22];
      v97 = v8;
      LODWORD(v85) = Size;
      v98 = 0;
      v177 = 1;
      if ( v96 )
        v97 = v96;
      v176 = 0;
      v86 = 0;
      v154 = 0;
      v173 = v169;
      *((_BYTE *)v97 + 32) = 1;
      v156 = v80;
LABEL_193:
      v104 = v165;
      v162 = v165;
      v160 = 0;
      if ( a8 )
      {
        v113 = Vdbe;
        v112 = v150;
LABEL_234:
        v116 = v153;
        goto LABEL_235;
      }
      if ( !v152 && v86 != 2 )
      {
        sqlite3WhereEnd(v98);
        v70 = 0;
      }
      v105 = HIDWORD(Size);
      if ( v198 == 2 )
        goto LABEL_208;
      v106 = 0;
      LODWORD(Size) = 0;
      LODWORD(v188) = 0;
      if ( v154 )
      {
        v107 = v172;
        v108 = v182;
        if ( (int)v85 >= 0 )
          *((_BYTE *)v182 + (int)v85 - v172) = 0;
        if ( v105 >= 0 )
          v108[v105 - v107] = 0;
        if ( v154 == 2 && v184 - (v105 >= 0) > 0 )
          v106 = sqlite3VdbeAddOp3(Vdbe, 15, 0, 0, 0);
      }
      sqlite3OpenTableAndIndices((_DWORD)v8, v11, 113, 0, v172, (__int64)v182, (__int64)&Size, (__int64)&v188);
      v70 = 0;
      if ( !v106 )
      {
LABEL_208:
        v110 = Vdbe;
      }
      else
      {
        v109 = v106;
        v110 = Vdbe;
        sqlite3VdbeJumpHereOrPopInst(Vdbe, v109);
      }
      v111 = v154;
      if ( v154 )
      {
        v112 = v150;
        v113 = Vdbe;
        if ( (_DWORD)v85 == v150 )
        {
          v114 = v156;
        }
        else
        {
          v20 = v105 == v150;
          v114 = v156;
          if ( !v20 )
          {
            sqlite3VdbeAddOp4Int(Vdbe, 28, v150, v165, v156, v173);
            v111 = v154;
            v70 = 0;
          }
        }
        if ( v111 != 1 )
        {
          v104 = *((_DWORD *)v8 + 17) - 1;
          v162 = v104;
          *((_DWORD *)v8 + 17) = v104;
        }
        v115 = v155;
        if ( v168 != v70 )
          v115 = v114;
        sqlite3VdbeAddOp3(Vdbe, 50, v115, v165, v70);
        goto LABEL_234;
      }
      if ( v168 || v152 != (_DWORD)v70 )
      {
        v116 = v153;
        v104 = *((_DWORD *)v8 + 17) - 1;
        v162 = v104;
        *((_DWORD *)v8 + 17) = v104;
        sqlite3VdbeAddOp3(v110, 36, v153, v165, v70);
        v160 = *(_DWORD *)(v110 + 144);
        v118 = v152;
        if ( !v152 )
        {
          v113 = Vdbe;
          sqlite3VdbeAddOp3(Vdbe, 134, v153, v156, 0);
          v112 = v150;
          sqlite3VdbeAddOp4Int(Vdbe, 28, v150, v104, v156, 0);
          goto LABEL_235;
        }
        if ( v198 == 2 )
        {
          v113 = Vdbe;
          v112 = v150;
          goto LABEL_236;
        }
        if ( v168 )
        {
          v119 = 0;
          if ( v169 > 0 )
          {
            do
            {
              sqlite3VdbeAddOp3(v110, 94, v153, v119, v119 + v80);
              ++v119;
            }
            while ( v119 < v169 );
            v8 = a1;
          }
          v112 = v150;
          v147 = v80;
          v113 = Vdbe;
          sqlite3VdbeAddOp4Int(Vdbe, 28, v150, v104, v147, v169);
          goto LABEL_234;
        }
        v113 = Vdbe;
        v117 = v155;
        sqlite3VdbeAddOp3(Vdbe, 135, v153, v155, 0);
      }
      else
      {
        v113 = Vdbe;
        v116 = v153;
        sqlite3VdbeAddOp3(Vdbe, 36, v153, v165, v70);
        v104 = *((_DWORD *)v8 + 17) - 1;
        v117 = v155;
        v162 = v104;
        *((_DWORD *)v8 + 17) = v104;
        v160 = sqlite3VdbeAddOp3(Vdbe, 135, v153, v155, 0);
      }
      v112 = v150;
      sqlite3VdbeAddOp3(v113, 31, v150, v104, v117);
LABEL_235:
      v118 = v152;
LABEL_236:
      if ( v197 )
      {
        if ( v118 )
          sqlite3VdbeAddOp3(v113, 94, v116, v167, v164);
        else
          sqlite3ExprCode(v8, v178, v164);
        sqlite3VdbeAddOp3(v113, 13, v164, 0, 0);
      }
      if ( !v151 )
      {
        if ( v157 )
          goto LABEL_245;
        if ( !v175 )
        {
LABEL_260:
          v125 = a5;
          v126 = (int)a3;
          v127 = sqlite3TriggerColmask((_DWORD)v8, v175, (_DWORD)a3, 1, 1, v11, a5);
          LOWORD(v128) = *(_WORD *)(v11 + 54);
          v129 = v127;
          if ( (__int16)v128 <= 0 )
            goto LABEL_279;
          v130 = v170;
          v131 = 0;
          while ( 1 )
          {
            if ( v131 == *(__int16 *)(v11 + 52) )
              goto LABEL_275;
            v132 = *(_QWORD *)(v11 + 8);
            if ( (*(_BYTE *)(v132 + 24LL * v131 + 18) & 0x60) != 0 )
            {
              if ( (*(_BYTE *)(v132 + 24LL * v131 + 18) & 0x20) != 0 )
                --v130;
              goto LABEL_277;
            }
            v133 = *(int *)(v166 + 4LL * v131);
            if ( (int)v133 >= 0 )
            {
              if ( v152 )
              {
                v134 = v169;
                if ( v198 == 2 )
                  v134 = v128;
                sqlite3VdbeAddOp3(v113, 94, v153, v133 + v134, v130);
              }
              else
              {
                sqlite3ExprCode(v8, *(_QWORD *)&a3[8 * v133 + 2], v130);
              }
              goto LABEL_277;
            }
            if ( (v179 & 1) != 0 && v131 <= 31 && !_bittest(&v129, v131) )
            {
LABEL_275:
              sqlite3VdbeAddOp3(v113, 75, 0, v130, 0);
            }
            else
            {
              sqlite3ExprCodeGetColumnOfTable(v113, v11, v150, v131, v130);
              v177 = 0;
            }
LABEL_277:
            v128 = *(__int16 *)(v11 + 54);
            ++v131;
            ++v130;
            if ( v131 >= v128 )
            {
              v104 = v162;
              v126 = (int)a3;
              v125 = a5;
LABEL_279:
              if ( (*(_BYTE *)(v11 + 48) & 0x60) != 0 )
                sqlite3ComputeGeneratedColumns(v8, v170, v11);
              if ( (v179 & 1) != 0 )
              {
                sqlite3TableAffinity(v113, v11, v170);
                v135 = v155;
                sqlite3CodeRowTrigger((_DWORD)v8, v175, 129, v126, 1, v11, v155, v125, v104);
                if ( v198 != 2 )
                {
                  if ( v168 )
                    sqlite3VdbeAddOp4Int(v113, 28, v150, v104, v156, v173);
                  else
                    sqlite3VdbeAddOp3(v113, 31, v150, v104, v155);
                  v136 = v170;
                  v137 = 0;
                  v138 = v170;
                  if ( *(__int16 *)(v11 + 54) > 0 )
                  {
                    do
                    {
                      v139 = *(_QWORD *)(v11 + 8);
                      if ( (*(_BYTE *)(v139 + 24LL * v137 + 18) & 0x60) != 0 )
                      {
                        v20 = (*(_BYTE *)(v139 + 24LL * v137 + 18) & 0x20) == 0;
                        v140 = v138 - 1;
                        if ( v20 )
                          v140 = v138;
                        v138 = v140;
                      }
                      else if ( *(int *)(v166 + 4LL * v137) < 0 && v137 != *(__int16 *)(v11 + 52) )
                      {
                        sqlite3ExprCodeGetColumnOfTable(v113, v11, v150, v137, v138);
                      }
                      ++v137;
                      ++v138;
                    }
                    while ( v137 < *(__int16 *)(v11 + 54) );
                    v8 = a1;
                    v136 = v170;
                  }
                  if ( (*(_BYTE *)(v11 + 48) & 0x60) != 0 )
                    sqlite3ComputeGeneratedColumns(v8, v136, v11);
LABEL_299:
                  v135 = v155;
                  sqlite3GenerateConstraintChecks(
                    (_DWORD)v8,
                    v11,
                    v183,
                    v150,
                    v174,
                    v164,
                    v155,
                    v149,
                    a5,
                    v104,
                    (__int64)&v171,
                    v166,
                    0);
                  if ( v171 || v149 )
                  {
                    if ( v168 )
                      sqlite3VdbeAddOp4Int(v113, 28, v150, v104, v156, v173);
                    else
                      sqlite3VdbeAddOp3(v113, 31, v150, v104, v155);
                  }
                  if ( v157 )
                    sqlite3FkCheck((_DWORD)v8, v11, v155, 0, v166, v180);
                  sqlite3GenerateRowIndexDelete((_DWORD)v8, v11, v150, v174, v183, -1);
                  if ( v177 )
                    sqlite3VdbeAddOp3(v113, 143, v150, 0, 0);
                  v141 = v157;
                  if ( v157 > 1 || v149 )
                  {
                    sqlite3VdbeAddOp3(v113, 130, v150, 0, 0);
                    v141 = v157;
                  }
                  if ( v141 )
                    sqlite3FkCheck((_DWORD)v8, v11, 0, v164, v166, v180);
                  v142 = v154;
                  v143 = 6;
                  if ( v154 != 2 )
                    v143 = 4;
                  sqlite3CompleteInsertion((_DWORD)v8, v11, v150, v174, v164, v183, v143, 0, 0);
                  if ( v157 )
                    sqlite3FkActions((_DWORD)v8, v11, (_DWORD)a3, v155, v166, v180);
LABEL_319:
                  v144 = v186;
                  if ( v186 )
                    sqlite3VdbeAddOp3(v113, 86, v186, 1, 0);
                  if ( v175 )
                    sqlite3CodeRowTrigger((_DWORD)v8, v175, 129, (_DWORD)a3, 2, v11, v135, a5, v104);
                  if ( v142 != 1 )
                  {
                    sqlite3VdbeResolveLabel(v113, v104);
                    if ( v142 == 2 )
                      sqlite3WhereEnd(v176);
                    else
                      sqlite3VdbeAddOp3(v113, 39, v153, v160, 0);
                  }
                  sqlite3VdbeResolveLabel(v113, v165);
                  if ( !*((_BYTE *)v8 + 30) && !v8[23] && !a8 )
                    sqlite3AutoincrementEnd(v8);
                  if ( v144 )
                    sqlite3CodeChangeCount(v113, v144, "rows updated");
LABEL_333:
                  if ( v189 )
                    v189[47] = v190;
                  goto LABEL_335;
                }
              }
              else
              {
                if ( v198 != 2 )
                  goto LABEL_299;
                v135 = v155;
              }
              v142 = v154;
              goto LABEL_319;
            }
          }
        }
      }
      if ( !v157 )
      {
        v120 = 0;
        goto LABEL_247;
      }
LABEL_245:
      v120 = sqlite3FkOldmask(v8, v11);
LABEL_247:
      v121 = sqlite3TriggerColmask((_DWORD)v8, v175, (_DWORD)a3, 0, 3, v11, a5) | v120;
      v122 = 0;
      if ( *(__int16 *)(v11 + 54) > 0 )
      {
        v123 = v185;
        do
        {
          v124 = v123 + (__int16)sqlite3TableColumnToStorage(v11, (unsigned __int16)v122);
          if ( v121 == -1
            || v122 < 32 && _bittest(&v121, v122)
            || (*(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL * v122 + 18) & 1) != 0 )
          {
            sqlite3ExprCodeGetColumnOfTable(v113, v11, v112, v122, v124);
          }
          else
          {
            sqlite3VdbeAddOp3(v113, 75, 0, v124, 0);
          }
          ++v122;
        }
        while ( v122 < *(__int16 *)(v11 + 54) );
        v8 = a1;
        v104 = v162;
      }
      if ( !v197 && !v168 )
        sqlite3VdbeAddOp3(v113, 80, v155, v164, 0);
      goto LABEL_260;
    }
    v37 = 8LL * v36;
    v38 = sqlite3StrIHash(*(_QWORD *)&a3[v37 + 4]);
    v148 = v38;
    if ( !v152 )
    {
      if ( (unsigned int)sqlite3ResolveExprNames(v192, *(_QWORD *)&v39[v37 + 2]) )
        goto LABEL_335;
      v38 = v148;
      v39 = a3;
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= *(__int16 *)(v11 + 54) )
      {
        v44 = v178;
        v43 = v167;
        goto LABEL_49;
      }
      v41 = *(_QWORD *)(v11 + 8);
      if ( *(_BYTE *)(v41 + 24LL * j + 14) == v38 )
        break;
LABEL_39:
      v39 = a3;
    }
    if ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v41 + 24LL * j), *(_QWORD *)&v39[v37 + 4]) )
    {
      v38 = v148;
      goto LABEL_39;
    }
    if ( j == *(__int16 *)(v11 + 52) )
    {
      v43 = v36;
      v197 = 1;
      v44 = *(_QWORD *)&a3[v37 + 2];
    }
    else
    {
      if ( v168 && (*(_BYTE *)(v41 + 24LL * j + 18) & 1) != 0 )
      {
        v151 = 1;
      }
      else if ( (*(_BYTE *)(v41 + 24LL * j + 18) & 0x60) != 0 )
      {
        sqlite3ErrorMsg(v8, "cannot UPDATE generated column \"%s\"", v42);
        goto LABEL_335;
      }
      v43 = v167;
      v44 = v178;
    }
    *(_DWORD *)(v166 + 4LL * j) = v36;
LABEL_49:
    v45 = *(__int16 *)(v11 + 54);
    v167 = v43;
    v178 = v44;
    if ( j >= v45 )
      break;
    v47 = j;
    v48 = j < 0;
    v35 = v197;
    if ( v48 )
    {
LABEL_54:
      v49 = "ROWID";
    }
    else
    {
      v50 = *(_QWORD *)(v11 + 8);
      v178 = v44;
      v167 = v43;
      v49 = *(const char **)(v50 + 24 * v47);
    }
    v51 = sqlite3AuthCheck(
            (_DWORD)v8,
            23,
            *(_QWORD *)v11,
            (_DWORD)v49,
            *(_QWORD *)(32LL * (int)v158 + *(_QWORD *)(v187 + 32)));
    if ( v51 == 1 )
      goto LABEL_335;
    if ( v51 == 2 )
      *(_DWORD *)(v166 + 4 * v47) = -1;
    ++v36;
    v32 = 0;
  }
  if ( !v168 && (unsigned int)sqlite3IsRowid(*(_QWORD *)&a3[v37 + 4], 0) )
  {
    v46 = *(_QWORD *)&a3[v37 + 2];
    v35 = 1;
    v197 = 1;
    v47 = -1;
    v178 = v46;
    v167 = v36;
    goto LABEL_54;
  }
  sqlite3ErrorMsg(v8, "no such column: %s", *(const char **)&a3[v37 + 4]);
  *((_BYTE *)v8 + 29) = 1;
LABEL_335:
  v9 = v166;
LABEL_336:
  v145 = v187;
  sqlite3DbFree(v187, v9);
  sqlite3SrcListDelete(v145, a2);
  sqlite3ExprListDeleteGeneric(v145, a3);
  return sqlite3ExprDeleteGeneric(v145, a4);
}

```

## disassembly

```asm
0x18002f9a4  mov     rax, rsp
0x18002f9a7  mov     [rax+20h], r9
0x18002f9ab  mov     [rax+18h], r8
0x18002f9af  mov     [rax+10h], rdx
0x18002f9b3  mov     [rax+8], rcx
0x18002f9b7  push    rbp
0x18002f9b8  push    rbx
0x18002f9b9  push    rsi
0x18002f9ba  push    rdi
0x18002f9bb  push    r12
0x18002f9bd  push    r13
0x18002f9bf  push    r14
0x18002f9c1  push    r15
0x18002f9c3  lea     rbp, [rax-0D8h]
0x18002f9ca  sub     rsp, 198h
0x18002f9d1  xor     r13d, r13d
0x18002f9d4  mov     rdi, rcx
0x18002f9d7  xor     ecx, ecx
0x18002f9d9  mov     [rbp+0D0h+var_D0], r13d
0x18002f9dd  xorps   xmm0, xmm0
0x18002f9e0  mov     [rbp+0D0h+var_48], rcx
0x18002f9e7  mov     r14d, r13d
0x18002f9ea  mov     [rbp+0D0h+var_100], r13d
0x18002f9ee  mov     rcx, [rdi]
0x18002f9f1  mov     [rbp+0D0h+var_A0], rcx
0x18002f9f5  movups  [rbp+0D0h+var_78], xmm0
0x18002f9f9  movups  [rbp+0D0h+var_68], xmm0
0x18002f9fd  movups  [rbp+0D0h+var_58], xmm0
0x18002fa01  cmp     [rdi+30h], r13d
0x18002fa05  jnz     loc_180031137
0x18002fa0b  mov     rcx, rdi
0x18002fa0e  call    sqlite3SrcListLookup
0x18002fa13  mov     [rbp+0D0h+var_E8], rax
0x18002fa17  mov     rsi, rax
0x18002fa1a  test    rax, rax
0x18002fa1d  jz      loc_180031137
0x18002fa23  mov     r9, [rdi]
0x18002fa26  mov     rdx, [rax+60h]
0x18002fa2a  mov     rcx, r9
0x18002fa2d  call    sqlite3SchemaToIndex
0x18002fa32  mov     [rbp+0D0h+var_13C], eax
0x18002fa35  cmp     [rsi+58h], r13
0x18002fa39  jnz     short loc_18002FA4E
0x18002fa3b  mov     rax, [r9+20h]
0x18002fa3f  mov     rcx, [rax+38h]
0x18002fa43  test    rcx, rcx
0x18002fa46  jz      short loc_18002FA57
0x18002fa48  cmp     [rcx+40h], r13
0x18002fa4c  jz      short loc_18002FA57
0x18002fa4e  cmp     [rdi+0E5h], r13b
0x18002fa55  jz      short loc_18002FA63
0x18002fa57  mov     rbx, [rbp+0D0h+arg_10]
0x18002fa5e  mov     r15, r13
0x18002fa61  jmp     short loc_18002FA8A
0x18002fa63  mov     rbx, [rbp+0D0h+arg_10]
0x18002fa6a  lea     rax, [rbp+0D0h+var_D0]
0x18002fa6e  mov     r9, rbx
0x18002fa71  mov     [rsp+1D0h+var_1B0], rax
0x18002fa76  mov     r8d, 81h
0x18002fa7c  mov     rdx, rsi
0x18002fa7f  mov     rcx, rdi
0x18002fa82  call    triggersReallyExist
0x18002fa87  mov     r15, rax
0x18002fa8a  mov     r12, [rbp+0D0h+arg_8]
0x18002fa91  mov     al, [rsi+3Fh]
0x18002fa94  mov     [rbp+0D0h+var_F0], r15
0x18002fa98  mov     [rbp+0D0h+arg_30], al
0x18002fa9e  cmp     dword ptr [r12], 1
0x18002faa3  jle     short loc_18002FAAD
0x18002faa5  mov     ebx, [rbx]
0x18002faa7  mov     [rsp+7Ch], ebx
0x18002faab  jmp     short loc_18002FAB2
0x18002faad  mov     [rsp+7Ch], r13d
0x18002fab2  mov     rdx, rsi
0x18002fab5  mov     rcx, rdi
0x18002fab8  call    sqlite3ViewGetColumnNames
0x18002fabd  test    eax, eax
0x18002fabf  jnz     loc_180031137
0x18002fac5  mov     r8, r15
0x18002fac8  mov     rdx, rsi
0x18002facb  mov     rcx, rdi
0x18002face  call    sqlite3IsReadOnly
0x18002fad3  test    eax, eax
0x18002fad5  jnz     loc_180031137
0x18002fadb  mov     r9d, [rdi+34h]
0x18002fadf  mov     edx, r9d
0x18002fae2  mov     [rsp+1D0h+var_15C], r9d
0x18002fae7  mov     [rbp+0D0h+var_FC], edx
0x18002faea  lea     r15d, [r9+1]
0x18002faee  mov     [rdi+34h], r15d
0x18002faf2  test    byte ptr [rsi+30h], 80h
0x18002faf6  mov     [rbp+0D0h+var_F4], r15d
0x18002fafa  jnz     short loc_18002FB01
0x18002fafc  mov     r11, r13
0x18002faff  jmp     short loc_18002FB0C
0x18002fb01  mov     rcx, rsi
0x18002fb04  call    sqlite3PrimaryKeyIndex
0x18002fb09  mov     r11, rax
0x18002fb0c  mov     rcx, [rsi+10h]
0x18002fb10  mov     r10d, r13d
0x18002fb13  mov     [rbp+0D0h+var_110], r11
0x18002fb17  mov     [rbp+0D0h+var_B0], r13d
0x18002fb1b  test    rcx, rcx
0x18002fb1e  jz      short loc_18002FB58
0x18002fb20  mov     r8d, r15d
0x18002fb23  mov     edx, r15d
0x18002fb26  cmp     r11, rcx
0x18002fb29  mov     eax, edx
0x18002fb2b  cmovnz  edx, r8d
0x18002fb2f  cmovnz  eax, r9d
0x18002fb33  inc     r10d
0x18002fb36  mov     r9d, eax
0x18002fb39  lea     r8d, [rdx+1]
0x18002fb3d  mov     [rdi+34h], r8d
0x18002fb41  mov     edx, r8d
0x18002fb44  mov     rcx, [rcx+28h]
0x18002fb48  test    rcx, rcx
0x18002fb4b  jnz     short loc_18002FB26
0x18002fb4d  mov     edx, [rbp+0D0h+var_FC]
0x18002fb50  mov     [rbp+0D0h+var_B0], r10d
0x18002fb54  mov     [rsp+1D0h+var_15C], eax
0x18002fb58  mov     r13, [rbp+0D0h+arg_38]
0x18002fb5f  test    r13, r13
0x18002fb62  jz      short loc_18002FB77
0x18002fb64  mov     r9d, [r13+4Ch]
0x18002fb68  mov     eax, [r13+50h]
0x18002fb6c  mov     [rsp+1D0h+var_15C], r9d
0x18002fb71  mov     [rbp+0D0h+var_F4], eax
0x18002fb74  mov     [rdi+34h], edx
0x18002fb77  mov     rcx, [rbp+0D0h+var_A0]
0x18002fb7b  mov     [r12+4Ch], r9d
0x18002fb80  movsx   eax, word ptr [rsi+36h]
0x18002fb84  inc     eax
0x18002fb86  movsxd  rbx, r10d
0x18002fb89  add     eax, r10d
0x18002fb8c  cdqe
0x18002fb8e  lea     rdx, ds:2[rax*4]
0x18002fb96  add     rdx, rbx
0x18002fb99  call    sqlite3DbMallocRawNN
0x18002fb9e  mov     [rbp+0D0h+var_120], rax
0x18002fba2  mov     r14, rax
0x18002fba5  test    rax, rax
0x18002fba8  jz      loc_180031137
0x18002fbae  movsx   rcx, word ptr [rsi+36h]
0x18002fbb3  lea     r12, [rbx+1]
0x18002fbb7  mov     r8, r12; Size
0x18002fbba  mov     [rbp+0D0h+Size], r12
0x18002fbbe  mov     edx, 1; Val
0x18002fbc3  lea     rax, [rax+rcx*4]
0x18002fbc7  lea     r15, [rax+4]
0x18002fbcb  mov     [rbp+0D0h+var_B8], rax
0x18002fbcf  lea     r15, [r15+rbx*4]
0x18002fbd3  mov     rcx, r15; void *
0x18002fbd6  mov     [rbp+0D0h+var_C0], r15
0x18002fbda  call    memset_0
0x18002fbdf  mov     byte ptr [r12+r15], 0
0x18002fbe4  xor     r15d, r15d
0x18002fbe7  mov     ecx, r15d
0x18002fbea  cmp     r15w, [rsi+36h]
0x18002fbef  jge     short loc_18002FC06
0x18002fbf1  movsxd  rax, ecx
0x18002fbf4  inc     ecx
0x18002fbf6  mov     dword ptr [r14+rax*4], 0FFFFFFFFh
0x18002fbfe  movsx   eax, word ptr [rsi+36h]
0x18002fc02  cmp     ecx, eax
0x18002fc04  jl      short loc_18002FBF1
0x18002fc06  mov     rbx, [rbp+0D0h+arg_8]
0x18002fc0d  xorps   xmm0, xmm0
0x18002fc10  mov     rcx, rdi
0x18002fc13  mov     qword ptr [rbp+0D0h+var_78+8], rbx
0x18002fc17  movdqu  [rbp+0D0h+var_68+8], xmm0
0x18002fc1c  mov     qword ptr [rbp+0D0h+var_58+0Ch], r15
0x18002fc23  mov     dword ptr [rbp+0D0h+var_48+4], r15d
0x18002fc2a  mov     qword ptr [rbp+0D0h+var_78], rdi
0x18002fc2e  mov     qword ptr [rbp+0D0h+var_68], r13
0x18002fc32  mov     dword ptr [rbp+0D0h+var_58+8], 200h
0x18002fc3c  call    sqlite3GetVdbe
0x18002fc41  mov     [rbp+0D0h+var_130], rax
0x18002fc45  test    rax, rax
0x18002fc48  jz      loc_180031137
0x18002fc4e  mov     [rbp+0D0h+var_D8], r15
0x18002fc52  mov     r14b, r15b
0x18002fc55  mov     [rbp+0D0h+var_118], 0FFFFFFFFh
0x18002fc5c  mov     r13d, r15d
0x18002fc5f  mov     [rsp+78h], r15b
0x18002fc64  mov     [rbp+0D0h+arg_28], r15b
0x18002fc6b  mov     r9, [rbp+0D0h+arg_10]
0x18002fc72  cmp     r13d, [r9]
0x18002fc75  jge     loc_18002FE72
0x18002fc7b  movsxd  rbx, r13d
0x18002fc7e  shl     rbx, 5
0x18002fc82  mov     rcx, [rbx+r9+10h]
0x18002fc87  call    sqlite3StrIHash
0x18002fc8c  mov     cl, al
0x18002fc8e  mov     [rsp+1D0h+var_160], al
0x18002fc92  cmp     [rsp+7Ch], r15d
0x18002fc97  jnz     short loc_18002FCBA
0x18002fc99  mov     rdx, [rbx+r9+8]
0x18002fc9e  lea     rcx, [rbp+0D0h+var_78]
0x18002fca2  call    sqlite3ResolveExprNames
0x18002fca7  test    eax, eax
0x18002fca9  jnz     loc_180031133
0x18002fcaf  mov     cl, [rsp+1D0h+var_160]
0x18002fcb3  mov     r9, [rbp+0D0h+arg_10]
0x18002fcba  mov     r14d, r15d
0x18002fcbd  movsx   eax, word ptr [rsi+36h]
0x18002fcc1  cmp     r14d, eax
0x18002fcc4  jge     loc_18002FD57
0x18002fcca  mov     r12, [rsi+8]
0x18002fcce  movsxd  rax, r14d
0x18002fcd1  lea     r15, [rax+rax*2]
0x18002fcd5  cmp     [r12+r15*8+0Eh], cl
0x18002fcda  jnz     short loc_18002FCF4
0x18002fcdc  mov     rcx, [r12+r15*8]
0x18002fce0  mov     rdx, [rbx+r9+10h]
0x18002fce5  call    sqlite3StrICmp
0x18002fcea  xor     edx, edx
0x18002fcec  test    eax, eax
0x18002fcee  jz      short loc_18002FD00
0x18002fcf0  mov     cl, [rsp+1D0h+var_160]
0x18002fcf4  mov     r9, [rbp+0D0h+arg_10]
0x18002fcfb  inc     r14d
0x18002fcfe  jmp     short loc_18002FCBD
0x18002fd00  movsx   eax, word ptr [rsi+34h]
0x18002fd04  cmp     r14d, eax
0x18002fd07  jnz     short loc_18002FD21
0x18002fd09  mov     r9, [rbp+0D0h+arg_10]
0x18002fd10  mov     r12d, r13d
0x18002fd13  mov     [rbp+0D0h+arg_28], 1
0x18002fd1a  mov     r15, [rbx+r9+8]
0x18002fd1f  jmp     short loc_18002FD4A
0x18002fd21  cmp     [rbp+0D0h+var_110], rdx
0x18002fd25  jz      short loc_18002FD36
0x18002fd27  test    byte ptr [r12+r15*8+12h], 1
0x18002fd2d  jz      short loc_18002FD36
0x18002fd2f  mov     byte ptr [rsp+78h], 1
0x18002fd34  jmp     short loc_18002FD42
0x18002fd36  test    byte ptr [r12+r15*8+12h], 60h
0x18002fd3c  jnz     loc_18002FE3E
0x18002fd42  mov     r12d, [rbp+0D0h+var_118]
0x18002fd46  mov     r15, [rbp+0D0h+var_D8]
0x18002fd4a  mov     rcx, [rbp+0D0h+var_120]
0x18002fd4e  movsxd  rax, r14d
0x18002fd51  mov     [rcx+rax*4], r13d
0x18002fd55  jmp     short loc_18002FD61
0x18002fd57  mov     r15, [rbp+0D0h+var_D8]
0x18002fd5b  xor     edx, edx
0x18002fd5d  mov     r12d, [rbp+0D0h+var_118]
0x18002fd61  mov     al, [rbp+0D0h+arg_28]
0x18002fd67  mov     [rbp+0D0h+arg_28], al
0x18002fd6d  movsx   eax, word ptr [rsi+36h]
0x18002fd71  mov     [rbp+0D0h+var_118], r12d
0x18002fd75  mov     [rbp+0D0h+var_D8], r15
0x18002fd79  cmp     r14d, eax
0x18002fd7c  jl      short loc_18002FDBE
0x18002fd7e  mov     r15, [rbp+0D0h+arg_10]
0x18002fd85  cmp     [rbp+0D0h+var_110], rdx
0x18002fd89  jnz     loc_18002FE55
0x18002fd8f  mov     rcx, [rbx+r15+10h]
0x18002fd94  call    sqlite3IsRowid
0x18002fd99  test    eax, eax
0x18002fd9b  jz      loc_18002FE55
0x18002fda1  mov     rdx, [rbx+r15+8]
0x18002fda6  mov     r14b, 1
0x18002fda9  mov     [rbp+0D0h+arg_28], r14b
0x18002fdb0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002fdb4  mov     [rbp+0D0h+var_D8], rdx
0x18002fdb8  mov     [rbp+0D0h+var_118], r13d
0x18002fdbc  jmp     short loc_18002FDCD
0x18002fdbe  movsxd  rbx, r14d
0x18002fdc1  test    r14d, r14d
0x18002fdc4  mov     r14b, [rbp+0D0h+arg_28]
0x18002fdcb  jns     short loc_18002FDD6
0x18002fdcd  lea     r9, aRowid_2; "ROWID"
0x18002fdd4  jmp     short loc_18002FDF1
0x18002fdd6  mov     rax, [rsi+8]
0x18002fdda  lea     rcx, [rbx+rbx*2]
0x18002fdde  mov     [rbp+0D0h+arg_28], r14b
0x18002fde5  mov     [rbp+0D0h+var_D8], r15
0x18002fde9  mov     [rbp+0D0h+var_118], r12d
0x18002fded  mov     r9, [rax+rcx*8]
0x18002fdf1  mov     rax, [rbp+0D0h+var_A0]
0x18002fdf5  mov     edx, 17h
0x18002fdfa  movsxd  rcx, [rbp+0D0h+var_13C]
0x18002fdfe  mov     r8, [rsi]
0x18002fe01  shl     rcx, 5
0x18002fe05  mov     rax, [rax+20h]
0x18002fe09  mov     rcx, [rcx+rax]
0x18002fe0d  mov     [rsp+1D0h+var_1B0], rcx
0x18002fe12  mov     rcx, rdi
0x18002fe15  call    sqlite3AuthCheck
0x18002fe1a  cmp     eax, 1
0x18002fe1d  jz      loc_180031133
0x18002fe23  cmp     eax, 2
0x18002fe26  jnz     short loc_18002FE33
0x18002fe28  mov     rax, [rbp+0D0h+var_120]
0x18002fe2c  mov     dword ptr [rax+rbx*4], 0FFFFFFFFh
0x18002fe33  inc     r13d
0x18002fe36  xor     r15d, r15d
0x18002fe39  jmp     loc_18002FC6B
  ... truncated ...
```
