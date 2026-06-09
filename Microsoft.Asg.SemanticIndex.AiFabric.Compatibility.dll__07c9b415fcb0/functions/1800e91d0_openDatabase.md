# openDatabase

- ea: `0x1800e91d0`
- end: `0x1800ea282`
- name: `openDatabase`
- size: `4274`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180156450`

## callees

- `0x1800bd140`
- `0x1800c97f0`
- `0x1800d1180`
- `0x1800d5a70`
- `0x1800e91d0`
- `0x1800fa360`
- `0x180101bb0`
- `0x180103860`
- `0x180105010`
- `0x180108840`
- `0x1801089d0`
- `0x18010b240`
- `0x18010b340`
- `0x180115540`
- `0x180119dd0`
- `0x18011de20`
- `0x18011e6c0`
- `0x18011ef50`
- `0x180121780`
- `0x18012c240`
- `0x1801309e0`
- `0x180155860`
- `0x180156080`
- `0x180156260`
- `0x180156350`
- `0x1801f7110`
- `0x180242860`
- `0x180242d80`
- `0x180242e40`

## string_xrefs

- `0x1800e9723`: `unopened`
- `0x1800e98ac`: `unopened`
- `0x1800e9e73`: `unopened`
- `0x1800e9d69`: `automatic extension loading failed: %s`
- `0x1800e9a21`: `unable to delete/modify user-function due to active statements`

## pseudocode

```c
__int64 __fastcall openDatabase(__int64 a1, const char **a2, unsigned int a3, __int64 a4)
{
  int v4; // ebx
  unsigned int v5; // edi
  __int64 v7; // r15
  unsigned int v8; // r12d
  int v9; // r14d
  int v10; // ebp
  unsigned int v11; // edi
  char *v12; // rax
  char *v13; // rsi
  const char *v14; // rbp
  __int64 v15; // rax
  int v16; // eax
  int v17; // r8d
  int v18; // r8d
  unsigned int v19; // ebp
  char *v20; // rax
  unsigned int v21; // eax
  const char *v22; // r8
  const char *v23; // r13
  int v24; // eax
  __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // rcx
  char v28; // al
  __int64 v29; // rdi
  __int64 v30; // rdi
  char v31; // al
  const char *v32; // r8
  __int64 v33; // rdi
  int v34; // r15d
  __int64 ElementWithHash; // rax
  __int64 v36; // rdx
  char v37; // al
  int v38; // ecx
  int v39; // esi
  __int64 i; // rdx
  char v41; // al
  int v42; // ecx
  __int64 v43; // r13
  char v44; // cl
  unsigned int v45; // edi
  const char *v46; // r8
  int v47; // edi
  __int64 v48; // rax
  _DWORD *v49; // r15
  _DWORD *v50; // rcx
  __int64 v51; // rdi
  int v52; // esi
  __int64 v53; // rdx
  char v54; // al
  int v55; // ecx
  int v56; // esi
  __int64 j; // rdx
  char v58; // al
  int v59; // ecx
  __int64 k; // rax
  __int64 v61; // rdi
  int v62; // esi
  __int64 v63; // rdx
  char v64; // al
  int v65; // ecx
  __int64 v66; // rax
  __int64 v67; // rsi
  unsigned __int8 *v68; // rcx
  unsigned __int8 m; // al
  __int64 v70; // rax
  char v71; // al
  unsigned int v72; // eax
  __int64 (__fastcall **v73)(); // rdi
  unsigned int v74; // r15d
  __int64 v75; // rdi
  __int64 v76; // rax
  __int64 (__fastcall *v77)(const char *, const char **, _QWORD); // rsi
  const char *v78; // rdi
  unsigned int v79; // eax
  int v80; // eax
  char v81; // al
  int v82; // r9d
  char v83; // al
  bool v84; // zf
  const char *v85; // rax
  __int64 v86; // rcx
  const char **v87; // rax
  char *v88; // r14
  char *v89; // rcx
  char *v90; // rbx
  int v91; // eax
  size_t v92; // rsi
  int v93; // edi
  const char *v94; // rsi
  size_t v95; // rdi
  int v96; // ebx
  const char *v97; // rdi
  char v98; // r8
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // rcx
  size_t v102; // rdi
  int v103; // ebx
  const char *v104; // rdi
  int v105; // eax
  char *Str; // [rsp+30h] [rbp-B8h]
  char *v109; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v110; // [rsp+48h] [rbp-A0h] BYREF
  const char **v111; // [rsp+50h] [rbp-98h]
  const char *v112; // [rsp+58h] [rbp-90h] BYREF
  unsigned int v113; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v114[40]; // [rsp+68h] [rbp-80h] BYREF

  v4 = 0;
  v111 = a2;
  v5 = a3;
  Str = 0;
  v109 = 0;
  v7 = 0;
  v110 = 0;
  if ( !a2 )
  {
    v8 = 21;
    sqlite3_log(
      21,
      "%s at line %d of [%.10s]",
      "misuse",
      183493,
      "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
    return v8;
  }
  *a2 = 0;
  v9 = 1;
  if ( (_BYTE)word_1803379C4 )
  {
    if ( (a3 & 0x8000) != 0 )
    {
      v10 = 0;
    }
    else
    {
      v10 = 1;
      if ( (a3 & 0x10000) == 0 )
        v10 = HIBYTE(word_1803379C4);
    }
  }
  else
  {
    v10 = 0;
  }
  if ( (a3 & 0x40000) != 0 )
  {
    v5 = a3 & 0xFFFDFFFF;
  }
  else if ( dword_180337B0C )
  {
    v5 = a3 | 0x20000;
  }
  v11 = v5 & 0xFFF600E7;
  v113 = v11;
  v12 = (char *)sqlite3Malloc(776);
  v13 = v12;
  if ( !v12 )
  {
    v14 = 0;
    goto LABEL_239;
  }
  memset(v12, 0, 0x308u);
  if ( v10 )
  {
    if ( !(_BYTE)word_1803379C4 )
    {
      *((_QWORD *)v13 + 3) = 0;
      sqlite3_free(v13);
      v14 = 0;
LABEL_239:
      v8 = 7;
      goto LABEL_240;
    }
    v15 = xmmword_180337A30(1);
    *((_QWORD *)v13 + 3) = v15;
    if ( !v15 )
    {
      sqlite3_free(v13);
      v14 = 0;
      goto LABEL_239;
    }
  }
  if ( *((_QWORD *)v13 + 3) )
    ((void (*)(void))xmmword_180337A40)();
  *((_DWORD *)v13 + 10) = 2;
  v13[113] = 109;
  *((_DWORD *)v13 + 100) = 1;
  v16 = 255;
  *((_WORD *)v13 + 202) = 0;
  if ( (v11 & 0x2000000) != 0 )
    v16 = -1;
  *((_DWORD *)v13 + 22) = v16;
  *((_QWORD *)v13 + 4) = v13 + 656;
  *(_OWORD *)(v13 + 136) = xmmword_18026CEA8;
  *(_OWORD *)(v13 + 152) = xmmword_18026CEB8;
  v13[101] = 1;
  v13[106] = -1;
  *(_OWORD *)(v13 + 168) = xmmword_18026CEC8;
  *((_DWORD *)v13 + 45) = 0;
  *((_QWORD *)v13 + 8) = qword_180337AE8;
  *((_QWORD *)v13 + 26) = off_180337B90;
  *((_QWORD *)v13 + 6) |= 0x8004C0E0uLL;
  *((_DWORD *)v13 + 29) = 0;
  *((_QWORD *)v13 + 77) = 0;
  *((_QWORD *)v13 + 76) = 0;
  *((_QWORD *)v13 + 78) = 0;
  *((_QWORD *)v13 + 68) = 0;
  *((_QWORD *)v13 + 67) = 0;
  *((_QWORD *)v13 + 69) = 0;
  createCollation((_DWORD)v13, (unsigned int)"BINARY", 1, 0, (__int64)&binCollFunc, 0);
  LOBYTE(v17) = 3;
  createCollation((_DWORD)v13, (unsigned int)"BINARY", v17, 0, (__int64)&binCollFunc, 0);
  LOBYTE(v18) = 2;
  createCollation((_DWORD)v13, (unsigned int)"BINARY", v18, 0, (__int64)&binCollFunc, 0);
  createCollation((_DWORD)v13, (unsigned int)"NOCASE", 1, 0, (__int64)nocaseCollatingFunc, 0);
  createCollation((_DWORD)v13, (unsigned int)"RTRIM", 1, 0, (__int64)&rtrimCollFunc, 0);
  v14 = v13;
  v8 = 21;
  if ( v13[103] )
    goto LABEL_43;
  *((_DWORD *)v13 + 19) = v11;
  if ( ((1 << (v11 & 7)) & 0x46) != 0 )
  {
    v21 = sqlite3ParseUri(a4, a1, &v113, v13, &v109, &v110);
    v7 = v110;
    v19 = v21;
    v20 = v109;
    v11 = v113;
    Str = v109;
  }
  else
  {
    v19 = sqlite3MisuseError(183708);
    v20 = 0;
  }
  if ( !v19 )
  {
    v26 = sqlite3BtreeOpen(*(_QWORD *)v13, v20, v13, *((_QWORD *)v13 + 4) + 8LL, 0, v11 | 0x100);
    if ( v26 )
    {
      if ( v26 == 3082 )
        v26 = 7;
      *((_DWORD *)v13 + 20) = v26;
      sqlite3ErrorFinish(v13, v26);
      v14 = v13;
LABEL_43:
      v23 = v13;
      goto LABEL_44;
    }
    v29 = *((_QWORD *)v13 + 4);
    *(_QWORD *)(v29 + 24) = sqlite3SchemaGet(v13, *(_QWORD *)(v29 + 8));
    if ( !v13[103] )
      sqlite3SetTextEncoding(v13, *(unsigned __int8 *)(*(_QWORD *)(*((_QWORD *)v13 + 4) + 24LL) + 113LL));
    v30 = *((_QWORD *)v13 + 4);
    *(_QWORD *)(v30 + 56) = sqlite3SchemaGet(v13, 0);
    v14 = v13;
    v23 = v13;
    **((_QWORD **)v13 + 4) = "main";
    *(_BYTE *)(*((_QWORD *)v13 + 4) + 16LL) = 3;
    *(_QWORD *)(*((_QWORD *)v13 + 4) + 32LL) = "temp";
    *(_BYTE *)(*((_QWORD *)v13 + 4) + 48LL) = 1;
    v13[113] = 118;
    if ( v13[103] )
      goto LABEL_44;
    *((_DWORD *)v13 + 20) = 0;
    if ( *((_QWORD *)v13 + 48) )
      sqlite3ErrorFinish(v13, 0);
    else
      *((_DWORD *)v13 + 21) = -1;
    v31 = v13[113];
    if ( v31 != 118 )
    {
      if ( v31 == -70 || (v32 = "invalid", v31 == 109) )
        v32 = "unopened";
      sqlite3_log(21, "API call with %s database connection pointer", v32);
      sqlite3_log(
        21,
        "%s at line %d of [%.10s]",
        "misuse",
        182390,
        "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
      goto LABEL_170;
    }
    if ( *((_QWORD *)v13 + 3) )
      ((void (*)(void))xmmword_180337A40)();
    v33 = 0;
    v34 = 0;
    ElementWithHash = findElementWithHash(v13 + 584, "MATCH", 0);
    v112 = v13;
    v36 = *(_QWORD *)(ElementWithHash + 16);
    if ( !v36 )
      goto LABEL_88;
    v112 = v13;
    do
    {
      v37 = *(_BYTE *)v36;
      if ( *(char *)v36 < 0 || v37 == 2 )
      {
        v38 = 4;
        if ( v37 != 2 )
          v38 = 1;
        if ( (*(_DWORD *)(v36 + 4) & 3) == 1 )
          v38 += 2;
      }
      else
      {
        v38 = 0;
      }
      if ( v38 > v34 )
      {
        v33 = v36;
        v34 = v38;
      }
      v36 = *(_QWORD *)(v36 + 16);
    }
    while ( v36 );
    if ( !v33 || (v13[44] & 2) != 0 )
    {
LABEL_88:
      v39 = 0;
      for ( i = sqlite3FunctionSearch(22, "MATCH"); i; i = *(_QWORD *)(i + 16) )
      {
        v41 = *(_BYTE *)i;
        if ( *(_BYTE *)i == 2 || v41 < 0 )
        {
          v42 = 4;
          if ( v41 != 2 )
            v42 = 1;
          if ( (*(_DWORD *)(i + 4) & 3) == 1 )
            v42 += 2;
        }
        else
        {
          v42 = 0;
        }
        if ( v42 > v39 )
        {
          v33 = i;
          v39 = v42;
        }
      }
      if ( !v33 )
        goto LABEL_90;
    }
    if ( !*(_QWORD *)(v33 + 24) )
LABEL_90:
      v33 = 0;
    if ( *((_QWORD *)v14 + 3) )
      ((void (*)(void))xmmword_180337A50)();
    if ( v33 )
    {
LABEL_170:
      v71 = v14[113];
      if ( v71 == -70 || v71 == 118 || v71 == 109 )
      {
        if ( v14[103] )
        {
          v72 = 7;
        }
        else
        {
          v72 = *((_DWORD *)v14 + 20) & *((_DWORD *)v14 + 22);
          if ( !v72 )
          {
            v73 = off_180272F70;
            while ( (__int64)v73 < (__int64)&qword_180272F88 )
            {
              v72 = ((__int64 (__fastcall *)(const char *))*v73++)(v14);
              if ( v72 )
                goto LABEL_211;
            }
            if ( dword_1803DCAD8 )
            {
              v74 = 0;
              do
              {
                if ( (_BYTE)word_1803379C4 )
                {
                  v76 = xmmword_180337A30(2);
                  v75 = v76;
                  if ( v76 )
                    xmmword_180337A40(v76);
                }
                else
                {
                  v75 = 0;
                }
                if ( v74 < dword_1803DCAD8 )
                {
                  v77 = *(__int64 (__fastcall **)(const char *, const char **, _QWORD))(qword_1803DCAE0 + 8LL * v74);
                }
                else
                {
                  v77 = 0;
                  v9 = 0;
                }
                if ( v75 )
                  xmmword_180337A50(v75);
                v112 = 0;
                v78 = 0;
                if ( v77 )
                {
                  v79 = v77(v14, &v112, 0);
                  if ( v79 )
                  {
                    sqlite3ErrorWithMsg(v14, v79, "automatic extension loading failed: %s", v112);
                    v9 = 0;
                  }
                  v78 = v112;
                }
                if ( v78 )
                {
                  if ( dword_1803379C0 )
                  {
                    if ( (_QWORD)xmmword_1803DC8D0 )
                      xmmword_180337A40(xmmword_1803DC8D0);
                    v80 = (*((__int64 (__fastcall **)(const char *))&xmmword_1803379F0 + 1))(v78);
                    --qword_1803DC858;
                    qword_1803DC810 -= v80;
                    (*((void (__fastcall **)(const char *))&xmmword_1803379E0 + 1))(v78);
                    if ( (_QWORD)xmmword_1803DC8D0 )
                      xmmword_180337A50(xmmword_1803DC8D0);
                  }
                  else
                  {
                    (*((void (__fastcall **)(const char *))&xmmword_1803379E0 + 1))(v78);
                  }
                }
                ++v74;
              }
              while ( v9 );
            }
            v81 = v14[113];
            if ( v81 != -70 && v81 != 118 && v81 != 109 )
            {
              sqlite3_log(21, "API call with %s database connection pointer", "invalid");
              v82 = 182944;
              goto LABEL_217;
            }
            if ( v14[103] || (*((_DWORD *)v14 + 22) & *((_DWORD *)v14 + 20)) != 0 )
              goto LABEL_44;
LABEL_212:
            setupLookaside(v14, 0, (unsigned int)dword_1803379D4, (unsigned int)dword_1803379D8);
            v83 = v14[113];
            if ( v83 == 118 )
            {
              v86 = *((_QWORD *)v14 + 3);
              if ( v86 )
                xmmword_180337A40(v86);
              v25 = *((_QWORD *)v14 + 3);
              *((_QWORD *)v14 + 43) = sqlite3WalDefaultHook;
              *((_QWORD *)v14 + 44) = 1000;
              if ( v25 )
                goto LABEL_37;
              goto LABEL_44;
            }
            if ( v83 == -70 || (v84 = v83 == 109, v85 = "invalid", v84) )
              v85 = "unopened";
            sqlite3_log(21, "API call with %s database connection pointer", v85);
            v82 = 182659;
LABEL_217:
            sqlite3_log(
              21,
              "%s at line %d of [%.10s]",
              "misuse",
              v82,
              "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
            goto LABEL_44;
          }
        }
      }
      else
      {
        sqlite3_log(21, "API call with %s database connection pointer", "invalid");
        sqlite3_log(
          21,
          "%s at line %d of [%.10s]",
          "misuse",
          182944,
          "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
        v72 = 21;
      }
LABEL_211:
      *((_DWORD *)v14 + 20) = v72;
      sqlite3ErrorFinish(v14, v72);
      goto LABEL_212;
    }
    v43 = sqlite3_mprintf("%s", "MATCH");
    if ( !v43 )
    {
      sqlite3OomFault(v14);
      goto LABEL_169;
    }
    v44 = v14[113];
    v45 = 1;
    if ( v44 != 118 )
    {
      if ( v44 == -70 || (v46 = "invalid", v44 == 109) )
        v46 = "unopened";
      sqlite3_log(21, "API call with %s database connection pointer", v46);
      sqlite3_log(
        21,
        "%s at line %d of [%.10s]",
        "misuse",
        182241,
        "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
      v47 = 21;
      goto LABEL_166;
    }
    if ( *((_QWORD *)v14 + 3) )
      ((void (*)(void))xmmword_180337A40)();
    v48 = sqlite3Malloc(24);
    v49 = (_DWORD *)v48;
    if ( !v48 )
    {
      sqlite3OomFault(v14);
      v50 = (_DWORD *)v43;
      goto LABEL_152;
    }
    *(_DWORD *)v48 = 0;
    *(_QWORD *)(v48 + 16) = v43;
    *(_QWORD *)(v48 + 8) = sqlite3_free;
    v51 = 0;
    v52 = 0;
    v53 = *(_QWORD *)(findElementWithHash(v14 + 584, "MATCH", 0) + 16);
    if ( v53 )
    {
      do
      {
        v54 = *(_BYTE *)v53;
        if ( *(char *)v53 < 0 || v54 == 2 )
        {
          v55 = 4;
          if ( v54 != 2 )
            v55 = 1;
          if ( (*(_DWORD *)(v53 + 4) & 3) == 1 )
            v55 += 2;
        }
        else
        {
          v55 = 0;
        }
        if ( v55 > v52 )
        {
          v51 = v53;
          v52 = v55;
        }
        v53 = *(_QWORD *)(v53 + 16);
      }
      while ( v53 );
      if ( v51 && (v14[44] & 2) == 0 )
        goto LABEL_131;
    }
    v56 = 0;
    for ( j = sqlite3FunctionSearch(22, "MATCH"); j; j = *(_QWORD *)(j + 16) )
    {
      v58 = *(_BYTE *)j;
      if ( *(char *)j < 0 || v58 == 2 )
      {
        v59 = 4;
        if ( v58 != 2 )
          v59 = 1;
        if ( (*(_DWORD *)(j + 4) & 3) == 1 )
          v59 += 2;
      }
      else
      {
        v59 = 0;
      }
      if ( v59 > v56 )
      {
        v51 = j;
        v56 = v59;
      }
    }
    if ( v51 )
    {
LABEL_131:
      if ( *(_QWORD *)(v51 + 24) && (*(_DWORD *)(v51 + 4) & 3) == 1 && *(_BYTE *)v51 == 2 )
      {
        if ( *((_DWORD *)v14 + 54) )
        {
          v45 = 5;
          sqlite3ErrorWithMsg(v14, 5, "unable to delete/modify user-function due to active statements");
LABEL_150:
          if ( *v49 )
          {
LABEL_153:
            if ( v14[103] || v45 )
              v47 = apiHandleError(v14, v45);
            else
              v47 = 0;
            if ( *((_QWORD *)v14 + 3) )
              ((void (*)(void))xmmword_180337A50)();
LABEL_166:
            if ( v47 == 7 )
            {
              sqlite3OomFault(v14);
              v23 = v112;
              goto LABEL_170;
            }
LABEL_169:
            v23 = v112;
            goto LABEL_170;
          }
          sqlite3_free(v43);
          v50 = v49;
LABEL_152:
          sqlite3_free(v50);
          goto LABEL_153;
        }
        for ( k = *((_QWORD *)v14 + 1); k; k = *(_QWORD *)(k + 16) )
        {
          *(_DWORD *)(k + 200) &= ~2u;
          *(_DWORD *)(k + 200) |= 1u;
        }
      }
    }
    v61 = 0;
    v62 = 0;
    v63 = *(_QWORD *)(findElementWithHash(v14 + 584, "MATCH", 0) + 16);
    if ( !v63 )
      goto LABEL_156;
    do
    {
      v64 = *(_BYTE *)v63;
      if ( *(_BYTE *)v63 == 2 || v64 < 0 )
      {
        v65 = 4;
        if ( v64 != 2 )
          v65 = 1;
        if ( (*(_DWORD *)(v63 + 4) & 3) == 1 )
          v65 += 2;
      }
      else
      {
        v65 = 0;
      }
      if ( v65 > v62 )
      {
        v61 = v63;
        v62 = v65;
      }
      v63 = *(_QWORD *)(v63 + 16);
    }
    while ( v63 );
    if ( v62 >= 6 )
    {
      if ( !v61 )
      {
LABEL_149:
        v45 = 7;
        goto LABEL_150;
      }
    }
    else
    {
LABEL_156:
      v66 = sqlite3DbMallocRawNN(v14, 78);
      v67 = v66;
      v61 = v66;
      if ( !v66 )
        goto LABEL_149;
      *(_OWORD *)v66 = 0;
      *(_OWORD *)(v66 + 16) = 0;
      *(_OWORD *)(v66 + 32) = 0;
      *(_OWORD *)(v66 + 48) = 0;
      *(_QWORD *)(v66 + 64) = 0;
      *(_DWORD *)(v66 + 72) = 0;
      *(_WORD *)(v66 + 76) = 0;
      *(_QWORD *)(v66 + 56) = v66 + 72;
      *(_BYTE *)v66 = 2;
      *(_DWORD *)(v66 + 4) = 1;
      strcpy((char *)(v66 + 72), "MATCH");
      v68 = *(unsigned __int8 **)(v66 + 56);
      for ( m = *v68; *v68; m = *v68 )
        *v68++ = *((_BYTE *)qword_18026E880 + m);
      v70 = sqlite3HashInsert(v14 + 584, *(_QWORD *)(v67 + 56), v67);
      if ( v70 == v67 )
      {
        sqlite3DbFreeNN(v14);
        sqlite3OomFault(v14);
        goto LABEL_149;
      }
      *(_QWORD *)(v67 + 16) = v70;
    }
    functionDestroy(v14, v61);
    ++*v49;
    *(_DWORD *)(v61 + 4) &= 3u;
    *(_DWORD *)(v61 + 4) |= 0x200000u;
    *(_QWORD *)(v61 + 24) = sqlite3InvalidFunction;
    *(_QWORD *)(v61 + 64) = v49;
    *(_QWORD *)(v61 + 32) = 0;
    *(_QWORD *)(v61 + 40) = 0;
    *(_QWORD *)(v61 + 48) = 0;
    *(_QWORD *)(v61 + 8) = v43;
    *(_BYTE *)v61 = 2;
    v45 = 0;
    goto LABEL_150;
  }
  if ( v19 == 7 )
    sqlite3OomFault(v13);
  v22 = 0;
  if ( v7 )
    v22 = "%s";
  sqlite3ErrorWithMsg(v13, v19, v22, v7);
  v14 = v13;
  v23 = v13;
  if ( v7 )
  {
    if ( dword_1803379C0 )
    {
      if ( (_QWORD)xmmword_1803DC8D0 )
        xmmword_180337A40(xmmword_1803DC8D0);
      v24 = (*((__int64 (__fastcall **)(__int64))&xmmword_1803379F0 + 1))(v7);
      --qword_1803DC858;
      qword_1803DC810 -= v24;
      (*((void (__fastcall **)(__int64))&xmmword_1803379E0 + 1))(v7);
      v25 = xmmword_1803DC8D0;
      if ( (_QWORD)xmmword_1803DC8D0 )
LABEL_37:
        xmmword_180337A50(v25);
    }
    else
    {
      (*((void (__fastcall **)(__int64))&xmmword_1803379E0 + 1))(v7);
    }
  }
LABEL_44:
  v27 = *((_QWORD *)v14 + 3);
  if ( v27 )
    xmmword_180337A50(v27);
  v28 = v14[113];
  if ( v28 != -70 && v28 != 118 && v28 != 109 )
  {
    sqlite3_log(21, "API call with %s database connection pointer", "invalid");
    sqlite3_log(
      21,
      "%s at line %d of [%.10s]",
      "misuse",
      182944,
      "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
    goto LABEL_225;
  }
  if ( v14[103] )
    goto LABEL_239;
  v8 = *((_DWORD *)v14 + 20) & *((_DWORD *)v14 + 22);
  v14 = v23;
  if ( (_BYTE)v8 != 7 )
  {
    if ( !v8 )
      goto LABEL_241;
LABEL_225:
    v87 = v111;
    *((_BYTE *)v14 + 113) = -70;
    *v87 = v23;
    goto LABEL_226;
  }
LABEL_240:
  sqlite3Close(v14, 0);
  v14 = 0;
LABEL_241:
  *v111 = v14;
  if ( !v8 )
  {
    v88 = Str;
    if ( Str )
    {
      v92 = (size_t)&Str[(strlen(Str) & 0x3FFFFFFF) + 1];
      if ( v92 )
      {
        while ( *(_BYTE *)v92 )
        {
          v93 = strcmp((const char *)v92, "hexkey");
          v94 = (const char *)((strlen((const char *)v92) & 0x3FFFFFFF) + v92 + 1);
          if ( !v93 )
          {
            if ( !v94 || !*v94 )
              break;
            v98 = 0;
            do
            {
              v99 = *(unsigned __int8 *)v94;
              if ( (*((_BYTE *)&qword_18026E9A0 + v99) & 8) == 0 )
                break;
              v98 = ((v99 - 7 * (((char)v99 >> 6) & 1)) & 0xF) + 16 * v98;
              if ( (v4 & 1) != 0 )
                v114[(unsigned __int64)(unsigned int)v4 >> 1] = v98;
              ++v4;
              ++v94;
            }
            while ( v4 < 80 );
            v88 = Str;
            if ( dword_1803380D4 )
            {
              v100 = *((_QWORD *)v14 + 3);
              if ( v100 )
                xmmword_180337A40(v100);
              sqlite3CodecAttach(v14, 0, v114, (unsigned int)v4 >> 1);
              v101 = *((_QWORD *)v14 + 3);
              if ( v101 )
                xmmword_180337A50(v101);
            }
            goto LABEL_227;
          }
          if ( v94 )
          {
            v92 = (size_t)&v94[(strlen(v94) & 0x3FFFFFFF) + 1];
            if ( !v92 )
              break;
          }
          else
          {
            v92 = 1;
          }
        }
      }
      v95 = (size_t)&Str[(strlen(Str) & 0x3FFFFFFF) + 1];
      if ( v95 )
      {
        while ( *(_BYTE *)v95 )
        {
          v96 = strcmp((const char *)v95, "key");
          v97 = (const char *)((strlen((const char *)v95) & 0x3FFFFFFF) + v95 + 1);
          if ( !v96 )
          {
            if ( !v97 )
              break;
            v105 = strlen(v97);
            sqlite3_key_v2(v14, 0, v97, v105 & 0x3FFFFFFF);
            goto LABEL_227;
          }
          if ( v97 )
          {
            v95 = (size_t)&v97[(strlen(v97) & 0x3FFFFFFF) + 1];
            if ( !v95 )
              break;
          }
          else
          {
            v95 = 1;
          }
        }
      }
      v102 = (size_t)&Str[(strlen(Str) & 0x3FFFFFFF) + 1];
      if ( v102 )
      {
        while ( *(_BYTE *)v102 )
        {
          v103 = strcmp((const char *)v102, "textkey");
          v104 = (const char *)((strlen((const char *)v102) & 0x3FFFFFFF) + v102 + 1);
          if ( !v103 )
          {
            if ( v104 )
              sqlite3_key_v2(v14, 0, v104, 0xFFFFFFFFLL);
            goto LABEL_227;
          }
          if ( v104 )
          {
            v102 = (size_t)&v104[(strlen(v104) & 0x3FFFFFFF) + 1];
            if ( !v102 )
              goto LABEL_227;
          }
          else
          {
            v102 = 1;
          }
        }
      }
    }
    goto LABEL_227;
  }
LABEL_226:
  v88 = Str;
LABEL_227:
  if ( v88 )
  {
    while ( 1 )
    {
      do
      {
        v84 = *(v88 - 1) == 0;
        v89 = v88--;
      }
      while ( !v84 );
      if ( !*(v89 - 2) && !*(v89 - 3) )
      {
        v90 = v89 - 4;
        if ( !*(v89 - 4) )
          break;
      }
    }
    if ( v89 != (char *)4 )
    {
      if ( dword_1803379C0 )
      {
        if ( (_QWORD)xmmword_1803DC8D0 )
          xmmword_180337A40(xmmword_1803DC8D0);
        v91 = (*((__int64 (__fastcall **)(char *))&xmmword_1803379F0 + 1))(v90);
        --qword_1803DC858;
        qword_1803DC810 -= v91;
        (*((void (__fastcall **)(char *))&xmmword_1803379E0 + 1))(v90);
        if ( (_QWORD)xmmword_1803DC8D0 )
          xmmword_180337A50(xmmword_1803DC8D0);
      }
      else
      {
        (*((void (__fastcall **)(char *))&xmmword_1803379E0 + 1))(v89 - 4);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800e91d0  push    rbx
0x1800e91d2  push    rdi
0x1800e91d3  push    r12
0x1800e91d5  push    r13
0x1800e91d7  push    r15
0x1800e91d9  sub     rsp, 0C0h
0x1800e91e0  mov     rax, cs:__security_cookie
0x1800e91e7  xor     rax, rsp
0x1800e91ea  mov     [rsp+0E8h+var_58], rax
0x1800e91f2  xor     ebx, ebx
0x1800e91f4  mov     [rsp+0E8h+var_B0], r9
0x1800e91f9  mov     [rsp+0E8h+var_98], rdx
0x1800e91fe  mov     edi, r8d
0x1800e9201  mov     [rsp+0E8h+Str], rbx
0x1800e9206  mov     r13, rcx
0x1800e9209  mov     [rsp+0E8h+var_A8], rbx
0x1800e920e  mov     r15d, ebx
0x1800e9211  mov     [rsp+0E8h+var_A0], rbx
0x1800e9216  test    rdx, rdx
0x1800e9219  jnz     short loc_1800E924E
0x1800e921b  lea     rax, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x1800e9222  mov     r12d, 15h
0x1800e9228  mov     ecx, r12d
0x1800e922b  mov     [rsp+0E8h+var_C8], rax
0x1800e9230  mov     r9d, 2CCC5h
0x1800e9236  lea     r8, aMisuse; "misuse"
0x1800e923d  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x1800e9244  call    sqlite3_log
0x1800e9249  jmp     loc_1800EA25F
0x1800e924e  mov     [rsp+0E8h+var_30], rbp
0x1800e9256  mov     [rsp+0E8h+var_38], rsi
0x1800e925e  mov     [rdx], rbx
0x1800e9261  cmp     byte ptr cs:word_1803379C4, bl
0x1800e9267  mov     [rsp+0E8h+var_40], r14
0x1800e926f  mov     r14d, 1
0x1800e9275  jnz     short loc_1800E927B
0x1800e9277  mov     ebp, ebx
0x1800e9279  jmp     short loc_1800E9295
0x1800e927b  bt      edi, 0Fh
0x1800e927f  jnb     short loc_1800E9285
0x1800e9281  mov     ebp, ebx
0x1800e9283  jmp     short loc_1800E9295
0x1800e9285  mov     ebp, r14d
0x1800e9288  bt      edi, 10h
0x1800e928c  jb      short loc_1800E9295
0x1800e928e  movzx   ebp, byte ptr cs:word_1803379C4+1
0x1800e9295  bt      edi, 12h
0x1800e9299  jnb     short loc_1800E92A1
0x1800e929b  btr     edi, 11h
0x1800e929f  jmp     short loc_1800E92AD
0x1800e92a1  cmp     cs:dword_180337B0C, ebx
0x1800e92a7  jz      short loc_1800E92AD
0x1800e92a9  bts     edi, 11h
0x1800e92ad  and     edi, 0FFF600E7h
0x1800e92b3  mov     ecx, 308h
0x1800e92b8  mov     [rsp+0E8h+var_88], edi
0x1800e92bc  call    sqlite3Malloc
0x1800e92c1  mov     rsi, rax
0x1800e92c4  mov     r12d, 0FFFFFFFFh
0x1800e92ca  test    rax, rax
0x1800e92cd  jz      loc_1800E9FDD
0x1800e92d3  xor     edx, edx; Val
0x1800e92d5  mov     r8d, 308h; Size
0x1800e92db  mov     rcx, rax; void *
0x1800e92de  call    memset
0x1800e92e3  test    ebp, ebp
0x1800e92e5  jz      short loc_1800E9325
0x1800e92e7  cmp     byte ptr cs:word_1803379C4, bl
0x1800e92ed  jnz     short loc_1800E9303
0x1800e92ef  mov     rcx, rsi
0x1800e92f2  mov     [rsi+18h], rbx
0x1800e92f6  call    sqlite3_free
0x1800e92fb  mov     rbp, rbx
0x1800e92fe  jmp     loc_1800E9FE0
0x1800e9303  mov     ecx, r14d
0x1800e9306  call    qword ptr cs:xmmword_180337A30
0x1800e930c  mov     [rsi+18h], rax
0x1800e9310  test    rax, rax
0x1800e9313  jnz     short loc_1800E9325
0x1800e9315  mov     rcx, rsi
0x1800e9318  call    sqlite3_free
0x1800e931d  mov     rbp, rbx
0x1800e9320  jmp     loc_1800E9FE0
0x1800e9325  mov     rcx, [rsi+18h]
0x1800e9329  test    rcx, rcx
0x1800e932c  jz      short loc_1800E9334
0x1800e932e  call    qword ptr cs:xmmword_180337A40
0x1800e9334  mov     dword ptr [rsi+28h], 2
0x1800e933b  lea     rbp, binCollFunc
0x1800e9342  mov     byte ptr [rsi+71h], 6Dh ; 'm'
0x1800e9346  lea     rdx, aBinary_1; "BINARY"
0x1800e934d  mov     [rsi+190h], r14d
0x1800e9354  mov     eax, 0FFh
0x1800e9359  mov     [rsi+194h], bx
0x1800e9360  bt      edi, 19h
0x1800e9364  mov     [rsp+0E8h+var_C0], rbx
0x1800e9369  movzx   r8d, r14b
0x1800e936d  cmovb   eax, r12d
0x1800e9371  mov     [rsp+0E8h+var_C8], rbp
0x1800e9376  mov     [rsi+58h], eax
0x1800e9379  xor     r9d, r9d
0x1800e937c  lea     rax, [rsi+290h]
0x1800e9383  mov     rcx, rsi
0x1800e9386  mov     [rsi+20h], rax
0x1800e938a  movups  xmm0, cs:xmmword_18026CEA8
0x1800e9391  movups  xmmword ptr [rsi+88h], xmm0
0x1800e9398  movups  xmm1, cs:xmmword_18026CEB8
0x1800e939f  movups  xmmword ptr [rsi+98h], xmm1
0x1800e93a6  movups  xmm0, cs:xmmword_18026CEC8
0x1800e93ad  mov     [rsi+65h], r14b
0x1800e93b1  mov     [rsi+6Ah], r12b
0x1800e93b5  movups  xmmword ptr [rsi+0A8h], xmm0
0x1800e93bc  mov     [rsi+0B4h], ebx
0x1800e93c2  mov     rax, cs:qword_180337AE8
0x1800e93c9  mov     [rsi+40h], rax
0x1800e93cd  lea     rax, off_180337B90; "ANY"
0x1800e93d4  mov     [rsi+0D0h], rax
0x1800e93db  mov     eax, 8004C0E0h
0x1800e93e0  or      [rsi+30h], rax
0x1800e93e4  mov     [rsi+74h], ebx
0x1800e93e7  mov     [rsi+268h], rbx
0x1800e93ee  mov     [rsi+260h], rbx
0x1800e93f5  mov     [rsi+270h], rbx
0x1800e93fc  mov     [rsi+220h], rbx
0x1800e9403  mov     [rsi+218h], rbx
0x1800e940a  mov     [rsi+228h], rbx
0x1800e9411  call    createCollation
0x1800e9416  xor     r9d, r9d
0x1800e9419  mov     [rsp+0E8h+var_C0], rbx
0x1800e941e  mov     r8b, 3
0x1800e9421  mov     [rsp+0E8h+var_C8], rbp
0x1800e9426  lea     rdx, aBinary_1; "BINARY"
0x1800e942d  mov     rcx, rsi
0x1800e9430  call    createCollation
0x1800e9435  xor     r9d, r9d
0x1800e9438  mov     [rsp+0E8h+var_C0], rbx
0x1800e943d  mov     r8b, 2
0x1800e9440  mov     [rsp+0E8h+var_C8], rbp
0x1800e9445  lea     rdx, aBinary_1; "BINARY"
0x1800e944c  mov     rcx, rsi
0x1800e944f  call    createCollation
0x1800e9454  lea     rax, nocaseCollatingFunc
0x1800e945b  mov     [rsp+0E8h+var_C0], rbx
0x1800e9460  xor     r9d, r9d
0x1800e9463  mov     [rsp+0E8h+var_C8], rax
0x1800e9468  movzx   r8d, r14b
0x1800e946c  lea     rdx, aNocase; "NOCASE"
0x1800e9473  mov     rcx, rsi
0x1800e9476  call    createCollation
0x1800e947b  lea     rax, rtrimCollFunc
0x1800e9482  mov     [rsp+0E8h+var_C0], rbx
0x1800e9487  xor     r9d, r9d
0x1800e948a  mov     [rsp+0E8h+var_C8], rax
0x1800e948f  movzx   r8d, r14b
0x1800e9493  lea     rdx, aRtrim_0; "RTRIM"
0x1800e949a  mov     rcx, rsi
0x1800e949d  call    createCollation
0x1800e94a2  mov     rbp, rsi
0x1800e94a5  mov     r12d, 15h
0x1800e94ab  cmp     [rsi+67h], bl
0x1800e94ae  jnz     loc_1800E95FA
0x1800e94b4  mov     ecx, edi
0x1800e94b6  mov     [rsi+4Ch], edi
0x1800e94b9  and     ecx, 7
0x1800e94bc  mov     eax, r14d
0x1800e94bf  shl     eax, cl
0x1800e94c1  test    al, 46h
0x1800e94c3  jnz     short loc_1800E94D6
0x1800e94c5  mov     ecx, 2CD9Ch
0x1800e94ca  call    sqlite3MisuseError
0x1800e94cf  mov     ebp, eax
0x1800e94d1  mov     rax, rbx
0x1800e94d4  jmp     short loc_1800E9514
0x1800e94d6  mov     rcx, [rsp+0E8h+var_B0]
0x1800e94db  lea     rax, [rsp+0E8h+var_A0]
0x1800e94e0  mov     [rsp+0E8h+var_C0], rax
0x1800e94e5  lea     r8, [rsp+0E8h+var_88]
0x1800e94ea  lea     rax, [rsp+0E8h+var_A8]
0x1800e94ef  mov     r9, rsi
0x1800e94f2  mov     rdx, r13
0x1800e94f5  mov     [rsp+0E8h+var_C8], rax
0x1800e94fa  call    sqlite3ParseUri
0x1800e94ff  mov     r15, [rsp+0E8h+var_A0]
0x1800e9504  mov     ebp, eax
0x1800e9506  mov     rax, [rsp+0E8h+var_A8]
0x1800e950b  mov     edi, [rsp+0E8h+var_88]
0x1800e950f  mov     [rsp+0E8h+Str], rax
0x1800e9514  test    ebp, ebp
0x1800e9516  jz      loc_1800E95B2
0x1800e951c  cmp     ebp, 7
0x1800e951f  jnz     short loc_1800E9529
0x1800e9521  mov     rcx, rsi
0x1800e9524  call    sqlite3OomFault
0x1800e9529  lea     rcx, aS_9; "%s"
0x1800e9530  test    r15, r15
0x1800e9533  mov     r8, rbx
0x1800e9536  mov     r9, r15
0x1800e9539  cmovnz  r8, rcx
0x1800e953d  mov     edx, ebp
0x1800e953f  mov     rcx, rsi
0x1800e9542  call    sqlite3ErrorWithMsg
0x1800e9547  mov     rbp, rsi
0x1800e954a  mov     r13, rsi
0x1800e954d  test    r15, r15
0x1800e9550  jz      loc_1800E95FD
0x1800e9556  cmp     cs:dword_1803379C0, ebx
0x1800e955c  jz      short loc_1800E95A7
0x1800e955e  mov     rcx, qword ptr cs:xmmword_1803DC8D0
0x1800e9565  test    rcx, rcx
0x1800e9568  jz      short loc_1800E9570
0x1800e956a  call    qword ptr cs:xmmword_180337A40
0x1800e9570  mov     rcx, r15
0x1800e9573  call    qword ptr cs:xmmword_1803379F0+8
0x1800e9579  dec     cs:qword_1803DC858
0x1800e9580  mov     rcx, r15
0x1800e9583  movsxd  rdx, eax
0x1800e9586  sub     cs:qword_1803DC810, rdx
0x1800e958d  call    qword ptr cs:xmmword_1803379E0+8
0x1800e9593  mov     rcx, qword ptr cs:xmmword_1803DC8D0
0x1800e959a  test    rcx, rcx
0x1800e959d  jz      short loc_1800E95FD
0x1800e959f  call    qword ptr cs:xmmword_180337A50
0x1800e95a5  jmp     short loc_1800E95FD
0x1800e95a7  mov     rcx, r15
0x1800e95aa  call    qword ptr cs:xmmword_1803379E0+8
0x1800e95b0  jmp     short loc_1800E95FD
0x1800e95b2  mov     r9, [rsi+20h]
0x1800e95b6  bts     edi, 8
0x1800e95ba  mov     rcx, [rsi]
0x1800e95bd  add     r9, 8
0x1800e95c1  mov     dword ptr [rsp+0E8h+var_C0], edi
0x1800e95c5  mov     r8, rsi
0x1800e95c8  mov     rdx, rax
0x1800e95cb  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x1800e95cf  call    sqlite3BtreeOpen
0x1800e95d4  test    eax, eax
0x1800e95d6  jz      loc_1800E966B
0x1800e95dc  cmp     eax, 0C0Ah
0x1800e95e1  jnz     short loc_1800E95E8
0x1800e95e3  mov     eax, 7
0x1800e95e8  mov     ecx, eax
0x1800e95ea  mov     [rsi+50h], eax
0x1800e95ed  mov     rcx, rsi
0x1800e95f0  mov     edx, eax
0x1800e95f2  call    sqlite3ErrorFinish
0x1800e95f7  mov     rbp, rsi
0x1800e95fa  mov     r13, rsi
0x1800e95fd  lea     rdi, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x1800e9604  mov     rcx, [rbp+18h]
0x1800e9608  test    rcx, rcx
0x1800e960b  jz      short loc_1800E9613
0x1800e960d  call    qword ptr cs:xmmword_180337A50
0x1800e9613  movzx   eax, byte ptr [rbp+71h]
0x1800e9617  cmp     al, 0BAh
0x1800e9619  jz      loc_1800E9EF9
0x1800e961f  cmp     al, 76h ; 'v'
0x1800e9621  jz      loc_1800E9EF9
0x1800e9627  cmp     al, 6Dh ; 'm'
0x1800e9629  jz      loc_1800E9EF9
0x1800e962f  lea     r8, aInvalid; "invalid"
0x1800e9636  mov     ecx, r12d
0x1800e9639  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x1800e9640  call    sqlite3_log
0x1800e9645  mov     r9d, 2CAA0h
0x1800e964b  mov     [rsp+0E8h+var_C8], rdi
0x1800e9650  lea     r8, aMisuse; "misuse"
0x1800e9657  mov     ecx, r12d
0x1800e965a  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x1800e9661  call    sqlite3_log
0x1800e9666  jmp     loc_1800E9F22
0x1800e966b  mov     rdi, [rsi+20h]
0x1800e966f  mov     rcx, rsi
0x1800e9672  mov     rdx, rdi
0x1800e9675  mov     rdx, [rdx+8]
0x1800e9679  call    sqlite3SchemaGet
0x1800e967e  mov     [rdi+18h], rax
0x1800e9682  cmp     [rsi+67h], bl
0x1800e9685  jnz     short loc_1800E969B
0x1800e9687  mov     rax, [rsi+20h]
0x1800e968b  mov     rcx, rsi
0x1800e968e  mov     rdx, [rax+18h]
0x1800e9692  movzx   edx, byte ptr [rdx+71h]
0x1800e9696  call    sqlite3SetTextEncoding
0x1800e969b  mov     rdi, [rsi+20h]
0x1800e969f  xor     edx, edx
0x1800e96a1  mov     rcx, rsi
0x1800e96a4  call    sqlite3SchemaGet
0x1800e96a9  mov     [rdi+38h], rax
0x1800e96ad  lea     rcx, aMain; "main"
0x1800e96b4  mov     rax, [rsi+20h]
0x1800e96b8  mov     rbp, rsi
0x1800e96bb  mov     r13, rsi
0x1800e96be  mov     [rax], rcx
0x1800e96c1  lea     rcx, aTemp; "temp"
0x1800e96c8  mov     rax, [rsi+20h]
0x1800e96cc  mov     byte ptr [rax+10h], 3
0x1800e96d0  mov     rax, [rsi+20h]
0x1800e96d4  mov     [rax+20h], rcx
0x1800e96d8  mov     rax, [rsi+20h]
0x1800e96dc  mov     [rax+30h], r14b
  ... truncated ...
```
