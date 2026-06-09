# sqlite3Update

- ea: `0x1800167c0`
- end: `0x180017fa3`
- name: `sqlite3Update`
- size: `6115`
- prototype: ``
- caller_count: `3`
- callee_count: `56`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018754`
- `0x180031b38`
- `0x180087e6c`

## callees

- `0x180002ed0`
- `0x180008894`
- `0x18000a9e0`
- `0x18000c930`
- `0x18000c960`
- `0x18000ca30`
- `0x180010390`
- `0x180010450`
- `0x180010810`
- `0x1800119e0`
- `0x180011d80`
- `0x1800143f0`
- `0x1800157d4`
- `0x1800161c8`
- `0x1800167c0`
- `0x1800184cc`
- `0x180018544`
- `0x180018600`
- `0x18001861c`
- `0x18001a8dc`
- `0x18001bdf0`
- `0x18001bee8`
- `0x18001c618`
- `0x18001c6f8`
- `0x1800351c8`
- `0x180036730`
- `0x1800370c0`
- `0x1800398f0`
- `0x18003a8dc`
- `0x18003abcc`
- `0x18003e5c0`
- `0x18003e944`
- `0x18003f6dc`
- `0x18004036c`
- `0x180054880`
- `0x180054d2c`
- `0x180056d54`
- `0x1800573d8`
- `0x18005a2c4`
- `0x18005a808`
- `0x18005cc60`
- `0x18005e35c`
- `0x18006074c`
- `0x180060ce8`
- `0x18006170c`
- `0x1800621a0`
- `0x180062c04`
- `0x180063dc8`
- `0x180065204`
- `0x180067068`

## string_xrefs

- `0x180016c60`: `cannot UPDATE generated column "%s"`
- `0x180017f70`: `rows updated`

## pseudocode

```c
__int64 __fastcall sqlite3Update(__int64 *a1, __int64 a2, int *a3, __int64 a4, int a5, char a6, char a7, __int64 a8)
{
  __int64 v8; // r15
  __int64 *v9; // rdi
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // r9
  __int64 v14; // rcx
  int *v15; // rbx
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
  char v35; // r13
  int v36; // r12d
  __int64 v37; // rbx
  __int64 v38; // rdx
  char v39; // cl
  int *v40; // r9
  int j; // r11d
  __int64 v42; // r15
  __int64 v43; // r14
  const char *v44; // r13
  int v45; // eax
  int v46; // r15d
  __int64 v47; // r14
  int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rbx
  const char *v51; // r9
  __int64 v52; // rax
  int v53; // eax
  __int64 v54; // rdi
  __int64 result; // rax
  unsigned __int8 v56; // cl
  int v57; // r14d
  __int64 v58; // rax
  int v59; // r13d
  __int64 v60; // rbx
  __int64 v61; // r12
  int v62; // r14d
  __int64 v63; // rcx
  void *v65; // r15
  __int64 v66; // rcx
  __int64 v67; // rax
  int *v68; // r14
  int v69; // eax
  __int64 v70; // rdx
  int *v71; // rbx
  __int64 v72; // r10
  int v73; // r13d
  __int64 v74; // rdx
  int v75; // r12d
  int v76; // eax
  int v77; // ecx
  char v78; // al
  int v79; // eax
  unsigned int v80; // ebx
  __int64 v81; // r8
  int v82; // r9d
  int v83; // r13d
  int v84; // r8d
  unsigned int v85; // r12d
  __int16 v86; // ax
  __int64 v87; // rax
  signed __int64 v88; // rbx
  int v89; // r14d
  int v90; // eax
  __int64 *v91; // rcx
  int v92; // ecx
  __int16 v93; // cx
  int v94; // eax
  int v95; // ebx
  int v96; // r14d
  int v97; // eax
  __int64 v98; // rax
  __int64 *v99; // rax
  __int64 *v100; // rcx
  __int64 v101; // rdx
  __int64 v102; // r8
  int v103; // eax
  __int64 v104; // rcx
  unsigned int v105; // r14d
  __int64 v106; // rax
  unsigned int v107; // r12d
  int v108; // r14d
  unsigned int v109; // r15d
  int v110; // r8d
  _BYTE *v111; // rdx
  __int64 v112; // rdx
  __int64 v113; // r15
  int v114; // eax
  int v115; // r15d
  __int64 v116; // r13
  int v117; // r14d
  int v118; // r8d
  int v119; // ebx
  int v120; // r14d
  int v121; // eax
  int v122; // ebx
  int v123; // r14d
  int v124; // r14d
  signed int v125; // ebx
  int v126; // r12d
  int v127; // edx
  int v128; // r14d
  int v129; // ebx
  int v130; // eax
  signed int v131; // r8d
  int v132; // r15d
  unsigned int v133; // ebx
  signed int v134; // r14d
  __int64 v135; // rax
  __int64 v136; // rcx
  __int16 v137; // ax
  int v138; // r15d
  unsigned int v139; // ecx
  int v140; // ebx
  unsigned int v141; // r14d
  __int64 v142; // rax
  unsigned int v143; // eax
  int v144; // eax
  int v145; // ebx
  int v146; // eax
  unsigned int v147; // r14d
  int v148; // [rsp+28h] [rbp-E0h]
  char v149; // [rsp+78h] [rbp-90h]
  char v150; // [rsp+78h] [rbp-90h]
  int v151; // [rsp+7Ch] [rbp-8Ch]
  char v152; // [rsp+80h] [rbp-88h]
  int v153; // [rsp+84h] [rbp-84h]
  int v154; // [rsp+88h] [rbp-80h]
  int v155; // [rsp+8Ch] [rbp-7Ch]
  int v156; // [rsp+90h] [rbp-78h]
  int v157; // [rsp+94h] [rbp-74h]
  int v158; // [rsp+98h] [rbp-70h]
  unsigned int v159; // [rsp+9Ch] [rbp-6Ch]
  unsigned int v160; // [rsp+9Ch] [rbp-6Ch]
  int v161; // [rsp+9Ch] [rbp-6Ch]
  int v162; // [rsp+A0h] [rbp-68h]
  unsigned int v163; // [rsp+A0h] [rbp-68h]
  __int64 Vdbe; // [rsp+A8h] [rbp-60h]
  unsigned int v165; // [rsp+B0h] [rbp-58h]
  unsigned int v166; // [rsp+B4h] [rbp-54h]
  __int64 v167; // [rsp+B8h] [rbp-50h]
  int v168; // [rsp+C0h] [rbp-48h]
  __int64 v169; // [rsp+C8h] [rbp-40h]
  __int16 v170; // [rsp+D0h] [rbp-38h]
  unsigned int v171; // [rsp+D4h] [rbp-34h]
  int v172; // [rsp+D8h] [rbp-30h] BYREF
  int v173; // [rsp+DCh] [rbp-2Ch]
  int v174; // [rsp+E0h] [rbp-28h]
  int v175; // [rsp+E4h] [rbp-24h]
  __int64 v176; // [rsp+E8h] [rbp-20h]
  __int64 v177; // [rsp+F0h] [rbp-18h]
  int v178; // [rsp+F8h] [rbp-10h]
  __int64 v179; // [rsp+100h] [rbp-8h]
  int v180; // [rsp+108h] [rbp+0h] BYREF
  int v181; // [rsp+10Ch] [rbp+4h]
  size_t Size; // [rsp+110h] [rbp+8h] BYREF
  void *v183; // [rsp+118h] [rbp+10h]
  __int64 v184; // [rsp+120h] [rbp+18h]
  int v185; // [rsp+128h] [rbp+20h]
  int v186; // [rsp+12Ch] [rbp+24h]
  int v187; // [rsp+130h] [rbp+28h]
  __int64 v188; // [rsp+138h] [rbp+30h]
  size_t v189; // [rsp+140h] [rbp+38h] BYREF
  __int64 *v190; // [rsp+148h] [rbp+40h]
  __int64 v191; // [rsp+150h] [rbp+48h]
  __int64 v192; // [rsp+158h] [rbp+50h]
  _OWORD v193[7]; // [rsp+160h] [rbp+58h] BYREF
  unsigned __int8 v198; // [rsp+210h] [rbp+108h]
  char v199; // [rsp+218h] [rbp+110h]

  v8 = 0;
  v9 = a1;
  v180 = 0;
  v10 = 0;
  v172 = 0;
  v188 = *a1;
  memset(v193, 0, 56);
  if ( *((_DWORD *)a1 + 13) )
    goto LABEL_62;
  v11 = sqlite3SrcListLookup(a1, a2);
  v177 = v11;
  v12 = v11;
  if ( !v11 )
    goto LABEL_62;
  if ( ((v159 = sqlite3SchemaToIndex(*v9, *(_QWORD *)(v11 + 96)), *(_QWORD *)(v12 + 88))
     || (v14 = *(_QWORD *)(*(_QWORD *)(v13 + 32) + 56LL)) != 0 && *(_QWORD *)(v14 + 64))
    && !*((_BYTE *)v9 + 229) )
  {
    v15 = a3;
    v8 = triggersReallyExist((_DWORD)v9, v12, 130, (_DWORD)a3, (__int64)&v180);
  }
  else
  {
    v15 = a3;
  }
  v16 = *(_BYTE *)(v12 + 63);
  v176 = v8;
  v199 = v16;
  v153 = *(int *)a2 <= 1 ? 0 : *v15;
  if ( (unsigned int)sqlite3ViewGetColumnNames(v9, v12) || (unsigned int)sqlite3IsReadOnly(v9, v12, v8) )
    goto LABEL_62;
  v17 = *((_DWORD *)v9 + 14);
  v18 = v17;
  v151 = v17;
  v173 = v17;
  v19 = v17 + 1;
  *((_DWORD *)v9 + 14) = v17 + 1;
  v20 = *(_BYTE *)(v12 + 48) >= 0;
  v175 = v17 + 1;
  if ( v20 )
  {
    v21 = 0;
    v169 = 0;
  }
  else
  {
    v21 = sqlite3PrimaryKeyIndex(v12);
    v169 = v21;
  }
  v22 = *(_QWORD *)(v12 + 16);
  v23 = 0;
  v185 = 0;
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
      *((_DWORD *)v9 + 14) = ++v25;
      v22 = *(_QWORD *)(v22 + 40);
    }
    while ( v22 );
    v18 = v173;
    v185 = v23;
    v151 = v26;
  }
  if ( a8 )
  {
    v17 = *(_DWORD *)(a8 + 76);
    v151 = v17;
    v175 = *(_DWORD *)(a8 + 80);
    *((_DWORD *)v9 + 14) = v18;
  }
  v27 = v188;
  *(_DWORD *)(a2 + 40) = v17;
  v28 = v23;
  v29 = sqlite3DbMallocRawNN(v27, v23 + 4LL * (v23 + *(__int16 *)(v12 + 54) + 1) + 2);
  v167 = v29;
  v10 = v29;
  if ( !v29 )
    goto LABEL_62;
  v30 = *(__int16 *)(v12 + 54);
  Size = v28 + 1;
  v184 = v29 + 4 * v30;
  v31 = (void *)(v184 + 4 + 4 * v28);
  v183 = v31;
  memset_0(v31, 1, v28 + 1);
  *((_BYTE *)v31 + v28 + 1) = 0;
  v32 = 0;
  for ( i = 0; i < *(__int16 *)(v12 + 54); *(_DWORD *)(v10 + 4 * v34) = -1 )
    v34 = i++;
  *((_QWORD *)&v193[0] + 1) = a2;
  *(_OWORD *)((char *)&v193[1] + 8) = 0;
  *(_QWORD *)((char *)&v193[2] + 12) = 0;
  DWORD1(v193[3]) = 0;
  *(_QWORD *)&v193[0] = v9;
  *(_QWORD *)&v193[1] = a8;
  DWORD2(v193[2]) = 512;
  Vdbe = sqlite3GetVdbe(v9);
  if ( !Vdbe )
    goto LABEL_62;
  v179 = 0;
  v35 = 0;
  v168 = -1;
  v36 = 0;
  v152 = 0;
  v198 = 0;
  while ( 1 )
  {
    if ( v36 >= *a3 )
    {
      v191 = 0;
      v56 = v152 + v35;
      v20 = (*(_BYTE *)(v12 + 48) & 0x60) == 0;
      v190 = 0;
      v157 = 0;
      v165 = 0;
      v171 = 0;
      v186 = 0;
      v162 = 0;
      v150 = v152 + v35;
      if ( !v20 )
      {
        do
        {
          v57 = 0;
          if ( *(__int16 *)(v12 + 54) <= 0 )
            break;
          do
          {
            if ( *(int *)(v167 + 4LL * v57) < 0 && (*(_BYTE *)(*(_QWORD *)(v12 + 8) + 24LL * v57 + 18) & 0x60) != 0 )
            {
              v58 = sqlite3ColumnExpr(v12);
              if ( (unsigned int)sqlite3ExprReferencesUpdatedColumn(v58, v167) )
              {
                *(_DWORD *)(v167 + 4LL * v57) = 99999;
                v32 = 1;
              }
            }
            ++v57;
          }
          while ( v57 < *(__int16 *)(v12 + 54) );
          v20 = v32 == 0;
          v32 = 0;
        }
        while ( !v20 );
        v56 = v152 + v35;
        v32 = 0;
      }
      *(_QWORD *)(a2 + 48) = (*(_BYTE *)(v12 + 63) != 1) - 1LL;
      v181 = v56;
      v59 = sqlite3FkRequired(v9, v12, v167, v56);
      v155 = v59;
      if ( a5 == 5 )
        v172 = 1;
      v60 = *(_QWORD *)(v12 + 16);
      LODWORD(v61) = 0;
      if ( v60 )
      {
        while ( 1 )
        {
          if ( v150 || v59 > 1 || v60 == v169 || (unsigned int)indexWhereClauseMightChange(v60, v167, v198) )
          {
            v62 = ++*((_DWORD *)v9 + 15);
            *((_DWORD *)v9 + 15) = v62 + *(unsigned __int16 *)(v60 + 96);
          }
          else
          {
            v62 = 0;
            while ( 1 )
            {
              if ( v32 >= *(unsigned __int16 *)(v60 + 94) )
                goto LABEL_96;
              v63 = *(__int16 *)(*(_QWORD *)(v60 + 8) + 2LL * v32);
              if ( (v63 & 0x8000u) != 0LL
                 ? sqlite3ExprReferencesUpdatedColumn(*(_QWORD *)(32LL * v32 + *(_QWORD *)(v60 + 80) + 8), v167)
                 : *(_DWORD *)(v167 + 4 * v63) >= 0 )
              {
                break;
              }
              ++v32;
            }
            v62 = ++*((_DWORD *)v9 + 15);
            *((_DWORD *)v9 + 15) = v62 + *(unsigned __int16 *)(v60 + 96);
            if ( a5 == 11 && *(_BYTE *)(v60 + 98) == 5 )
              v172 = 1;
          }
          if ( v62 )
          {
            v65 = v183;
          }
          else
          {
LABEL_96:
            v65 = v183;
            *((_BYTE *)v183 + (int)v61 + 1) = 0;
          }
          v66 = v184;
          v59 = v155;
          v67 = (int)v61;
          LODWORD(v61) = v61 + 1;
          *(_DWORD *)(v184 + 4 * v67) = v62;
          v60 = *(_QWORD *)(v60 + 40);
          if ( !v60 )
            break;
          v32 = 0;
        }
        v12 = v177;
      }
      else
      {
        v65 = v183;
        v66 = v184;
      }
      v61 = (int)v61;
      v68 = (int *)v9 + 15;
      v69 = ++*((_DWORD *)v9 + 15);
      v192 = v61;
      *(_DWORD *)(v66 + 4LL * (int)v61) = v69;
      if ( v172 )
        memset_0(v65, 1, Size);
      if ( !*((_BYTE *)v9 + 30) )
      {
        *(_DWORD *)(Vdbe + 200) |= 0x10u;
        v68 = (int *)v9 + 15;
      }
      if ( v176 )
      {
        v71 = v68;
      }
      else
      {
        if ( !v59 )
        {
          v70 = 0;
          v71 = v68;
          goto LABEL_111;
        }
        v71 = (int *)v9 + 15;
      }
      v70 = 1;
LABEL_111:
      sqlite3BeginWriteOperation(v9, v70, v159);
      v72 = 0;
      if ( *(_BYTE *)(v12 + 63) == 1 )
      {
        v75 = 0;
        goto LABEL_125;
      }
      v73 = *((_DWORD *)v9 + 15) + 1;
      v74 = v176;
      v157 = v73;
      v75 = *(_DWORD *)(v184 + 4LL * (int)v61);
      v162 = v75;
      *v68 = v73;
      if ( v152 )
      {
        v71 = v68;
      }
      else if ( !v74 )
      {
        v76 = v155;
        if ( !v155 )
        {
          v77 = v73;
          goto LABEL_118;
        }
      }
      v77 = v73 + *(__int16 *)(v12 + 54);
      v186 = v73 + 1;
      v76 = v155;
      *v71 = v77;
LABEL_118:
      if ( v150 || v74 || v76 )
      {
        v165 = ++v77;
        *v71 = v77;
      }
      else
      {
        v165 = v73;
      }
      v171 = v77 + 1;
      *v71 = v77 + *(__int16 *)(v12 + 54);
LABEL_125:
      v78 = v199;
      if ( v199 == 2 )
      {
        v191 = v9[47];
        v9[47] = *(_QWORD *)v12;
        v78 = 2;
        v190 = v9;
      }
      if ( !v153 )
      {
        if ( v78 == 2 )
          sqlite3MaterializeView((_DWORD)v9, v12, a4, 0, 0, v151);
        v79 = sqlite3ResolveExprNames(v193, a4);
        v72 = 0;
        if ( v79 )
          goto LABEL_337;
      }
      if ( *(_BYTE *)(v12 + 63) == 1 )
      {
        updateVirtualTable((_DWORD)v9, a2, v12, (_DWORD)a3, v179, v167, a4, a5);
        goto LABEL_337;
      }
      v80 = --*((_DWORD *)v9 + 18);
      v81 = a8;
      v187 = 0;
      v166 = v80;
      if ( (*(_QWORD *)(v188 + 48) & 0x100000000LL) != 0
        && !v9[23]
        && !*((_BYTE *)v9 + 30)
        && !*((_BYTE *)v9 + 227)
        && !a8 )
      {
        v82 = *((_DWORD *)v9 + 15) + 1;
        v187 = v82;
        *((_DWORD *)v9 + 15) = v82;
        sqlite3VdbeAddOp3(Vdbe, 71, 0, v82, 0);
        v81 = 0;
        v72 = 0;
      }
      if ( !v153 && *(char *)(v12 + 48) >= 0 )
      {
        v170 = 0;
        v158 = 0;
        v83 = 0;
        sqlite3VdbeAddOp3(Vdbe, 75, 0, v75, v157);
        v84 = *((_DWORD *)v9 + 14);
        v154 = v84;
        *((_DWORD *)v9 + 14) = v84 + 1;
        v160 = sqlite3VdbeAddOp3(Vdbe, 117, v84, 0, v75);
        v85 = v160;
        if ( !a8 )
          goto LABEL_142;
LABEL_180:
        v89 = 1;
        v177 = 0;
        v156 = 1;
        sqlite3ExprIfFalse(v9, a4, v80, 16);
        LODWORD(v88) = Size;
        v72 = 0;
        v178 = 0;
        v189 = Size;
        goto LABEL_181;
      }
      if ( v169 )
        v93 = *(_WORD *)(v169 + 94);
      else
        v93 = 0;
      v170 = v93;
      v83 = *((_DWORD *)v9 + 15) + 1;
      v158 = v153 + v93 + v83;
      *((_DWORD *)v9 + 15) = v158;
      if ( v81 )
      {
        v154 = 0;
        if ( !v153 )
        {
          v85 = 0;
          v160 = 0;
          goto LABEL_180;
        }
      }
      else
      {
        if ( v199 == 2 )
          v94 = *(__int16 *)(v12 + 54);
        else
          v94 = 0;
        v95 = v153 + v93 + v94;
        v96 = *((_DWORD *)v9 + 14);
        v154 = v96;
        *((_DWORD *)v9 + 14) = v96 + 1;
        if ( v169 )
          sqlite3VdbeAddOp3(Vdbe, 75, 0, v83, v93 + v83 - 1);
        v85 = sqlite3VdbeAddOp3(Vdbe, 117, v96, v95, 0);
        v160 = v85;
        v97 = v169;
        if ( v169 )
        {
          v98 = sqlite3KeyInfoOfIndex(v9, v169);
          if ( v98 )
          {
            *(_WORD *)(v98 + 8) = v95;
            sqlite3VdbeAppendP4(Vdbe, v98, 4294967288LL);
          }
          v97 = v169;
        }
        if ( !v153 )
        {
LABEL_142:
          v86 = 4;
          if ( !*((_BYTE *)v9 + 30)
            && !v176
            && !v155
            && !v150
            && !v172
            && (!a4 || (*(_DWORD *)(a4 + 4) & 0x400000) == 0) )
          {
            v86 = 12;
          }
          v87 = sqlite3WhereBegin((_DWORD)v9, a2, a4, 0, 0, 0, v86, v175);
          v72 = 0;
          v177 = v87;
          if ( !v87 )
            goto LABEL_337;
          v88 = *(_QWORD *)(v87 + 40);
          v89 = *(unsigned __int8 *)(v87 + 66);
          v90 = *(_DWORD *)(v87 + 68) & 1;
          v189 = v88;
          Size = v88;
          v156 = v89;
          v178 = v90;
          if ( v89 != 1 )
          {
            v91 = v9;
            if ( v9[22] )
              v91 = (__int64 *)v9[22];
            *((_BYTE *)v91 + 32) = 1;
            v92 = v151;
            if ( v89 == 2 && v88 >= 0 && HIDWORD(v88) != v151 && *((_BYTE *)v183 + HIDWORD(v88) - v173) )
            {
              v89 = 0;
              v156 = 0;
            }
LABEL_182:
            v20 = *(_BYTE *)(v12 + 48) >= 0;
            v174 = 0;
            if ( v20 )
            {
              sqlite3VdbeAddOp3(Vdbe, 135, v92, v157, 0);
              v72 = 0;
              if ( v89 )
              {
                if ( !v85 )
                {
LABEL_196:
                  v101 = v177;
                  goto LABEL_197;
                }
                sqlite3VdbeChangeToNoop(Vdbe, v85);
              }
              else
              {
                v102 = v184;
                v103 = *((_DWORD *)v9 + 15) + 1;
                v104 = v192;
                *((_DWORD *)v9 + 15) = v103;
                *(_DWORD *)(v102 + 4 * v104) = v103;
                sqlite3VdbeAddOp3(Vdbe, 128, v154, v162, v157);
              }
            }
            else
            {
              v105 = 0;
              if ( v170 > 0 )
              {
                do
                {
                  sqlite3ExprCodeGetColumnOfTable(
                    Vdbe,
                    v12,
                    v151,
                    *(__int16 *)(*(_QWORD *)(v169 + 8) + 2LL * v105),
                    v105 + v83);
                  ++v105;
                }
                while ( (int)v105 < v170 );
                LODWORD(v88) = v189;
                v72 = 0;
                v9 = a1;
                v85 = v160;
              }
              v89 = v156;
              if ( v156 )
              {
                if ( v85 )
                {
                  sqlite3VdbeChangeToNoop(Vdbe, v85);
                  v72 = 0;
                }
                v174 = v170;
                v158 = v83;
                goto LABEL_196;
              }
              v106 = sqlite3IndexAffinityStr(v188, v169);
              sqlite3VdbeAddOp4(Vdbe, 97, v83, v170, v158, v106, v170);
              sqlite3VdbeAddOp4Int(Vdbe, 138, v154, v158, v83, v170);
            }
            v72 = 0;
            goto LABEL_196;
          }
LABEL_181:
          v92 = v151;
          goto LABEL_182;
        }
        updateFromSelect((_DWORD)v9, v96, v97, (_DWORD)a3, a2, a4);
        v72 = 0;
        if ( v199 == 2 )
          v151 = v96;
      }
      v99 = (__int64 *)v9[22];
      v100 = v9;
      LODWORD(v88) = Size;
      v101 = 0;
      v178 = 1;
      if ( v99 )
        v100 = v99;
      v177 = 0;
      v89 = 0;
      v156 = 0;
      v174 = v170;
      *((_BYTE *)v100 + 32) = 1;
      v158 = v83;
LABEL_197:
      v107 = v166;
      v163 = v166;
      v161 = 0;
      if ( a8 )
      {
        v116 = Vdbe;
        v115 = v151;
LABEL_238:
        v119 = v154;
        goto LABEL_239;
      }
      if ( !v153 && v89 != 2 )
      {
        sqlite3WhereEnd(v101);
        v72 = 0;
      }
      v108 = HIDWORD(Size);
      if ( v199 == 2 )
        goto LABEL_212;
      v109 = 0;
      LODWORD(Size) = 0;
      LODWORD(v189) = 0;
      if ( v156 )
      {
        v110 = v173;
        v111 = v183;
        if ( (int)v88 >= 0 )
          *((_BYTE *)v183 + (int)v88 - v173) = 0;
        if ( v108 >= 0 )
          v111[v108 - v110] = 0;
        if ( v156 == 2 && v185 - (v108 >= 0) > 0 )
          v109 = sqlite3VdbeAddOp3(Vdbe, 15, 0, 0, 0);
      }
      sqlite3OpenTableAndIndices((_DWORD)v9, v12, 113, 0, v173, (__int64)v183, (__int64)&Size, (__int64)&v189);
      v72 = 0;
      if ( !v109 )
      {
LABEL_212:
        v113 = Vdbe;
      }
      else
      {
        v112 = v109;
        v113 = Vdbe;
        sqlite3VdbeJumpHereOrPopInst(Vdbe, v112);
      }
      v114 = v156;
      if ( v156 )
      {
        v115 = v151;
        v116 = Vdbe;
        if ( (_DWORD)v88 == v151 )
        {
          v117 = v158;
        }
        else
        {
          v20 = v108 == v151;
          v117 = v158;
          if ( !v20 )
          {
            sqlite3VdbeAddOp4Int(Vdbe, 28, v151, v166, v158, v174);
            v114 = v156;
            v72 = 0;
          }
        }
        if ( v114 != 1 )
        {
          v107 = *((_DWORD *)v9 + 18) - 1;
          v163 = v107;
          *((_DWORD *)v9 + 18) = v107;
        }
        v118 = v157;
        if ( v169 != v72 )
          v118 = v117;
        sqlite3VdbeAddOp3(Vdbe, 51, v118, v166, v72);
        goto LABEL_238;
      }
      if ( v169 || v153 != (_DWORD)v72 )
      {
        v119 = v154;
        v107 = *((_DWORD *)v9 + 18) - 1;
        v163 = v107;
        *((_DWORD *)v9 + 18) = v107;
        sqlite3VdbeAddOp3(v113, 36, v154, v166, v72);
        v161 = *(_DWORD *)(v113 + 144);
        v121 = v153;
        if ( !v153 )
        {
          v116 = Vdbe;
          sqlite3VdbeAddOp3(Vdbe, 134, v154, v158, 0);
          v115 = v151;
          sqlite3VdbeAddOp4Int(Vdbe, 28, v151, v107, v158, 0);
          goto LABEL_239;
        }
        if ( v199 == 2 )
        {
          v116 = Vdbe;
          v115 = v151;
          goto LABEL_240;
        }
        if ( v169 )
        {
          v122 = 0;
          if ( v170 > 0 )
          {
            do
            {
              sqlite3VdbeAddOp3(v113, 94, v154, v122, v122 + v83);
              ++v122;
            }
            while ( v122 < v170 );
            v9 = a1;
          }
          v115 = v151;
          v148 = v83;
          v116 = Vdbe;
          sqlite3VdbeAddOp4Int(Vdbe, 28, v151, v107, v148, v170);
          goto LABEL_238;
        }
        v116 = Vdbe;
        v120 = v157;
        sqlite3VdbeAddOp3(Vdbe, 135, v154, v157, 0);
      }
      else
      {
        v116 = Vdbe;
        v119 = v154;
        sqlite3VdbeAddOp3(Vdbe, 36, v154, v166, v72);
        v107 = *((_DWORD *)v9 + 18) - 1;
        v120 = v157;
        v163 = v107;
        *((_DWORD *)v9 + 18) = v107;
        v161 = sqlite3VdbeAddOp3(Vdbe, 135, v154, v157, 0);
      }
      v115 = v151;
      sqlite3VdbeAddOp3(v116, 31, v151, v107, v120);
LABEL_239:
      v121 = v153;
LABEL_240:
      if ( v198 )
      {
        if ( v121 )
          sqlite3VdbeAddOp3(v116, 94, v119, v168, v165);
        else
          sqlite3ExprCode(v9, v179, v165);
        sqlite3VdbeAddOp3(v116, 13, v165, 0, 0);
      }
      if ( !v152 )
      {
        if ( v155 )
          goto LABEL_249;
        if ( !v176 )
        {
LABEL_264:
          v128 = a5;
          v129 = (int)a3;
          v130 = sqlite3TriggerColmask((_DWORD)v9, v176, (_DWORD)a3, 1, 1, v12, a5);
          LOWORD(v131) = *(_WORD *)(v12 + 54);
          v132 = v130;
          if ( (__int16)v131 <= 0 )
            goto LABEL_283;
          v133 = v171;
          v134 = 0;
          while ( 1 )
          {
            if ( v134 == *(__int16 *)(v12 + 52) )
              goto LABEL_279;
            v135 = *(_QWORD *)(v12 + 8);
            if ( (*(_BYTE *)(v135 + 24LL * v134 + 18) & 0x60) != 0 )
            {
              if ( (*(_BYTE *)(v135 + 24LL * v134 + 18) & 0x20) != 0 )
                --v133;
              goto LABEL_281;
            }
            v136 = *(int *)(v167 + 4LL * v134);
            if ( (int)v136 >= 0 )
            {
              if ( v153 )
              {
                v137 = v170;
                if ( v199 == 2 )
                  v137 = v131;
                sqlite3VdbeAddOp3(v116, 94, v154, v136 + v137, v133);
              }
              else
              {
                sqlite3ExprCode(v9, *(_QWORD *)&a3[8 * v136 + 2], v133);
              }
              goto LABEL_281;
            }
            if ( (v180 & 1) != 0 && v134 <= 31 && !_bittest(&v132, v134) )
            {
LABEL_279:
              sqlite3VdbeAddOp3(v116, 75, 0, v133, 0);
            }
            else
            {
              sqlite3ExprCodeGetColumnOfTable(v116, v12, v151, v134, v133);
              v178 = 0;
            }
LABEL_281:
            v131 = *(__int16 *)(v12 + 54);
            ++v134;
            ++v133;
            if ( v134 >= v131 )
            {
              v107 = v163;
              v129 = (int)a3;
              v128 = a5;
LABEL_283:
              if ( (*(_BYTE *)(v12 + 48) & 0x60) != 0 )
                sqlite3ComputeGeneratedColumns(v9, v171, v12);
              if ( (v180 & 1) != 0 )
              {
                sqlite3TableAffinity(v116, v12, v171);
                v138 = v157;
                sqlite3CodeRowTrigger((_DWORD)v9, v176, 130, v129, 1, v12, v157, v128, v107);
                if ( v199 != 2 )
                {
                  if ( v169 )
                    sqlite3VdbeAddOp4Int(v116, 28, v151, v107, v158, v174);
                  else
                    sqlite3VdbeAddOp3(v116, 31, v151, v107, v157);
                  v139 = v171;
                  v140 = 0;
                  v141 = v171;
                  if ( *(__int16 *)(v12 + 54) > 0 )
                  {
                    do
                    {
                      v142 = *(_QWORD *)(v12 + 8);
                      if ( (*(_BYTE *)(v142 + 24LL * v140 + 18) & 0x60) != 0 )
                      {
                        v20 = (*(_BYTE *)(v142 + 24LL * v140 + 18) & 0x20) == 0;
                        v143 = v141 - 1;
                        if ( v20 )
                          v143 = v141;
                        v141 = v143;
                      }
                      else if ( *(int *)(v167 + 4LL * v140) < 0 && v140 != *(__int16 *)(v12 + 52) )
                      {
                        sqlite3ExprCodeGetColumnOfTable(v116, v12, v151, v140, v141);
                      }
                      ++v140;
                      ++v141;
                    }
                    while ( v140 < *(__int16 *)(v12 + 54) );
                    v9 = a1;
                    v139 = v171;
                  }
                  if ( (*(_BYTE *)(v12 + 48) & 0x60) != 0 )
                    sqlite3ComputeGeneratedColumns(v9, v139, v12);
LABEL_303:
                  v138 = v157;
                  sqlite3GenerateConstraintChecks(
                    (_DWORD)v9,
                    v12,
                    v184,
                    v151,
                    v175,
                    v165,
                    v157,
                    v150,
                    a5,
                    v107,
                    (__int64)&v172,
                    v167,
                    0);
                  if ( v172 || v150 )
                  {
                    if ( v169 )
                      sqlite3VdbeAddOp4Int(v116, 28, v151, v107, v158, v174);
                    else
                      sqlite3VdbeAddOp3(v116, 31, v151, v107, v157);
                  }
                  if ( v155 )
                    sqlite3FkCheck((_DWORD)v9, v12, v157, 0, v167, v181);
                  sqlite3GenerateRowIndexDelete((_DWORD)v9, v12, v151, v175, v184, -1);
                  if ( v178 )
                    sqlite3VdbeAddOp3(v116, 143, v151, 0, 0);
                  v144 = v155;
                  if ( v155 > 1 || v150 )
                  {
                    sqlite3VdbeAddOp3(v116, 130, v151, 0, 0);
                    v144 = v155;
                  }
                  if ( v144 )
                    sqlite3FkCheck((_DWORD)v9, v12, 0, v165, v167, v181);
                  v145 = v156;
                  v146 = 6;
                  if ( v156 != 2 )
                    v146 = 4;
                  sqlite3CompleteInsertion((_DWORD)v9, v12, v151, v175, v165, v184, v146, 0, 0);
                  if ( v155 )
                    sqlite3FkActions((_DWORD)v9, v12, (_DWORD)a3, v157, v167, v181);
LABEL_323:
                  v147 = v187;
                  if ( v187 )
                    sqlite3VdbeAddOp3(v116, 86, v187, 1, 0);
                  if ( v176 )
                    sqlite3CodeRowTrigger((_DWORD)v9, v176, 130, (_DWORD)a3, 2, v12, v138, a5, v107);
                  if ( v145 != 1 )
                  {
                    sqlite3VdbeResolveLabel(v116, v107);
                    if ( v145 == 2 )
                      sqlite3WhereEnd(v177);
                    else
                      sqlite3VdbeAddOp3(v116, 39, v154, v161, 0);
                  }
                  sqlite3VdbeResolveLabel(v116, v166);
                  if ( !*((_BYTE *)v9 + 30) && !v9[23] && !a8 )
                    sqlite3AutoincrementEnd(v9);
                  if ( v147 )
                    sqlite3CodeChangeCount(v116, v147, "rows updated");
LABEL_337:
                  v10 = v167;
                  if ( v190 )
                    v190[47] = v191;
                  goto LABEL_62;
                }
              }
              else
              {
                if ( v199 != 2 )
                  goto LABEL_303;
                v138 = v157;
              }
              v145 = v156;
              goto LABEL_323;
            }
          }
        }
      }
      if ( !v155 )
      {
        v123 = 0;
        goto LABEL_251;
      }
LABEL_249:
      v123 = sqlite3FkOldmask(v9, v12);
LABEL_251:
      v124 = sqlite3TriggerColmask((_DWORD)v9, v176, (_DWORD)a3, 0, 3, v12, a5) | v123;
      v125 = 0;
      if ( *(__int16 *)(v12 + 54) > 0 )
      {
        v126 = v186;
        do
        {
          v127 = v126 + (__int16)sqlite3TableColumnToStorage(v12, (unsigned __int16)v125);
          if ( v124 == -1
            || v125 < 32 && _bittest(&v124, v125)
            || (*(_BYTE *)(*(_QWORD *)(v12 + 8) + 24LL * v125 + 18) & 1) != 0 )
          {
            sqlite3ExprCodeGetColumnOfTable(v116, v12, v115, v125, v127);
          }
          else
          {
            sqlite3VdbeAddOp3(v116, 75, 0, v127, 0);
          }
          ++v125;
        }
        while ( v125 < *(__int16 *)(v12 + 54) );
        v9 = a1;
        v107 = v163;
      }
      if ( !v198 && !v169 )
        sqlite3VdbeAddOp3(v116, 80, v157, v165, 0);
      goto LABEL_264;
    }
    v37 = 8LL * v36;
    v39 = sqlite3StrIHash(*(_QWORD *)&a3[v37 + 4]);
    v149 = v39;
    if ( !v153 )
    {
      if ( (unsigned int)sqlite3ResolveExprNames(v193, *(_QWORD *)&v40[v37 + 2]) )
        goto LABEL_61;
      v39 = v149;
      v40 = a3;
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= *(__int16 *)(v12 + 54) )
      {
        v47 = v179;
        v46 = v168;
        v35 = v198;
        goto LABEL_49;
      }
      v42 = *(_QWORD *)(v12 + 8);
      v43 = 3LL * j;
      if ( *(_BYTE *)(v42 + 24LL * j + 14) == v39 )
        break;
LABEL_39:
      v40 = a3;
    }
    v44 = *(const char **)(v42 + 24LL * j);
    v45 = sqlite3StrICmp(v44, *(_QWORD *)&v40[v37 + 4]);
    v38 = 0;
    if ( v45 )
    {
      v39 = v149;
      goto LABEL_39;
    }
    if ( j == *(__int16 *)(v12 + 52) )
    {
      v35 = 1;
      v46 = v36;
      v47 = *(_QWORD *)&a3[v37 + 2];
    }
    else
    {
      if ( v169 && (*(_BYTE *)(v42 + 8 * v43 + 18) & 1) != 0 )
      {
        v152 = 1;
      }
      else if ( (*(_BYTE *)(v42 + 8 * v43 + 18) & 0x60) != 0 )
      {
        sqlite3ErrorMsg(v9, "cannot UPDATE generated column \"%s\"", v44);
        goto LABEL_61;
      }
      v35 = v198;
      v46 = v168;
      v47 = v179;
    }
    *(_DWORD *)(v167 + 4LL * j) = v36;
