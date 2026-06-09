# sqlite3BeginTrigger

- ea: `0x1800fe6b0`
- end: `0x1800ff2bc`
- name: `sqlite3BeginTrigger`
- size: `3084`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `reparse_path`

## callers

- `0x180174050`

## callees

- `0x1800c9ef0`
- `0x1800ce5c0`
- `0x1800d1180`
- `0x1800e6050`
- `0x1800fdf90`
- `0x1800fe6b0`
- `0x180102f70`
- `0x180108840`
- `0x180109f90`
- `0x18010b290`
- `0x18010fd20`
- `0x180111a00`
- `0x18011a1c0`
- `0x18011eaa0`
- `0x18011f340`
- `0x180128f00`
- `0x180130eb0`
- `0x1801314e0`
- `0x1801341d0`
- `0x180147ca0`
- `0x180147d80`
- `0x180147eb0`
- `0x1801f7110`
- `0x1802421a0`
- `0x180242d80`

## string_xrefs

- `0x1800fedb9`: `sqlite_temp_master`
- `0x1800fe745`: `temporary trigger may not have qualified name`
- `0x1800feb09`: `cannot create triggers on virtual tables`
- `0x1800feb61`: `cannot create triggers on shadow tables`
- `0x1800febe2`: `trigger %T already exists`
- `0x1800feca3`: `cannot create trigger on system table`
- `0x1800fecf3`: `cannot create %s trigger on view: %S`
- `0x1800fed12`: `cannot create INSTEAD OF trigger on table: %S`

## pseudocode

