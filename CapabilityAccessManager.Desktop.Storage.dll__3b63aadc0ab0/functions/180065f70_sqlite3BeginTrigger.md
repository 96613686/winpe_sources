# sqlite3BeginTrigger

- ea: `0x180065f70`
- end: `0x1800669b6`
- name: `sqlite3BeginTrigger`
- size: `2630`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path`

## callers

- `0x1800d8b00`

## callees

- `0x180003060`
- `0x180005980`
- `0x1800349e0`
- `0x180039a90`
- `0x18003c1a0`
- `0x18004dba0`
- `0x1800658d0`
- `0x180065f70`
- `0x18006b6d0`
- `0x180072a30`
- `0x1800743d0`
- `0x1800795a0`
- `0x18007b1b0`
- `0x180088db0`
- `0x1800896a0`
- `0x18009bde0`
- `0x18009c660`
- `0x1800b3e50`
- `0x1800e4dce`
- `0x1800e4dfe`
- `0x18010d010`

## string_xrefs

- `0x1800664ae`: `sqlite_temp_master`
- `0x180065fec`: `temporary trigger may not have qualified name`
- `0x180066213`: `cannot create triggers on virtual tables`
- `0x1800662dd`: `trigger %T already exists`
- `0x18006638f`: `cannot create trigger on system table`
- `0x1800663cc`: `cannot create %s trigger on view: %S`
- `0x1800663f0`: `cannot create INSTEAD OF trigger on table: %S`

## pseudocode

```c
__int64 __fastcall sqlite3BeginTrigger(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        _DWORD *a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10)
{
  __int64 v10; // r15
  int v11; // eax
  __int64 v14; // rbx
  signed int Db; // edi
  _BYTE *v16; // rsi
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rsi
  __int64 v25; // rax
  __int64 *v26; // rcx
  int v27; // eax
  int v28; // r10d
  int v29; // edx
  const char *v30; // r9
  unsigned __int8 *v31; // r8
  __int64 v32; // rcx
  const char *v33; // r8
  unsigned __int8 *v34; // rcx
  int v35; // edi
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r13
  __int64 v39; // rax
  const char *v40; // r8
  int v41; // eax
  __int64 v42; // rax
  __int64 v43; // r13
  const char *v44; // rax
  _QWORD *v45; // rsi
  size_t v46; // r13
  __int64 v47; // rax
  _QWORD *v48; // rax
  __int64 v49; // rdx
  int i; // edi
  _QWORD *v51; // rcx
  int v52; // eax
  void (*v53)(void); // rax
  __int64 result; // rax
  int v56; // [rsp+30h] [rbp-D0h]
  unsigned __int8 **v58; // [rsp+40h] [rbp-C0h]
  __int64 v59; // [rsp+48h] [rbp-B8h]
  __int64 v60; // [rsp+50h] [rbp-B0h]
  const char *Src; // [rsp+58h] [rbp-A8h]
  __int64 *v62; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v63[4]; // [rsp+68h] [rbp-98h] BYREF
  int v64; // [rsp+88h] [rbp-78h]
  __int16 v65; // [rsp+8Ch] [rbp-74h]
  __int64 **v66; // [rsp+90h] [rbp-70h]
  __int64 v67; // [rsp+98h] [rbp-68h]
  bool v68; // [rsp+A0h] [rbp-60h]
  __int64 v69; // [rsp+A8h] [rbp-58h]
  const char *v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h]
  _OWORD v72[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v73; // [rsp+E0h] [rbp-20h]
  __int128 v74; // [rsp+F0h] [rbp-10h]
  __int128 v75; // [rsp+100h] [rbp+0h]
  __int128 v76; // [rsp+110h] [rbp+10h]
  __int128 v77; // [rsp+120h] [rbp+20h]
  __int128 v78; // [rsp+130h] [rbp+30h]

  v10 = 0;
  v11 = *(_DWORD *)(a3 + 8);
  v14 = *a1;
  v59 = a8;
  if ( a9 )
  {
    if ( v11 )
    {
      sqlite3ErrorMsg(a1, "temporary trigger may not have qualified name");
      goto LABEL_136;
    }
    Db = 1;
    v16 = (_BYTE *)(v14 + 197);
  }
  else
  {
    v16 = (_BYTE *)(v14 + 197);
    if ( v11 )
    {
      if ( *v16 )
      {
        sqlite3ErrorMsg(a1, "corrupt database");
        goto LABEL_136;
      }
      Db = sqlite3FindDb(v14);
      if ( Db < 0 )
      {
        sqlite3ErrorMsg(a1, "unknown database %T", a2);
        goto LABEL_136;
      }
      a2 = a3;
    }
    else
    {
      Db = *(unsigned __int8 *)(v14 + 196);
    }
  }
  v17 = a7;
  if ( !a7 || *(_BYTE *)(v14 + 103) )
    goto LABEL_136;
  if ( *v16 && Db != 1 )
  {
    v18 = *(_QWORD **)(a7 + 16);
    if ( v18 )
    {
      if ( (unsigned __int64)v18 < *(_QWORD *)(v14 + 496) )
      {
        if ( (unsigned __int64)v18 >= *(_QWORD *)(v14 + 480) )
        {
          *v18 = *(_QWORD *)(v14 + 472);
          *(_QWORD *)(v14 + 472) = v18;
          goto LABEL_25;
        }
        if ( (unsigned __int64)v18 >= *(_QWORD *)(v14 + 488) )
        {
          *v18 = *(_QWORD *)(v14 + 456);
          *(_QWORD *)(v14 + 456) = v18;
          goto LABEL_25;
        }
      }
      if ( *(_QWORD *)(v14 + 776) )
        measureAllocationSize(v14, v18);
      else
        sqlite3_free(v18);
    }
LABEL_25:
    v17 = a7;
    *(_QWORD *)(a7 + 16) = 0;
  }
  v19 = sqlite3SrcListLookup(a1, v17);
  if ( !*v16 && !*(_DWORD *)(a3 + 8) && v19 && *(_QWORD *)(v19 + 96) == *(_QWORD *)(*(_QWORD *)(v14 + 32) + 56LL) )
    Db = 1;
  if ( *(_BYTE *)(v14 + 103) )
    goto LABEL_136;
  v20 = *a1;
  v62 = a1;
  v21 = *(_QWORD *)(v20 + 32);
  v73 = 0;
  v60 = 32LL * (unsigned int)Db;
  memset(v72, 0, sizeof(v72));
  v69 = *(_QWORD *)(v60 + v21);
  v22 = *(_QWORD *)(v20 + 32);
  v74 = 0;
  v23 = *(_QWORD *)(v60 + v22 + 24);
  v70 = "trigger";
  v68 = Db == 1;
  v67 = v23;
  v63[1] = fixExprCb;
  v71 = a2;
  v63[2] = fixSelectCb;
  v63[3] = Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
  v65 = 0;
  v66 = &v62;
  *((_QWORD *)&v73 + 1) = a7;
  v63[0] = a1;
  v64 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  if ( (unsigned int)sqlite3WalkSelect(v63, v72) )
    goto LABEL_136;
  v24 = 0;
  v25 = sqlite3SrcListLookup(a1, a7);
  v58 = (unsigned __int8 **)v25;
  if ( !v25 )
    goto LABEL_36;
  if ( *(_BYTE *)(v25 + 63) == 1 )
  {
    sqlite3ErrorMsg(a1, "cannot create triggers on virtual tables");
    goto LABEL_36;
  }
  v24 = (_QWORD *)sqlite3NameFromToken(v14, a2);
  if ( !v24 )
    goto LABEL_136;
  if ( !(unsigned int)sqlite3CheckObjectName(a1, v24, "trigger", *v58) )
  {
    if ( *((_BYTE *)a1 + 300) < 2u
      && *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(v14 + 32) + v60 + 24) + 56LL, v24, 0) + 16) )
    {
      v26 = a1;
      if ( a10 )
      {
        if ( a1[21] )
          v26 = (__int64 *)a1[21];
        v27 = *((_DWORD *)v26 + 31);
        if ( !_bittest(&v27, Db) )
        {
          *((_DWORD *)v26 + 31) = v27 | (1 << Db);
          if ( Db == 1 )
            sqlite3OpenTempDatabase();
        }
      }
      else
      {
        sqlite3ErrorMsg(a1, "trigger %T already exists", a2);
      }
      goto LABEL_39;
    }
    v28 = 7;
    if ( *v58 )
    {
      v29 = 7;
      v30 = "sqlite_";
      v31 = *v58;
      while ( 1 )
      {
        v32 = *v31;
        --v29;
        if ( !(_BYTE)v32 || *((_BYTE *)qword_180114680 + v32) != *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v30) )
          break;
        ++v31;
        ++v30;
        if ( v29 <= 0 )
        {
          --v29;
          break;
        }
      }
      if ( v29 < 0
        || *((unsigned __int8 *)qword_180114680 + *v31) == *((unsigned __int8 *)qword_180114680 + *(unsigned __int8 *)v30) )
      {
        sqlite3ErrorMsg(a1, "cannot create trigger on system table", v31, v30);
        goto LABEL_39;
      }
    }
    if ( *((_BYTE *)v58 + 63) == 2 )
    {
      if ( a4 != 65 )
      {
        v33 = "AFTER";
        if ( a4 == 33 )
          v33 = "BEFORE";
        sqlite3ErrorMsg(a1, "cannot create %s trigger on view: %S", v33, a7 + 8);
LABEL_36:
        if ( *(_BYTE *)(v14 + 196) == 1 )
          *(_DWORD *)(v14 + 200) |= 1u;
        if ( !v24 )
          goto LABEL_136;
        goto LABEL_39;
      }
    }
    else if ( a4 == 65 )
    {
      sqlite3ErrorMsg(a1, "cannot create INSTEAD OF trigger on table: %S", (const wchar_t *)(a7 + 8));
      goto LABEL_36;
    }
    if ( *((_BYTE *)a1 + 300) < 2u )
    {
      v34 = v58[12];
      v35 = -32768;
      if ( v34 )
      {
        v36 = *(_QWORD *)(v14 + 32);
        v35 = 0;
        if ( *(unsigned __int8 **)(v36 + 24) != v34 )
        {
          do
            ++v35;
          while ( *(unsigned __int8 **)(32LL * v35 + v36 + 24) != v34 );
        }
      }
      v37 = *(_QWORD *)(v14 + 32);
      v38 = *(_QWORD *)(32LL * v35 + v37);
      if ( a9 )
        v39 = *(_QWORD *)(v37 + 32);
      else
        v39 = *(_QWORD *)(32LL * v35 + v37);
      if ( v35 == 1 || a9 )
        v28 = 5;
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, v28, (_DWORD)v24, (unsigned int)*v58, v39) )
        goto LABEL_39;
      v40 = "sqlite_temp_master";
      if ( v35 != 1 )
        v40 = "sqlite_master";
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v40, 0, v38) )
        goto LABEL_39;
    }
    v41 = 33;
    if ( a4 != 65 )
      v41 = a4;
    v56 = v41;
    if ( *(_WORD *)(v14 + 420) >= 0x48u )
    {
      v10 = *(_QWORD *)(v14 + 472);
      if ( v10 )
      {
        *(_QWORD *)(v14 + 472) = *(_QWORD *)v10;
        ++*(_DWORD *)(v14 + 432);
        goto LABEL_100;
      }
      v10 = *(_QWORD *)(v14 + 464);
      if ( v10 )
      {
        *(_QWORD *)(v14 + 464) = *(_QWORD *)v10;
        ++*(_DWORD *)(v14 + 432);
        goto LABEL_100;
      }
      v10 = *(_QWORD *)(v14 + 456);
      if ( v10 )
      {
        *(_QWORD *)(v14 + 456) = *(_QWORD *)v10;
        ++*(_DWORD *)(v14 + 432);
        goto LABEL_100;
      }
      v10 = *(_QWORD *)(v14 + 448);
      if ( v10 )
      {
        v42 = *(_QWORD *)v10;
        ++*(_DWORD *)(v14 + 432);
        *(_QWORD *)(v14 + 448) = v42;
        goto LABEL_100;
      }
      ++*(_DWORD *)(v14 + 440);
    }
    else if ( *(_DWORD *)(v14 + 416) )
    {
      if ( *(_BYTE *)(v14 + 103) )
        goto LABEL_39;
    }
    else
    {
      ++*(_DWORD *)(v14 + 436);
    }
    v10 = dbMallocRawFinish(v14, 72);
    if ( !v10 )
      goto LABEL_39;