LABEL_49:
    v48 = *(__int16 *)(v12 + 54);
    v168 = v46;
    v179 = v47;
    v198 = v35;
    if ( j >= v48 )
      break;
    v50 = j;
    if ( j >= 0 )
    {
      v52 = *(_QWORD *)(v12 + 8);
      v198 = v35;
      v179 = v47;
      v168 = v46;
      v51 = *(const char **)(v52 + 24LL * j);
    }
    else
    {
LABEL_54:
      v51 = "ROWID";
    }
    v53 = sqlite3AuthCheck(
            (_DWORD)v9,
            23,
            *(_QWORD *)v12,
            (_DWORD)v51,
            *(_QWORD *)(32LL * (int)v159 + *(_QWORD *)(v188 + 32)));
    if ( v53 == 1 )
      goto LABEL_61;
    if ( v53 == 2 )
      *(_DWORD *)(v167 + 4 * v50) = -1;
    ++v36;
    v32 = 0;
  }
  if ( !v169 && (unsigned int)sqlite3IsRowid(*(_QWORD *)&a3[v37 + 4], v38) )
  {
    v49 = *(_QWORD *)&a3[v37 + 2];
    v35 = 1;
    v198 = 1;
    v50 = -1;
    v179 = v49;
    v168 = v36;
    goto LABEL_54;
  }
  sqlite3ErrorMsg(v9, "no such column: %s", *(const char **)&a3[v37 + 4]);
  *((_BYTE *)v9 + 29) = 1;
