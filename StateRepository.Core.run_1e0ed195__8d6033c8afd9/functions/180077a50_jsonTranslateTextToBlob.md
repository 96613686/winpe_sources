# jsonTranslateTextToBlob

- ea: `0x180077a50`
- end: `0x180078579`
- name: `jsonTranslateTextToBlob`
- size: `2857`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180073c34`
- `0x180076f78`
- `0x180077a50`

## callees

- `0x18004b050`
- `0x180072934`
- `0x180073548`
- `0x180073628`
- `0x18007364c`
- `0x1800752f0`
- `0x18007531c`
- `0x18007534c`
- `0x180077a50`
- `0x1800997f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180077af0`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180077fe5`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x1800781d5`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180077af0`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180077fe5`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x1800781d5`

## pseudocode

```c
__int64 __fastcall jsonTranslateTextToBlob(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 v5; // r13
  __int64 v6; // rdx
  _BYTE *v7; // r11
  unsigned int v8; // r15d
  char v9; // r14
  unsigned int v10; // r9d
  unsigned __int8 *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdi
  __int64 v14; // rdx
  int v15; // eax
  char v16; // r10
  char v17; // r11
  __int64 v18; // r9
  __int64 v19; // rdx
  char v20; // cl
  unsigned __int64 v21; // r8
  int v22; // ecx
  __int64 v23; // rcx
  __int64 v25; // rcx
  unsigned int v26; // r14d
  __int64 v27; // r8
  unsigned int v28; // r15d
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rbp
  __int64 v32; // rdx
  __int64 v33; // rax
  int v34; // r9d
  unsigned __int8 *v35; // rcx
  __int64 v36; // r15
  __int64 v37; // rcx
  int v38; // eax
  int v39; // eax
  char v40; // al
  __int64 v41; // rcx
  int v42; // eax
  int v43; // eax
  bool v44; // zf
  __int64 v45; // rdx
  unsigned int v46; // r13d
  int v47; // r15d
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rdi
  char *v51; // rax
  const char *v52; // r9
  char v53; // al
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // r8
  char v58; // cl
  __int64 v59; // rax
  __int64 v60; // r14
  __int64 v61; // rdi
  int v62; // r13d
  __int64 v63; // rdx
  _BYTE *v64; // [rsp+70h] [rbp+8h] BYREF
  int v65; // [rsp+78h] [rbp+10h]
  unsigned int v66; // [rsp+80h] [rbp+18h]
  unsigned int v67; // [rsp+88h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 16);
  LODWORD(v5) = -1;
  while ( 1 )
  {
    v6 = 9;
    v7 = (_BYTE *)(v2 + a2);
    v64 = v7;
    v8 = (unsigned __int8)*v7;
    if ( v8 > 0x34 )
      break;
    if ( v8 == 52 )
      goto LABEL_21;
    if ( v8 > 0x2B )
    {
      switch ( v8 )
      {
        case ',':
          v26 = -4;
          goto LABEL_231;
        case '-':
          goto LABEL_21;
        case '.':
          if ( (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(a2 + 1 + v2)) & 4) != 0 )
          {
            *(_BYTE *)(a1 + 49) = 1;
            LOBYTE(v6) = 3;
            v9 = 0;
            goto LABEL_81;
          }
LABEL_230:
          v26 = -1;
LABEL_231:
          *(_DWORD *)(a1 + 40) = a2;
          return v26;
      }
      if ( v8 != 47 )
      {
        if ( v8 == 48 || v8 == 49 || v8 - 50 <= 1 )
          goto LABEL_21;
LABEL_219:
        v60 = 0;
        while ( 1 )
        {
          v61 = 12 * v60;
          if ( (_BYTE)v8 == byte_18009C340[24 * v60] || (_BYTE)v8 == byte_18009C340[v61 * 2 + 1] )
          {
            v62 = SLOBYTE(word_18009C342[12 * v60]);
            if ( !(unsigned int)sqlite3_strnicmp(v7, off_18009C348[3 * v60]) )
            {
              v5 = a2 + v62;
              if ( (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(v5 + v2)) & 6) == 0 )
                break;
            }
          }
          v60 = (unsigned int)(v60 + 1);
          if ( (unsigned int)v60 >= 5 )
            goto LABEL_230;
          v7 = v64;
        }
        if ( HIBYTE(word_18009C342[v61]) == 5 )
        {
          LOBYTE(v63) = 5;
          jsonBlobAppendNode(a1, v63, 5, "9e999");
        }
        else
        {
          jsonBlobAppendOneByte(a1, 0);
        }
        *(_BYTE *)(a1 + 49) = 1;
        return (unsigned int)v5;
      }
      goto LABEL_35;
    }
    if ( v8 == 43 )
    {
      *(_BYTE *)(a1 + 49) = 1;
      goto LABEL_21;
    }
    if ( !*v7 )
      return 0;
    switch ( v8 )
    {
      case 9u:
      case 0xAu:
        goto LABEL_13;
      case 0xBu:
      case 0xCu:
LABEL_35:
        v15 = json5Whitespace(v2 + a2, v6);
        if ( !v15 )
          goto LABEL_230;
        a2 += v15;
        *(_BYTE *)(a1 + 49) = 1;
        break;
      case 0xDu:
      case 0x20u:
LABEL_13:
        a2 += strspn((const char *)(v2 + a2 + 1), "\t\n\r ") + 1;
        break;
      default:
        if ( v8 != 34 )
        {
          if ( v8 != 39 )
            goto LABEL_219;
          *(_BYTE *)(a1 + 49) = 1;
        }
        v16 = 7;
        v17 = *v7;
        v18 = a2 + 1;
        LODWORD(v13) = a2 + 1;
        while ( 2 )
        {
          while ( 2 )
          {
            if ( *((_BYTE *)qword_1800AA810 + *(unsigned __int8 *)((unsigned int)v13 + v2)) )
            {
              v19 = (unsigned int)(v13 + 1);
              if ( *((_BYTE *)qword_1800AA810 + *(unsigned __int8 *)(v19 + v2)) )
              {
                v19 = (unsigned int)(v13 + 2);
                if ( *((_BYTE *)qword_1800AA810 + *(unsigned __int8 *)(v19 + v2)) )
                {
                  LODWORD(v13) = v13 + 3;
                  v6 = 9;
                  continue;
                }
              }
              LODWORD(v13) = v19;
              v6 = 9;
            }
            break;
          }
          v20 = *(_BYTE *)((unsigned int)v13 + v2);
          if ( v20 == v17 )
          {
            LOBYTE(v6) = v16;
            jsonBlobAppendNode(a1, v6, (unsigned int)v13 - a2 - 1, v2 + v18);
            return (unsigned int)(v13 + 1);
          }
          if ( v20 == 92 )
          {
            v13 = (unsigned int)(v13 + 1);
            v21 = *(char *)(v13 + v2);
            if ( (_BYTE)v21 == 34
              || (unsigned __int8)(v21 - 92) <= 0x18u && (v22 = 21234753, _bittest(&v22, v21 - 92))
              || (_BYTE)v21 == 47
              || (_BYTE)v21 == 117 && (unsigned int)jsonIs4Hex(v2 + (unsigned int)(v13 + 1), 9) )
            {
              v6 = 9;
              if ( v16 == 7 )
                v16 = 8;
            }
            else
            {
              if ( (unsigned __int8)v21 > 0x30u || (v23 = 0x1008000000400LL, !_bittest64(&v23, v21)) )
              {
                if ( (_BYTE)v21 != 118 )
                {
                  if ( (_BYTE)v21 == 0xE2 )
                  {
                    if ( *(_BYTE *)((unsigned int)(v13 + 1) + v2) != 0x80 )
                      goto LABEL_66;
                    if ( (unsigned __int8)(*(_BYTE *)((unsigned int)(v13 + 2) + v2) + 88) > 1u )
                    {
LABEL_59:
                      if ( (_BYTE)v21 != 13 )
                        goto LABEL_66;
                      if ( *(_BYTE *)((unsigned int)(v13 + 1) + v2) == 10 )
                        LODWORD(v13) = v13 + 1;
                    }
                  }
                  else
                  {
                    if ( (_BYTE)v21 != 120 )
                      goto LABEL_59;
                    if ( !(unsigned int)jsonIs2Hex(v2 + (unsigned int)(v13 + 1), v6) )
                      goto LABEL_66;
                  }
                }
              }
              v6 = 9;
LABEL_72:
              v16 = 9;
              *(_BYTE *)(a1 + 49) = 1;
            }
          }
          else
          {
            if ( v20 <= 31 )
            {
              if ( !v20 )
                goto LABEL_66;
              goto LABEL_72;
            }
            if ( v20 == 34 )
              v16 = 9;
          }
          LODWORD(v13) = v13 + 1;
          continue;
        }
    }
  }
  LODWORD(v5) = -1;
  if ( v8 > 0x6E )
  {
    if ( v8 == 116 )
    {
      if ( strncmp_0((const char *)(v2 + a2), "true", 4u) )
        goto LABEL_230;
      v13 = a2 + 4;
      v45 = *(unsigned __int8 *)(v13 + v2);
      if ( (*((_BYTE *)&qword_18009E630 + v45) & 6) != 0 )
        goto LABEL_230;
      LOBYTE(v45) = 1;
      goto LABEL_136;
    }
    v14 = v8 - 123;
    if ( v8 == 123 )
    {
      v27 = *(_DWORD *)(a1 + 32) - a2;
      LODWORD(v14) = 12;
      v67 = *(_DWORD *)(a1 + 8);
      jsonBlobAppendNode(a1, v14, v27, 0);
      if ( ++*(_WORD *)(a1 + 44) > 0x3E8u )
        goto LABEL_230;
      LODWORD(v13) = a2 + 1;
      v65 = *(_DWORD *)(a1 + 8);
      while ( 2 )
      {
        v28 = *(_DWORD *)(a1 + 8);
        v66 = v28;
        v29 = jsonTranslateTextToBlob(a1, (unsigned int)v13);
        LODWORD(v31) = v29;
        if ( v29 <= 0 )
        {
          if ( v29 == -2 )
          {
            v43 = v65;
            LODWORD(v13) = *(_DWORD *)(a1 + 40);
            if ( *(_DWORD *)(a1 + 8) != v65 )
              *(_BYTE *)(a1 + 49) = 1;
            goto LABEL_127;
          }
          LODWORD(v13) = json5Whitespace(v2 + (unsigned int)v13, v30) + v13;
          LODWORD(v64) = 7;
          v33 = *(unsigned __int8 *)(v2 + (unsigned int)v13);
          if ( (*((_BYTE *)&qword_18009E630 + v33) & 0x42) != 0 )
          {
            v34 = v13 + 1;
          }
          else if ( (_BYTE)v33 != 92 || !(unsigned int)jsonIs4HexB(v2 + (unsigned int)(v13 + 1), &v64) )
          {
            goto LABEL_95;
          }
          do
          {
            while ( 1 )
            {
              LODWORD(v31) = v34;
              v35 = (unsigned __int8 *)(v2 + v34);
              v36 = *v35;
              if ( (*((_BYTE *)&qword_18009E630 + v36) & 0x46) == 0 || (unsigned int)json5Whitespace(v35, v32) )
                break;
              v34 = v31 + 1;
            }
          }
          while ( (_BYTE)v36 == 92 && (unsigned int)jsonIs4HexB(v2 + (int)v31 + 1, &v64) );
          LOBYTE(v32) = (_BYTE)v64;
          jsonBlobAppendNode(a1, v32, (unsigned int)(v31 - v13), v2 + (unsigned int)v13);
          v28 = v66;
          *(_BYTE *)(a1 + 49) = 1;
        }
        if ( *(_BYTE *)(a1 + 47) )
          return 0xFFFFFFFFLL;
        if ( (unsigned __int8)((*(_BYTE *)(v28 + *(_QWORD *)a1) & 0xF) - 7) > 3u )
          goto LABEL_96;
        if ( *(_BYTE *)((unsigned int)v31 + v2) != 58 )
        {
          if ( !*((_BYTE *)&qword_1800A6970 + *(unsigned __int8 *)((unsigned int)v31 + v2)) )
            goto LABEL_111;
          do
          {
            v31 = (unsigned int)(v31 + 1);
            v37 = *(unsigned __int8 *)(v31 + v2);
          }
          while ( *((_BYTE *)&qword_1800A6970 + v37) );
          LODWORD(v64) = v31;
          if ( (_BYTE)v37 != 58 )
          {
LABEL_111:
            v38 = jsonTranslateTextToBlob(a1, (unsigned int)v31);
            if ( v38 != -5 )
            {
              v44 = v38 == -1;
LABEL_131:
              if ( !v44 )
                *(_DWORD *)(a1 + 40) = v31;
              return 0xFFFFFFFFLL;
            }
            LODWORD(v31) = *(_DWORD *)(a1 + 40);
          }
        }
        LODWORD(v31) = v31 + 1;
        v39 = jsonTranslateTextToBlob(a1, (unsigned int)v31);
        v13 = (unsigned int)v39;
        if ( v39 <= 0 )
        {
          v44 = v39 == -1;
          goto LABEL_131;
        }
        v40 = *(_BYTE *)((unsigned int)v39 + v2);
        if ( v40 != 44 )
        {
          if ( v40 == 125 )
            goto LABEL_126;
          _mm_lfence();
          if ( !*((_BYTE *)&qword_1800A6970 + *(unsigned __int8 *)(v13 + v2)) )
            goto LABEL_119;
          v41 = (unsigned int)v13 + (unsigned int)strspn((const char *)(v2 + (unsigned int)(v13 + 1)), "\t\n\r ") + 1;
          LODWORD(v13) = v41;
          if ( *(_BYTE *)(v41 + v2) != 44 )
          {
            if ( *(_BYTE *)(v41 + v2) == 125 )
              goto LABEL_126;
LABEL_119:
            v42 = jsonTranslateTextToBlob(a1, (unsigned int)v13);
            if ( v42 != -4 )
            {
              if ( v42 == -2 )
              {
                LODWORD(v13) = *(_DWORD *)(a1 + 40);
LABEL_126:
                v43 = v65;
LABEL_127:
                jsonBlobChangePayloadSize(a1, v67, (unsigned int)(*(_DWORD *)(a1 + 8) - v43));
                --*(_WORD *)(a1 + 44);
                return (unsigned int)(v13 + 1);
              }
LABEL_96:
              *(_DWORD *)(a1 + 40) = v13;
              return 0xFFFFFFFFLL;
            }
            LODWORD(v13) = *(_DWORD *)(a1 + 40);
          }
        }
        LODWORD(v13) = v13 + 1;
        LODWORD(v64) = v13;
        continue;
      }
    }
    if ( v8 == 125 )
    {
      v26 = -2;
      goto LABEL_231;
    }
    v6 = v8 - 194;
    if ( v8 != 194 )
    {
      v6 = v8 - 225;
      if ( v8 != 225 )
      {
        v6 = v8 - 226;
        if ( v8 != 226 )
        {
          v6 = v8 - 227;
          if ( v8 != 227 && v8 != 239 )
            goto LABEL_219;
        }
      }
    }
    goto LABEL_35;
  }
  if ( v8 == 110 )
  {
    if ( strncmp_0((const char *)(v2 + a2), "null", 4u)
      || (v13 = a2 + 4, (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(v13 + v2)) & 6) != 0) )
    {
      v7 = v64;
      goto LABEL_219;
    }
    v45 = 0;
    goto LABEL_136;
  }
  if ( v8 != 53 && v8 != 54 && v8 != 55 && v8 != 56 && v8 != 57 )
  {
    if ( v8 == 58 )
    {
      v26 = -5;
      goto LABEL_231;
    }
    if ( v8 != 91 )
    {
      if ( v8 == 93 )
      {
        v26 = -3;
        goto LABEL_231;
      }
      if ( v8 != 102 )
        goto LABEL_219;
      if ( strncmp_0((const char *)(v2 + a2), "false", 5u) )
        goto LABEL_230;
      v13 = a2 + 5;
      if ( (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(v13 + v2)) & 6) != 0 )
        goto LABEL_230;
      LOBYTE(v45) = 2;
LABEL_136:
      jsonBlobAppendOneByte(a1, v45);
      return (unsigned int)v13;
    }
    v46 = *(_DWORD *)(a1 + 8);
    LOBYTE(v6) = 11;
    jsonBlobAppendNode(a1, v6, *(_DWORD *)(a1 + 32) - a2, 0);
    if ( *(_BYTE *)(a1 + 47) )
      return 0xFFFFFFFFLL;
    if ( ++*(_WORD *)(a1 + 44) > 0x3E8u )
      goto LABEL_230;
    v47 = *(_DWORD *)(a1 + 8);
    LODWORD(v13) = a2 + 1;
    LODWORD(v31) = jsonTranslateTextToBlob(a1, a2 + 1);
    if ( (int)v31 <= 0 )
    {
LABEL_163:
      if ( (_DWORD)v31 != -3 )
      {
LABEL_95:
        if ( (_DWORD)v31 != -1 )
          goto LABEL_96;
        return 0xFFFFFFFFLL;
      }
      LODWORD(v13) = *(_DWORD *)(a1 + 40);
      if ( *(_DWORD *)(a1 + 8) != v47 )
        *(_BYTE *)(a1 + 49) = 1;
LABEL_166:
      jsonBlobChangePayloadSize(a1, v46, (unsigned int)(*(_DWORD *)(a1 + 8) - v47));
      --*(_WORD *)(a1 + 44);
      return (unsigned int)(v13 + 1);
    }
    while ( 2 )
    {
      LODWORD(v13) = v31;
      v48 = *(unsigned __int8 *)((unsigned int)v31 + v2);
      if ( (_BYTE)v48 != 44 )
      {
        if ( (_BYTE)v48 == 93 )
          goto LABEL_166;
        if ( !*((_BYTE *)&qword_1800A6970 + v48) )
          goto LABEL_160;
        v13 = (unsigned int)v31 + (unsigned int)strspn((const char *)(v2 + (unsigned int)(v31 + 1)), "\t\n\r ") + 1;
        if ( *(_BYTE *)(v13 + v2) != 44 )
        {
          if ( *(_BYTE *)(v13 + v2) == 93 )
            goto LABEL_166;
LABEL_160:
          v49 = jsonTranslateTextToBlob(a1, (unsigned int)v13);
          if ( v49 != -4 )
          {
            if ( v49 != -3 )
              goto LABEL_96;
            LODWORD(v13) = *(_DWORD *)(a1 + 40);
            goto LABEL_166;
          }
          LODWORD(v13) = *(_DWORD *)(a1 + 40);
        }
      }
      LODWORD(v13) = v13 + 1;
      LODWORD(v31) = jsonTranslateTextToBlob(a1, (unsigned int)v13);
      if ( (int)v31 <= 0 )
        goto LABEL_163;
      continue;
    }
  }
LABEL_21:
  LOBYTE(v6) = 0;
  v9 = 0;
  if ( (char)*v7 > 48 )
    goto LABEL_81;
  v10 = a2 + 1;
  v11 = (unsigned __int8 *)(v2 + a2 + 1);
  if ( *v7 == 48 )
  {
    v12 = *v11;
    if ( (((_BYTE)v12 - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(a2 + 2 + v2)) & 8) != 0 )
    {
      *(_BYTE *)(a1 + 49) = 1;
      v13 = a2 + 3;
      LOBYTE(v6) = 1;
      while ( (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(v13 + v2)) & 8) != 0 )
        v13 = (unsigned int)(v13 + 1);
      goto LABEL_212;
    }
    if ( (*((_BYTE *)&qword_18009E630 + v12) & 4) == 0 )
      goto LABEL_81;
LABEL_186:
    *(_DWORD *)(a1 + 40) = v10;
    return (unsigned int)v5;
  }
  v50 = *v11;
  if ( (*((_BYTE *)&qword_18009E630 + v50) & 4) != 0 )
  {
    if ( (_BYTE)v50 != 48 )
      goto LABEL_81;
    v54 = *(unsigned __int8 *)(a2 + 2 + v2);
    if ( (*((_BYTE *)&qword_18009E630 + v54) & 4) != 0 )
      goto LABEL_186;
    if ( (((_BYTE)v54 - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(a2 + 3 + v2)) & 8) != 0 )
    {
      *(_BYTE *)(a1 + 49) = 1;
      v13 = a2 + 4;
      LOBYTE(v6) = 1;
      while ( (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(v13 + v2)) & 8) != 0 )
        v13 = (unsigned int)(v13 + 1);
      goto LABEL_212;
    }
  }
  else
  {
    if ( (((_BYTE)v50 - 73) & 0xDF) == 0 )
    {
      if ( !(unsigned int)sqlite3_strnicmp(v11, "inf") )
      {
        v51 = v64;
        *(_BYTE *)(a1 + 49) = 1;
        v52 = "-9e999";
        LOBYTE(v6) = 5;
        v53 = *v51;
        if ( v53 != 45 )
          v52 = "9e999";
        jsonBlobAppendNode(a1, v6, 6 - (unsigned int)(v53 != 45), v52);
        return a2 + ((unsigned int)sqlite3_strnicmp(v2 + a2 + 4, "inity") != 0 ? 4 : 9);
      }
      v7 = v64;
    }
    if ( (_BYTE)v50 != 46 )
      goto LABEL_230;
    *(_BYTE *)(a1 + 49) = 1;
    LOBYTE(v6) = 1;
  }
LABEL_81:
  v10 = a2 + 1;
  LODWORD(v13) = a2 + 1;
  while ( 2 )
  {
    v25 = *(unsigned __int8 *)((unsigned int)v13 + v2);
    if ( (*((_BYTE *)&qword_18009E630 + v25) & 4) != 0 )
      goto LABEL_206;
    if ( (_BYTE)v25 == 46 )
    {
      if ( (v6 & 2) != 0 )
        goto LABEL_66;
      goto LABEL_205;
    }
    v55 = (unsigned int)(v13 - 1);
    if ( (((_BYTE)v25 - 69) & 0xDF) == 0 )
    {
      if ( *(char *)(v55 + v2) < 48 )
      {
        if ( *(_BYTE *)(v55 + v2) != 46 )
          goto LABEL_66;
        v56 = (unsigned int)(v13 - 2);
        if ( (unsigned int)v56 < a2 || (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(v56 + v2)) & 4) == 0 )
          goto LABEL_66;
        *(_BYTE *)(a1 + 49) = 1;
        LOBYTE(v6) = v6 | 1;
      }
      if ( v9 )
        goto LABEL_66;
      v57 = (unsigned int)(v13 + 1);
      v58 = *(_BYTE *)(v57 + v2);
      if ( v58 == 43 || v58 == 45 )
      {
        LODWORD(v13) = v13 + 1;
        v58 = *(_BYTE *)((unsigned int)(v57 + 1) + v2);
      }
      if ( (unsigned __int8)(v58 - 48) > 9u )
        goto LABEL_66;
      v9 = 1;
LABEL_205:
      LOBYTE(v6) = v6 | 2;
LABEL_206:
      LODWORD(v13) = v13 + 1;
      continue;
    }
    break;
  }
  if ( *(char *)(v55 + v2) < 48 )
  {
    if ( *(_BYTE *)(v55 + v2) != 46
      || (v59 = (unsigned int)(v13 - 2), (unsigned int)v59 < a2)
      || (*((_BYTE *)&qword_18009E630 + *(unsigned __int8 *)(v59 + v2)) & 4) == 0 )
    {
LABEL_66:
      *(_DWORD *)(a1 + 40) = v13;
      return (unsigned int)v5;
    }
    *(_BYTE *)(a1 + 49) = 1;
    LOBYTE(v6) = v6 | 1;
  }
LABEL_212:
  if ( *v7 == 43 )
    a2 = v10;
  LOBYTE(v6) = v6 + 3;
  jsonBlobAppendNode(a1, v6, (unsigned int)v13 - a2, v2 + a2);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180077a50  push    rbx
0x180077a52  push    rbp
0x180077a53  push    rsi
0x180077a54  push    rdi
0x180077a55  push    r12
0x180077a57  push    r13
0x180077a59  push    r14
0x180077a5b  push    r15
0x180077a5d  sub     rsp, 28h
0x180077a61  mov     rsi, [rcx+10h]
0x180077a65  mov     ebp, edx
0x180077a67  mov     rbx, rcx
0x180077a6a  mov     r14d, 1
0x180077a70  or      r13d, 0FFFFFFFFh
0x180077a74  mov     edx, 9
0x180077a79  mov     r11d, ebp
0x180077a7c  lea     r12, cs:180000000h
0x180077a83  add     r11, rsi
0x180077a86  mov     r10b, 30h ; '0'
0x180077a89  mov     [rsp+68h+arg_0], r11
0x180077a8e  movzx   r15d, byte ptr [r11]
0x180077a92  cmp     r15d, 34h ; '4'
0x180077a96  ja      loc_180077B8F
0x180077a9c  jz      loc_180077B3A
0x180077aa2  cmp     r15d, 2Bh ; '+'
0x180077aa6  ja      short loc_180077AFF
0x180077aa8  jz      loc_180077D8B
0x180077aae  mov     ecx, r15d
0x180077ab1  test    r15d, r15d
0x180077ab4  jz      loc_180077D84
0x180077aba  sub     ecx, edx
0x180077abc  jz      short loc_180077AE3
0x180077abe  sub     ecx, r14d
0x180077ac1  jz      short loc_180077AE3
0x180077ac3  sub     ecx, r14d
0x180077ac6  jz      loc_180077BD8
0x180077acc  sub     ecx, r14d
0x180077acf  jz      loc_180077BD8
0x180077ad5  sub     ecx, r14d
0x180077ad8  jz      short loc_180077AE3
0x180077ada  sub     ecx, 13h
0x180077add  jnz     loc_180077BF3
0x180077ae3  lea     ecx, [rbp+1]
0x180077ae6  add     rcx, rsi; Str
0x180077ae9  lea     rdx, asc_1800A7824; "\t\n\r "
0x180077af0  call    cs:__imp_strspn
0x180077af6  inc     ebp
0x180077af8  add     ebp, eax
0x180077afa  jmp     loc_180077A74
0x180077aff  mov     ecx, r15d
0x180077b02  sub     ecx, 2Ch ; ','
0x180077b05  jz      loc_180077DEC
0x180077b0b  sub     ecx, r14d
0x180077b0e  jz      short loc_180077B3A
0x180077b10  sub     ecx, r14d
0x180077b13  jz      loc_180077D94
0x180077b19  sub     ecx, r14d
0x180077b1c  jz      loc_180077BD8
0x180077b22  sub     ecx, r14d
0x180077b25  jz      short loc_180077B3A
0x180077b27  sub     ecx, r14d
0x180077b2a  jz      short loc_180077B3A
0x180077b2c  sub     ecx, r14d
0x180077b2f  jz      short loc_180077B3A
0x180077b31  cmp     ecx, r14d
0x180077b34  jnz     loc_1800784B9
0x180077b3a  xor     dl, dl
0x180077b3c  xor     r14b, r14b
0x180077b3f  cmp     [r11], r10b
0x180077b42  jg      loc_180077DB3
0x180077b48  lea     r9d, [rbp+1]
0x180077b4c  mov     ecx, r9d
0x180077b4f  add     rcx, rsi
0x180077b52  cmp     [r11], r10b
0x180077b55  jnz     loc_180078295
0x180077b5b  movzx   r8d, byte ptr [rcx]
0x180077b5f  lea     eax, [r8-58h]
0x180077b63  test    al, 0DFh
0x180077b65  jnz     loc_180078281
0x180077b6b  lea     eax, [rbp+2]
0x180077b6e  movzx   eax, byte ptr [rax+rsi]
0x180077b72  test    byte ptr [rax+r12+9E630h], 8
0x180077b7b  jz      loc_180078281
0x180077b81  mov     byte ptr [rbx+31h], 1
0x180077b85  lea     edi, [rbp+3]
0x180077b88  mov     dl, 1
0x180077b8a  jmp     loc_18007826D
0x180077b8f  or      r13d, 0FFFFFFFFh
0x180077b93  cmp     r15d, 6Eh ; 'n'
0x180077b97  jbe     loc_1800780BC
0x180077b9d  mov     edx, r15d
0x180077ba0  sub     edx, 74h ; 't'
0x180077ba3  jz      loc_180078077
0x180077ba9  sub     edx, 7
0x180077bac  jz      loc_180077E02
0x180077bb2  sub     edx, 2
0x180077bb5  jz      loc_180077DF7
0x180077bbb  sub     edx, 45h ; 'E'
0x180077bbe  jz      short loc_180077BD8
0x180077bc0  sub     edx, 1Fh
0x180077bc3  jz      short loc_180077BD8
0x180077bc5  sub     edx, r14d
0x180077bc8  jz      short loc_180077BD8
0x180077bca  sub     edx, r14d
0x180077bcd  jz      short loc_180077BD8
0x180077bcf  cmp     edx, 0Ch
0x180077bd2  jnz     loc_1800784B9
0x180077bd8  mov     rcx, r11
0x180077bdb  call    json5Whitespace
0x180077be0  test    eax, eax
0x180077be2  jz      loc_18007855E
0x180077be8  add     ebp, eax
0x180077bea  mov     [rbx+31h], r14b
0x180077bee  jmp     loc_180077A74
0x180077bf3  sub     ecx, 2
0x180077bf6  jz      short loc_180077C05
0x180077bf8  cmp     ecx, 5
0x180077bfb  jnz     loc_1800784B9
0x180077c01  mov     [rbx+31h], r14b
0x180077c05  mov     r10b, 7
0x180077c08  mov     r11b, [r11]
0x180077c0b  lea     r9d, [rbp+1]
0x180077c0f  mov     edi, r9d
0x180077c12  lea     r12, cs:180000000h
0x180077c19  xor     r15d, r15d
0x180077c1c  mov     eax, edi
0x180077c1e  movzx   ecx, byte ptr [rax+rsi]
0x180077c22  cmp     [rcx+r12+0AA810h], r15b
0x180077c2a  jz      short loc_180077C59
0x180077c2c  lea     edx, [rdi+1]
0x180077c2f  movzx   ecx, byte ptr [rdx+rsi]
0x180077c33  cmp     [rcx+r12+0AA810h], r15b
0x180077c3b  jz      short loc_180077C52
0x180077c3d  lea     edx, [rdi+2]
0x180077c40  movzx   ecx, byte ptr [rdx+rsi]
0x180077c44  cmp     [rcx+r12+0AA810h], r15b
0x180077c4c  jnz     loc_180077D06
0x180077c52  mov     edi, edx
0x180077c54  mov     edx, 9
0x180077c59  mov     eax, edi
0x180077c5b  mov     cl, [rax+rsi]
0x180077c5e  cmp     cl, r11b
0x180077c61  jz      loc_180077D68
0x180077c67  cmp     cl, 5Ch ; '\'
0x180077c6a  jnz     loc_180077D43
0x180077c70  add     edi, r14d
0x180077c73  movsx   r8, byte ptr [rdi+rsi]
0x180077c78  cmp     r8b, 22h ; '"'
0x180077c7c  jz      loc_180077D33
0x180077c82  lea     eax, [r8-5Ch]
0x180077c86  cmp     al, 18h
0x180077c88  ja      short loc_180077C98
0x180077c8a  mov     ecx, 1440441h
0x180077c8f  bt      ecx, eax
0x180077c92  jb      loc_180077D33
0x180077c98  cmp     r8b, 2Fh ; '/'
0x180077c9c  jz      loc_180077D33
0x180077ca2  cmp     r8b, 75h ; 'u'
0x180077ca6  jnz     short loc_180077CB7
0x180077ca8  lea     ecx, [rdi+1]
0x180077cab  add     rcx, rsi
0x180077cae  call    jsonIs4Hex
0x180077cb3  test    eax, eax
0x180077cb5  jnz     short loc_180077D33
0x180077cb7  cmp     r8b, 30h ; '0'
0x180077cbb  ja      short loc_180077CCD
0x180077cbd  mov     rcx, 1008000000400h
0x180077cc7  bt      rcx, r8
0x180077ccb  jb      short loc_180077CFF
0x180077ccd  cmp     r8b, 76h ; 'v'
0x180077cd1  jz      short loc_180077CFF
0x180077cd3  cmp     r8b, 0E2h
0x180077cd7  jnz     short loc_180077D13
0x180077cd9  lea     eax, [rdi+1]
0x180077cdc  cmp     byte ptr [rax+rsi], 80h
0x180077ce0  jnz     short loc_180077D28
0x180077ce2  lea     eax, [rdi+2]
0x180077ce5  mov     al, [rax+rsi]
0x180077ce8  add     al, 58h ; 'X'
0x180077cea  cmp     al, r14b
0x180077ced  jbe     short loc_180077CFF
0x180077cef  cmp     r8b, 0Dh
0x180077cf3  jnz     short loc_180077D28
0x180077cf5  lea     ecx, [rdi+1]
0x180077cf8  cmp     byte ptr [rcx+rsi], 0Ah
0x180077cfc  cmovz   edi, ecx
0x180077cff  mov     edx, 9
0x180077d04  jmp     short loc_180077D4C
0x180077d06  add     edi, 3
0x180077d09  mov     edx, 9
0x180077d0e  jmp     loc_180077C1C
0x180077d13  cmp     r8b, 78h ; 'x'
0x180077d17  jnz     short loc_180077CEF
0x180077d19  lea     ecx, [rdi+1]
0x180077d1c  add     rcx, rsi
0x180077d1f  call    jsonIs2Hex
0x180077d24  test    eax, eax
0x180077d26  jnz     short loc_180077CFF
0x180077d28  mov     [rbx+28h], edi
0x180077d2b  mov     eax, r13d
0x180077d2e  jmp     loc_180078568
0x180077d33  mov     edx, 9
0x180077d38  cmp     r10b, 7
0x180077d3c  jnz     short loc_180077D60
0x180077d3e  mov     r10b, 8
0x180077d41  jmp     short loc_180077D60
0x180077d43  cmp     cl, 1Fh
0x180077d46  jg      short loc_180077D55
0x180077d48  test    cl, cl
0x180077d4a  jz      short loc_180077D28
0x180077d4c  mov     r10b, dl
0x180077d4f  mov     [rbx+31h], r14b
0x180077d53  jmp     short loc_180077D60
0x180077d55  cmp     cl, 22h ; '"'
0x180077d58  movzx   r10d, r10b
0x180077d5c  cmovz   r10d, edx
0x180077d60  add     edi, r14d
0x180077d63  jmp     loc_180077C1C
0x180077d68  mov     r8d, edi
0x180077d6b  add     r9, rsi
0x180077d6e  sub     r8d, ebp
0x180077d71  mov     dl, r10b
0x180077d74  sub     r8d, r14d
0x180077d77  mov     rcx, rbx
0x180077d7a  call    jsonBlobAppendNode
0x180077d7f  jmp     loc_180078059
0x180077d84  xor     eax, eax
0x180077d86  jmp     loc_180078568
0x180077d8b  mov     [rbx+31h], r14b
0x180077d8f  jmp     loc_180077B3A
0x180077d94  lea     eax, [rbp+1]
0x180077d97  movzx   eax, byte ptr [rax+rsi]
0x180077d9b  test    byte ptr [rax+r12+9E630h], 4
0x180077da4  jz      loc_18007855E
0x180077daa  mov     [rbx+31h], r14b
0x180077dae  mov     dl, 3
0x180077db0  xor     r14b, r14b
0x180077db3  mov     r15d, 1
0x180077db9  lea     r9d, [rbp+1]
0x180077dbd  mov     edi, r9d
0x180077dc0  mov     eax, edi
0x180077dc2  movzx   ecx, byte ptr [rax+rsi]
0x180077dc6  test    byte ptr [rcx+r12+9E630h], 4
0x180077dcf  jnz     loc_180078421
0x180077dd5  cmp     cl, 2Eh ; '.'
0x180077dd8  jnz     loc_1800783AA
0x180077dde  test    dl, 2
0x180077de1  jnz     loc_180077D28
0x180077de7  jmp     loc_18007841E
0x180077dec  mov     r14d, 0FFFFFFFCh
0x180077df2  jmp     loc_180078562
0x180077df7  mov     r14d, 0FFFFFFFEh
0x180077dfd  jmp     loc_180078562
0x180077e02  mov     r8d, [rbx+20h]
0x180077e06  xor     r9d, r9d
0x180077e09  mov     eax, [rbx+8]
0x180077e0c  sub     r8d, ebp
0x180077e0f  mov     dl, 0Ch
0x180077e11  mov     [rsp+68h+arg_18], eax
0x180077e18  mov     rcx, rbx
0x180077e1b  call    jsonBlobAppendNode
0x180077e20  add     [rbx+2Ch], r14w
0x180077e25  mov     eax, 3E8h
0x180077e2a  cmp     [rbx+2Ch], ax
0x180077e2e  ja      loc_18007855E
0x180077e34  mov     eax, [rbx+8]
0x180077e37  lea     edi, [rbp+1]
0x180077e3a  mov     r14d, 0FFFFFFFCh
0x180077e40  mov     [rsp+68h+arg_8], eax
0x180077e44  lea     r12, cs:180000000h
0x180077e4b  lea     r13d, [r14+5]
0x180077e4f  mov     r15d, [rbx+8]
0x180077e53  mov     edx, edi
0x180077e55  mov     rcx, rbx
0x180077e58  mov     [rsp+68h+arg_10], r15d
0x180077e60  call    jsonTranslateTextToBlob
0x180077e65  mov     ebp, eax
0x180077e67  test    eax, eax
0x180077e69  jg      loc_180077F3E
0x180077e6f  cmp     eax, 0FFFFFFFEh
0x180077e72  jz      loc_18007801C
0x180077e78  mov     ecx, edi
0x180077e7a  add     rcx, rsi
0x180077e7d  call    json5Whitespace
0x180077e82  add     edi, eax
0x180077e84  mov     dword ptr [rsp+68h+arg_0], 7
0x180077e8c  mov     r13d, edi
0x180077e8f  add     r13, rsi
0x180077e92  movzx   eax, byte ptr [r13+0]
0x180077e97  test    byte ptr [rax+r12+9E630h], 42h
0x180077ea0  jnz     short loc_180077ECE
0x180077ea2  cmp     al, 5Ch ; '\'
0x180077ea4  jnz     short loc_180077EBE
0x180077ea6  lea     r9d, [rdi+1]
0x180077eaa  mov     ecx, r9d
0x180077ead  lea     rdx, [rsp+68h+arg_0]
0x180077eb2  add     rcx, rsi
0x180077eb5  call    jsonIs4HexB
0x180077eba  test    eax, eax
0x180077ebc  jnz     short loc_180077ED2
  ... truncated ...
```