LABEL_100:
    v43 = a7;
    *(_QWORD *)(v10 + 8) = 0;
    *(_QWORD *)(v10 + 16) = 0;
    *(_QWORD *)(v10 + 24) = 0;
    *(_QWORD *)(v10 + 32) = 0;
    *(_QWORD *)(v10 + 40) = 0;
    *(_QWORD *)(v10 + 48) = 0;
    *(_QWORD *)(v10 + 56) = 0;
    *(_QWORD *)(v10 + 64) = 0;
    *(_QWORD *)v10 = v24;
    v44 = *(const char **)(a7 + 24);
    Src = v44;
    if ( !v44 )
    {
      v45 = 0;
LABEL_120:
      *(_QWORD *)(v10 + 8) = v45;
      *(_QWORD *)(v10 + 40) = *(_QWORD *)(*(_QWORD *)(v14 + 32) + v60 + 24);
      *(_QWORD *)(v10 + 48) = v58[12];
      *(_BYTE *)(v10 + 16) = a5;
      *(_BYTE *)(v10 + 17) = (v56 != 33) + 1;
      if ( *((_BYTE *)a1 + 300) < 2u )
      {
        if ( a8 )
          v49 = exprDup(v14, a8, 1, 0);
        else
          v49 = 0;
      }
      else
      {
        v48 = (_QWORD *)a1[51];
        v49 = a8;
        if ( v48 )
        {
          while ( *v48 != *(_QWORD *)(v43 + 24) )
          {
            v48 = (_QWORD *)v48[3];
            if ( !v48 )
            {
              v59 = 0;
              goto LABEL_130;
            }
          }
          *v48 = v45;
        }
        v59 = 0;
      }
LABEL_130:
      *(_QWORD *)(v10 + 24) = v49;
      *(_QWORD *)(v10 + 32) = a6;
      a1[45] = v10;
      sqlite3SrcListDelete(v14, v43);
      goto LABEL_163;
    }
    v46 = strlen_0(v44) + 1;
    if ( v46 > *(unsigned __int16 *)(v14 + 420) )
    {
      if ( *(_DWORD *)(v14 + 416) )
      {
        if ( *(_BYTE *)(v14 + 103) )
        {
          v45 = 0;
          goto LABEL_119;
        }
      }
      else
      {
        ++*(_DWORD *)(v14 + 436);
      }
LABEL_117:
      v45 = (_QWORD *)dbMallocRawFinish(v14, v46);
      if ( v45 )
        goto LABEL_118;
LABEL_119:
      v43 = a7;
      goto LABEL_120;
    }
    if ( v46 <= 0x80 )
    {
      v45 = *(_QWORD **)(v14 + 472);
      if ( v45 )
      {
        *(_QWORD *)(v14 + 472) = *v45;
        ++*(_DWORD *)(v14 + 432);
        goto LABEL_118;
      }
      v45 = *(_QWORD **)(v14 + 464);
      if ( v45 )
      {
        *(_QWORD *)(v14 + 464) = *v45;
        ++*(_DWORD *)(v14 + 432);
        goto LABEL_118;
      }
    }
    v45 = *(_QWORD **)(v14 + 456);
    if ( v45 )
    {
      *(_QWORD *)(v14 + 456) = *v45;
      ++*(_DWORD *)(v14 + 432);
    }
    else
    {
      v45 = *(_QWORD **)(v14 + 448);
      if ( !v45 )
      {
        ++*(_DWORD *)(v14 + 440);
        goto LABEL_117;
      }
      v47 = *v45;
      ++*(_DWORD *)(v14 + 432);
      *(_QWORD *)(v14 + 448) = v47;
    }
