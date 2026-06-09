# attachFunc

- ea: `0x1800ac8c0`
- end: `0x1800ad49b`
- name: `attachFunc`
- size: `3035`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `broker_com_uri`

## callees

- `0x1800ac8c0`
- `0x1800c9f30`
- `0x1800fa150`
- `0x1800ffd30`
- `0x180101bb0`
- `0x180105010`
- `0x180108840`
- `0x180108920`
- `0x1801089d0`
- `0x18010b1f0`
- `0x18011a7e0`
- `0x18011ddf0`
- `0x18011eb80`
- `0x18011ef50`
- `0x180120cc0`
- `0x180121780`
- `0x180129ee0`
- `0x18012c240`
- `0x180143100`
- `0x180143700`
- `0x180156080`
- `0x180158e20`
- `0x180158ea0`
- `0x18015db30`
- `0x18015f250`
- `0x1801f7110`
- `0x1802421a0`
- `0x180242d80`
- `0x180242e40`

## string_xrefs

- `0x1800acb57`: `database %s is already in use`
- `0x1800ace1a`: `database is already attached`
- `0x1800ad3a9`: `unable to open database: %s`

## pseudocode

```c
int __fastcall attachFunc(__int64 *a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rsi
  unsigned int v5; // r14d
  __int64 *v6; // rdi
  __int64 v7; // rcx
  char *v8; // r15
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  wchar_t *v14; // r12
  const char *v15; // rcx
  bool v16; // zf
  __int64 i; // rbx
  unsigned __int64 v18; // r9
  __int64 v19; // rsi
  __int64 v20; // r12
  __int64 v21; // rbx
  __int64 v22; // rcx
  int v23; // r8d
  int v24; // esi
  unsigned int v25; // ebx
  unsigned __int64 v26; // rdx
  _OWORD *v27; // rcx
  unsigned __int64 v28; // r8
  __int64 v29; // rbx
  const char *v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rbx
  char *v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rax
  int v38; // r14d
  signed __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  int v43; // esi
  size_t v44; // r14
  __int64 v45; // rdx
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rsi
  size_t v49; // r12
  size_t v50; // r8
  __int64 v51; // rax
  __int64 *v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rax
  __int16 v56; // cx
  __int64 v57; // rdx
  size_t v58; // rsi
  int v59; // ebx
  const char *v60; // rsi
  __int64 v61; // r8
  size_t v62; // rsi
  int v63; // ebx
  const char *v64; // rsi
  int v65; // ebx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // rcx
  size_t v69; // rsi
  int v70; // ebx
  const char *v71; // rsi
  int v72; // eax
  __int64 v73; // rdx
  __int64 v74; // r8
  _QWORD *v75; // r8
  unsigned int v76; // ebx
  __int64 v77; // rax
  char *v78; // rcx
  char *v79; // rbx
  int v80; // eax
  __int64 v81; // rbx
  int v82; // esi
  __int64 v83; // rcx
  __int64 *v84; // rbx
  __int64 v85; // rdx
  __int64 v86; // rcx
  int v87; // eax
  int v88; // r9d
  __int64 v90; // [rsp+30h] [rbp-49h] BYREF
  void *Src; // [rsp+38h] [rbp-41h]
  __int64 *v92; // [rsp+40h] [rbp-39h]
  char *Str; // [rsp+48h] [rbp-31h] BYREF
  char *v94; // [rsp+50h] [rbp-29h] BYREF
  const char *v95; // [rsp+58h] [rbp-21h]
  __int64 v96; // [rsp+60h] [rbp-19h] BYREF
  __int64 v97; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v98[40]; // [rsp+70h] [rbp-9h] BYREF

  v3 = 0;
  v92 = a1;
  v5 = 0;
  if ( a1 )
    v6 = *(__int64 **)(*a1 + 24);
  else
    v6 = 0;
  v7 = *a3;
  v8 = 0;
  v94 = 0;
  Str = 0;
  v97 = 0;
  if ( v7 )
  {
    v10 = *(unsigned __int16 *)(v7 + 20);
    if ( (v10 & 0x202) == 0x202 && *(_BYTE *)(v7 + 22) == 1 )
    {
      v9 = *(_QWORD *)(v7 + 8);
    }
    else if ( (v10 & 1) != 0 )
    {
      v9 = 0;
    }
    else
    {
      LOBYTE(v10) = 1;
      v9 = valueToText(v7, v10);
    }
  }
  else
  {
    v9 = 0;
  }
  v11 = a3[1];
  if ( v11 )
  {
    v13 = *(unsigned __int16 *)(v11 + 20);
    if ( (v13 & 0x202) == 0x202 && *(_BYTE *)(v11 + 22) == 1 )
    {
      v12 = *(_QWORD *)(v11 + 8);
    }
    else if ( (v13 & 1) != 0 )
    {
      v12 = 0;
    }
    else
    {
      LOBYTE(v13) = 1;
      v12 = valueToText(v11, v13);
    }
  }
  else
  {
    v12 = 0;
  }
  v14 = (wchar_t *)&byte_1802990D8;
  v15 = (const char *)&byte_1802990D8;
  if ( v9 )
    v15 = (const char *)v9;
  v95 = v15;
  if ( v12 )
    v14 = (wchar_t *)v12;
  v16 = (v6[25] & 4) == 0;
  Src = v14;
  if ( !v16 )
  {
    v90 = 0;
    if ( (_BYTE)word_1803379C4 )
    {
      v12 = xmmword_180337A30(2);
      v3 = v12;
      if ( v12 )
        LODWORD(v12) = xmmword_180337A40(v12);
    }
    for ( i = qword_1803DC8B0; i; i = *(_QWORD *)(i + 16) )
    {
      LODWORD(v12) = strcmp("memdb", *(const char **)(i + 24));
      if ( !(_DWORD)v12 )
        break;
    }
    if ( v3 )
      LODWORD(v12) = xmmword_180337A50(v3);
    if ( !i )
      return v12;
    LODWORD(v12) = sqlite3BtreeOpen(i, "x", v6, &v90, 0, 256);
    v5 = v12;
    if ( (_DWORD)v12 )
      goto LABEL_195;
    v19 = v90;
    v20 = sqlite3SchemaGet(v6, v90);
    if ( !v20 )
    {
      LODWORD(v12) = sqlite3BtreeClose(v19);
      v5 = 7;
      goto LABEL_195;
    }
    v21 = v6[4] + 32LL * *((unsigned __int8 *)v6 + 196);
    v22 = *(_QWORD *)(v21 + 8);
    if ( v22 )
      sqlite3BtreeClose(v22);
    *(_QWORD *)(v21 + 24) = v20;
    v14 = (wchar_t *)Src;
    *(_QWORD *)(v21 + 8) = v19;
    *((_BYTE *)v6 + 111) = 0;
LABEL_99:
    v51 = sqlite3SchemaGet(v6, *(_QWORD *)(v21 + 8));
    *(_QWORD *)(v21 + 24) = v51;
    if ( v51 )
    {
      if ( *(_BYTE *)(v51 + 112) && *(_BYTE *)(v51 + 113) != *((_BYTE *)v6 + 100) )
      {
        v97 = sqlite3MPrintf(v6, "attached databases must use the same text encoding as main database");
        v5 = 1;
      }
    }
    else
    {
      v5 = 7;
    }
    v52 = *(__int64 **)(*(_QWORD *)(v21 + 8) + 8LL);
    v53 = *v52;
    if ( !*(_BYTE *)(*v52 + 16) )
    {
      v54 = *(_QWORD *)(v53 + 328);
      if ( !v54 || *(_BYTE *)(v54 + 63) != 2 )
        *(_BYTE *)(v53 + 8) = *((_BYTE *)v6 + 105);
    }
    v55 = *(_QWORD *)(v6[4] + 8);
    if ( v55 )
      v56 = (*(_WORD *)(*(_QWORD *)(v55 + 8) + 40LL) >> 2) & 3;
    else
      v56 = 0;
    v57 = *(_QWORD *)(v21 + 8);
    if ( v57 )
    {
      *(_WORD *)(*(_QWORD *)(v57 + 8) + 40LL) &= 0xFFF3u;
      *(_WORD *)(*(_QWORD *)(v57 + 8) + 40LL) |= 4 * v56;
    }
    LODWORD(v12) = sqlite3PagerSetFlags(**(_QWORD **)(*(_QWORD *)(v21 + 8) + 8LL), v6[6] & 0x38 | 3);
    goto LABEL_114;
  }
  v23 = *((_DWORD *)v6 + 41);
  v24 = *((_DWORD *)v6 + 10);
  if ( v24 >= v23 + 2 )
  {
    v12 = sqlite3MPrintf(v6, "too many attached databases - max %d", v23);
    v97 = v12;
    goto LABEL_195;
  }
  v25 = 0;
  if ( v24 > 0 )
  {
    while ( !(unsigned int)sqlite3DbIsNamed(v6, v25, v14) )
    {
      if ( (int)++v25 >= v24 )
        goto LABEL_45;
    }
    v12 = sqlite3MPrintf(v6, "database %s is already in use", (const char *)v14);
    v97 = v12;
    goto LABEL_195;
  }
LABEL_45:
  v26 = v6[4];
  if ( (__int64 *)v26 == v6 + 82 )
  {
    v12 = sqlite3DbMallocRawNN(v6, 96);
    v26 = v12;
    if ( !v12 )
      return v12;
    v27 = (_OWORD *)v6[4];
    *(_OWORD *)v12 = *v27;
    *(_OWORD *)(v12 + 16) = v27[1];
    *(_OWORD *)(v12 + 32) = v27[2];
    *(_OWORD *)(v12 + 48) = v27[3];
  }
  else
  {
    v28 = 32LL * (v24 + 1);
    if ( v26 )
    {
      if ( v26 < v6[60] )
      {
        if ( v26 < v6[58] )
        {
          if ( v26 >= v6[59] && v28 <= *((unsigned __int16 *)v6 + 203) )
            goto LABEL_59;
        }
        else if ( v28 <= 0x80 )
        {
          goto LABEL_59;
        }
      }
      v12 = dbReallocFinish(v6, v26, v28);
    }
    else
    {
      v12 = sqlite3DbMallocRawNN(v6, 32LL * (v24 + 1));
    }
    v26 = v12;
    if ( !v12 )
      return v12;
  }
LABEL_59:
  v29 = *((int *)v6 + 10);
  v6[4] = v26;
  v21 = v26 + 32 * v29;
  v30 = v95;
  *(_OWORD *)v21 = 0;
  *(_OWORD *)(v21 + 16) = 0;
  v31 = *v6;
  LODWORD(v90) = *((_DWORD *)v6 + 19);
  LODWORD(v12) = sqlite3ParseUri(*(_QWORD *)(v31 + 24), v30, &v90, &v96, &v94, &Str);
  if ( (_DWORD)v12 )
  {
    if ( (_DWORD)v12 == 7 )
      LODWORD(v12) = sqlite3OomFault(v6);
    v34 = v92;
    v35 = Str;
    if ( !v92 )
      goto LABEL_84;
    *((_DWORD *)v92 + 9) = 1;
    v36 = *v34;
    if ( v35 )
    {
      v37 = *(_QWORD *)(v36 + 24);
      if ( v37 )
        v38 = *(_DWORD *)(v37 + 136);
      else
        v38 = 1000000000;
      v39 = strlen(v35);
      v43 = v39;
      if ( v39 > v38 )
      {
        if ( (*(_WORD *)(v36 + 20) & 0x9000) != 0 )
          vdbeMemClearExternAndSetNull(v36, v40, v41);
        else
          *(_WORD *)(v36 + 20) = 1;
        v12 = *(_QWORD *)(v36 + 24);
        if ( v12 )
        {
          v12 = *(_QWORD *)(v12 + 336);
          if ( v12 )
          {
            ++*(_DWORD *)(v12 + 48);
            *(_DWORD *)(v12 + 24) = 18;
          }
        }
        goto LABEL_84;
      }
      v44 = v39 + 1;
      v45 = 32;
      if ( v39 + 1 > 32 )
        v45 = (unsigned int)v44;
      if ( *(_DWORD *)(v36 + 32) >= (int)v45 )
      {
        v46 = *(_QWORD *)(v36 + 40);
        *(_WORD *)(v36 + 20) &= 0x2Du;
        *(_QWORD *)(v36 + 8) = v46;
      }
      else
      {
        _mm_lfence();
        LODWORD(v12) = sqlite3VdbeMemGrow(v36, v45, 0, v42);
        if ( (_DWORD)v12 )
          goto LABEL_84;
      }
      LODWORD(v12) = (unsigned int)memmove(*(void **)(v36 + 8), v35, v44);
      *(_WORD *)(v36 + 20) = 514;
      *(_DWORD *)(v36 + 16) = v43 & 0x7FFFFFFF;
      *(_BYTE *)(v36 + 22) = 1;
    }
    else
    {
      LODWORD(v12) = 36864;
      if ( (*(_WORD *)(v36 + 20) & 0x9000) != 0 )
        LODWORD(v12) = vdbeMemClearExternAndSetNull(v36, v32, v33);
      else
        *(_WORD *)(v36 + 20) = 1;
    }
LABEL_84:
    if ( v35 )
    {
      if ( dword_1803379C0 )
      {
        if ( (_QWORD)xmmword_1803DC8D0 )
          xmmword_180337A40(xmmword_1803DC8D0);
        v47 = (*((__int64 (__fastcall **)(char *))&xmmword_1803379F0 + 1))(v35);
        --qword_1803DC858;
        qword_1803DC810 -= v47;
        LODWORD(v12) = (*((__int64 (__fastcall **)(char *))&xmmword_1803379E0 + 1))(v35);
        if ( (_QWORD)xmmword_1803DC8D0 )
          LODWORD(v12) = xmmword_180337A50(xmmword_1803DC8D0);
      }
      else
      {
        LODWORD(v12) = (*((__int64 (__fastcall **)(char *))&xmmword_1803379E0 + 1))(v35);
      }
    }
    return v12;
  }
  v8 = v94;
  LODWORD(v12) = sqlite3BtreeOpen(v96, v94, v6, v21 + 8, 0, (unsigned int)v90 | 0x100);
  ++*((_DWORD *)v6 + 10);
  v5 = v12;
  if ( v14 )
  {
    v49 = strlen((const char *)v14) + 1;
    v12 = sqlite3DbMallocRawNN(v6, v49);
    v48 = v12;
    if ( v12 )
    {
      v50 = v49;
      v14 = (wchar_t *)Src;
      LODWORD(v12) = (unsigned int)memmove((void *)v12, Src, v50);
    }
    else
    {
      v14 = (wchar_t *)Src;
    }
  }
  else
  {
    v48 = 0;
  }
  *(_QWORD *)v21 = v48;
  *((_BYTE *)v6 + 111) = 0;
  if ( v5 == 19 )
  {
    v5 = 1;
    v12 = sqlite3MPrintf(v6, "database is already attached");
    v97 = v12;
    *(_BYTE *)(v21 + 16) = 3;
    goto LABEL_170;
  }
  if ( !v5 )
    goto LABEL_99;
LABEL_114:
  *(_BYTE *)(v21 + 16) = 3;
  if ( !v5 )
  {
    if ( !*(_QWORD *)v21 )
    {
      v5 = 7;
      goto LABEL_170;
    }
    v12 = *(_WORD *)(a3[2] + 20) & 0x3F;
    switch ( *((_BYTE *)qword_18026F2C0 + v12) )
    {
      case 1:
      case 2:
        v12 = sqlite3DbMallocRawNN(v6, 18);
        if ( v12 )
          strcpy((char *)v12, "Invalid key value");
        v97 = v12;
        v5 = 1;
        break;
      case 3:
      case 4:
        v76 = sqlite3_value_bytes(a3[2]);
        v77 = sqlite3_value_blob(a3[2]);
        LODWORD(v12) = sqlite3CodecAttach(v6, (unsigned int)(*((_DWORD *)v6 + 10) - 1), v77, v76);
        v5 = v12;
        break;
      case 5:
        if ( v8 )
        {
          v58 = (size_t)&v8[(strlen(v8) & 0x3FFFFFFF) + 1];
          if ( v58 )
          {
            while ( *(_BYTE *)v58 )
            {
              v59 = strcmp((const char *)v58, "hexkey");
              v60 = (const char *)((strlen((const char *)v58) & 0x3FFFFFFF) + v58 + 1);
              if ( !v59 )
              {
                if ( !v60 || !*v60 )
                  break;
                LODWORD(v12) = 0;
                v18 = 0x180000000uLL;
                v65 = 0;
                LOBYTE(v61) = 0;
                do
                {
                  v66 = *(unsigned __int8 *)v60;
                  if ( (*((_BYTE *)&qword_18026E9A0 + v66) & 8) == 0 )
                    break;
                  LOBYTE(v61) = 16 * v61;
                  LODWORD(v12) = ((char)v66 >> 6) & 1;
                  LOBYTE(v66) = (v66 - 7 * v12) & 0xF;
                  v61 = (unsigned int)(v66 + v61);
                  if ( (v65 & 1) != 0 )
                  {
                    v12 = (unsigned __int64)(unsigned int)v65 >> 1;
                    v98[v12] = v61;
                  }
                  ++v65;
                  ++v60;
                }
                while ( v65 < 80 );
                if ( dword_1803380D4 )
                {
                  v67 = v6[3];
                  if ( v67 )
                    xmmword_180337A40(v67);
                  LODWORD(v12) = sqlite3NameToDb(v6, v14, v61, v18);
                  if ( (int)v12 >= 0 )
                  {
                    _mm_lfence();
                    LODWORD(v12) = sqlite3CodecAttach(v6, (unsigned int)v12, v98, (unsigned int)v65 >> 1);
                  }
                  v68 = v6[3];
                  if ( v68 )
                    LODWORD(v12) = xmmword_180337A50(v68);
                }
                goto LABEL_170;
              }
              if ( v60 )
              {
                v58 = (size_t)&v60[(strlen(v60) & 0x3FFFFFFF) + 1];
                if ( !v58 )
                  break;
              }
              else
              {
                v58 = 1;
              }
            }
          }
          v62 = (size_t)&v8[(strlen(v8) & 0x3FFFFFFF) + 1];
          if ( v62 )
          {
            while ( *(_BYTE *)v62 )
            {
              v63 = strcmp((const char *)v62, "key");
              v64 = (const char *)((strlen((const char *)v62) & 0x3FFFFFFF) + v62 + 1);
              if ( !v63 )
              {
                if ( !v64 )
                  break;
                v72 = strlen(v64);
                LODWORD(v12) = sqlite3_key_v2(v6, v14, v64, v72 & 0x3FFFFFFF);
                goto LABEL_170;
              }
              if ( v64 )
              {
                v62 = (size_t)&v64[(strlen(v64) & 0x3FFFFFFF) + 1];
                if ( !v62 )
                  break;
              }
              else
              {
                v62 = 1;
              }
            }
          }
          v69 = (size_t)&v8[(strlen(v8) & 0x3FFFFFFF) + 1];
          if ( v69 )
          {
            while ( *(_BYTE *)v69 )
            {
              v70 = strcmp((const char *)v69, "textkey");
              v71 = (const char *)((strlen((const char *)v69) & 0x3FFFFFFF) + v69 + 1);
              if ( !v70 )
              {
                if ( !v71 )
                  break;
                LODWORD(v12) = sqlite3_key_v2(v6, v14, v71, 0xFFFFFFFFLL);
                goto LABEL_170;
              }
              if ( v71 )
              {
                v69 = (size_t)&v71[(strlen(v71) & 0x3FFFFFFF) + 1];
                if ( !v69 )
                  break;
              }
              else
              {
                v69 = 1;
              }
            }
          }
        }
        v73 = *(_QWORD *)(*(_QWORD *)(v6[4] + 8) + 8LL);
        v74 = *(_QWORD *)(*(_QWORD *)v73 + 304LL);
        if ( v74 )
        {
          v75 = (_QWORD *)(v74 + 8);
          if ( *v75 )
          {
            v18 = 8;
LABEL_165:
            LODWORD(v12) = sqlite3CodecAttach(v6, (unsigned int)(*((_DWORD *)v6 + 10) - 1), v75, v18);
            v5 = v12;
            break;
          }
        }
        v18 = 0;
        v75 = 0;
        LODWORD(v12) = *(_DWORD *)(v73 + 52) - *(_DWORD *)(v73 + 56);
        if ( *(unsigned __int8 *)(v73 + 38) > (int)v12 )
          LODWORD(v12) = *(unsigned __int8 *)(v73 + 38);
        if ( (int)v12 > 0 )
          goto LABEL_165;
        break;
    }
  }
LABEL_170:
  if ( v8 )
  {
    while ( 1 )
    {
      do
      {
        v16 = *(v8 - 1) == 0;
        LODWORD(v12) = (_DWORD)v8 - 1;
        v78 = v8--;
      }
      while ( !v16 );
      if ( !*(v78 - 2) && !*(v78 - 3) )
      {
        v79 = v78 - 4;
        if ( !*(v78 - 4) )
          break;
      }
    }
    if ( v78 != (char *)4 )
    {
      if ( dword_1803379C0 )
      {
        if ( (_QWORD)xmmword_1803DC8D0 )
          xmmword_180337A40(xmmword_1803DC8D0);
        v80 = (*((__int64 (__fastcall **)(char *))&xmmword_1803379F0 + 1))(v79);
        --qword_1803DC858;
        qword_1803DC810 -= v80;
        LODWORD(v12) = (*((__int64 (__fastcall **)(char *))&xmmword_1803379E0 + 1))(v79);
        if ( (_QWORD)xmmword_1803DC8D0 )
          LODWORD(v12) = xmmword_180337A50(xmmword_1803DC8D0);
      }
      else
      {
        LODWORD(v12) = (*((__int64 (__fastcall **)(char *))&xmmword_1803379E0 + 1))(v78 - 4);
      }
    }
  }
  if ( v5
    || (*((_DWORD *)v6 + 11) &= ~0x10u, v16 = (v6[25] & 4) == 0, *((_BYTE *)v6 + 196) = 0, v16)
    && (LODWORD(v12) = sqlite3Init(v6, &v97), (v5 = v12) != 0) )
  {
    if ( (v6[25] & 4) == 0 )
    {
      v81 = 32LL * *((int *)v6 + 10);
      v82 = *((_DWORD *)v6 + 10) - 1;
      v83 = *(_QWORD *)(v81 + v6[4] - 24);
      if ( v83 )
      {
        sqlite3BtreeClose(v83);
        *(_QWORD *)(v6[4] + v81 - 24) = 0;
        *(_QWORD *)(v6[4] + v81 - 8) = 0;
      }
      LODWORD(v12) = sqlite3ResetAllSchemasOfConnection(v6);
      *((_DWORD *)v6 + 10) = v82;
      if ( v5 == 7 || v5 == 3082 )
      {
        sqlite3OomFault(v6);
        if ( v97 )
          sqlite3DbFreeNN(v6);
        v12 = sqlite3MPrintf(v6, "out of memory");
        v97 = v12;
      }
      else
      {
        if ( v97 )
          goto LABEL_196;
        v12 = sqlite3MPrintf(v6, "unable to open database: %s", v95);
        v97 = v12;
      }
    }
LABEL_195:
    if ( !v97 )
    {
      v84 = v92;
LABEL_201:
      if ( v5 )
      {
        if ( v84 )
        {
          v12 = *v84;
          *((_DWORD *)v84 + 9) = v5;
          if ( (*(_BYTE *)(v12 + 20) & 1) != 0 )
          {
            v87 = sqlite3_errstr(v5);
            LOBYTE(v88) = 1;
            LODWORD(v12) = setResultStrOrError((_DWORD)v84, v87, -1, v88, 0);
          }
        }
      }
      return v12;
    }
LABEL_196:
    v84 = v92;
    if ( v92 )
    {
      v85 = v97;
      LOBYTE(v18) = 1;
      v86 = *v92;
      *((_DWORD *)v92 + 9) = 1;
      LODWORD(v12) = sqlite3VdbeMemSetStr(v86, v85, -1, v18, -1);
    }
    if ( v97 )
      LODWORD(v12) = sqlite3DbFreeNN(v6);
    goto LABEL_201;
  }
  return v12;
}

```