LABEL_61:
  v10 = v167;
LABEL_62:
  v54 = v188;
  sqlite3DbFree(v188, v10);
  sqlite3SrcListDelete(v54, a2);
  sqlite3ExprListDeleteGeneric(v54, a3);
  result = a4;
  if ( a4 )
    return sqlite3ExprDeleteNN(v54);
  return result;
}

```

## disassembly

```asm
0x1800167c0  mov     rax, rsp
0x1800167c3  mov     [rax+20h], r9
0x1800167c7  mov     [rax+18h], r8
0x1800167cb  mov     [rax+10h], rdx
0x1800167cf  mov     [rax+8], rcx
0x1800167d3  push    rbp
0x1800167d4  push    rbx
0x1800167d5  push    rsi
0x1800167d6  push    rdi
0x1800167d7  push    r12
0x1800167d9  push    r13
0x1800167db  push    r14
0x1800167dd  push    r15
0x1800167df  lea     rbp, [rax-0D8h]
0x1800167e6  sub     rsp, 198h
0x1800167ed  xor     r15d, r15d
0x1800167f0  mov     rdi, rcx
0x1800167f3  xor     ecx, ecx
0x1800167f5  mov     [rbp+0D0h+var_D0], r15d
0x1800167f9  xorps   xmm0, xmm0
0x1800167fc  mov     [rbp+0D0h+var_48], rcx
0x180016803  mov     r14d, r15d
0x180016806  mov     [rbp+0D0h+var_100], r15d
0x18001680a  mov     rcx, [rdi]
0x18001680d  mov     [rbp+0D0h+var_A0], rcx
0x180016811  movups  [rbp+0D0h+var_78], xmm0
0x180016815  movups  [rbp+0D0h+var_68], xmm0
0x180016819  movups  [rbp+0D0h+var_58], xmm0
0x18001681d  cmp     [rdi+34h], r15d
0x180016821  jnz     loc_180016C73
0x180016827  mov     rcx, rdi
0x18001682a  call    sqlite3SrcListLookup
0x18001682f  mov     [rbp+0D0h+var_E8], rax
0x180016833  mov     rsi, rax
0x180016836  test    rax, rax
0x180016839  jz      loc_180016C73
0x18001683f  mov     r9, [rdi]
0x180016842  mov     rdx, [rax+60h]
0x180016846  mov     rcx, r9
0x180016849  call    sqlite3SchemaToIndex
0x18001684e  mov     [rbp+0D0h+var_13C], eax
0x180016851  cmp     [rsi+58h], r15
0x180016855  jnz     short loc_18001686A
0x180016857  mov     rax, [r9+20h]
0x18001685b  mov     rcx, [rax+38h]
0x18001685f  test    rcx, rcx
0x180016862  jz      short loc_180016873
0x180016864  cmp     [rcx+40h], r15
0x180016868  jz      short loc_180016873
0x18001686a  cmp     [rdi+0E5h], r15b
0x180016871  jz      short loc_18001687C
0x180016873  mov     rbx, [rbp+0D0h+arg_10]
0x18001687a  jmp     short loc_1800168A3
0x18001687c  mov     rbx, [rbp+0D0h+arg_10]
0x180016883  lea     rax, [rbp+0D0h+var_D0]
0x180016887  mov     r9, rbx
0x18001688a  mov     [rsp+1D0h+var_1B0], rax
0x18001688f  mov     r8d, 82h
0x180016895  mov     rdx, rsi
0x180016898  mov     rcx, rdi
0x18001689b  call    triggersReallyExist
0x1800168a0  mov     r15, rax
0x1800168a3  mov     r13, [rbp+0D0h+arg_8]
0x1800168aa  mov     al, [rsi+3Fh]
0x1800168ad  mov     [rbp+0D0h+var_F0], r15
0x1800168b1  mov     [rbp+0D0h+arg_30], al
0x1800168b7  cmp     dword ptr [r13+0], 1
0x1800168bc  jle     short loc_1800168C6
0x1800168be  mov     ebx, [rbx]
0x1800168c0  mov     [rsp+7Ch], ebx
0x1800168c4  jmp     short loc_1800168CB
0x1800168c6  mov     [rsp+7Ch], r14d
0x1800168cb  mov     rdx, rsi
0x1800168ce  mov     rcx, rdi
0x1800168d1  call    sqlite3ViewGetColumnNames
0x1800168d6  test    eax, eax
0x1800168d8  jnz     loc_180016C73
0x1800168de  mov     r8, r15
0x1800168e1  mov     rdx, rsi
0x1800168e4  mov     rcx, rdi
0x1800168e7  call    sqlite3IsReadOnly
0x1800168ec  test    eax, eax
0x1800168ee  jnz     loc_180016C73
0x1800168f4  mov     r9d, [rdi+38h]
0x1800168f8  mov     edx, r9d
0x1800168fb  mov     [rsp+1D0h+var_15C], r9d
0x180016900  mov     [rbp+0D0h+var_FC], edx
0x180016903  lea     r15d, [r9+1]
0x180016907  mov     [rdi+38h], r15d
0x18001690b  test    byte ptr [rsi+30h], 80h
0x18001690f  mov     [rbp+0D0h+var_F4], r15d
0x180016913  jnz     short loc_180016920
0x180016915  xor     eax, eax
0x180016917  mov     r11d, eax
0x18001691a  mov     [rbp+0D0h+var_110], rax
0x18001691e  jmp     short loc_180016931
0x180016920  mov     rcx, rsi
0x180016923  call    sqlite3PrimaryKeyIndex
0x180016928  mov     r11, rax
0x18001692b  mov     [rbp+0D0h+var_110], rax
0x18001692f  xor     eax, eax
0x180016931  mov     rcx, [rsi+10h]
0x180016935  mov     r10d, eax
0x180016938  mov     [rbp+0D0h+var_B0], eax
0x18001693b  test    rcx, rcx
0x18001693e  jz      short loc_180016978
0x180016940  mov     r8d, r15d
0x180016943  mov     edx, r15d
0x180016946  cmp     r11, rcx
0x180016949  mov     eax, edx
0x18001694b  cmovnz  edx, r8d
0x18001694f  cmovnz  eax, r9d
0x180016953  inc     r10d
0x180016956  mov     r9d, eax
0x180016959  lea     r8d, [rdx+1]
0x18001695d  mov     [rdi+38h], r8d
0x180016961  mov     edx, r8d
0x180016964  mov     rcx, [rcx+28h]
0x180016968  test    rcx, rcx
0x18001696b  jnz     short loc_180016946
0x18001696d  mov     edx, [rbp+0D0h+var_FC]
0x180016970  mov     [rbp+0D0h+var_B0], r10d
0x180016974  mov     [rsp+1D0h+var_15C], eax
0x180016978  mov     r12, [rbp+0D0h+arg_38]
0x18001697f  test    r12, r12
0x180016982  jz      short loc_180016999
0x180016984  mov     r9d, [r12+4Ch]
0x180016989  mov     eax, [r12+50h]
0x18001698e  mov     [rsp+1D0h+var_15C], r9d
0x180016993  mov     [rbp+0D0h+var_F4], eax
0x180016996  mov     [rdi+38h], edx
0x180016999  mov     rcx, [rbp+0D0h+var_A0]
0x18001699d  mov     [r13+28h], r9d
0x1800169a1  movsx   eax, word ptr [rsi+36h]
0x1800169a5  inc     eax
0x1800169a7  movsxd  rbx, r10d
0x1800169aa  add     eax, r10d
0x1800169ad  cdqe
0x1800169af  lea     rdx, ds:2[rax*4]
0x1800169b7  add     rdx, rbx
0x1800169ba  call    sqlite3DbMallocRawNN
0x1800169bf  mov     [rbp+0D0h+var_120], rax
0x1800169c3  mov     r14, rax
0x1800169c6  test    rax, rax
0x1800169c9  jz      loc_180016C73
0x1800169cf  movsx   rcx, word ptr [rsi+36h]
0x1800169d4  lea     r13, [rbx+1]
0x1800169d8  mov     r8, r13; Size
0x1800169db  mov     [rbp+0D0h+Size], r13
0x1800169df  mov     edx, 1; Val
0x1800169e4  lea     rax, [rax+rcx*4]
0x1800169e8  lea     r15, [rax+4]
0x1800169ec  mov     [rbp+0D0h+var_B8], rax
0x1800169f0  lea     r15, [r15+rbx*4]
0x1800169f4  mov     rcx, r15; void *
0x1800169f7  mov     [rbp+0D0h+var_C0], r15
0x1800169fb  call    memset_0
0x180016a00  mov     byte ptr [r15+r13], 0
0x180016a05  xor     r15d, r15d
0x180016a08  mov     ecx, r15d
0x180016a0b  cmp     r15w, [rsi+36h]
0x180016a10  jge     short loc_180016A27
0x180016a12  movsxd  rax, ecx
0x180016a15  inc     ecx
0x180016a17  mov     dword ptr [r14+rax*4], 0FFFFFFFFh
0x180016a1f  movsx   eax, word ptr [rsi+36h]
0x180016a23  cmp     ecx, eax
0x180016a25  jl      short loc_180016A12
0x180016a27  mov     rbx, [rbp+0D0h+arg_8]
0x180016a2e  xorps   xmm0, xmm0
0x180016a31  mov     rcx, rdi
0x180016a34  mov     qword ptr [rbp+0D0h+var_78+8], rbx
0x180016a38  movdqu  [rbp+0D0h+var_68+8], xmm0
0x180016a3d  mov     qword ptr [rbp+0D0h+var_58+0Ch], r15
0x180016a44  mov     dword ptr [rbp+0D0h+var_48+4], r15d
0x180016a4b  mov     qword ptr [rbp+0D0h+var_78], rdi
0x180016a4f  mov     qword ptr [rbp+0D0h+var_68], r12
0x180016a53  mov     dword ptr [rbp+0D0h+var_58+8], 200h
0x180016a5d  call    sqlite3GetVdbe
0x180016a62  mov     [rbp+0D0h+var_130], rax
0x180016a66  test    rax, rax
0x180016a69  jz      loc_180016C73
0x180016a6f  mov     [rbp+0D0h+var_D8], r15
0x180016a73  mov     r13b, r15b
0x180016a76  mov     [rbp+0D0h+var_118], 0FFFFFFFFh
0x180016a7d  mov     r12d, r15d
0x180016a80  mov     [rsp+78h], r15b
0x180016a85  mov     [rbp+0D0h+arg_28], r15b
0x180016a8c  mov     r9, [rbp+0D0h+arg_10]
0x180016a93  cmp     r12d, [r9]
0x180016a96  jge     loc_180016CE5
0x180016a9c  movsxd  rbx, r12d
0x180016a9f  shl     rbx, 5
0x180016aa3  mov     rcx, [rbx+r9+10h]
0x180016aa8  call    sqlite3StrIHash
0x180016aad  mov     cl, al
0x180016aaf  mov     [rsp+1D0h+var_160], al
0x180016ab3  cmp     [rsp+7Ch], r15d
0x180016ab8  jnz     short loc_180016ADB
0x180016aba  mov     rdx, [rbx+r9+8]
0x180016abf  lea     rcx, [rbp+0D0h+var_78]
0x180016ac3  call    sqlite3ResolveExprNames
0x180016ac8  test    eax, eax
0x180016aca  jnz     loc_180016C6F
0x180016ad0  mov     cl, [rsp+1D0h+var_160]
0x180016ad4  mov     r9, [rbp+0D0h+arg_10]
0x180016adb  mov     r11d, r15d
0x180016ade  movsx   eax, word ptr [rsi+36h]
0x180016ae2  cmp     r11d, eax
0x180016ae5  jge     loc_180016B7E
0x180016aeb  mov     r15, [rsi+8]
0x180016aef  movsxd  rax, r11d
0x180016af2  lea     r14, [rax+rax*2]
0x180016af6  cmp     [r15+r14*8+0Eh], cl
0x180016afb  jnz     short loc_180016B18
0x180016afd  mov     r13, [r15+r14*8]
0x180016b01  mov     rdx, [rbx+r9+10h]
0x180016b06  mov     rcx, r13
0x180016b09  call    sqlite3StrICmp
0x180016b0e  xor     edx, edx
0x180016b10  test    eax, eax
0x180016b12  jz      short loc_180016B24
0x180016b14  mov     cl, [rsp+1D0h+var_160]
0x180016b18  mov     r9, [rbp+0D0h+arg_10]
0x180016b1f  inc     r11d
0x180016b22  jmp     short loc_180016ADE
0x180016b24  movsx   eax, word ptr [rsi+34h]
0x180016b28  cmp     r11d, eax
0x180016b2b  jnz     short loc_180016B41
0x180016b2d  mov     r9, [rbp+0D0h+arg_10]
0x180016b34  mov     r13b, 1
0x180016b37  mov     r15d, r12d
0x180016b3a  mov     r14, [rbx+r9+8]
0x180016b3f  jmp     short loc_180016B71
0x180016b41  cmp     [rbp+0D0h+var_110], rdx
0x180016b45  jz      short loc_180016B56
0x180016b47  test    byte ptr [r15+r14*8+12h], 1
0x180016b4d  jz      short loc_180016B56
0x180016b4f  mov     byte ptr [rsp+78h], 1
0x180016b54  jmp     short loc_180016B62
0x180016b56  test    byte ptr [r15+r14*8+12h], 60h
0x180016b5c  jnz     loc_180016C5D
0x180016b62  mov     r13b, [rbp+0D0h+arg_28]
0x180016b69  mov     r15d, [rbp+0D0h+var_118]
0x180016b6d  mov     r14, [rbp+0D0h+var_D8]
0x180016b71  mov     rcx, [rbp+0D0h+var_120]
0x180016b75  movsxd  rax, r11d
0x180016b78  mov     [rcx+rax*4], r12d
0x180016b7c  jmp     short loc_180016B8D
0x180016b7e  mov     r14, [rbp+0D0h+var_D8]
0x180016b82  mov     r15d, [rbp+0D0h+var_118]
0x180016b86  mov     r13b, [rbp+0D0h+arg_28]
0x180016b8d  movsx   eax, word ptr [rsi+36h]
0x180016b91  mov     [rbp+0D0h+var_118], r15d
0x180016b95  mov     [rbp+0D0h+var_D8], r14
0x180016b99  mov     [rbp+0D0h+arg_28], r13b
0x180016ba0  cmp     r11d, eax
0x180016ba3  jl      short loc_180016BE8
0x180016ba5  mov     r14, [rbp+0D0h+arg_10]
0x180016bac  xor     r15d, r15d
0x180016baf  cmp     [rbp+0D0h+var_110], r15
0x180016bb3  jnz     loc_180016CCB
0x180016bb9  mov     rcx, [rbx+r14+10h]
0x180016bbe  call    sqlite3IsRowid
0x180016bc3  test    eax, eax
0x180016bc5  jz      loc_180016CCB
0x180016bcb  mov     rdx, [rbx+r14+8]
0x180016bd0  mov     r13b, 1
0x180016bd3  mov     [rbp+0D0h+arg_28], r13b
0x180016bda  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016bde  mov     [rbp+0D0h+var_D8], rdx
0x180016be2  mov     [rbp+0D0h+var_118], r12d
0x180016be6  jmp     short loc_180016BF0
0x180016be8  movsxd  rbx, r11d
0x180016beb  test    r11d, r11d
0x180016bee  jns     short loc_180016BF9
0x180016bf0  lea     r9, aRowid_2; "ROWID"
0x180016bf7  jmp     short loc_180016C14
0x180016bf9  mov     rax, [rsi+8]
0x180016bfd  lea     rcx, [rbx+rbx*2]
0x180016c01  mov     [rbp+0D0h+arg_28], r13b
0x180016c08  mov     [rbp+0D0h+var_D8], r14
0x180016c0c  mov     [rbp+0D0h+var_118], r15d
0x180016c10  mov     r9, [rax+rcx*8]
0x180016c14  mov     rax, [rbp+0D0h+var_A0]
0x180016c18  mov     edx, 17h
0x180016c1d  movsxd  rcx, [rbp+0D0h+var_13C]
0x180016c21  mov     r8, [rsi]
0x180016c24  shl     rcx, 5
0x180016c28  mov     rax, [rax+20h]
0x180016c2c  mov     rcx, [rcx+rax]
0x180016c30  mov     [rsp+1D0h+var_1B0], rcx
0x180016c35  mov     rcx, rdi
0x180016c38  call    sqlite3AuthCheck
0x180016c3d  cmp     eax, 1
0x180016c40  jz      short loc_180016C6F
0x180016c42  cmp     eax, 2
0x180016c45  jnz     short loc_180016C52
0x180016c47  mov     rax, [rbp+0D0h+var_120]
0x180016c4b  mov     dword ptr [rax+rbx*4], 0FFFFFFFFh
  ... truncated ...
```