LABEL_118:
    memcpy_0(v45, Src, v46);
    goto LABEL_119;
  }
LABEL_39:
  if ( (unsigned __int64)v24 >= *(_QWORD *)(v14 + 496) )
    goto LABEL_169;
  if ( (unsigned __int64)v24 >= *(_QWORD *)(v14 + 480) )
  {
    *v24 = *(_QWORD *)(v14 + 472);
    *(_QWORD *)(v14 + 472) = v24;
    goto LABEL_136;
  }
  if ( (unsigned __int64)v24 < *(_QWORD *)(v14 + 488) )
  {
LABEL_169:
    if ( *(_QWORD *)(v14 + 776) )
      measureAllocationSize(v14, v24);
    else
      sqlite3_free(v24);
  }
  else
  {
    *v24 = *(_QWORD *)(v14 + 456);
    *(_QWORD *)(v14 + 456) = v24;
  }
LABEL_136:
  sqlite3SrcListDelete(v14, a7);
  if ( !a6 )
    goto LABEL_163;
  for ( i = 0; i < *a6; ++i )
  {
    v51 = *(_QWORD **)&a6[4 * i + 2];
    if ( v51 )
    {
      if ( !v14 )
        goto LABEL_147;
      if ( (unsigned __int64)v51 < *(_QWORD *)(v14 + 496) )
      {
        if ( (unsigned __int64)v51 >= *(_QWORD *)(v14 + 480) )
        {
          *v51 = *(_QWORD *)(v14 + 472);
          *(_QWORD *)(v14 + 472) = v51;
          continue;
        }
        if ( (unsigned __int64)v51 >= *(_QWORD *)(v14 + 488) )
        {
          *v51 = *(_QWORD *)(v14 + 456);
          *(_QWORD *)(v14 + 456) = v51;
          continue;
        }
      }
      if ( !*(_QWORD *)(v14 + 776) )
      {
LABEL_147:
        sqlite3_free(v51);
        continue;
      }
      measureAllocationSize(v14, *(_QWORD *)&a6[4 * i + 2]);
    }
  }
  if ( (unsigned __int64)a6 < *(_QWORD *)(v14 + 496) )
  {
    if ( (unsigned __int64)a6 >= *(_QWORD *)(v14 + 480) )
    {
      *(_QWORD *)a6 = *(_QWORD *)(v14 + 472);
      *(_QWORD *)(v14 + 472) = a6;
      goto LABEL_163;
    }
    if ( (unsigned __int64)a6 >= *(_QWORD *)(v14 + 488) )
    {
      *(_QWORD *)a6 = *(_QWORD *)(v14 + 456);
      *(_QWORD *)(v14 + 456) = a6;
      goto LABEL_163;
    }
  }
  if ( *(_QWORD *)(v14 + 776) )
  {
    measureAllocationSize(v14, a6);
    goto LABEL_163;
  }
  if ( !dword_18013C1B0 )
  {
    v53 = (void (*)(void))xmmword_18013C1D8;
    goto LABEL_162;
  }
  if ( (_QWORD)xmmword_18013FC60 )
    ((void (*)(void))xmmword_18013C230)();
  v52 = ((__int64 (__fastcall *)(_DWORD *))xmmword_18013C1E8)(a6);
  --qword_18013FBE8;
  qword_18013FBA0 -= v52;
  ((void (__fastcall *)(_DWORD *))xmmword_18013C1D8)(a6);
  if ( (_QWORD)xmmword_18013FC60 )
  {
    v53 = (void (*)(void))xmmword_18013C240;
LABEL_162:
    v53();
  }