## disassembly

```asm
0x1800ac8c0  mov     [rsp-8+arg_8], rbx
0x1800ac8c5  push    rbp
0x1800ac8c6  push    rsi
0x1800ac8c7  push    rdi
0x1800ac8c8  push    r12
0x1800ac8ca  push    r13
0x1800ac8cc  push    r14
0x1800ac8ce  push    r15
0x1800ac8d0  lea     rbp, [rsp-27h]
0x1800ac8d5  sub     rsp, 0A0h
0x1800ac8dc  mov     rax, cs:__security_cookie
0x1800ac8e3  xor     rax, rsp
0x1800ac8e6  mov     [rbp+57h+var_38], rax
0x1800ac8ea  xor     esi, esi
0x1800ac8ec  mov     [rbp+57h+var_90], rcx
0x1800ac8f0  mov     r13, r8
0x1800ac8f3  mov     r14d, esi
0x1800ac8f6  test    rcx, rcx
0x1800ac8f9  jnz     short loc_1800AC8FF
0x1800ac8fb  mov     edi, esi
0x1800ac8fd  jmp     short loc_1800AC906
0x1800ac8ff  mov     rax, [rcx]
0x1800ac902  mov     rdi, [rax+18h]
0x1800ac906  mov     rcx, [r8]
0x1800ac909  mov     r15, rsi
0x1800ac90c  mov     [rbp+57h+var_80], rsi
0x1800ac910  mov     r8d, 202h
0x1800ac916  mov     [rbp+57h+Str], rsi
0x1800ac91a  mov     [rbp+57h+var_68], rsi
0x1800ac91e  test    rcx, rcx
0x1800ac921  jnz     short loc_1800AC928
0x1800ac923  mov     rbx, rsi
0x1800ac926  jmp     short loc_1800AC95F
0x1800ac928  movzx   edx, word ptr [rcx+14h]
0x1800ac92c  movzx   eax, dx
0x1800ac92f  and     ax, r8w
0x1800ac933  cmp     ax, r8w
0x1800ac937  jnz     short loc_1800AC945
0x1800ac939  cmp     byte ptr [rcx+16h], 1
0x1800ac93d  jnz     short loc_1800AC945
0x1800ac93f  mov     rbx, [rcx+8]
0x1800ac943  jmp     short loc_1800AC95F
0x1800ac945  test    dl, 1
0x1800ac948  jz      short loc_1800AC94F
0x1800ac94a  mov     rbx, rsi
0x1800ac94d  jmp     short loc_1800AC95F
0x1800ac94f  mov     dl, 1
0x1800ac951  call    valueToText
0x1800ac956  mov     rbx, rax
0x1800ac959  mov     r8d, 202h
0x1800ac95f  mov     rcx, [r13+8]
0x1800ac963  test    rcx, rcx
0x1800ac966  jnz     short loc_1800AC96D
0x1800ac968  mov     rax, rsi
0x1800ac96b  jmp     short loc_1800AC99B
0x1800ac96d  movzx   edx, word ptr [rcx+14h]
0x1800ac971  movzx   eax, dx
0x1800ac974  and     ax, r8w
0x1800ac978  cmp     ax, r8w
0x1800ac97c  jnz     short loc_1800AC98A
0x1800ac97e  cmp     byte ptr [rcx+16h], 1
0x1800ac982  jnz     short loc_1800AC98A
0x1800ac984  mov     rax, [rcx+8]
0x1800ac988  jmp     short loc_1800AC99B
0x1800ac98a  test    dl, 1
0x1800ac98d  jz      short loc_1800AC994
0x1800ac98f  mov     rax, rsi
0x1800ac992  jmp     short loc_1800AC99B
0x1800ac994  mov     dl, 1
0x1800ac996  call    valueToText
0x1800ac99b  test    rbx, rbx
0x1800ac99e  lea     r12, byte_1802990D8
0x1800ac9a5  mov     rcx, r12
0x1800ac9a8  cmovnz  rcx, rbx
0x1800ac9ac  test    rax, rax
0x1800ac9af  mov     [rbp+57h+var_78], rcx
0x1800ac9b3  cmovnz  r12, rax
0x1800ac9b7  test    byte ptr [rdi+0C8h], 4
0x1800ac9be  mov     [rbp+57h+Src], r12
0x1800ac9c2  jz      loc_1800ACABE
0x1800ac9c8  cmp     byte ptr cs:word_1803379C4, sil
0x1800ac9cf  mov     [rbp+57h+var_A0], rsi
0x1800ac9d3  jz      short loc_1800AC9F1
0x1800ac9d5  mov     ecx, 2
0x1800ac9da  call    qword ptr cs:xmmword_180337A30
0x1800ac9e0  mov     rsi, rax
0x1800ac9e3  test    rax, rax
0x1800ac9e6  jz      short loc_1800AC9F1
0x1800ac9e8  mov     rcx, rax
0x1800ac9eb  call    qword ptr cs:xmmword_180337A40
0x1800ac9f1  mov     rbx, cs:qword_1803DC8B0
0x1800ac9f8  test    rbx, rbx
0x1800ac9fb  jz      short loc_1800ACA1D
0x1800ac9fd  nop     dword ptr [rax]
0x1800aca00  mov     rdx, [rbx+18h]; Str2
0x1800aca04  lea     rcx, Str1; "memdb"
0x1800aca0b  call    strcmp
0x1800aca10  test    eax, eax
0x1800aca12  jz      short loc_1800ACA1D
0x1800aca14  mov     rbx, [rbx+10h]
0x1800aca18  test    rbx, rbx
0x1800aca1b  jnz     short loc_1800ACA00
0x1800aca1d  test    rsi, rsi
0x1800aca20  jz      short loc_1800ACA2B
0x1800aca22  mov     rcx, rsi
0x1800aca25  call    qword ptr cs:xmmword_180337A50
0x1800aca2b  test    rbx, rbx
0x1800aca2e  jz      loc_1800AD474
0x1800aca34  mov     dword ptr [rsp+0D0h+var_A8], 100h
0x1800aca3c  lea     r9, [rbp+57h+var_A0]
0x1800aca40  mov     r8, rdi
0x1800aca43  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800aca48  lea     rdx, asc_180277C04; "x"
0x1800aca4f  mov     rcx, rbx
0x1800aca52  call    sqlite3BtreeOpen
0x1800aca57  mov     r14d, eax
0x1800aca5a  test    eax, eax
0x1800aca5c  jnz     loc_1800AD3EF
0x1800aca62  mov     rsi, [rbp+57h+var_A0]
0x1800aca66  mov     rcx, rdi
0x1800aca69  mov     rdx, rsi
0x1800aca6c  call    sqlite3SchemaGet
0x1800aca71  mov     r12, rax
0x1800aca74  test    rax, rax
0x1800aca77  jz      short loc_1800ACAAB
0x1800aca79  movzx   ebx, byte ptr [rdi+0C4h]
0x1800aca80  shl     rbx, 5
0x1800aca84  add     rbx, [rdi+20h]
0x1800aca88  mov     rcx, [rbx+8]
0x1800aca8c  test    rcx, rcx
0x1800aca8f  jz      short loc_1800ACA96
0x1800aca91  call    sqlite3BtreeClose
0x1800aca96  mov     [rbx+18h], r12
0x1800aca9a  mov     r12, [rbp+57h+Src]
0x1800aca9e  mov     [rbx+8], rsi
0x1800acaa2  mov     [rdi+6Fh], r15b
0x1800acaa6  jmp     loc_1800ACE45
0x1800acaab  mov     rcx, rsi
0x1800acaae  call    sqlite3BtreeClose
0x1800acab3  mov     r14d, 7
0x1800acab9  jmp     loc_1800AD3EF
0x1800acabe  mov     r8d, [rdi+0A4h]
0x1800acac5  mov     esi, [rdi+28h]
0x1800acac8  lea     eax, [r8+2]
0x1800acacc  cmp     esi, eax
0x1800acace  jl      short loc_1800ACAE8
0x1800acad0  lea     rdx, aTooManyAttache; "too many attached databases - max %d"
0x1800acad7  mov     rcx, rdi
0x1800acada  call    sqlite3MPrintf
0x1800acadf  mov     [rbp+57h+var_68], rax
0x1800acae3  jmp     loc_1800AD3EF
0x1800acae8  mov     ebx, r15d
0x1800acaeb  test    esi, esi
0x1800acaed  jle     short loc_1800ACB07
0x1800acaef  nop
0x1800acaf0  mov     r8, r12
0x1800acaf3  mov     edx, ebx
0x1800acaf5  mov     rcx, rdi
0x1800acaf8  call    sqlite3DbIsNamed
0x1800acafd  test    eax, eax
0x1800acaff  jnz     short loc_1800ACB54
0x1800acb01  inc     ebx
0x1800acb03  cmp     ebx, esi
0x1800acb05  jl      short loc_1800ACAF0
0x1800acb07  mov     rdx, [rdi+20h]
0x1800acb0b  lea     rax, [rdi+290h]
0x1800acb12  cmp     rdx, rax
0x1800acb15  jnz     short loc_1800ACB6F
0x1800acb17  mov     edx, 60h ; '`'
0x1800acb1c  mov     rcx, rdi
0x1800acb1f  call    sqlite3DbMallocRawNN
0x1800acb24  mov     rdx, rax
0x1800acb27  test    rax, rax
0x1800acb2a  jz      loc_1800AD474
0x1800acb30  mov     rcx, [rdi+20h]
0x1800acb34  movups  xmm0, xmmword ptr [rcx]
0x1800acb37  movups  xmmword ptr [rax], xmm0
0x1800acb3a  movups  xmm1, xmmword ptr [rcx+10h]
0x1800acb3e  movups  xmmword ptr [rax+10h], xmm1
0x1800acb42  movups  xmm0, xmmword ptr [rcx+20h]
0x1800acb46  movups  xmmword ptr [rax+20h], xmm0
0x1800acb4a  movups  xmm1, xmmword ptr [rcx+30h]
0x1800acb4e  movups  xmmword ptr [rax+30h], xmm1
0x1800acb52  jmp     short loc_1800ACBD1
0x1800acb54  mov     r8, r12
0x1800acb57  lea     rdx, aDatabaseSIsAlr; "database %s is already in use"
0x1800acb5e  mov     rcx, rdi
0x1800acb61  call    sqlite3MPrintf
0x1800acb66  mov     [rbp+57h+var_68], rax
0x1800acb6a  jmp     loc_1800AD3EF
0x1800acb6f  lea     eax, [rsi+1]
0x1800acb72  movsxd  r8, eax
0x1800acb75  shl     r8, 5
0x1800acb79  test    rdx, rdx
0x1800acb7c  jnz     short loc_1800ACB8B
0x1800acb7e  mov     rdx, r8
0x1800acb81  mov     rcx, rdi
0x1800acb84  call    sqlite3DbMallocRawNN
0x1800acb89  jmp     short loc_1800ACBC5
0x1800acb8b  cmp     rdx, [rdi+1E0h]
0x1800acb92  jnb     short loc_1800ACBBD
0x1800acb94  cmp     rdx, [rdi+1D0h]
0x1800acb9b  jb      short loc_1800ACBA8
0x1800acb9d  cmp     r8, 80h
0x1800acba4  ja      short loc_1800ACBBD
0x1800acba6  jmp     short loc_1800ACBD1
0x1800acba8  cmp     rdx, [rdi+1D8h]
0x1800acbaf  jb      short loc_1800ACBBD
0x1800acbb1  movzx   eax, word ptr [rdi+196h]
0x1800acbb8  cmp     r8, rax
0x1800acbbb  jbe     short loc_1800ACBD1
0x1800acbbd  mov     rcx, rdi
0x1800acbc0  call    dbReallocFinish
0x1800acbc5  mov     rdx, rax
0x1800acbc8  test    rax, rax
0x1800acbcb  jz      loc_1800AD474
0x1800acbd1  movsxd  rbx, dword ptr [rdi+28h]
0x1800acbd5  lea     r9, [rbp+57h+var_70]
0x1800acbd9  mov     [rdi+20h], rdx
0x1800acbdd  lea     r8, [rbp+57h+var_A0]
0x1800acbe1  xorps   xmm0, xmm0
0x1800acbe4  shl     rbx, 5
0x1800acbe8  add     rbx, rdx
0x1800acbeb  mov     rdx, [rbp+57h+var_78]
0x1800acbef  movups  xmmword ptr [rbx], xmm0
0x1800acbf2  movups  xmmword ptr [rbx+10h], xmm0
0x1800acbf6  mov     eax, [rdi+4Ch]
0x1800acbf9  mov     rcx, [rdi]
0x1800acbfc  mov     dword ptr [rbp+57h+var_A0], eax
0x1800acbff  lea     rax, [rbp+57h+Str]
0x1800acc03  mov     [rsp+0D0h+var_A8], rax
0x1800acc08  lea     rax, [rbp+57h+var_80]
0x1800acc0c  mov     [rsp+0D0h+var_B0], rax
0x1800acc11  mov     rcx, [rcx+18h]
0x1800acc15  call    sqlite3ParseUri
0x1800acc1a  test    eax, eax
0x1800acc1c  jz      loc_1800ACDA0
0x1800acc22  cmp     eax, 7
0x1800acc25  jnz     short loc_1800ACC2F
0x1800acc27  mov     rcx, rdi
0x1800acc2a  call    sqlite3OomFault
0x1800acc2f  mov     rbx, [rbp+57h+var_90]
0x1800acc33  mov     rdi, [rbp+57h+Str]
0x1800acc37  test    rbx, rbx
0x1800acc3a  jz      loc_1800ACD30
0x1800acc40  mov     r15d, 1
0x1800acc46  mov     [rbx+24h], r15d
0x1800acc4a  mov     rbx, [rbx]
0x1800acc4d  test    rdi, rdi
0x1800acc50  jnz     short loc_1800ACC74
0x1800acc52  mov     eax, 9000h
0x1800acc57  test    [rbx+14h], ax
0x1800acc5b  jz      short loc_1800ACC6A
0x1800acc5d  mov     rcx, rbx
0x1800acc60  call    vdbeMemClearExternAndSetNull
0x1800acc65  jmp     loc_1800ACD30
0x1800acc6a  mov     [rbx+14h], r15w
0x1800acc6f  jmp     loc_1800ACD30
0x1800acc74  mov     rax, [rbx+18h]
0x1800acc78  test    rax, rax
0x1800acc7b  jz      short loc_1800ACC86
0x1800acc7d  mov     r14d, [rax+88h]
0x1800acc84  jmp     short loc_1800ACC8C
0x1800acc86  mov     r14d, 3B9ACA00h
0x1800acc8c  mov     rcx, rdi; Str
0x1800acc8f  call    strlen
0x1800acc94  movsxd  rcx, r14d
0x1800acc97  mov     rsi, rax
0x1800acc9a  cmp     rax, rcx
0x1800acc9d  jle     short loc_1800ACCDA
0x1800acc9f  mov     eax, 9000h
0x1800acca4  test    [rbx+14h], ax
0x1800acca8  jz      short loc_1800ACCB4
0x1800accaa  mov     rcx, rbx
0x1800accad  call    vdbeMemClearExternAndSetNull
0x1800accb2  jmp     short loc_1800ACCB9
0x1800accb4  mov     [rbx+14h], r15w
0x1800accb9  mov     rax, [rbx+18h]
0x1800accbd  test    rax, rax
0x1800accc0  jz      short loc_1800ACD30
0x1800accc2  mov     rax, [rax+150h]
0x1800accc9  test    rax, rax
0x1800acccc  jz      short loc_1800ACD30
0x1800accce  inc     dword ptr [rax+30h]
0x1800accd1  mov     dword ptr [rax+18h], 12h
0x1800accd8  jmp     short loc_1800ACD30
0x1800accda  lea     r14, [rax+1]
0x1800accde  mov     edx, 20h ; ' '
0x1800acce3  cmp     r14, rdx
0x1800acce6  cmovg   edx, r14d
0x1800accea  cmp     [rbx+20h], edx
0x1800acced  jge     short loc_1800ACD03
0x1800accef  lfence
0x1800accf2  xor     r8d, r8d
0x1800accf5  mov     rcx, rbx
0x1800accf8  call    sqlite3VdbeMemGrow
0x1800accfd  test    eax, eax
0x1800accff  jnz     short loc_1800ACD30
0x1800acd01  jmp     short loc_1800ACD10
0x1800acd03  mov     rax, [rbx+28h]
  ... truncated ...
```