```c
__int64 __fastcall sqlite3BeginTrigger(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        int *a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10)
{
  __int64 v11; // r15
  __int64 v12; // r13
  _QWORD *v13; // r12
  __int64 v14; // r14
  unsigned int v15; // edi
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 **v19; // r14
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  _OWORD *v24; // r15
  __int64 (__fastcall *v25)(); // rax
  __int64 *v26; // rdx
  int DbName; // eax
  int *v28; // r12
  int *v29; // rbx
  int v30; // r15d
  _QWORD *v31; // rsi
  __int64 v32; // rdi
  int v33; // eax
  __int64 *v34; // rax
  int *v35; // rax
  int v36; // edi
  __int64 v37; // rbx
  int v38; // eax
  int *v39; // rsi
  int v40; // r14d
  _DWORD *v41; // rsi
  __int64 v42; // rdx
  _DWORD *v43; // rdi
  int v44; // ebx
  _QWORD *v45; // rdi
  __int64 v46; // rax
  unsigned __int8 **v47; // r15
  __int64 v48; // rsi
  __int64 v49; // rdi
  __int64 v50; // rax
  __int64 *v51; // rcx
  int v52; // eax
  unsigned __int8 *v53; // r8
  int v54; // r10d
  int v55; // edx
  const char *v56; // r9
  __int64 v57; // rcx
  const char *v58; // r8
  unsigned __int8 *v59; // rcx
  int v60; // ebx
  unsigned __int8 **i; // rax
  __int64 v62; // rcx
  __int64 v63; // rdi
  __int64 v64; // rax
  const char *v65; // r8
  int v66; // r12d
  _QWORD *v67; // rdi
  __int64 v68; // rbx
  _QWORD *v69; // rdi
  _QWORD *v70; // rdi
  __int64 *v71; // rdi
  __int64 v72; // rax
  const char *v73; // r14
  _QWORD *v74; // rdi
  size_t v75; // rsi
  __int64 v76; // rax
  bool v77; // zf
  _QWORD *v78; // rax
  __int64 v79; // rdi
  __int64 result; // rax
  int *v81; // rsi
  _QWORD *v82; // rbx
  __int64 v83; // rax
  int v84; // eax
  __int64 v85; // rdx
  __int64 v86; // [rsp+30h] [rbp-D0h]
  unsigned int v87; // [rsp+38h] [rbp-C8h]
  _OWORD *v90; // [rsp+60h] [rbp-A0h]
  __int64 v91; // [rsp+68h] [rbp-98h] BYREF
  int v92; // [rsp+70h] [rbp-90h]
  __int64 v93; // [rsp+78h] [rbp-88h]
  __int64 v94; // [rsp+80h] [rbp-80h]
  __int64 v95; // [rsp+88h] [rbp-78h]
  __int64 v96; // [rsp+90h] [rbp-70h]
  int *v97; // [rsp+98h] [rbp-68h]
  _OWORD v98[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v99; // [rsp+C0h] [rbp-40h]
  __int128 v100; // [rsp+D0h] [rbp-30h]
  __int128 v101; // [rsp+E0h] [rbp-20h]
  __int128 v102; // [rsp+F0h] [rbp-10h]
  __int128 v103; // [rsp+100h] [rbp+0h]
  __int128 v104; // [rsp+110h] [rbp+10h]
  _QWORD *v105; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v106[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 (__fastcall *v107)(); // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v108)(); // [rsp+140h] [rbp+40h]
  int v109; // [rsp+148h] [rbp+48h]
  __int16 v110; // [rsp+14Ch] [rbp+4Ch]
  __int64 **v111; // [rsp+150h] [rbp+50h]
  __int64 v112; // [rsp+158h] [rbp+58h]
  bool v113; // [rsp+160h] [rbp+60h]
  __int64 v114; // [rsp+168h] [rbp+68h]
  const char *v115; // [rsp+170h] [rbp+70h]
  __int64 v116; // [rsp+178h] [rbp+78h]

  v11 = a2;
  v12 = *a1;
  v13 = a1;
  v97 = a6;
  v14 = 0;
  v93 = a8;
  v91 = a2;
  v95 = 0;
  v94 = 0;
  if ( a9 )
  {
    if ( *(_DWORD *)(a3 + 8) )
    {
      sqlite3ErrorMsg(a1, "temporary trigger may not have qualified name");
      goto LABEL_169;
    }
    v15 = 1;
    v87 = 1;
  }
  else
  {
    v87 = sqlite3TwoPartName(a1, a2, a3, &v91);
    v15 = v87;
    if ( (v87 & 0x80000000) != 0 )
      goto LABEL_169;
    v11 = v91;
  }
  v16 = a7;
  if ( !a7 || *(_BYTE *)(v12 + 103) )
    goto LABEL_169;
  if ( *(_BYTE *)(v12 + 197) && v15 != 1 )
  {
    if ( *(_QWORD *)(a7 + 16) )
    {
      sqlite3DbFreeNN(v12);
      v16 = a7;
    }
    *(_QWORD *)(v16 + 16) = 0;
  }
  v17 = sqlite3SrcListLookup(v13, v16);
  if ( !*(_BYTE *)(v12 + 197) && !*(_DWORD *)(a3 + 8) && v17 )
  {
    if ( *(_QWORD *)(v17 + 96) == *(_QWORD *)(*(_QWORD *)(v12 + 32) + 56LL) )
      v15 = 1;
    v87 = v15;
  }
  if ( *(_BYTE *)(v12 + 103) )
  {
LABEL_169:
    result = sqlite3SrcListDelete(v12, a7);
    v81 = v97;
    if ( v97 )
    {
      if ( *v97 > 0 )
      {
        v82 = v97 + 2;
        LODWORD(v83) = 0;
        do
        {
          if ( *v82 )
          {
            sqlite3DbFreeNN(v12);
            LODWORD(v83) = v95;
          }
          v83 = (unsigned int)(v83 + 1);
          v82 += 2;
          v95 = v83;
        }
        while ( (int)v83 < *v81 );
      }
      if ( (unsigned __int64)v81 < *(_QWORD *)(v12 + 480) )
      {
        if ( (unsigned __int64)v81 >= *(_QWORD *)(v12 + 464) )
        {
          result = *(_QWORD *)(v12 + 456);
          *(_QWORD *)v81 = result;
          *(_QWORD *)(v12 + 456) = v81;
          goto LABEL_188;
        }
        if ( (unsigned __int64)v81 >= *(_QWORD *)(v12 + 472) )
        {
          result = *(_QWORD *)(v12 + 440);
          *(_QWORD *)v81 = result;
          *(_QWORD *)(v12 + 440) = v81;
          goto LABEL_188;
        }
      }
      if ( *(_QWORD *)(v12 + 760) )
      {
        result = measureAllocationSize(v12, v81);
      }
      else if ( dword_1803379C0 )
      {
        if ( (_QWORD)xmmword_1803DC8D0 )
          xmmword_180337A40();
        v84 = (*((__int64 (__fastcall **)(int *))&xmmword_1803379F0 + 1))(v81);
        --qword_1803DC858;
        qword_1803DC810 -= v84;
        result = (*((__int64 (__fastcall **)(int *))&xmmword_1803379E0 + 1))(v81);
        if ( (_QWORD)xmmword_1803DC8D0 )
          result = xmmword_180337A50();
      }
      else
      {
        result = (*((__int64 (__fastcall **)(int *))&xmmword_1803379E0 + 1))(v81);
      }
    }
LABEL_188:
    v79 = a8;
    goto LABEL_189;
  }
  v18 = *v13;
  v19 = &v105;
  v105 = v13;
  v20 = 32LL * v15;
  v21 = *(_QWORD *)(v18 + 32);
  v99 = 0;
  memset(v98, 0, sizeof(v98));
  v114 = *(_QWORD *)(v20 + v21);
  v22 = *(_QWORD *)(v18 + 32);
  v100 = 0;
  v23 = *(_QWORD *)(v22 + v20 + 24);
  v115 = "trigger";
  v112 = v23;
  v113 = v15 == 1;
  v116 = v11;
  v24 = v98;
  v106[0] = v13;
  v106[1] = fixExprCb;
  v25 = fixSelectCb;
  v107 = fixSelectCb;
  v108 = std::_Associated_state<std::vector<asg::SemanticIndex::ItemMatch>>::_Run_deferred_function;
  v109 = 0;
  v110 = 0;
  v111 = &v105;
  v101 = 0;
  *((_QWORD *)&v99 + 1) = a7;
  v102 = 0;
  v90 = v98;
  v103 = 0;
  v104 = 0;
  while ( 2 )
  {
    if ( v25 != fixSelectCb )
    {
      v38 = ((__int64 (__fastcall *)(_QWORD *, _OWORD *))v25)(v106, v24);
      goto LABEL_45;
    }
    v26 = v19[9];
    v96 = **v19;
    DbName = sqlite3FindDbName(v96, v26);
    v28 = (int *)*((_QWORD *)v24 + 5);
    v92 = DbName;
    if ( !v28 )
      goto LABEL_40;
    v29 = v28 + 2;
    v30 = 0;
    if ( *v28 <= 0 )
    {
LABEL_35:
      v24 = v90;
      v35 = (int *)*((_QWORD *)v90 + 13);
      if ( v35 )
      {
        v36 = 0;
        if ( *v35 > 0 )
        {
          v37 = 0;
          while ( !(unsigned int)sqlite3WalkSelect(v106, *(_QWORD *)&v35[v37 + 8]) )
          {
            v35 = (int *)*((_QWORD *)v90 + 13);
            ++v36;
            v37 += 12;
            if ( v36 >= *v35 )
              goto LABEL_40;
          }
          v38 = 2;
          goto LABEL_45;
        }
      }
LABEL_40:
      v38 = 0;
      goto LABEL_45;
    }
    v31 = v28 + 20;
    while ( *((_BYTE *)v19 + 64) )
    {
LABEL_31:
      if ( (*(_DWORD *)(v31 - 1) & 0x400) == 0 && *v31 && (unsigned int)sqlite3WalkExprNN(v19 + 1) )
        goto LABEL_42;
      ++v30;
      v31 += 13;
      v29 += 26;
      if ( v30 >= *v28 )
        goto LABEL_35;
    }
    v32 = *((_QWORD *)v29 + 1);
    if ( !v32 )
    {
LABEL_30:
      v34 = v19[7];
      v29[16] |= 0x80u;
      *(_QWORD *)v29 = v34;
      goto LABEL_31;
    }
    v33 = sqlite3FindDbName(v96, *((_QWORD *)v29 + 1));
    if ( v92 == v33 )
    {
      sqlite3DbFreeNN(v96);
      v29[16] |= 0x200u;
      *((_QWORD *)v29 + 1) = 0;
      goto LABEL_30;
    }
    sqlite3ErrorMsg(*v19, "%s %T cannot reference objects in database %s", v19[10], v19[11], v32);
LABEL_42:
    v24 = v90;
    v38 = 2;
LABEL_45:
    if ( !v38 )
    {
      if ( (unsigned int)sqlite3WalkSelectExpr(v106, v24) )
        goto LABEL_168;
      v39 = (int *)*((_QWORD *)v24 + 5);
      if ( v39 )
      {
        v40 = *v39;
        if ( *v39 > 0 )
        {
          v41 = v39 + 18;
          while ( 1 )
          {
            v42 = *((_QWORD *)v41 - 3);
            if ( v42 )
            {
              if ( (unsigned int)sqlite3WalkSelect(v106, v42) )
                break;
            }
            if ( (*(_BYTE *)v41 & 4) != 0 )
            {
              v43 = (_DWORD *)*((_QWORD *)v41 + 3);
              if ( v43 )
              {
                v44 = *v43;
                v45 = v43 + 2;
                if ( v44 > 0 )
                {
                  while ( !*v45 || !(unsigned int)sqlite3WalkExprNN(v106) )
                  {
                    --v44;
                    v45 += 4;
                    if ( v44 <= 0 )
                      goto LABEL_58;
                  }
                  break;
                }
              }
            }
LABEL_58:
            --v40;
            v41 += 26;
            if ( v40 <= 0 )
              goto LABEL_59;
          }
LABEL_168:
          v13 = a1;
          v14 = 0;
          goto LABEL_169;
        }
      }
LABEL_59:
      if ( v108 && v108 != std::_Associated_state<std::vector<asg::SemanticIndex::ItemMatch>>::_Run_deferred_function )
        ((void (__fastcall *)(_QWORD *, _OWORD *))v108)(v106, v24);
      v24 = (_OWORD *)*((_QWORD *)v24 + 10);
      v90 = v24;
      if ( !v24 )
        goto LABEL_65;
      v19 = v111;
      v25 = v107;
      continue;
    }
    break;
  }
  if ( (v38 & 2) != 0 )
    goto LABEL_168;
LABEL_65:
  v13 = a1;
  v46 = sqlite3SrcListLookup(a1, a7);
  v47 = (unsigned __int8 **)v46;
  if ( !v46 )
  {
LABEL_68:
    v48 = v94;
    goto LABEL_69;
  }
  if ( *(_BYTE *)(v46 + 63) == 1 )
  {
    sqlite3ErrorMsg(a1, "cannot create triggers on virtual tables");
    goto LABEL_68;
  }
  if ( (*(_DWORD *)(v46 + 48) & 0x1000) != 0 && (unsigned int)sqlite3ReadOnlyShadowTables(v12) )
  {
    sqlite3ErrorMsg(a1, "cannot create triggers on shadow tables");
    goto LABEL_68;
  }
  v49 = v91;
  v50 = sqlite3NameFromToken(v12, v91);
  v48 = v50;
  if ( !v50 )
  {
LABEL_71:
    v14 = 0;
    if ( v48 )
      sqlite3DbFreeNN(v12);
    goto LABEL_169;
  }
  if ( (unsigned int)sqlite3CheckObjectName(a1, v50, "trigger", *v47) )
    goto LABEL_82;
  if ( *((_BYTE *)a1 + 300) < 2u
    && *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v87 + *(_QWORD *)(v12 + 32) + 24) + 56LL, v48, 0) + 16) )
  {
    v51 = a1;
    if ( a10 )
    {
      if ( a1[21] )
        v51 = (__int64 *)a1[21];
      v52 = *((_DWORD *)v51 + 33);
      if ( !_bittest(&v52, v87) )
      {
        *((_DWORD *)v51 + 33) = v52 | (1 << v87);
        if ( v87 == 1 )
        {
          sqlite3OpenTempDatabase();
          v14 = 0;
          sqlite3DbFreeNN(v12);
          goto LABEL_169;
        }
      }
    }
    else
    {
      sqlite3ErrorMsg(a1, "trigger %T already exists", v49);
    }
LABEL_82:
    v14 = 0;
    sqlite3DbFreeNN(v12);
    goto LABEL_169;
  }
  v53 = *v47;
  v54 = 7;
  v55 = 7;
  if ( *v47 )
  {
    v56 = "sqlite_";
    while ( 1 )
    {
      v57 = *v53;
      --v55;
      if ( !(_BYTE)v57 || *((_BYTE *)qword_18026E880 + v57) != *((_BYTE *)qword_18026E880 + *(unsigned __int8 *)v56) )
        break;
      ++v53;
      ++v56;
      if ( v55 <= 0 )
      {
        --v55;
        break;
      }
    }
    if ( v55 < 0
      || *((unsigned __int8 *)qword_18026E880 + *v53) == *((unsigned __int8 *)qword_18026E880 + *(unsigned __int8 *)v56) )
    {
      sqlite3ErrorMsg(a1, "cannot create trigger on system table", v53, v56);
      v14 = 0;
      sqlite3DbFreeNN(v12);
      goto LABEL_169;
    }
  }
  if ( *((_BYTE *)v47 + 63) == 2 )
  {
    if ( a4 != 65 )
    {
      v58 = "AFTER";
      if ( a4 == 33 )
        v58 = "BEFORE";
      sqlite3ErrorMsg(a1, "cannot create %s trigger on view: %S", v58, (const wchar_t *)(a7 + 8));
LABEL_69:
      if ( *(_BYTE *)(v12 + 196) == 1 )
        *(_DWORD *)(v12 + 200) |= 1u;
      goto LABEL_71;
    }
  }
  else if ( a4 == 65 )
  {
    sqlite3ErrorMsg(a1, "cannot create INSTEAD OF trigger on table: %S", (const wchar_t *)(a7 + 8));
    goto LABEL_69;
  }
  if ( *((_BYTE *)a1 + 300) < 2u )
  {
    v59 = v47[12];
    v60 = -32768;
    if ( v59 )
    {
      v60 = 0;
      for ( i = (unsigned __int8 **)(*(_QWORD *)(v12 + 32) + 24LL); *i != v59; i += 4 )
        ++v60;
    }
    v62 = *(_QWORD *)(v12 + 32);
    v63 = *(_QWORD *)(32LL * v60 + v62);
    if ( a9 )
      v64 = *(_QWORD *)(v62 + 32);
    else
      v64 = *(_QWORD *)(32LL * v60 + v62);
    if ( v60 == 1 || a9 )
      v54 = 5;
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, v54, v48, (unsigned int)*v47, v64) )
      goto LABEL_82;
    v65 = "sqlite_temp_master";
    if ( v60 != 1 )
      v65 = "sqlite_master";
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v65, 0, v63) )
      goto LABEL_82;
  }
  v66 = 33;
  if ( a4 != 65 )
    v66 = a4;
  if ( *(_WORD *)(v12 + 404) >= 0x48u )
  {
    v67 = *(_QWORD **)(v12 + 456);
    v86 = (__int64)v67;
    if ( v67 )
    {
      v68 = *(_QWORD *)(v12 + 456);
      *(_QWORD *)(v12 + 456) = *v67;
      ++*(_DWORD *)(v12 + 416);
    }
    else
    {
      v69 = *(_QWORD **)(v12 + 448);
      v86 = (__int64)v69;
      if ( v69 )
      {
        v68 = *(_QWORD *)(v12 + 448);
        *(_QWORD *)(v12 + 448) = *v69;
        ++*(_DWORD *)(v12 + 416);
      }
      else
      {
        v70 = *(_QWORD **)(v12 + 440);
        v86 = (__int64)v70;
        if ( v70 )
        {
          v68 = *(_QWORD *)(v12 + 440);
          *(_QWORD *)(v12 + 440) = *v70;
          ++*(_DWORD *)(v12 + 416);
        }
        else
        {
          v71 = *(__int64 **)(v12 + 432);
          v86 = (__int64)v71;
          if ( !v71 )
          {
            ++*(_DWORD *)(v12 + 424);
            goto LABEL_134;
          }
          v72 = *v71;
          v68 = *(_QWORD *)(v12 + 432);
          ++*(_DWORD *)(v12 + 416);
          *(_QWORD *)(v12 + 432) = v72;
        }
      }
    }
  }
  else
  {
    if ( !*(_DWORD *)(v12 + 400) )
    {
      ++*(_DWORD *)(v12 + 420);
      goto LABEL_134;
    }
    if ( *(_BYTE *)(v12 + 103) )
    {
LABEL_124:
      v13 = a1;
      v14 = 0;
      sqlite3DbFreeNN(v12);
      goto LABEL_169;
    }
LABEL_134:
    v86 = dbMallocRawFinish(v12, 72);
    v68 = v86;
    if ( !v86 )
      goto LABEL_124;
  }
  *(_QWORD *)(v68 + 8) = 0;
  *(_QWORD *)(v68 + 16) = 0;
  *(_QWORD *)(v68 + 24) = 0;
  *(_QWORD *)(v68 + 32) = 0;
  *(_QWORD *)(v68 + 40) = 0;
  *(_QWORD *)(v68 + 48) = 0;
  *(_QWORD *)(v68 + 56) = 0;
  *(_QWORD *)(v68 + 64) = 0;
  *(_QWORD *)v68 = v48;
  v73 = *(const char **)(a7 + 24);
  if ( !v73 )
  {
    v74 = 0;
    goto LABEL_155;
  }
  v75 = strlen(v73) + 1;
  if ( v75 <= *(unsigned __int16 *)(v12 + 404) )
  {
    if ( v75 > 0x80 )
      goto LABEL_148;
    v74 = *(_QWORD **)(v12 + 456);
    if ( v74 )
    {
      *(_QWORD *)(v12 + 456) = *v74;
      ++*(_DWORD *)(v12 + 416);
      goto LABEL_154;
    }
    v74 = *(_QWORD **)(v12 + 448);
    if ( v74 )
    {
      *(_QWORD *)(v12 + 448) = *v74;
      ++*(_DWORD *)(v12 + 416);
    }
    else
    {
LABEL_148:
      v74 = *(_QWORD **)(v12 + 440);
      if ( v74 )
      {
        *(_QWORD *)(v12 + 440) = *v74;
        ++*(_DWORD *)(v12 + 416);
      }
      else
      {
        v74 = *(_QWORD **)(v12 + 432);
        if ( !v74 )
        {
          _mm_lfence();
          ++*(_DWORD *)(v12 + 424);
          goto LABEL_153;
        }
        v76 = *v74;
        ++*(_DWORD *)(v12 + 416);
        *(_QWORD *)(v12 + 432) = v76;
      }
    }
LABEL_154:
    memmove(v74, v73, v75);
  }
  else
  {
    if ( !*(_DWORD *)(v12 + 400) )
    {
      ++*(_DWORD *)(v12 + 420);
      goto LABEL_140;
    }
    if ( *(_BYTE *)(v12 + 103) )
    {
      v74 = 0;
      goto LABEL_155;
    }
LABEL_140:
    _mm_lfence();
LABEL_153:
    v74 = (_QWORD *)dbMallocRawFinish(v12, v75);
    if ( v74 )
      goto LABEL_154;
  }
LABEL_155:
  *(_QWORD *)(v68 + 8) = v74;
  v77 = v66 == 33;
  v13 = a1;
  *(_QWORD *)(v68 + 40) = *(_QWORD *)(32LL * v87 + *(_QWORD *)(v12 + 32) + 24);
  *(_QWORD *)(v68 + 48) = v47[12];
  *(_BYTE *)(v68 + 16) = a5;
  *(_BYTE *)(v68 + 17) = !v77 + 1;
  if ( *((_BYTE *)a1 + 300) < 2u )
  {
    v79 = a8;
    if ( a8 )
      v93 = exprDup(v12, a8, 1, 0);
    else
      v93 = 0;
    v14 = v86;
  }
  else
  {
    v14 = v86;
    v78 = (_QWORD *)a1[51];
    if ( v78 )
    {
      while ( *v78 != *(_QWORD *)(a7 + 24) )
      {
        v78 = (_QWORD *)v78[3];
        if ( !v78 )
        {
          v79 = 0;
          goto LABEL_166;
        }
      }
      *v78 = v74;
    }
    v79 = 0;
  }
LABEL_166:
  *(_QWORD *)(v68 + 24) = v93;
  *(_QWORD *)(v68 + 32) = v97;
  a1[45] = v68;
  result = sqlite3SrcListDelete(v12, a7);
LABEL_189:
  if ( v79 )
    result = sqlite3ExprDeleteNN(v12, v79);
  if ( !v13[45] && v14 && !*(_BYTE *)(v14 + 18) )
  {
    sqlite3DeleteTriggerStep(v12, *(_QWORD *)(v14 + 56));
    if ( *(_QWORD *)v14 )
      sqlite3DbFreeNN(v12);
    if ( *(_QWORD *)(v14 + 8) )
      sqlite3DbFreeNN(v12);
    v85 = *(_QWORD *)(v14 + 24);
    if ( v85 )
      sqlite3ExprDeleteNN(v12, v85);
    sqlite3IdListDelete(v12, *(_QWORD *)(v14 + 32));
    return sqlite3DbFreeNN(v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800fe6b0  push    rbp
0x1800fe6b2  push    rbx
0x1800fe6b3  push    rsi
0x1800fe6b4  push    rdi
0x1800fe6b5  push    r12
0x1800fe6b7  push    r13
0x1800fe6b9  push    r14
0x1800fe6bb  push    r15
0x1800fe6bd  lea     rbp, [rsp-98h]
0x1800fe6c5  sub     rsp, 198h
0x1800fe6cc  mov     rax, cs:__security_cookie
0x1800fe6d3  xor     rax, rsp
0x1800fe6d6  mov     [rbp+0D0h+var_50], rax
0x1800fe6dd  mov     rax, [rbp+0D0h+arg_28]
0x1800fe6e4  mov     rbx, r8
0x1800fe6e7  mov     rsi, [rbp+0D0h+arg_30]
0x1800fe6ee  mov     r15, rdx
0x1800fe6f1  mov     r13, [rcx]
0x1800fe6f4  mov     r12, rcx
0x1800fe6f7  mov     [rbp+0D0h+var_138], rax
0x1800fe6fb  mov     rax, [rbp+0D0h+arg_38]
0x1800fe702  mov     [rsp+1D0h+var_178], rsi
0x1800fe707  xor     esi, esi
0x1800fe709  mov     r14d, esi
0x1800fe70c  mov     [rsp+1D0h+var_188], rax
0x1800fe711  mov     [rsp+1D0h+var_158], rax
0x1800fe716  mov     eax, 1
0x1800fe71b  mov     [rsp+1D0h+var_180], r9d
0x1800fe720  mov     [rsp+1D0h+var_168], rdx
0x1800fe725  mov     [rsp+1D0h+var_190], rcx
0x1800fe72a  mov     [rbp+0D0h+var_148], rsi
0x1800fe72e  mov     [rsp+1D0h+var_1A0], rsi
0x1800fe733  mov     [rbp+0D0h+var_150], rsi
0x1800fe737  cmp     [rbp+0D0h+arg_40], esi
0x1800fe73d  jz      short loc_1800FE75E
0x1800fe73f  cmp     [r8+8], esi
0x1800fe743  jbe     short loc_1800FE756
0x1800fe745  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x1800fe74c  call    sqlite3ErrorMsg
0x1800fe751  jmp     loc_1800FF114
0x1800fe756  mov     edi, eax
0x1800fe758  mov     [rsp+1D0h+var_198], eax
0x1800fe75c  jmp     short loc_1800FE780
0x1800fe75e  lea     r9, [rsp+1D0h+var_168]
0x1800fe763  call    sqlite3TwoPartName
0x1800fe768  mov     [rsp+1D0h+var_198], eax
0x1800fe76c  mov     edi, eax
0x1800fe76e  test    eax, eax
0x1800fe770  js      loc_1800FF114
0x1800fe776  mov     r15, [rsp+1D0h+var_168]
0x1800fe77b  mov     [rsp+1D0h+var_168], r15
0x1800fe780  mov     rax, [rsp+1D0h+var_178]
0x1800fe785  test    rax, rax
0x1800fe788  jz      loc_1800FF114
0x1800fe78e  cmp     [r13+67h], sil
0x1800fe792  jnz     loc_1800FF114
0x1800fe798  cmp     [r13+0C5h], sil
0x1800fe79f  jz      short loc_1800FE7C0
0x1800fe7a1  cmp     edi, 1
0x1800fe7a4  jz      short loc_1800FE7C0
0x1800fe7a6  mov     rdx, [rax+10h]
0x1800fe7aa  test    rdx, rdx
0x1800fe7ad  jz      short loc_1800FE7BC
0x1800fe7af  mov     rcx, r13
0x1800fe7b2  call    sqlite3DbFreeNN
0x1800fe7b7  mov     rax, [rsp+1D0h+var_178]
0x1800fe7bc  mov     [rax+10h], rsi
0x1800fe7c0  mov     rdx, rax
0x1800fe7c3  mov     rcx, r12
0x1800fe7c6  call    sqlite3SrcListLookup
0x1800fe7cb  mov     rcx, rax
0x1800fe7ce  cmp     [r13+0C5h], sil
0x1800fe7d5  jnz     short loc_1800FE7F9
0x1800fe7d7  cmp     [rbx+8], esi
0x1800fe7da  jnz     short loc_1800FE7F9
0x1800fe7dc  test    rax, rax
0x1800fe7df  jz      short loc_1800FE7F9
0x1800fe7e1  mov     rax, [r13+20h]
0x1800fe7e5  mov     rax, [rax+38h]
0x1800fe7e9  cmp     [rcx+60h], rax
0x1800fe7ed  mov     eax, 1
0x1800fe7f2  cmovz   edi, eax
0x1800fe7f5  mov     [rsp+1D0h+var_198], edi
0x1800fe7f9  cmp     [r13+67h], sil
0x1800fe7fd  jnz     loc_1800FF114
0x1800fe803  mov     r8, [r12]
0x1800fe807  lea     r14, [rbp+0D0h+var_B0]
0x1800fe80b  xorps   xmm0, xmm0
0x1800fe80e  mov     [rbp+0D0h+var_B0], r12
0x1800fe812  mov     edx, edi
0x1800fe814  shl     rdx, 5
0x1800fe818  mov     rax, [r8+20h]
0x1800fe81c  cmp     edi, 1
0x1800fe81f  movups  [rbp+0D0h+var_110], xmm0
0x1800fe823  movups  [rbp+0D0h+var_130], xmm0
0x1800fe827  mov     rcx, [rdx+rax]
0x1800fe82b  mov     [rbp+0D0h+var_68], rcx
0x1800fe82f  mov     rax, [r8+20h]
0x1800fe833  movups  [rbp+0D0h+var_120], xmm0
0x1800fe837  movups  [rbp+0D0h+var_100], xmm0
0x1800fe83b  mov     rcx, [rax+rdx+18h]
0x1800fe840  lea     rax, aTrigger; "trigger"
0x1800fe847  mov     [rbp+0D0h+var_60], rax
0x1800fe84b  lea     rdx, fixSelectCb
0x1800fe852  lea     rax, fixExprCb
0x1800fe859  mov     [rbp+0D0h+var_78], rcx
0x1800fe85d  mov     rcx, [rsp+1D0h+var_178]
0x1800fe862  setz    [rbp+0D0h+var_70]
0x1800fe866  mov     [rbp+0D0h+var_58], r15
0x1800fe86a  lea     r15, [rbp+0D0h+var_130]
0x1800fe86e  mov     [rbp+0D0h+var_A8], r12
0x1800fe872  lea     r12, ?_Run_deferred_function@?$_Associated_state@V?$vector@UItemMatch@SemanticIndex@asg@@V?$allocator@UItemMatch@SemanticIndex@asg@@@std@@@std@@@std@@EEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<std::vector<asg::SemanticIndex::ItemMatch>>::_Run_deferred_function(std::unique_lock<std::mutex> &)
0x1800fe879  mov     [rbp+0D0h+var_A0], rax
0x1800fe87d  mov     rax, rdx
0x1800fe880  mov     [rbp+0D0h+var_98], rdx
0x1800fe884  mov     [rbp+0D0h+var_90], r12
0x1800fe888  mov     [rbp+0D0h+var_88], esi
0x1800fe88b  mov     [rbp+0D0h+var_84], si
0x1800fe88f  mov     [rbp+0D0h+var_80], r14
0x1800fe893  movups  [rbp+0D0h+var_F0], xmm0
0x1800fe897  mov     qword ptr [rbp+0D0h+var_110+8], rcx
0x1800fe89b  movups  [rbp+0D0h+var_E0], xmm0
0x1800fe89f  mov     [rsp+1D0h+var_170], r15
0x1800fe8a4  movups  [rbp+0D0h+var_D0], xmm0
0x1800fe8a8  movups  [rbp+0D0h+var_C0], xmm0
0x1800fe8ac  nop     dword ptr [rax+00h]
0x1800fe8b0  cmp     rax, rdx
0x1800fe8b3  jnz     loc_1800FEA08
0x1800fe8b9  mov     rax, [r14]
0x1800fe8bc  mov     rdx, [r14+48h]
0x1800fe8c0  mov     rax, [rax]
0x1800fe8c3  mov     rcx, rax
0x1800fe8c6  mov     [rbp+0D0h+var_140], rax
0x1800fe8ca  call    sqlite3FindDbName
0x1800fe8cf  mov     r12, [r15+28h]
0x1800fe8d3  mov     [rsp+1D0h+var_160], eax
0x1800fe8d7  test    r12, r12
0x1800fe8da  jz      loc_1800FE9C0
0x1800fe8e0  cmp     dword ptr [r12], 0
0x1800fe8e5  lea     rbx, [r12+8]
0x1800fe8ea  mov     r15d, esi
0x1800fe8ed  jle     loc_1800FE980
0x1800fe8f3  lea     rsi, [r12+50h]
0x1800fe8f8  cmp     byte ptr [r14+40h], 0
0x1800fe8fd  jnz     short loc_1800FE947
0x1800fe8ff  mov     rdi, [rbx+8]
0x1800fe903  test    rdi, rdi
0x1800fe906  jz      short loc_1800FE939
0x1800fe908  mov     rcx, [rbp+0D0h+var_140]
0x1800fe90c  mov     rdx, rdi
0x1800fe90f  call    sqlite3FindDbName
0x1800fe914  cmp     [rsp+1D0h+var_160], eax
0x1800fe918  jnz     loc_1800FE9CB
0x1800fe91e  mov     rcx, [rbp+0D0h+var_140]
0x1800fe922  mov     rdx, rdi
0x1800fe925  call    sqlite3DbFreeNN
0x1800fe92a  or      dword ptr [rbx+40h], 200h
0x1800fe931  mov     qword ptr [rbx+8], 0
0x1800fe939  mov     rax, [r14+38h]
0x1800fe93d  or      dword ptr [rbx+40h], 80h
0x1800fe944  mov     [rbx], rax
0x1800fe947  test    dword ptr [rsi-8], 400h
0x1800fe94e  jnz     short loc_1800FE969
0x1800fe950  mov     rdx, [rsi]
0x1800fe953  test    rdx, rdx
0x1800fe956  jz      short loc_1800FE969
0x1800fe958  lea     rcx, [r14+8]
0x1800fe95c  call    sqlite3WalkExprNN
0x1800fe961  test    eax, eax
0x1800fe963  jnz     loc_1800FE9E7
0x1800fe969  inc     r15d
0x1800fe96c  add     rsi, 68h ; 'h'
0x1800fe970  add     rbx, 68h ; 'h'
0x1800fe974  cmp     r15d, [r12]
0x1800fe978  jl      loc_1800FE8F8
0x1800fe97e  xor     esi, esi
0x1800fe980  mov     r15, [rsp+1D0h+var_170]
0x1800fe985  mov     rax, [r15+68h]
0x1800fe989  test    rax, rax
0x1800fe98c  jz      short loc_1800FE9C0
0x1800fe98e  cmp     dword ptr [rax], 0
0x1800fe991  mov     edi, esi
0x1800fe993  jle     short loc_1800FE9C0
0x1800fe995  mov     rbx, rsi
0x1800fe998  nop     dword ptr [rax+rax+00000000h]
0x1800fe9a0  mov     rdx, [rax+rbx+20h]
0x1800fe9a5  lea     rcx, [rbp+0D0h+var_A8]
0x1800fe9a9  call    sqlite3WalkSelect
0x1800fe9ae  test    eax, eax
0x1800fe9b0  jnz     short loc_1800FE9FA
0x1800fe9b2  mov     rax, [r15+68h]
0x1800fe9b6  inc     edi
0x1800fe9b8  add     rbx, 30h ; '0'
0x1800fe9bc  cmp     edi, [rax]
0x1800fe9be  jl      short loc_1800FE9A0
0x1800fe9c0  mov     eax, esi
0x1800fe9c2  lea     r12, ?_Run_deferred_function@?$_Associated_state@V?$vector@UItemMatch@SemanticIndex@asg@@V?$allocator@UItemMatch@SemanticIndex@asg@@@std@@@std@@@std@@EEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<std::vector<asg::SemanticIndex::ItemMatch>>::_Run_deferred_function(std::unique_lock<std::mutex> &)
0x1800fe9c9  jmp     short loc_1800FEA11
0x1800fe9cb  mov     r9, [r14+58h]
0x1800fe9cf  lea     rdx, aSTCannotRefere; "%s %T cannot reference objects in datab"...
0x1800fe9d6  mov     r8, [r14+50h]
0x1800fe9da  mov     rcx, [r14]
0x1800fe9dd  mov     [rsp+1D0h+var_1B0], rdi
0x1800fe9e2  call    sqlite3ErrorMsg
0x1800fe9e7  mov     r15, [rsp+1D0h+var_170]
0x1800fe9ec  lea     r12, ?_Run_deferred_function@?$_Associated_state@V?$vector@UItemMatch@SemanticIndex@asg@@V?$allocator@UItemMatch@SemanticIndex@asg@@@std@@@std@@@std@@EEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<std::vector<asg::SemanticIndex::ItemMatch>>::_Run_deferred_function(std::unique_lock<std::mutex> &)
0x1800fe9f3  mov     eax, 2
0x1800fe9f8  jmp     short loc_1800FEA11
0x1800fe9fa  mov     eax, 2
0x1800fe9ff  lea     r12, ?_Run_deferred_function@?$_Associated_state@V?$vector@UItemMatch@SemanticIndex@asg@@V?$allocator@UItemMatch@SemanticIndex@asg@@@std@@@std@@@std@@EEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<std::vector<asg::SemanticIndex::ItemMatch>>::_Run_deferred_function(std::unique_lock<std::mutex> &)
0x1800fea06  jmp     short loc_1800FEA11
0x1800fea08  mov     rdx, r15
0x1800fea0b  lea     rcx, [rbp+0D0h+var_A8]
0x1800fea0f  call    rax
0x1800fea11  test    eax, eax
0x1800fea13  jnz     loc_1800FEADE
0x1800fea19  mov     rdx, r15
0x1800fea1c  lea     rcx, [rbp+0D0h+var_A8]
0x1800fea20  call    sqlite3WalkSelectExpr
0x1800fea25  test    eax, eax
0x1800fea27  jnz     loc_1800FF10A
0x1800fea2d  mov     rsi, [r15+28h]
0x1800fea31  test    rsi, rsi
0x1800fea34  jz      short loc_1800FEAA3
0x1800fea36  mov     r14d, [rsi]
0x1800fea39  test    r14d, r14d
0x1800fea3c  jle     short loc_1800FEAA3
0x1800fea3e  add     rsi, 48h ; 'H'
0x1800fea42  mov     rdx, [rsi-18h]
0x1800fea46  test    rdx, rdx
0x1800fea49  jz      short loc_1800FEA5C
0x1800fea4b  lea     rcx, [rbp+0D0h+var_A8]
0x1800fea4f  call    sqlite3WalkSelect
0x1800fea54  test    eax, eax
0x1800fea56  jnz     loc_1800FF10A
0x1800fea5c  test    byte ptr [rsi], 4
0x1800fea5f  jz      short loc_1800FEA97
0x1800fea61  mov     rdi, [rsi+18h]
0x1800fea65  test    rdi, rdi
0x1800fea68  jz      short loc_1800FEA97
0x1800fea6a  mov     ebx, [rdi]
0x1800fea6c  add     rdi, 8
0x1800fea70  test    ebx, ebx
0x1800fea72  jle     short loc_1800FEA97
0x1800fea74  mov     rdx, [rdi]
0x1800fea77  test    rdx, rdx
0x1800fea7a  jz      short loc_1800FEA8D
0x1800fea7c  lea     rcx, [rbp+0D0h+var_A8]
0x1800fea80  call    sqlite3WalkExprNN
0x1800fea85  test    eax, eax
0x1800fea87  jnz     loc_1800FF10A
0x1800fea8d  dec     ebx
0x1800fea8f  add     rdi, 20h ; ' '
0x1800fea93  test    ebx, ebx
0x1800fea95  jg      short loc_1800FEA74
0x1800fea97  dec     r14d
0x1800fea9a  add     rsi, 68h ; 'h'
0x1800fea9e  test    r14d, r14d
0x1800feaa1  jg      short loc_1800FEA42
0x1800feaa3  mov     rax, [rbp+0D0h+var_90]
0x1800feaa7  test    rax, rax
0x1800feaaa  jz      short loc_1800FEABA
0x1800feaac  cmp     rax, r12
0x1800feaaf  jz      short loc_1800FEABA
0x1800feab1  mov     rdx, r15
0x1800feab4  lea     rcx, [rbp+0D0h+var_A8]
0x1800feab8  call    rax
0x1800feaba  mov     r15, [r15+50h]
0x1800feabe  mov     [rsp+1D0h+var_170], r15
0x1800feac3  test    r15, r15
0x1800feac6  jz      short loc_1800FEAE6
0x1800feac8  mov     r14, [rbp+0D0h+var_80]
0x1800feacc  lea     rdx, fixSelectCb
0x1800fead3  mov     rax, [rbp+0D0h+var_98]
0x1800fead7  xor     esi, esi
0x1800fead9  jmp     loc_1800FE8B0
0x1800feade  test    al, 2
0x1800feae0  jnz     loc_1800FF10A
0x1800feae6  mov     r14, [rsp+1D0h+var_178]
0x1800feaeb  mov     r12, [rsp+1D0h+var_190]
0x1800feaf0  mov     rdx, r14
0x1800feaf3  mov     rcx, r12
0x1800feaf6  call    sqlite3SrcListLookup
0x1800feafb  mov     r15, rax
0x1800feafe  test    rax, rax
0x1800feb01  jz      short loc_1800FEB18
0x1800feb03  cmp     byte ptr [rax+3Fh], 1
0x1800feb07  jnz     short loc_1800FEB4C
0x1800feb09  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x1800feb10  mov     rcx, r12
0x1800feb13  call    sqlite3ErrorMsg
0x1800feb18  mov     rsi, [rbp+0D0h+var_150]
0x1800feb1c  cmp     byte ptr [r13+0C4h], 1
0x1800feb24  jnz     short loc_1800FEB2E
0x1800feb26  or      dword ptr [r13+0C8h], 1
0x1800feb2e  mov     r14, [rsp+1D0h+var_1A0]
0x1800feb33  test    rsi, rsi
0x1800feb36  jz      loc_1800FF114
0x1800feb3c  mov     rdx, rsi
0x1800feb3f  mov     rcx, r13
  ... truncated ...
```