LABEL_163:
  result = v59;
  if ( v59 )
    result = sqlite3ExprDeleteNN(v14, v59);
  if ( !a1[45] )
    return sqlite3DeleteTrigger(v14, v10);
  return result;
}

```

## disassembly

```asm
0x180065f70  mov     r11, rsp
0x180065f73  push    rbp
0x180065f74  push    rbx
0x180065f75  push    r15
0x180065f77  lea     rbp, [rsp-80h]
0x180065f7c  sub     rsp, 180h
0x180065f83  mov     rax, cs:__security_cookie
0x180065f8a  xor     rax, rsp
0x180065f8d  mov     [rbp+90h+var_50], rax
0x180065f91  mov     rbx, [rbp+90h+arg_30]
0x180065f98  xor     r15d, r15d
0x180065f9b  mov     eax, [r8+8]
0x180065f9f  mov     [r11-20h], rsi
0x180065fa3  mov     [r11-28h], rdi
0x180065fa7  mov     [r11-30h], r12
0x180065fab  mov     r12, rcx
0x180065fae  mov     rcx, [rbp+90h+arg_38]
0x180065fb5  mov     [r11-38h], r13
0x180065fb9  mov     r13, rdx
0x180065fbc  mov     [r11-40h], r14
0x180065fc0  mov     r14, [rbp+90h+arg_28]
0x180065fc7  mov     [rsp+190h+var_158], rbx
0x180065fcc  mov     rbx, [r12]
0x180065fd0  mov     [rsp+190h+var_160], r9d
0x180065fd5  mov     [rsp+190h+var_150], r8
0x180065fda  mov     [rsp+190h+var_148], rcx
0x180065fdf  cmp     [rbp+90h+arg_40], r15d
0x180065fe6  jz      short loc_18006600E
0x180065fe8  test    eax, eax
0x180065fea  jz      short loc_180066000
0x180065fec  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x180065ff3  mov     rcx, r12
0x180065ff6  call    sqlite3ErrorMsg
0x180065ffb  jmp     loc_1800667D6
0x180066000  mov     edi, 1
0x180066005  lea     rsi, [rbx+0C5h]
0x18006600c  jmp     short loc_180066065
0x18006600e  lea     rsi, [rbx+0C5h]
0x180066015  test    eax, eax
0x180066017  jz      short loc_18006605E
0x180066019  cmp     [rsi], r15b
0x18006601c  jz      short loc_180066032
0x18006601e  lea     rdx, aCorruptDatabas; "corrupt database"
0x180066025  mov     rcx, r12
0x180066028  call    sqlite3ErrorMsg
0x18006602d  jmp     loc_1800667D6
0x180066032  mov     rcx, rbx
0x180066035  call    sqlite3FindDb
0x18006603a  mov     edi, eax
0x18006603c  test    eax, eax
0x18006603e  jns     short loc_180066057
0x180066040  mov     r8, r13
0x180066043  lea     rdx, aUnknownDatabas_0; "unknown database %T"
0x18006604a  mov     rcx, r12
0x18006604d  call    sqlite3ErrorMsg
0x180066052  jmp     loc_1800667D6
0x180066057  mov     r13, [rsp+190h+var_150]
0x18006605c  jmp     short loc_180066065
0x18006605e  movzx   edi, byte ptr [rbx+0C4h]
0x180066065  mov     rcx, [rsp+190h+var_158]
0x18006606a  test    rcx, rcx
0x18006606d  jz      loc_1800667D6
0x180066073  cmp     [rbx+67h], r15b
0x180066077  jnz     loc_1800667D6
0x18006607d  cmp     [rsi], r15b
0x180066080  jz      short loc_1800660F5
0x180066082  cmp     edi, 1
0x180066085  jz      short loc_1800660F5
0x180066087  mov     rcx, [rcx+10h]
0x18006608b  test    rcx, rcx
0x18006608e  jz      short loc_1800660EC
0x180066090  cmp     rcx, [rbx+1F0h]
0x180066097  jnb     short loc_1800660D1
0x180066099  cmp     rcx, [rbx+1E0h]
0x1800660a0  jb      short loc_1800660B5
0x1800660a2  mov     rax, [rbx+1D8h]
0x1800660a9  mov     [rcx], rax
0x1800660ac  mov     [rbx+1D8h], rcx
0x1800660b3  jmp     short loc_1800660EC
0x1800660b5  cmp     rcx, [rbx+1E8h]
0x1800660bc  jb      short loc_1800660D1
0x1800660be  mov     rax, [rbx+1C8h]
0x1800660c5  mov     [rcx], rax
0x1800660c8  mov     [rbx+1C8h], rcx
0x1800660cf  jmp     short loc_1800660EC
0x1800660d1  cmp     [rbx+308h], r15
0x1800660d8  jz      short loc_1800660E7
0x1800660da  mov     rdx, rcx
0x1800660dd  mov     rcx, rbx
0x1800660e0  call    measureAllocationSize
0x1800660e5  jmp     short loc_1800660EC
0x1800660e7  call    sqlite3_free
0x1800660ec  mov     rcx, [rsp+190h+var_158]
0x1800660f1  mov     [rcx+10h], r15
0x1800660f5  mov     rdx, rcx
0x1800660f8  mov     rcx, r12
0x1800660fb  call    sqlite3SrcListLookup
0x180066100  cmp     [rsi], r15b
0x180066103  jnz     short loc_180066129
0x180066105  mov     rcx, [rsp+190h+var_150]
0x18006610a  cmp     [rcx+8], r15d
0x18006610e  jnz     short loc_180066129
0x180066110  test    rax, rax
0x180066113  jz      short loc_180066129
0x180066115  mov     rcx, [rbx+20h]
0x180066119  mov     rcx, [rcx+38h]
0x18006611d  cmp     [rax+60h], rcx
0x180066121  mov     eax, 1
0x180066126  cmovz   edi, eax
0x180066129  cmp     [rbx+67h], r15b
0x18006612d  jnz     loc_1800667D6
0x180066133  mov     rdx, [r12]
0x180066137  xorps   xmm0, xmm0
0x18006613a  mov     [rsp+190h+var_130], r12
0x18006613f  mov     r8d, edi
0x180066142  shl     r8, 5
0x180066146  mov     rax, [rdx+20h]
0x18006614a  cmp     edi, 1
0x18006614d  movups  [rbp+90h+var_B0], xmm0
0x180066151  mov     [rsp+190h+var_140], r8
0x180066156  movups  [rbp+90h+var_D0], xmm0
0x18006615a  mov     rcx, [r8+rax]
0x18006615e  mov     [rbp+90h+var_E8], rcx
0x180066162  mov     rax, [rdx+20h]
0x180066166  lea     rdx, [rbp+90h+var_D0]
0x18006616a  movups  [rbp+90h+var_C0], xmm0
0x18006616e  movups  [rbp+90h+var_A0], xmm0
0x180066172  mov     rcx, [r8+rax+18h]
0x180066177  lea     rax, aTrigger; "trigger"
0x18006617e  mov     [rbp+90h+var_E0], rax
0x180066182  setz    [rbp+90h+var_F0]
0x180066186  lea     rax, fixExprCb
0x18006618d  mov     [rbp+90h+var_F8], rcx
0x180066191  mov     [rsp+190h+var_120], rax
0x180066196  lea     rcx, [rsp+190h+var_128]
0x18006619b  lea     rax, fixSelectCb
0x1800661a2  mov     [rbp+90h+var_D8], r13
0x1800661a6  mov     [rsp+190h+var_118], rax
0x1800661ab  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x1800661b2  mov     [rbp+90h+var_110], rax
0x1800661b6  xor     eax, eax
0x1800661b8  mov     [rbp+90h+var_104], ax
0x1800661bc  lea     rax, [rsp+190h+var_130]
0x1800661c1  mov     [rbp+90h+var_100], rax
0x1800661c5  mov     rax, [rsp+190h+var_158]
0x1800661ca  mov     qword ptr [rbp+90h+var_B0+8], rax
0x1800661ce  mov     [rsp+190h+var_128], r12
0x1800661d3  mov     [rbp+90h+var_108], r15d
0x1800661d7  movups  [rbp+90h+var_90], xmm0
0x1800661db  movups  [rbp+90h+var_80], xmm0
0x1800661df  movups  [rbp+90h+var_70], xmm0
0x1800661e3  movups  [rbp+90h+var_60], xmm0
0x1800661e7  call    sqlite3WalkSelect
0x1800661ec  test    eax, eax
0x1800661ee  jnz     loc_1800667D6
0x1800661f4  mov     rdx, [rsp+190h+var_158]
0x1800661f9  mov     rcx, r12
0x1800661fc  xor     esi, esi
0x1800661fe  call    sqlite3SrcListLookup
0x180066203  mov     [rsp+190h+var_150], rax
0x180066208  test    rax, rax
0x18006620b  jz      short loc_180066222
0x18006620d  cmp     byte ptr [rax+3Fh], 1
0x180066211  jnz     short loc_18006626B
0x180066213  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x18006621a  mov     rcx, r12
0x18006621d  call    sqlite3ErrorMsg
0x180066222  cmp     byte ptr [rbx+0C4h], 1
0x180066229  jnz     short loc_180066232
0x18006622b  or      dword ptr [rbx+0C8h], 1
0x180066232  test    rsi, rsi
0x180066235  jz      loc_1800667D6
0x18006623b  cmp     rsi, [rbx+1F0h]
0x180066242  jnb     loc_1800667B7
0x180066248  cmp     rsi, [rbx+1E0h]
0x18006624f  jb      loc_18006679B
0x180066255  mov     rax, [rbx+1D8h]
0x18006625c  mov     [rsi], rax
0x18006625f  mov     [rbx+1D8h], rsi
0x180066266  jmp     loc_1800667D6
0x18006626b  mov     rdx, r13
0x18006626e  mov     rcx, rbx
0x180066271  call    sqlite3NameFromToken
0x180066276  mov     rsi, rax
0x180066279  test    rax, rax
0x18006627c  jz      loc_1800667D6
0x180066282  mov     rax, [rsp+190h+var_150]
0x180066287  lea     r8, aTrigger; "trigger"
0x18006628e  mov     rdx, rsi
0x180066291  mov     rcx, r12
0x180066294  mov     r9, [rax]
0x180066297  call    sqlite3CheckObjectName
0x18006629c  test    eax, eax
0x18006629e  jnz     short loc_18006623B
0x1800662a0  cmp     byte ptr [r12+12Ch], 2
0x1800662a9  jnb     short loc_180066322
0x1800662ab  mov     rax, [rbx+20h]
0x1800662af  xor     r8d, r8d
0x1800662b2  mov     rcx, [rsp+190h+var_140]
0x1800662b7  mov     rdx, rsi
0x1800662ba  mov     rcx, [rax+rcx+18h]
0x1800662bf  add     rcx, 38h ; '8'
0x1800662c3  call    findElementWithHash
0x1800662c8  cmp     [rax+10h], r15
0x1800662cc  jz      short loc_180066322
0x1800662ce  mov     rcx, r12
0x1800662d1  cmp     [rbp+90h+arg_48], r15d
0x1800662d8  jnz     short loc_1800662EE
0x1800662da  mov     r8, r13
0x1800662dd  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x1800662e4  call    sqlite3ErrorMsg
0x1800662e9  jmp     loc_18006623B
0x1800662ee  mov     rax, [r12+0A8h]
0x1800662f6  test    rax, rax
0x1800662f9  cmovnz  rcx, rax
0x1800662fd  mov     eax, [rcx+7Ch]
0x180066300  bt      eax, edi
0x180066303  jb      loc_18006623B
0x180066309  bts     eax, edi
0x18006630c  mov     [rcx+7Ch], eax
0x18006630f  cmp     edi, 1
0x180066312  jnz     loc_18006623B
0x180066318  call    sqlite3OpenTempDatabase
0x18006631d  jmp     loc_18006623B
0x180066322  mov     rdi, [rsp+190h+var_150]
0x180066327  mov     r10d, 7
0x18006632d  mov     r11, [rdi]
0x180066330  test    r11, r11
0x180066333  jz      short loc_1800663A3
0x180066335  mov     edx, r10d
0x180066338  lea     r9, aSqlite_0; "sqlite_"
0x18006633f  mov     r8, r11
0x180066342  lea     r13, qword_180114680
0x180066349  nop     dword ptr [rax+00000000h]
0x180066350  movzx   ecx, byte ptr [r8]
0x180066354  dec     edx
0x180066356  test    cl, cl
0x180066358  jz      short loc_180066375
0x18006635a  movzx   eax, byte ptr [r9]
0x18006635e  movzx   eax, byte ptr [rax+r13]
0x180066363  cmp     [rcx+r13], al
0x180066367  jnz     short loc_180066375
0x180066369  inc     r8
0x18006636c  inc     r9
0x18006636f  test    edx, edx
0x180066371  jg      short loc_180066350
0x180066373  dec     edx
0x180066375  test    edx, edx
0x180066377  js      short loc_18006638F
0x180066379  movzx   eax, byte ptr [r9]
0x18006637d  movzx   ecx, byte ptr [rax+r13]
0x180066382  movzx   eax, byte ptr [r8]
0x180066386  movzx   eax, byte ptr [rax+r13]
0x18006638b  cmp     eax, ecx
0x18006638d  jnz     short loc_1800663A3
0x18006638f  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x180066396  mov     rcx, r12
0x180066399  call    sqlite3ErrorMsg
0x18006639e  jmp     loc_18006623B
0x1800663a3  cmp     byte ptr [rdi+3Fh], 2
0x1800663a7  jnz     short loc_1800663E4
0x1800663a9  mov     ecx, [rsp+190h+var_160]
0x1800663ad  cmp     ecx, 41h ; 'A'
0x1800663b0  jz      short loc_180066408
0x1800663b2  mov     r9, [rsp+190h+var_158]
0x1800663b7  lea     rax, aBefore; "BEFORE"
0x1800663be  add     r9, 8
0x1800663c2  lea     r8, aAfter; "AFTER"
0x1800663c9  cmp     ecx, 21h ; '!'
0x1800663cc  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x1800663d3  mov     rcx, r12
0x1800663d6  cmovz   r8, rax
0x1800663da  call    sqlite3ErrorMsg
0x1800663df  jmp     loc_180066222
0x1800663e4  cmp     [rsp+190h+var_160], 41h ; 'A'
0x1800663e9  jnz     short loc_180066408
0x1800663eb  mov     r8, [rsp+190h+var_158]
0x1800663f0  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x1800663f7  add     r8, 8
0x1800663fb  mov     rcx, r12
0x1800663fe  call    sqlite3ErrorMsg
0x180066403  jmp     loc_180066222
0x180066408  cmp     byte ptr [r12+12Ch], 2
0x180066411  jnb     loc_1800664D1
0x180066417  mov     rcx, [rdi+60h]
0x18006641b  mov     edi, 0FFFF8000h
0x180066420  test    rcx, rcx
0x180066423  jz      short loc_180066450
0x180066425  mov     rdx, [rbx+20h]
0x180066429  xor     edi, edi
0x18006642b  cmp     [rdx+18h], rcx
0x18006642f  jz      short loc_180066450
0x180066431  nop     dword ptr [rax+00h]
0x180066435  nop     word ptr [rax+rax+00000000h]
0x180066440  inc     edi
0x180066442  movsxd  rax, edi
0x180066445  shl     rax, 5
0x180066449  cmp     [rax+rdx+18h], rcx
0x18006644e  jnz     short loc_180066440
0x180066450  mov     rcx, [rbx+20h]
  ... truncated ...
```
