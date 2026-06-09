# sqlite3Update

- ea: `0x18000a954`
- end: `0x18000c62d`
- name: `sqlite3Update`
- size: `7385`
- prototype: ``
- caller_count: `3`
- callee_count: `57`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000213c`
- `0x1800544ac`
- `0x18007be68`

## callees

- `0x1800071bc`
- `0x1800071dc`
- `0x180007ac0`
- `0x180009884`
- `0x180009ac0`
- `0x180009b98`
- `0x180009c54`
- `0x180009ccc`
- `0x180009e04`
- `0x180009e78`
- `0x180009ef0`
- `0x18000a754`
- `0x18000a954`
- `0x18000c640`
- `0x18000d04c`
- `0x180011bcc`
- `0x1800136f0`
- `0x1800147b8`
- `0x1800151f0`
- `0x180015460`
- `0x180015700`
- `0x180015eb0`
- `0x1800168c0`
- `0x180018d00`
- `0x180019470`
- `0x18001bb70`
- `0x18001bc5c`
- `0x18001c170`
- `0x18001c9b4`
- `0x18001cb40`
- `0x18001d0e0`
- `0x18001e090`
- `0x18001e860`
- `0x18002319c`
- `0x180041d10`
- `0x180051998`
- `0x180051e60`
- `0x180051fd0`
- `0x180052008`
- `0x1800595c4`
- `0x18005c76c`
- `0x18005d8a0`
- `0x18005db24`
- `0x18005e15c`
- `0x18005fa10`
- `0x180062418`
- `0x18006a580`
- `0x18006ac58`
- `0x1800707f8`
- `0x180070c9c`

## string_xrefs

- `0x18000bdf3`: `cannot UPDATE generated column "%s"`
- `0x18000c616`: `rows updated`

## pseudocode

```c
__int64 __fastcall sqlite3Update(
        __int64 a1,
        __int64 a2,
        int *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // r13
  __int64 v12; // r15
  __int64 v13; // rax
  _QWORD *v14; // r14
  __int64 v15; // rcx
  int v16; // r13d
  __int64 v17; // rdx
  __int64 v18; // rax
  char v19; // cl
  int v20; // r10d
  int v21; // edx
  int v22; // edi
  bool v23; // zf
  __int64 v24; // r11
  __int64 v25; // rcx
  int v26; // r9d
  int v27; // r8d
  int v28; // edx
  int v29; // eax
  _QWORD *v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rax
  void *v33; // rdi
  int v34; // edi
  int i; // ecx
  __int64 v36; // rax
  __int64 v37; // r8
  const char *v38; // r9
  int v39; // r15d
  __int64 v40; // rdi
  int *v41; // r11
  char v42; // cl
  int v43; // eax
  int v44; // ebx
  __int64 v45; // r9
  unsigned __int8 *v46; // r11
  _BYTE *v47; // r10
  __int64 v48; // rax
  int m; // r8d
  signed int v50; // r9d
  int v51; // edx
  __int64 v52; // rdi
  int v53; // r8d
  __int64 v54; // rax
  _DWORD *v55; // rcx
  __int64 v56; // rdx
  void *v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rax
  int *v60; // rdi
  int v61; // r11d
  __int64 v62; // r9
  signed int v63; // r12d
  unsigned int v64; // r13d
  int v65; // r12d
  int v66; // r12d
  unsigned int v67; // ebx
  int v68; // edi
  int v69; // eax
  int v70; // r13d
  unsigned int v71; // r12d
  _QWORD *v72; // rbx
  __int64 result; // rax
  int v74; // ecx
  __int64 v75; // r10
  int v76; // r12d
  _QWORD *v77; // r8
  int v78; // edi
  unsigned int v79; // r15d
  _BYTE *v80; // rdx
  _QWORD *v81; // r15
  int v82; // r13d
  int v83; // edi
  int v84; // r8d
  int v85; // ebx
  int v86; // eax
  unsigned __int8 v87; // r12
  int v88; // eax
  __int64 v89; // r10
  __int64 v90; // r8
  __int64 v91; // rdx
  __int64 k; // rdx
  int v93; // r15d
  __int16 v94; // ax
  __int64 v95; // r12
  __int64 v96; // rcx
  __int64 (__fastcall *v97)(_QWORD, __int64, _QWORD, const char *, _QWORD, _QWORD); // rax
  unsigned __int8 v98; // r12
  unsigned __int8 v99; // cl
  __int64 v100; // rdi
  int v101; // eax
  __int64 v102; // r9
  __int64 v103; // rbx
  int v104; // r15d
  _BYTE *v105; // r13
  int v106; // r14d
  int v107; // edi
  int j; // r15d
  __int64 v109; // rax
  __int64 v110; // rdx
  int *v111; // rdi
  __int64 v112; // rdx
  int *v113; // rbx
  int v114; // edx
  __int64 v115; // r8
  int v116; // eax
  int v117; // ecx
  char v118; // bl
  int v119; // eax
  __int64 v120; // r9
  __int16 v121; // di
  int v122; // r13d
  int v123; // eax
  int v124; // ebx
  unsigned int v125; // r12d
  int v126; // eax
  __int64 v127; // rax
  __int16 v128; // ax
  __int64 v129; // rax
  __int64 v130; // rbx
  int v131; // edi
  int v132; // eax
  int v133; // ecx
  __int16 v134; // ax
  unsigned int v135; // edi
  __int64 v136; // rax
  int v138; // eax
  int v139; // edi
  __int64 v140; // rdx
  int v141; // ecx
  __int64 v142; // rcx
  int v143; // edi
  __int64 v144; // rax
  __int64 v145; // rcx
  int v146; // r15d
  __int64 v147; // rdx
  __int64 v148; // rax
  int v149; // r9d
  __int64 v150; // rdx
  int v151; // edi
  int v152; // eax
  int v153; // r9d
  int v154; // r9d
  __int16 v155; // ax
  int v156; // ebx
  int v157; // r9d
  int v158; // edi
  int v159; // edi
  __int64 v160; // r8
  __int64 v161; // r9
  signed int v162; // ebx
  int v163; // r12d
  int v164; // edx
  __int64 v165; // r15
  __int64 v166; // rdi
  int v167; // ebx
  unsigned int v168; // ecx
  int v169; // ebx
  unsigned int v170; // edi
  __int64 v171; // rax
  unsigned int v172; // eax
  int v173; // [rsp+28h] [rbp-E0h]
  char v174; // [rsp+78h] [rbp-90h]
  char v175; // [rsp+78h] [rbp-90h]
  unsigned __int8 v176; // [rsp+79h] [rbp-8Fh]
  char v177; // [rsp+7Ah] [rbp-8Eh]
  int v178; // [rsp+7Ch] [rbp-8Ch]
  int v179; // [rsp+80h] [rbp-88h]
  int v180; // [rsp+80h] [rbp-88h]
  char v181; // [rsp+84h] [rbp-84h]
  int v182; // [rsp+88h] [rbp-80h]
  int v183; // [rsp+88h] [rbp-80h]
  unsigned int v184; // [rsp+88h] [rbp-80h]
  int v185; // [rsp+8Ch] [rbp-7Ch]
  int v186; // [rsp+90h] [rbp-78h]
  int v187; // [rsp+94h] [rbp-74h]
  int v188; // [rsp+98h] [rbp-70h]
  __int64 Vdbe; // [rsp+A0h] [rbp-68h]
  int v190; // [rsp+A8h] [rbp-60h]
  int v191; // [rsp+A8h] [rbp-60h]
  __int64 v192; // [rsp+B0h] [rbp-58h]
  __int16 v193; // [rsp+B8h] [rbp-50h]
  int v194; // [rsp+BCh] [rbp-4Ch]
  unsigned int v195; // [rsp+C0h] [rbp-48h]
  unsigned int v196; // [rsp+C4h] [rbp-44h]
  int v197; // [rsp+C8h] [rbp-40h]
  int v198; // [rsp+C8h] [rbp-40h]
  __int64 v199; // [rsp+D0h] [rbp-38h]
  int v200; // [rsp+D8h] [rbp-30h]
  unsigned int v201; // [rsp+DCh] [rbp-2Ch]
  int v202; // [rsp+E0h] [rbp-28h] BYREF
  int v203; // [rsp+E4h] [rbp-24h]
  int v204; // [rsp+E8h] [rbp-20h]
  __int64 v205; // [rsp+F0h] [rbp-18h]
  _QWORD *v206; // [rsp+F8h] [rbp-10h]
  int v207; // [rsp+100h] [rbp-8h]
  void *v208; // [rsp+108h] [rbp+0h] BYREF
  __int64 v209; // [rsp+110h] [rbp+8h]
  int v210; // [rsp+118h] [rbp+10h]
  int v211; // [rsp+11Ch] [rbp+14h] BYREF
  int v212; // [rsp+120h] [rbp+18h]
  __int64 v213; // [rsp+128h] [rbp+20h]
  __int64 v214; // [rsp+130h] [rbp+28h] BYREF
  int v215; // [rsp+138h] [rbp+30h]
  int v216; // [rsp+13Ch] [rbp+34h]
  _QWORD *v217; // [rsp+140h] [rbp+38h]
  __int64 v218; // [rsp+148h] [rbp+40h] BYREF
  __int64 v219; // [rsp+150h] [rbp+48h]
  __int64 v220; // [rsp+158h] [rbp+50h]
  _OWORD v221[7]; // [rsp+160h] [rbp+58h] BYREF

  v8 = 0;
  v9 = a1;
  v211 = 0;
  v10 = a4;
  v202 = 0;
  v12 = 0;
  v217 = *(_QWORD **)a1;
  memset(v221, 0, 56);
  if ( *(_DWORD *)(a1 + 48) )
    goto LABEL_91;
  v13 = sqlite3SrcListLookup(a1, a2);
  v206 = (_QWORD *)v13;
  v14 = (_QWORD *)v13;
  if ( !v13 )
    goto LABEL_91;
  v15 = *(_QWORD *)(v13 + 96);
  v16 = -32768;
  v179 = -32768;
  if ( v15 )
  {
    v16 = 0;
    v179 = 0;
    v17 = *(_QWORD *)(*(_QWORD *)v9 + 32LL);
    if ( *(_QWORD *)(v17 + 24) != v15 )
    {
      do
        ++v16;
      while ( *(_QWORD *)(32LL * v16 + v17 + 24) != v15 );
      v179 = v16;
    }
  }
  if ( (*(_QWORD *)(v13 + 88)
     || (v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v9 + 32LL) + 56LL)) != 0 && *(_QWORD *)(v18 + 64))
    && !*(_BYTE *)(v9 + 229) )
  {
    v8 = triggersReallyExist(v9, (_DWORD)v14, 129, (_DWORD)a3, (__int64)&v211);
  }
  v19 = *((_BYTE *)v14 + 63);
  v205 = v8;
  v177 = v19;
  if ( *(int *)a2 > 1 )
    v185 = *a3;
  else
    v185 = 0;
  if ( (v19 == 1 || *((__int16 *)v14 + 27) <= 0) && (unsigned int)viewGetColumnNames(v9, v14)
    || (unsigned int)sqlite3IsReadOnly(v9, v14, v8) )
  {
    goto LABEL_321;
  }
  v20 = *(_DWORD *)(v9 + 52);
  v21 = v20;
  v178 = v20;
  v190 = v20;
  v22 = v20 + 1;
  *(_DWORD *)(v9 + 52) = v20 + 1;
  v23 = *((_BYTE *)v14 + 48) >= 0;
  v204 = v20 + 1;
  if ( v23 )
  {
    v24 = 0;
    v199 = 0;
  }
  else
  {
    v24 = sqlite3PrimaryKeyIndex(v14);
    v199 = v24;
  }
  v25 = v14[2];
  v26 = 0;
  v210 = 0;
  if ( v25 )
  {
    v27 = v22;
    v28 = v22;
    do
    {
      v29 = v28;
      if ( v24 != v25 )
      {
        v28 = v27;
        v29 = v20;
      }
      ++v26;
      v20 = v29;
      v27 = v28 + 1;
      *(_DWORD *)(v9 + 52) = ++v28;
      v25 = *(_QWORD *)(v25 + 40);
    }
    while ( v25 );
    v21 = v190;
    v210 = v26;
    v178 = v29;
  }
  if ( a8 )
  {
    v20 = *(_DWORD *)(a8 + 76);
    v178 = v20;
    v204 = *(_DWORD *)(a8 + 80);
    *(_DWORD *)(v9 + 52) = v21;
  }
  v30 = v217;
  v31 = v26;
  *(_DWORD *)(a2 + 76) = v20;
  v32 = sqlite3DbMallocRawNN(v30, v26 + 4LL * (v26 + *((__int16 *)v14 + 27) + 1) + 2);
  v192 = v32;
  v12 = v32;
  if ( !v32 )
    goto LABEL_321;
  v213 = v32 + 4LL * *((__int16 *)v14 + 27);
  v33 = (void *)(v213 + 4 + 4 * v31);
  v208 = v33;
  memset_0(v33, 1, v31 + 1);
  *((_BYTE *)v33 + v31 + 1) = 0;
  v34 = 0;
  for ( i = 0; i < *((__int16 *)v14 + 27); *(_DWORD *)(v12 + 4 * v36) = -1 )
    v36 = i++;
  *((_QWORD *)&v221[0] + 1) = a2;
  *(_OWORD *)((char *)&v221[1] + 8) = 0;
  *(_QWORD *)((char *)&v221[2] + 12) = 0;
  DWORD1(v221[3]) = 0;
  *(_QWORD *)&v221[0] = v9;
  *(_QWORD *)&v221[1] = a8;
  DWORD2(v221[2]) = 512;
  Vdbe = sqlite3GetVdbe(v9);
  if ( !Vdbe )
    goto LABEL_321;
  v209 = 0;
  v39 = 0;
  v200 = -1;
  v181 = 0;
  v176 = 0;
  while ( 1 )
  {
    if ( v39 >= *a3 )
    {
      v98 = v176;
      v220 = 0;
      v99 = v181 + v176;
      v23 = (v14[6] & 0x60) == 0;
      v219 = 0;
      v188 = 0;
      v195 = 0;
      v201 = 0;
      v215 = 0;
      v198 = 0;
      v175 = v181 + v176;
      if ( !v23 )
      {
        do
        {
          v146 = 0;
          if ( *((__int16 *)v14 + 27) <= 0 )
            break;
          do
          {
            if ( *(int *)(v192 + 4LL * v34) < 0 )
            {
              v147 = v14[1] + 24LL * v34;
              if ( (*(_BYTE *)(v147 + 18) & 0x60) != 0 )
              {
                v148 = sqlite3ColumnExpr(v14, v147, v37, v38);
                if ( (unsigned int)sqlite3ExprReferencesUpdatedColumn(v148, v192, v176) )
                {
                  *(_DWORD *)(v192 + 4LL * v34) = 99999;
                  v146 = 1;
                }
              }
            }
            ++v34;
          }
          while ( v34 < *((__int16 *)v14 + 27) );
          v34 = 0;
        }
        while ( v146 );
        v16 = v179;
        v99 = v181 + v176;
      }
      v100 = v192;
      *(_QWORD *)(a2 + 88) = (*((_BYTE *)v14 + 63) != 1) - 1LL;
      v212 = v99;
      v101 = sqlite3FkRequired(v9, v14, v192, v99);
      v194 = v101;
      if ( (_DWORD)a5 == 5 )
        v202 = 1;
      v103 = v14[2];
      v183 = 0;
      v104 = 0;
      if ( v103 )
      {
        v105 = v208;
        v106 = v101;
        while ( 1 )
        {
          if ( v175 || v103 == v199 || v106 > 1 || (unsigned int)indexWhereClauseMightChange(v103, v100, v98) )
          {
            v107 = ++*(_DWORD *)(v9 + 56);
            *(_DWORD *)(v9 + 56) = v107 + *(unsigned __int16 *)(v103 + 96);
            goto LABEL_255;
          }
          v107 = 0;
          for ( j = 0; ; ++j )
          {
            if ( j >= *(unsigned __int16 *)(v103 + 94) )
            {
              v104 = v183;
LABEL_198:
              v105[v104 + 1] = 0;
              goto LABEL_199;
            }
            v136 = *(_QWORD *)(v103 + 8);
            v102 = j;
            if ( *(__int16 *)(v136 + 2LL * j) < 0
               ? sqlite3ExprReferencesUpdatedColumn(*(_QWORD *)(32LL * j + *(_QWORD *)(v103 + 80) + 8), v192, v98)
               : *(_DWORD *)(v192 + 4LL * *(__int16 *)(v136 + 2LL * j)) >= 0 )
            {
              break;
            }
          }
          v107 = ++*(_DWORD *)(v9 + 56);
          v104 = v183;
          *(_DWORD *)(v9 + 56) = v107 + *(unsigned __int16 *)(v103 + 96);
          if ( (_DWORD)a5 == 11 && *(_BYTE *)(v103 + 98) == 5 )
            v202 = 1;
LABEL_255:
          if ( !v107 )
            goto LABEL_198;
LABEL_199:
          v98 = v176;
          v109 = v104++;
          v183 = v104;
          *(_DWORD *)(v213 + 4 * v109) = v107;
          v103 = *(_QWORD *)(v103 + 40);
          if ( !v103 )
          {
            v14 = v206;
            v16 = v179;
            break;
          }
          v100 = v192;
        }
      }
      v110 = v213;
      v111 = (int *)(v9 + 56);
      *(_DWORD *)(v110 + 4LL * v104) = ++*(_DWORD *)(v9 + 56);
      if ( v202 )
        memset_0(v208, 1, v210 + 1);
      if ( !*(_BYTE *)(v9 + 30) )
      {
        *(_DWORD *)(Vdbe + 200) |= 0x10u;
        v111 = (int *)(v9 + 56);
      }
      if ( v205 )
      {
        v113 = v111;
      }
      else
      {
        if ( !v194 )
        {
          v112 = 0;
          v113 = v111;
          goto LABEL_208;
        }
        v113 = (int *)(v9 + 56);
      }
      v112 = 1;
LABEL_208:
      sqlite3BeginWriteOperation(v9, v112, (unsigned int)v16, v102);
      v75 = 0;
      if ( *((_BYTE *)v14 + 63) == 1 )
        goto LABEL_217;
      v114 = *(_DWORD *)(v9 + 56) + 1;
      v115 = v205;
      v188 = v114;
      v198 = *(_DWORD *)(v213 + 4LL * v104);
      *v111 = v114;
      if ( v181 )
      {
        v113 = v111;
      }
      else if ( !v115 )
      {
        v116 = v194;
        if ( !v194 )
        {
          v117 = v114;
          goto LABEL_213;
        }
      }
      v117 = v114 + *((__int16 *)v14 + 27);
      v215 = v114 + 1;
      v116 = v194;
      *v113 = v117;
LABEL_213:
      if ( v175 || v115 || v116 )
      {
        v114 = v117 + 1;
        *v113 = ++v117;
      }
      v195 = v114;
      v201 = v117 + 1;
      *v113 = v117 + *((__int16 *)v14 + 27);
LABEL_217:
      v118 = v177;
      if ( v177 == 2 )
      {
        v220 = *(_QWORD *)(v9 + 376);
        *(_QWORD *)(v9 + 376) = *v14;
        v219 = v9;
      }
      v10 = a4;
      if ( !v185 )
      {
        if ( v177 == 2 )
          sqlite3MaterializeView((__int64 *)v9, v14, a4, a6, a7, v178);
        v119 = sqlite3ResolveExprNames(v221, a4);
        v75 = 0;
        if ( v119 )
          goto LABEL_89;
      }
      if ( *((_BYTE *)v14 + 63) == 1 )
      {
        updateVirtualTable(v9, a2, (_DWORD)v14, (_DWORD)a3, v209, v192, a4, a5);
LABEL_89:
        v12 = v192;
        if ( v219 )
          *(_QWORD *)(v219 + 376) = v220;
        goto LABEL_91;
      }
      --*(_DWORD *)(v9 + 68);
      v120 = a8;
      v196 = *(_DWORD *)(v9 + 68);
      v216 = 0;
      if ( (v217[6] & 0x100000000LL) != 0
        && !*(_QWORD *)(v9 + 184)
        && !*(_BYTE *)(v9 + 30)
        && !*(_BYTE *)(v9 + 227)
        && !a8 )
      {
        v149 = *(_DWORD *)(v9 + 56) + 1;
        v216 = v149;
        *(_DWORD *)(v9 + 56) = v149;
        sqlite3VdbeAddOp3(Vdbe, 71, 0, v149, 0);
        v120 = 0;
        v75 = 0;
        v118 = v177;
      }
      if ( v185 || *((char *)v14 + 48) < 0 )
      {
        if ( v199 )
          v121 = *(_WORD *)(v199 + 94);
        else
          v121 = 0;
        v193 = v121;
        v122 = *(_DWORD *)(v9 + 56) + 1;
        v180 = v185 + v121 + v122;
        *(_DWORD *)(v9 + 56) = v180;
        if ( !v120 )
        {
          if ( v118 == 2 )
            v123 = *((__int16 *)v14 + 27);
          else
            v123 = 0;
          v124 = v185 + v121 + v123;
          v187 = *(_DWORD *)(v9 + 52);
          *(_DWORD *)(v9 + 52) = v187 + 1;
          if ( v199 )
            sqlite3VdbeAddOp3(Vdbe, 75, 0, v122, v121 + v122 - 1);
          v125 = sqlite3VdbeAddOp3(Vdbe, 118, v187, v124, 0);
          v184 = v125;
          v126 = v199;
          if ( v199 )
          {
            v127 = sqlite3KeyInfoOfIndex(v9, v199);
            if ( v127 )
            {
              *(_WORD *)(v127 + 8) = v124;
              sqlite3VdbeAppendP4(Vdbe, v127, 4294967288LL);
            }
            v126 = v199;
          }
          if ( !v185 )
          {
LABEL_239:
            v128 = 4;
            if ( !*(_BYTE *)(v9 + 30)
              && !v205
              && !v194
              && !v175
              && !v202
              && (!a4 || (*(_DWORD *)(a4 + 4) & 0x400000) == 0) )
            {
              v128 = 12;
            }
            v129 = sqlite3WhereBegin(v9, a2, a4, 0, 0, 0, v128, v204);
            v75 = 0;
            v206 = (_QWORD *)v129;
            if ( !v129 )
              goto LABEL_88;
            v130 = *(_QWORD *)(v129 + 40);
            v131 = *(unsigned __int8 *)(v129 + 66);
            v132 = *(_DWORD *)(v129 + 68) & 1;
            v218 = v130;
            v214 = v130;
            v186 = v131;
            v207 = v132;
            if ( v131 != 1 )
            {
              v142 = v9;
              if ( *(_QWORD *)(v9 + 176) )
                v142 = *(_QWORD *)(v9 + 176);
              *(_BYTE *)(v142 + 32) = 1;
              v133 = v178;
              if ( v131 == 2 && v130 >= 0 && HIDWORD(v130) != v178 )
              {
                v133 = v178;
                if ( *((_BYTE *)v208 + HIDWORD(v130) - v190) )
                  v186 = 0;
              }
LABEL_250:
              v23 = *((_BYTE *)v14 + 48) >= 0;
              v203 = 0;
              if ( !v23 )
              {
                v134 = v193;
                v135 = 0;
                if ( v193 > 0 )
                {
                  do
                  {
                    sqlite3ExprCodeGetColumnOfTable(
                      Vdbe,
                      (_DWORD)v14,
                      v178,
                      *(__int16 *)(*(_QWORD *)(v199 + 8) + 2LL * v135),
                      v135 + v122);
                    ++v135;
                  }
                  while ( (int)v135 < v193 );
                  LODWORD(v130) = v218;
                  v75 = 0;
                  v9 = a1;
                  v125 = v184;
                  v134 = v193;
                }
                v74 = v186;
                if ( v186 )
                {
                  if ( v125 )
                  {
                    sqlite3VdbeChangeToNoop(Vdbe, v125);
                    v74 = v186;
                    v75 = 0;
                  }
                  v76 = Vdbe;
                  v203 = v193;
                  v180 = v122;
                }
                else
                {
                  v143 = v134;
                  v144 = sqlite3IndexAffinityStr(v217);
                  v76 = Vdbe;
                  sqlite3VdbeAddOp4(Vdbe, 97, v122, v143, v180, v144, v143);
                  sqlite3VdbeAddOp4Int(Vdbe, 138, v187, v180, v122, v143);
                  v74 = 0;
                  v75 = 0;
                }
                goto LABEL_100;
              }
              sqlite3VdbeAddOp3(Vdbe, 135, v133, v188, 0);
              v74 = v186;
              v75 = 0;
              if ( v186 )
              {
                if ( !v125 )
                {
LABEL_278:
                  v76 = Vdbe;
LABEL_100:
                  v77 = v206;
                  goto LABEL_101;
                }
                sqlite3VdbeChangeToNoop(Vdbe, v125);
              }
              else
              {
                v140 = v213;
                v141 = *(_DWORD *)(v9 + 56) + 1;
                *(_DWORD *)(v9 + 56) = v141;
                *(_DWORD *)(v140 + 4LL * v104) = v141;
                sqlite3VdbeAddOp3(Vdbe, 128, v187, v198, v188);
              }
              v74 = v186;
              v75 = 0;
              goto LABEL_278;
            }
LABEL_249:
            v133 = v178;
            goto LABEL_250;
          }
          updateFromSelect(v9, v187, v126, (_DWORD)a3, a2, a4);
          v75 = 0;
          if ( v177 == 2 )
            v178 = v187;
LABEL_315:
          v145 = v9;
          LODWORD(v130) = v214;
          v76 = Vdbe;
          v77 = 0;
          if ( *(_QWORD *)(v9 + 176) )
            v145 = *(_QWORD *)(v9 + 176);
          v206 = 0;
          v207 = 1;
          v203 = v121;
          *(_BYTE *)(v145 + 32) = 1;
          v74 = 0;
          v186 = 0;
          v180 = v122;
LABEL_101:
          v182 = v196;
          v197 = 0;
          if ( a8 )
          {
            v81 = (_QWORD *)Vdbe;
            v82 = v178;
          }
          else
          {
            if ( !v185 && v74 != 2 )
            {
              sqlite3WhereEnd(v77);
              v75 = 0;
            }
            v78 = HIDWORD(v214);
            if ( v177 == 2 )
              goto LABEL_113;
            v79 = 0;
            LODWORD(v214) = 0;
            LODWORD(v218) = 0;
            if ( v186 )
            {
              v80 = v208;
              if ( (int)v130 >= 0 )
                *((_BYTE *)v208 + (int)v130 - v190) = 0;
              if ( v78 >= 0 )
                v80[v78 - v190] = 0;
              if ( v186 == 2 && v210 - (v78 >= 0) > 0 )
                v79 = sqlite3VdbeAddOp3(v76, 15, 0, 0, 0);
            }
            sqlite3OpenTableAndIndices(v9, (_DWORD)v14, 113, 0, v190, (__int64)v208, (__int64)&v214, (__int64)&v218);
            v75 = 0;
            if ( v79 )
            {
              v150 = v79;
              v81 = (_QWORD *)Vdbe;
              sqlite3VdbeJumpHereOrPopInst(Vdbe, v150);
            }
            else
            {
LABEL_113:
              v81 = (_QWORD *)Vdbe;
            }
            if ( !v186 )
            {
              if ( v199 || v185 != (_DWORD)v75 )
              {
                v93 = *(_DWORD *)(v9 + 68) - 1;
                v85 = v187;
                v182 = v93;
                *(_DWORD *)(v9 + 68) = v93;
                sqlite3VdbeAddOp3(Vdbe, 36, v187, v196, v75);
                v197 = *(_DWORD *)(Vdbe + 144);
                v86 = v185;
                if ( !v185 )
                {
                  sqlite3VdbeAddOp3(Vdbe, 134, v187, v180, 0);
                  v82 = v178;
                  v154 = v93;
                  v81 = (_QWORD *)Vdbe;
                  sqlite3VdbeAddOp4Int(Vdbe, 28, v178, v154, v180, 0);
                  goto LABEL_124;
                }
                if ( v177 == 2 )
                {
                  v82 = v178;
                  v81 = (_QWORD *)Vdbe;
LABEL_125:
                  v87 = v176;
                  if ( v176 )
                  {
                    if ( v86 )
                      sqlite3VdbeAddOp3((_DWORD)v81, 94, v85, v200, v195);
                    else
                      sqlite3ExprCode(v9, v209, v195);
                    sqlite3VdbeAddOp3((_DWORD)v81, 13, v195, 0, 0);
                  }
                  if ( !v181 )
                  {
                    if ( v194 )
                      goto LABEL_359;
                    if ( !v205 )
                      goto LABEL_129;
                  }
                  if ( !v194 )
                  {
                    v158 = 0;
LABEL_360:
                    v159 = sqlite3TriggerColmask(v9, v205, (_DWORD)a3, 0, 3, (__int64)v14, a5) | v158;
                    v162 = 0;
                    if ( *((__int16 *)v14 + 27) > 0 )
                    {
                      v163 = v215;
                      do
                      {
                        v164 = v163 + (__int16)sqlite3TableColumnToStorage(v14, (unsigned __int16)v162, v160, v161);
                        if ( v159 == -1
                          || v162 < 32 && _bittest(&v159, v162)
                          || (*(_BYTE *)(v14[1] + 24LL * v162 + 18) & 1) != 0 )
                        {
                          sqlite3ExprCodeGetColumnOfTable((_DWORD)v81, (_DWORD)v14, v82, v162, v164);
                        }
                        else
                        {
                          sqlite3VdbeAddOp3((_DWORD)v81, 75, 0, v164, 0);
                        }
                        ++v162;
                      }
                      while ( v162 < *((__int16 *)v14 + 27) );
                      v9 = a1;
                      v87 = v176;
                    }
                    if ( !v87 && !v199 )
                      sqlite3VdbeAddOp3((_DWORD)v81, 80, v188, v195, 0);
LABEL_129:
                    v65 = a5;
                    v60 = a3;
                    v88 = sqlite3TriggerColmask(v9, v205, (_DWORD)a3, 1, 1, (__int64)v14, a5);
                    v62 = *((unsigned __int16 *)v14 + 27);
                    v61 = v88;
                    v191 = v88;
                    if ( (__int16)v62 > 0 )
                    {
                      v64 = v201;
                      v63 = 0;
                      while ( 1 )
                      {
                        if ( v63 == *((__int16 *)v14 + 26) )
                          goto LABEL_159;
                        v89 = v14[1];
                        v90 = *(unsigned __int16 *)(v89 + 24LL * v63 + 18);
                        if ( (v90 & 0x60) != 0 )
                        {
                          if ( (v90 & 0x20) != 0 )
                            --v64;
                          goto LABEL_56;
                        }
                        v91 = *(int *)(v192 + 4LL * v63);
                        if ( (int)v91 >= 0 )
                        {
                          if ( v185 )
                          {
                            v94 = v193;
                            if ( v177 == 2 )
                              v94 = v62;
                            sqlite3VdbeAddOp3((_DWORD)v81, 94, v187, v91 + v94, v64);
                          }
                          else
                          {
                            sqlite3ExprCode(v9, *(_QWORD *)&v60[8 * v91 + 2], v64);
                          }
                          goto LABEL_55;
                        }
                        if ( (v211 & 1) != 0 && v63 <= 31 && !_bittest(&v61, v63) )
                        {
LABEL_159:
                          sqlite3VdbeAddOp3((_DWORD)v81, 75, 0, v64, 0);
                          goto LABEL_55;
                        }
                        if ( v63 < 0 )
                        {
                          sqlite3VdbeAddOp3((_DWORD)v81, 135, v178, v64, 0);
                          goto LABEL_54;
                        }
                        if ( *((_BYTE *)v14 + 63) == 1 )
                          break;
                        if ( (v90 & 0x20) == 0 )
                        {
                          if ( *((char *)v14 + 48) >= 0 )
                          {
                            v50 = (__int16)sqlite3TableColumnToStorage(v14, (unsigned __int16)v63, v90, v62);
                          }
                          else
                          {
                            for ( k = v14[2]; k && (*(_DWORD *)(k + 100) & 3) != 2; k = *(_QWORD *)(k + 40) )
                              ;
                            for ( m = 0; m < *(unsigned __int16 *)(k + 96); ++m )
                            {
                              if ( (_WORD)v63 == *(_WORD *)(*(_QWORD *)(k + 8) + 2LL * m) )
                                goto LABEL_42;
                            }
                            LOWORD(m) = -1;
LABEL_42:
                            v50 = (__int16)m;
                          }
                          v51 = 94;
                          goto LABEL_44;
                        }
                        v165 = v81[3];
                        v166 = v89 + 24LL * v63;
                        if ( (v90 & 0x100) != 0 )
                        {
                          sqlite3ErrorMsg(v165, "generated column loop on \"%s\"", *(const char **)v166);
                        }
                        else
                        {
                          v167 = *(_DWORD *)(v165 + 64);
                          *(_WORD *)(v166 + 18) = v90 | 0x100;
                          *(_DWORD *)(v165 + 64) = v178 + 1;
                          sqlite3ExprCodeGeneratedColumn(v165, v14, v89 + 24LL * v63, v64);
                          *(_DWORD *)(v165 + 64) = v167;
                          *(_WORD *)(v166 + 18) &= ~0x100u;
                        }
                        v81 = (_QWORD *)Vdbe;
LABEL_53:
                        v60 = a3;
LABEL_54:
                        v207 = 0;
LABEL_55:
                        v61 = v191;
LABEL_56:
                        v62 = (unsigned int)*((__int16 *)v14 + 27);
                        ++v63;
                        ++v64;
                        if ( v63 >= (int)v62 )
                        {
                          v65 = a5;
                          goto LABEL_58;
                        }
                      }
                      v51 = 176;
                      v50 = v63;
LABEL_44:
                      sqlite3VdbeAddOp3((_DWORD)v81, v51, v178, v50, v64);
                      v52 = v14[1];
                      v53 = 0;
                      v54 = *(unsigned __int16 *)(v52 + 24LL * v63 + 16);
                      if ( (_WORD)v54 )
                      {
                        v208 = 0;
                        if ( !*((_BYTE *)v14 + 63) )
                        {
                          v55 = (_DWORD *)v14[10];
                          if ( v55 )
                          {
                            if ( *v55 >= (int)v54 )
                            {
                              v56 = *(_QWORD *)&v55[8 * v54 - 6];
                              if ( v56 )
                              {
                                LOBYTE(v53) = *(_BYTE *)(*v81 + 100LL);
                                valueFromExpr(*v81, v56, v53, *(_BYTE *)(v52 + 24LL * v63 + 12), (__int64)&v208);
                                v57 = v208;
                                if ( v208 )
                                {
                                  if ( *(_BYTE *)(*v81 + 103LL) )
                                  {
                                    freeP4(*v81, 4294967286LL, v208);
                                  }
                                  else
                                  {
                                    v58 = 3LL * *((int *)v81 + 36);
                                    v59 = v81[17];
                                    *(_BYTE *)(v59 + 8 * v58 - 23) = -10;
                                    *(_QWORD *)(v59 + 8 * v58 - 8) = v57;
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                      if ( *(_BYTE *)(v52 + 24LL * v63 + 12) == 69 && *((_BYTE *)v14 + 63) != 1 )
                        sqlite3VdbeAddOp3((_DWORD)v81, 87, v64, 0, 0);
                      goto LABEL_53;
                    }
LABEL_58:
                    if ( (v14[6] & 0x60) != 0 )
                      sqlite3ComputeGeneratedColumns(v9, v201, v14);
                    if ( (v211 & 1) != 0 )
                    {
                      sqlite3TableAffinity(v81, v14, v201);
                      v67 = v182;
                      v70 = v188;
                      sqlite3CodeRowTrigger(v9, v205, 129, (_DWORD)v60, 1, (__int64)v14, v188, v65, v182);
                      if ( v177 != 2 )
                      {
                        if ( v199 )
                        {
                          v66 = v180;
                          sqlite3VdbeAddOp4Int((_DWORD)v81, 28, v178, v182, v180, v203);
                        }
                        else
                        {
                          sqlite3VdbeAddOp3((_DWORD)v81, 31, v178, v182, v188);
                          v66 = v180;
                        }
                        v168 = v201;
                        v169 = 0;
                        v170 = v201;
                        if ( *((__int16 *)v14 + 27) > 0 )
                        {
                          do
                          {
                            v171 = v14[1];
                            if ( (*(_BYTE *)(v171 + 24LL * v169 + 18) & 0x60) != 0 )
                            {
                              v23 = (*(_BYTE *)(v171 + 24LL * v169 + 18) & 0x20) == 0;
                              v172 = v170 - 1;
                              if ( v23 )
                                v172 = v170;
                              v170 = v172;
                            }
                            else if ( *(int *)(v192 + 4LL * v169) < 0 && v169 != *((__int16 *)v14 + 26) )
                            {
                              sqlite3ExprCodeGetColumnOfTable((_DWORD)v81, (_DWORD)v14, v178, v169, v170);
                            }
                            ++v169;
                            ++v170;
                          }
                          while ( v169 < *((__int16 *)v14 + 27) );
                          v9 = a1;
                          v168 = v201;
                        }
                        if ( (v14[6] & 0x60) != 0 )
                          sqlite3ComputeGeneratedColumns(v9, v168, v14);
                        goto LABEL_63;
                      }
                    }
                    else
                    {
                      if ( v177 != 2 )
                      {
                        v66 = v180;
LABEL_63:
                        v67 = v182;
                        sqlite3GenerateConstraintChecks(
                          v9,
                          (_DWORD)v14,
                          v213,
                          v178,
                          v204,
                          v195,
                          v188,
                          v175,
                          a5,
                          v182,
                          (__int64)&v202,
                          v192,
                          0);
                        if ( v202 || v175 )
                        {
                          if ( v199 )
                            sqlite3VdbeAddOp4Int((_DWORD)v81, 28, v178, v182, v66, v203);
                          else
                            sqlite3VdbeAddOp3((_DWORD)v81, 31, v178, v182, v188);
                        }
                        if ( v194 )
                          sqlite3FkCheck(v9, (_DWORD)v14, v188, 0, v192, v212);
                        sqlite3GenerateRowIndexDelete(v9, (_DWORD)v14, v178, v204, v213, -1);
                        if ( v207 )
                          sqlite3VdbeAddOp3((_DWORD)v81, 143, v178, 0, 0);
                        if ( v194 > 1 || v175 )
                          sqlite3VdbeAddOp3((_DWORD)v81, 130, v178, 0, 0);
                        if ( v194 )
                          sqlite3FkCheck(v9, (_DWORD)v14, 0, v195, v192, v212);
                        v68 = v186;
                        v69 = 6;
                        if ( v186 != 2 )
                          v69 = 4;
                        sqlite3CompleteInsertion(v9, (_DWORD)v14, v178, v204, v195, v213, v69, 0, 0);
                        v70 = v188;
                        if ( v194 )
                          sqlite3FkActions(v9, (_DWORD)v14, (_DWORD)a3, v188, v192, v212);
                        goto LABEL_77;
                      }
                      v67 = v182;
                      v70 = v188;
                    }
                    v68 = v186;
LABEL_77:
                    v71 = v216;
                    if ( v216 )
                      sqlite3VdbeAddOp3((_DWORD)v81, 86, v216, 1, 0);
                    if ( v205 )
                      sqlite3CodeRowTrigger(v9, v205, 129, (_DWORD)a3, 2, (__int64)v14, v70, a5, v67);
                    if ( v68 != 1 )
                    {
                      sqlite3VdbeResolveLabel(v81, v67);
                      if ( v68 == 2 )
                        sqlite3WhereEnd(v206);
                      else
                        sqlite3VdbeAddOp3((_DWORD)v81, 39, v187, v197, 0);
                    }
                    sqlite3VdbeResolveLabel(v81, v196);
                    if ( !*(_BYTE *)(v9 + 30) && !a8 && !*(_QWORD *)(v9 + 184) )
                      sqlite3AutoincrementEnd(v9);
                    if ( v71 )
                      sqlite3CodeChangeCount(v81, v71, "rows updated");
LABEL_88:
                    v10 = a4;
                    goto LABEL_89;
                  }
LABEL_359:
                  v158 = sqlite3FkOldmask(v9, v14);
                  goto LABEL_360;
                }
                if ( v199 )
                {
                  v155 = v193;
                  v156 = 0;
                  if ( v193 > 0 )
                  {
                    do
                    {
                      sqlite3VdbeAddOp3(Vdbe, 94, v187, v156, v156 + v122);
                      ++v156;
                    }
                    while ( v156 < v193 );
                    v9 = a1;
                    v155 = v193;
                  }
                  v157 = v93;
                  v173 = v122;
                  v82 = v178;
                  v81 = (_QWORD *)Vdbe;
                  sqlite3VdbeAddOp4Int(Vdbe, 28, v178, v157, v173, v155);
                  goto LABEL_123;
                }
                v151 = v188;
                sqlite3VdbeAddOp3(Vdbe, 135, v187, v188, 0);
                v153 = v93;
                v81 = (_QWORD *)Vdbe;
              }
              else
              {
                v85 = v187;
                sqlite3VdbeAddOp3((_DWORD)v81, 36, v187, v196, v75);
                v151 = v188;
                v182 = *(_DWORD *)(v9 + 68) - 1;
                *(_DWORD *)(v9 + 68) = v182;
                v152 = sqlite3VdbeAddOp3(Vdbe, 135, v187, v188, 0);
                v153 = v182;
                v197 = v152;
                v81 = (_QWORD *)Vdbe;
              }
              v82 = v178;
              sqlite3VdbeAddOp3((_DWORD)v81, 31, v178, v153, v151);
              goto LABEL_124;
            }
            v82 = v178;
            if ( (_DWORD)v130 == v178 )
            {
              v83 = v180;
            }
            else
            {
              v23 = v78 == v178;
              v83 = v180;
              if ( !v23 )
              {
                sqlite3VdbeAddOp4Int((_DWORD)v81, 28, v178, v196, v180, v203);
                v75 = 0;
              }
            }
            if ( v186 != 1 )
            {
              v182 = *(_DWORD *)(v9 + 68) - 1;
              *(_DWORD *)(v9 + 68) = v182;
            }
            v84 = v188;
            if ( v199 != v75 )
              v84 = v83;
            sqlite3VdbeAddOp3((_DWORD)v81, 50, v84, v196, v75);
          }
LABEL_123:
          v85 = v187;
LABEL_124:
          v86 = v185;
          goto LABEL_125;
        }
        v187 = 0;
        if ( v185 )
          goto LABEL_315;
        v125 = 0;
        v184 = 0;
      }
      else
      {
        v193 = 0;
        v122 = 0;
        v180 = 0;
        sqlite3VdbeAddOp3(Vdbe, 75, 0, v198, v188);
        v187 = *(_DWORD *)(v9 + 52);
        *(_DWORD *)(v9 + 52) = v187 + 1;
        v184 = sqlite3VdbeAddOp3(Vdbe, 118, v187, 0, v198);
        v125 = v184;
        if ( !a8 )
          goto LABEL_239;
      }
      v206 = 0;
      v186 = 1;
      sqlite3ExprIfFalse(v9, a4, v196, 16);
      LODWORD(v130) = v214;
      v75 = 0;
      v207 = 0;
      v218 = v214;
      goto LABEL_249;
    }
    v40 = 8LL * v39;
    v174 = sqlite3StrIHash(*(_QWORD *)&a3[v40 + 4]);
    v42 = v174;
    if ( !v185 )
    {
      if ( (unsigned int)sqlite3ResolveExprNames(v221, *(_QWORD *)&v41[v40 + 2]) )
        goto LABEL_320;
      v42 = v174;
      v41 = a3;
    }
    v43 = *((__int16 *)v14 + 27);
    v44 = 0;
LABEL_35:
    if ( v44 < v43 )
      break;
    v95 = v209;
LABEL_177:
    if ( v44 >= *((__int16 *)v14 + 27) )
    {
      if ( v199 || !(unsigned int)sqlite3IsRowid(*(_QWORD *)&a3[v40 + 4]) )
      {
        sqlite3ErrorMsg(v9, "no such column: %s", *(const char **)&a3[v40 + 4]);
        *(_BYTE *)(v9 + 29) = 1;
        goto LABEL_320;
      }
      v44 = -1;
      v209 = *(_QWORD *)&a3[v40 + 2];
      v34 = 0;
      v176 = 1;
      v200 = v39;
LABEL_267:
      v38 = "ROWID";
      goto LABEL_180;
    }
    LOBYTE(v37) = v176;
    v34 = 0;
    v209 = v95;
    if ( v44 < 0 )
      goto LABEL_267;
    v209 = v95;
    v38 = *(const char **)(v14[1] + 24LL * v44);
LABEL_180:
    v96 = *(_QWORD *)v9;
    v97 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, const char *, _QWORD, _QWORD))(*(_QWORD *)v9 + 512LL);
    if ( !v97 || *(_BYTE *)(v96 + 197) || *(_BYTE *)(v9 + 308) )
    {
      v16 = v179;
    }
    else
    {
      v16 = v179;
      v138 = v97(*(_QWORD *)(v96 + 520), 23, *v14, v38, *(_QWORD *)(32LL * v179 + v217[4]), *(_QWORD *)(v9 + 376));
      v139 = v138;
      if ( v138 == 1 )
      {
        sqlite3ErrorMsg(v9, "not authorized");
        *(_DWORD *)(v9 + 24) = 23;
      }
      else if ( (v138 & 0xFFFFFFFD) != 0 )
      {
        v139 = 1;
        sqlite3ErrorMsg(v9, "authorizer malfunction");
        *(_DWORD *)(v9 + 24) = 1;
      }
      if ( v139 == 1 )
        goto LABEL_320;
      if ( v139 == 2 )
        *(_DWORD *)(v192 + 4LL * v44) = -1;
      v34 = 0;
    }
    ++v39;
  }
  v45 = v14[1];
  v37 = 3LL * v44;
  if ( *(_BYTE *)(v45 + 24LL * v44 + 14) != v42 )
    goto LABEL_175;
  v46 = *(unsigned __int8 **)&v41[v40 + 4];
  v47 = *(_BYTE **)(v45 + 24LL * v44);
  while ( 2 )
  {
    v48 = *v46;
    if ( (unsigned __int8)*v47 != (_DWORD)v48 )
    {
      if ( *((unsigned __int8 *)qword_1800B4ED0 + (unsigned __int8)*v47) != *((unsigned __int8 *)qword_1800B4ED0 + v48) )
      {
        v43 = *((__int16 *)v14 + 27);
        v42 = v174;
LABEL_175:
        v41 = a3;
        ++v44;
        goto LABEL_35;
      }
      goto LABEL_40;
    }
    if ( *v47 )
    {
LABEL_40:
      ++v47;
      ++v46;
      continue;
    }
    break;
  }
  if ( v44 == *((__int16 *)v14 + 26) )
  {
    v176 = 1;
    v200 = v39;
    v95 = *(_QWORD *)&a3[v40 + 2];
    goto LABEL_172;
  }
  if ( v199 && (*(_BYTE *)(v45 + 24LL * v44 + 18) & 1) != 0 )
  {
    v181 = 1;
LABEL_171:
    v95 = v209;
LABEL_172:
    *(_DWORD *)(v192 + 4LL * v44) = v39;
    goto LABEL_177;
  }
  if ( (*(_BYTE *)(v45 + 24LL * v44 + 18) & 0x60) == 0 )
    goto LABEL_171;
  sqlite3ErrorMsg(v9, "cannot UPDATE generated column \"%s\"", *(const char **)(v45 + 24LL * v44));
LABEL_320:
  v12 = v192;
LABEL_321:
  v10 = a4;
LABEL_91:
  v72 = v217;
  sqlite3DbFree(v217, v12);
  sqlite3SrcListDelete(v72, a2);
  result = (__int64)a3;
  if ( a3 )
    result = exprListDeleteNN(v72, a3);
  if ( v10 )
    return sqlite3ExprDeleteNN(v72);
  return result;
}

```

## disassembly

```asm
0x18000a954  mov     rax, rsp
0x18000a957  mov     [rax+20h], r9
0x18000a95b  mov     [rax+18h], r8
0x18000a95f  mov     [rax+10h], rdx
0x18000a963  mov     [rax+8], rcx
0x18000a967  push    rbp
0x18000a968  push    rbx
0x18000a969  push    rsi
0x18000a96a  push    rdi
0x18000a96b  push    r12
0x18000a96d  push    r13
0x18000a96f  push    r14
0x18000a971  push    r15
0x18000a973  lea     rbp, [rax-0D8h]
0x18000a97a  sub     rsp, 198h
0x18000a981  xor     edi, edi
0x18000a983  mov     rsi, rcx
0x18000a986  xor     ecx, ecx
0x18000a988  mov     [rbp+0D0h+var_BC], edi
0x18000a98b  xorps   xmm0, xmm0
0x18000a98e  mov     [rbp+0D0h+var_48], rcx
0x18000a995  mov     r13, r9
0x18000a998  mov     [rbp+0D0h+var_F8], edi
0x18000a99b  mov     rbx, r8
0x18000a99e  mov     rcx, [rsi]
0x18000a9a1  mov     r15d, edi
0x18000a9a4  mov     [rbp+0D0h+var_98], rcx
0x18000a9a8  movups  [rbp+0D0h+var_78], xmm0
0x18000a9ac  movups  [rbp+0D0h+var_68], xmm0
0x18000a9b0  movups  [rbp+0D0h+var_58], xmm0
0x18000a9b4  cmp     [rsi+30h], edi
0x18000a9b7  jnz     loc_18000AF43
0x18000a9bd  mov     rcx, rsi
0x18000a9c0  call    sqlite3SrcListLookup
0x18000a9c5  mov     [rbp+0D0h+var_E0], rax
0x18000a9c9  mov     r14, rax
0x18000a9cc  test    rax, rax
0x18000a9cf  jz      loc_18000AF43
0x18000a9d5  mov     rcx, [rax+60h]
0x18000a9d9  mov     r13d, 0FFFF8000h
0x18000a9df  mov     [rsp+1D0h+var_158], r13d
0x18000a9e4  test    rcx, rcx
0x18000a9e7  jz      short loc_18000AA13
0x18000a9e9  mov     rax, [rsi]
0x18000a9ec  mov     r13d, edi
0x18000a9ef  mov     [rsp+1D0h+var_158], edi
0x18000a9f3  mov     rdx, [rax+20h]
0x18000a9f7  cmp     [rdx+18h], rcx
0x18000a9fb  jz      short loc_18000AA13
0x18000a9fd  inc     r13d
0x18000aa00  movsxd  rax, r13d
0x18000aa03  shl     rax, 5
0x18000aa07  cmp     [rax+rdx+18h], rcx
0x18000aa0c  jnz     short loc_18000A9FD
0x18000aa0e  mov     [rsp+1D0h+var_158], r13d
0x18000aa13  cmp     [r14+58h], rdi
0x18000aa17  jnz     short loc_18000AA2F
0x18000aa19  mov     rax, [rsi]
0x18000aa1c  mov     rcx, [rax+20h]
0x18000aa20  mov     rax, [rcx+38h]
0x18000aa24  test    rax, rax
0x18000aa27  jz      short loc_18000AA58
0x18000aa29  cmp     [rax+40h], rdi
0x18000aa2d  jz      short loc_18000AA58
0x18000aa2f  cmp     [rsi+0E5h], dil
0x18000aa36  jnz     short loc_18000AA58
0x18000aa38  lea     rax, [rbp+0D0h+var_BC]
0x18000aa3c  mov     r9, rbx
0x18000aa3f  mov     r8d, 81h
0x18000aa45  mov     [rsp+1D0h+var_1B0], rax
0x18000aa4a  mov     rdx, r14
0x18000aa4d  mov     rcx, rsi
0x18000aa50  call    triggersReallyExist
0x18000aa55  mov     rdi, rax
0x18000aa58  mov     rax, [rbp+0D0h+arg_8]
0x18000aa5f  mov     cl, [r14+3Fh]
0x18000aa63  mov     [rbp+0D0h+var_E8], rdi
0x18000aa67  mov     byte ptr [rsp+1D0h+var_160+2], cl
0x18000aa6b  cmp     dword ptr [rax], 1
0x18000aa6e  jg      loc_18000BDE4
0x18000aa74  xor     ebx, ebx
0x18000aa76  mov     [rbp+0D0h+var_14C], ebx
0x18000aa79  cmp     cl, 1
0x18000aa7c  jz      loc_18000B9E0
0x18000aa82  cmp     [r14+36h], bx
0x18000aa87  jle     loc_18000B9E0
0x18000aa8d  mov     r8, rdi
0x18000aa90  mov     rdx, r14
0x18000aa93  mov     rcx, rsi
0x18000aa96  call    sqlite3IsReadOnly
0x18000aa9b  test    eax, eax
0x18000aa9d  jnz     loc_18000BE06
0x18000aaa3  mov     r10d, [rsi+34h]
0x18000aaa7  mov     edx, r10d
0x18000aaaa  mov     [rsp+1D0h+var_15C], r10d
0x18000aaaf  mov     [rbp+0D0h+var_130], edx
0x18000aab2  lea     edi, [r10+1]
0x18000aab6  mov     [rsi+34h], edi
0x18000aab9  test    byte ptr [r14+30h], 80h
0x18000aabe  mov     [rbp+0D0h+var_F0], edi
0x18000aac1  jz      loc_18000BA4B
0x18000aac7  mov     rcx, r14
0x18000aaca  call    sqlite3PrimaryKeyIndex
0x18000aacf  mov     r11, rax
0x18000aad2  mov     [rbp+0D0h+var_108], rax
0x18000aad6  xor     eax, eax
0x18000aad8  mov     rcx, [r14+10h]
0x18000aadc  mov     r9d, eax
0x18000aadf  mov     [rbp+0D0h+var_C0], eax
0x18000aae2  test    rcx, rcx
0x18000aae5  jz      short loc_18000AB1E
0x18000aae7  mov     r8d, edi
0x18000aaea  mov     edx, edi
0x18000aaec  cmp     r11, rcx
0x18000aaef  mov     eax, edx
0x18000aaf1  cmovnz  edx, r8d
0x18000aaf5  cmovnz  eax, r10d
0x18000aaf9  inc     r9d
0x18000aafc  mov     r10d, eax
0x18000aaff  lea     r8d, [rdx+1]
0x18000ab03  mov     [rsi+34h], r8d
0x18000ab07  mov     edx, r8d
0x18000ab0a  mov     rcx, [rcx+28h]
0x18000ab0e  test    rcx, rcx
0x18000ab11  jnz     short loc_18000AAEC
0x18000ab13  mov     edx, [rbp+0D0h+var_130]
0x18000ab16  mov     [rbp+0D0h+var_C0], r9d
0x18000ab1a  mov     [rsp+1D0h+var_15C], eax
0x18000ab1e  mov     r12, [rbp+0D0h+arg_38]
0x18000ab25  test    r12, r12
0x18000ab28  jnz     loc_18000BAF2
0x18000ab2e  mov     rax, [rbp+0D0h+arg_8]
0x18000ab35  mov     rcx, [rbp+0D0h+var_98]
0x18000ab39  movsxd  rbx, r9d
0x18000ab3c  mov     [rax+4Ch], r10d
0x18000ab40  movsx   eax, word ptr [r14+36h]
0x18000ab45  inc     eax
0x18000ab47  add     eax, r9d
0x18000ab4a  cdqe
0x18000ab4c  lea     rdx, ds:2[rax*4]
0x18000ab54  add     rdx, rbx
0x18000ab57  call    sqlite3DbMallocRawNN
0x18000ab5c  mov     [rbp+0D0h+var_128], rax
0x18000ab60  mov     r15, rax
0x18000ab63  test    rax, rax
0x18000ab66  jz      loc_18000BE06
0x18000ab6c  movsx   rcx, word ptr [r14+36h]
0x18000ab71  lea     r8, [rbx+1]; Size
0x18000ab75  mov     edx, 1; Val
0x18000ab7a  lea     rax, [rax+rcx*4]
0x18000ab7e  lea     rdi, [rax+4]
0x18000ab82  mov     [rbp+0D0h+var_B0], rax
0x18000ab86  lea     rdi, [rdi+rbx*4]
0x18000ab8a  mov     rcx, rdi; void *
0x18000ab8d  mov     [rbp+0D0h+var_D0], rdi
0x18000ab91  call    memset_0
0x18000ab96  mov     byte ptr [rbx+rdi+1], 0
0x18000ab9b  xor     edi, edi
0x18000ab9d  mov     ecx, edi
0x18000ab9f  cmp     di, [r14+36h]
0x18000aba4  jge     short loc_18000ABBC
0x18000aba6  movsxd  rax, ecx
0x18000aba9  inc     ecx
0x18000abab  mov     dword ptr [r15+rax*4], 0FFFFFFFFh
0x18000abb3  movsx   eax, word ptr [r14+36h]
0x18000abb8  cmp     ecx, eax
0x18000abba  jl      short loc_18000ABA6
0x18000abbc  mov     rbx, [rbp+0D0h+arg_8]
0x18000abc3  xorps   xmm0, xmm0
0x18000abc6  mov     rcx, rsi
0x18000abc9  mov     qword ptr [rbp+0D0h+var_78+8], rbx
0x18000abcd  movdqu  [rbp+0D0h+var_68+8], xmm0
0x18000abd2  mov     qword ptr [rbp+0D0h+var_58+0Ch], rdi
0x18000abd9  mov     dword ptr [rbp+0D0h+var_48+4], edi
0x18000abdf  mov     qword ptr [rbp+0D0h+var_78], rsi
0x18000abe3  mov     qword ptr [rbp+0D0h+var_68], r12
0x18000abe7  mov     dword ptr [rbp+0D0h+var_58+8], 200h
0x18000abf1  call    sqlite3GetVdbe
0x18000abf6  mov     [rbp+0D0h+var_138], rax
0x18000abfa  test    rax, rax
0x18000abfd  jz      loc_18000BE06
0x18000ac03  mov     [rbp+0D0h+var_C8], rdi
0x18000ac07  mov     r15d, edi
0x18000ac0a  mov     [rbp+0D0h+var_100], 0FFFFFFFFh
0x18000ac11  mov     [rsp+1D0h+var_154], dil
0x18000ac16  mov     byte ptr [rsp+1D0h+var_160+1], dil
0x18000ac1b  mov     r11, [rbp+0D0h+arg_10]
0x18000ac22  cmp     r15d, [r11]
0x18000ac25  jge     loc_18000B497
0x18000ac2b  movsxd  rdi, r15d
0x18000ac2e  shl     rdi, 5
0x18000ac32  mov     rcx, [r11+rdi+10h]
0x18000ac37  call    sqlite3StrIHash
0x18000ac3c  xor     r13d, r13d
0x18000ac3f  mov     byte ptr [rsp+1D0h+var_160], al
0x18000ac43  mov     cl, al
0x18000ac45  cmp     [rbp+0D0h+var_14C], r13d
0x18000ac49  jz      loc_18000B471
0x18000ac4f  movsx   eax, word ptr [r14+36h]
0x18000ac54  mov     ebx, r13d
0x18000ac57  cmp     ebx, eax
0x18000ac59  jge     loc_18000B405
0x18000ac5f  mov     r9, [r14+8]
0x18000ac63  movsxd  r13, ebx
0x18000ac66  lea     r8, ds:0[r13*2]
0x18000ac6e  add     r8, r13
0x18000ac71  cmp     [r9+r8*8+0Eh], cl
0x18000ac76  jnz     loc_18000B3F7
0x18000ac7c  mov     r12, [r9+r8*8]
0x18000ac80  mov     r11, [rdi+r11+10h]
0x18000ac85  mov     r10, r12
0x18000ac88  movzx   edx, byte ptr [r10]
0x18000ac8c  movzx   eax, byte ptr [r11]
0x18000ac90  cmp     edx, eax
0x18000ac92  jnz     loc_18000B3CD
0x18000ac98  xor     ecx, ecx
0x18000ac9a  test    edx, edx
0x18000ac9c  jz      loc_18000B394
0x18000aca2  inc     r10
0x18000aca5  inc     r11
0x18000aca8  jmp     short loc_18000AC88
0x18000acaa  or      r8d, 0FFFFFFFFh
0x18000acae  movsx   r9d, r8w
0x18000acb2  mov     edx, 5Eh ; '^'
0x18000acb7  mov     r8d, [rsp+1D0h+var_15C]
0x18000acbc  mov     rcx, r15
0x18000acbf  mov     dword ptr [rsp+1D0h+var_1B0], r13d
0x18000acc4  call    sqlite3VdbeAddOp3
0x18000acc9  mov     rdi, [r14+8]
0x18000accd  xor     r8d, r8d
0x18000acd0  movsxd  rax, r12d
0x18000acd3  lea     rbx, [rax+rax*2]
0x18000acd7  movzx   eax, word ptr [rdi+rbx*8+10h]
0x18000acdc  test    ax, ax
0x18000acdf  jz      short loc_18000AD53
0x18000ace1  mov     [rbp+0D0h+var_D0], r8
0x18000ace5  cmp     [r14+3Fh], r8b
0x18000ace9  jnz     short loc_18000AD53
0x18000aceb  mov     rcx, [r14+50h]
0x18000acef  test    rcx, rcx
0x18000acf2  jz      short loc_18000AD53
0x18000acf4  cmp     [rcx], eax
0x18000acf6  jl      short loc_18000AD53
0x18000acf8  shl     rax, 5
0x18000acfc  mov     rdx, [rax+rcx-18h]
0x18000ad01  test    rdx, rdx
0x18000ad04  jz      short loc_18000AD53
0x18000ad06  mov     rcx, [r15]
0x18000ad09  lea     rax, [rbp+0D0h+var_D0]
0x18000ad0d  mov     r9b, [rdi+rbx*8+0Ch]
0x18000ad12  mov     [rsp+1D0h+var_1B0], rax
0x18000ad17  mov     r8b, [rcx+64h]
0x18000ad1b  call    valueFromExpr
0x18000ad20  mov     rdx, [rbp+0D0h+var_D0]
0x18000ad24  xor     eax, eax
0x18000ad26  test    rdx, rdx
0x18000ad29  jz      short loc_18000AD53
0x18000ad2b  mov     rcx, [r15]
0x18000ad2e  cmp     [rcx+67h], al
0x18000ad31  jnz     loc_18000B336
0x18000ad37  movsxd  rax, dword ptr [r15+90h]
0x18000ad3e  lea     rcx, [rax+rax*2]
0x18000ad42  mov     rax, [r15+88h]
0x18000ad49  mov     byte ptr [rax+rcx*8-17h], 0F6h
0x18000ad4e  mov     [rax+rcx*8-8], rdx
0x18000ad53  cmp     byte ptr [rdi+rbx*8+0Ch], 45h ; 'E'
0x18000ad58  jz      loc_18000B2E0
0x18000ad5e  xor     ebx, ebx
0x18000ad60  mov     rdi, [rbp+0D0h+arg_10]
0x18000ad67  mov     [rbp+0D0h+var_D8], ebx
0x18000ad6a  mov     r11d, [rbp+0D0h+var_130]
0x18000ad6e  movsx   r9d, word ptr [r14+36h]
0x18000ad73  inc     r12d
0x18000ad76  inc     r13d
0x18000ad79  cmp     r12d, r9d
0x18000ad7c  jl      loc_18000B17C
0x18000ad82  mov     r12d, dword ptr [rbp+0D0h+arg_20]
0x18000ad89  test    byte ptr [r14+30h], 60h
0x18000ad8e  mov     ebx, [rbp+0D0h+var_FC]
0x18000ad91  jnz     loc_18000C383
0x18000ad97  test    byte ptr [rbp+0D0h+var_BC], 1
0x18000ad9b  jnz     loc_18000C395
0x18000ada1  cmp     byte ptr [rsp+1D0h+var_160+2], 2
0x18000ada6  jz      loc_18000BCEF
0x18000adac  mov     r12d, [rsp+1D0h+var_158]
0x18000adb1  mov     rax, [rbp+0D0h+var_128]
0x18000adb5  mov     rdx, r14
0x18000adb8  mov     ebx, [rbp+0D0h+var_150]
0x18000adbb  mov     rcx, rsi
0x18000adbe  mov     edi, [rbp+0D0h+var_140]
0x18000adc1  mov     r13d, [rsp+1D0h+var_15C]
0x18000adc6  mov     r9d, r13d
0x18000adc9  mov     r8, [rbp+0D0h+var_B0]
0x18000adcd  mov     [rsp+1D0h+var_170], 0
0x18000add6  mov     [rsp+1D0h+var_178], rax
0x18000addb  lea     rax, [rbp+0D0h+var_F8]
0x18000addf  mov     [rsp+1D0h+var_180], rax
0x18000ade4  mov     eax, dword ptr [rbp+0D0h+arg_20]
0x18000adea  mov     dword ptr [rsp+1D0h+var_188], ebx
0x18000adee  mov     byte ptr [rsp+1D0h+var_190], al
  ... truncated ...
```
