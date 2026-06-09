# jsonTranslateTextToBlob

- ea: `0x180069bdc`
- end: `0x18006a705`
- name: `jsonTranslateTextToBlob`
- size: `2857`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180065e14`
- `0x180069118`
- `0x180069bdc`

## callees

- `0x1800367a0`
- `0x180064b8c`
- `0x1800657a8`
- `0x180065888`
- `0x1800658ac`
- `0x1800674c0`
- `0x1800674ec`
- `0x18006751c`
- `0x180069bdc`
- `0x1800a6cc0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180069c7c`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x18006a171`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x18006a361`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180069c7c`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x18006a171`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x18006a361`

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
  unsigned int v62; // r13d
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
          if ( (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(a2 + 1 + v2)) & 4) != 0 )
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
          if ( (_BYTE)v8 == byte_1800AA6F0[24 * v60] || (_BYTE)v8 == byte_1800AA6F0[v61 * 2 + 1] )
          {
            v62 = SLOBYTE(word_1800AA6F2[12 * v60]);
            if ( !(unsigned int)sqlite3_strnicmp(v7, off_1800AA6F8[3 * v60], v62) )
            {
              v5 = a2 + v62;
              if ( (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(v5 + v2)) & 6) == 0 )
                break;
            }
          }
          v60 = (unsigned int)(v60 + 1);
          if ( (unsigned int)v60 >= 5 )
            goto LABEL_230;
          v7 = v64;
        }
        if ( HIBYTE(word_1800AA6F2[v61]) == 5 )
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
            if ( *((_BYTE *)qword_1800BA610 + *(unsigned __int8 *)((unsigned int)v13 + v2)) )
            {
              v19 = (unsigned int)(v13 + 1);
              if ( *((_BYTE *)qword_1800BA610 + *(unsigned __int8 *)(v19 + v2)) )
              {
                v19 = (unsigned int)(v13 + 2);
                if ( *((_BYTE *)qword_1800BA610 + *(unsigned __int8 *)(v19 + v2)) )
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
      if ( (*((_BYTE *)&qword_1800ADE90 + v45) & 6) != 0 )
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
          if ( (*((_BYTE *)&qword_1800ADE90 + v33) & 0x42) != 0 )
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
              if ( (*((_BYTE *)&qword_1800ADE90 + v36) & 0x46) == 0 || (unsigned int)json5Whitespace(v35, v32) )
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
          if ( !*((_BYTE *)&qword_1800B6630 + *(unsigned __int8 *)((unsigned int)v31 + v2)) )
            goto LABEL_111;
          do
          {
            v31 = (unsigned int)(v31 + 1);
            v37 = *(unsigned __int8 *)(v31 + v2);
          }
          while ( *((_BYTE *)&qword_1800B6630 + v37) );
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
          if ( !*((_BYTE *)&qword_1800B6630 + *(unsigned __int8 *)(v13 + v2)) )
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
      || (v13 = a2 + 4, (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(v13 + v2)) & 6) != 0) )
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
      if ( (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(v13 + v2)) & 6) != 0 )
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
        if ( !*((_BYTE *)&qword_1800B6630 + v48) )
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
    if ( (((_BYTE)v12 - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(a2 + 2 + v2)) & 8) != 0 )
    {
      *(_BYTE *)(a1 + 49) = 1;
      v13 = a2 + 3;
      LOBYTE(v6) = 1;
      while ( (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(v13 + v2)) & 8) != 0 )
        v13 = (unsigned int)(v13 + 1);
      goto LABEL_212;
    }
    if ( (*((_BYTE *)&qword_1800ADE90 + v12) & 4) == 0 )
      goto LABEL_81;
LABEL_186:
    *(_DWORD *)(a1 + 40) = v10;
    return (unsigned int)v5;
  }
  v50 = *v11;
  if ( (*((_BYTE *)&qword_1800ADE90 + v50) & 4) != 0 )
  {
    if ( (_BYTE)v50 != 48 )
      goto LABEL_81;
    v54 = *(unsigned __int8 *)(a2 + 2 + v2);
    if ( (*((_BYTE *)&qword_1800ADE90 + v54) & 4) != 0 )
      goto LABEL_186;
    if ( (((_BYTE)v54 - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(a2 + 3 + v2)) & 8) != 0 )
    {
      *(_BYTE *)(a1 + 49) = 1;
      v13 = a2 + 4;
      LOBYTE(v6) = 1;
      while ( (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(v13 + v2)) & 8) != 0 )
        v13 = (unsigned int)(v13 + 1);
      goto LABEL_212;
    }
  }
  else
  {
    if ( (((_BYTE)v50 - 73) & 0xDF) == 0 )
    {
      if ( !(unsigned int)sqlite3_strnicmp(v11, "inf", 3) )
      {
        v51 = v64;
        *(_BYTE *)(a1 + 49) = 1;
        v52 = "-9e999";
        LOBYTE(v6) = 5;
        v53 = *v51;
        if ( v53 != 45 )
          v52 = "9e999";
        jsonBlobAppendNode(a1, v6, 6 - (unsigned int)(v53 != 45), v52);
        return a2 + ((unsigned int)sqlite3_strnicmp(v2 + a2 + 4, "inity", 5) != 0 ? 4 : 9);
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
    if ( (*((_BYTE *)&qword_1800ADE90 + v25) & 4) != 0 )
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
        if ( (unsigned int)v56 < a2 || (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(v56 + v2)) & 4) == 0 )
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
      || (*((_BYTE *)&qword_1800ADE90 + *(unsigned __int8 *)(v59 + v2)) & 4) == 0 )
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
0x180069bdc  push    rbx
0x180069bde  push    rbp
0x180069bdf  push    rsi
0x180069be0  push    rdi
0x180069be1  push    r12
0x180069be3  push    r13
0x180069be5  push    r14
0x180069be7  push    r15
0x180069be9  sub     rsp, 28h
0x180069bed  mov     rsi, [rcx+10h]
0x180069bf1  mov     ebp, edx
0x180069bf3  mov     rbx, rcx
0x180069bf6  mov     r14d, 1
0x180069bfc  or      r13d, 0FFFFFFFFh
0x180069c00  mov     edx, 9
0x180069c05  mov     r11d, ebp
0x180069c08  lea     r12, __ImageBase
0x180069c0f  add     r11, rsi
0x180069c12  mov     r10b, 30h ; '0'
0x180069c15  mov     [rsp+68h+arg_0], r11
0x180069c1a  movzx   r15d, byte ptr [r11]
0x180069c1e  cmp     r15d, 34h ; '4'
0x180069c22  ja      loc_180069D1B
0x180069c28  jz      loc_180069CC6
0x180069c2e  cmp     r15d, 2Bh ; '+'
0x180069c32  ja      short loc_180069C8B
0x180069c34  jz      loc_180069F17
0x180069c3a  mov     ecx, r15d
0x180069c3d  test    r15d, r15d
0x180069c40  jz      loc_180069F10
0x180069c46  sub     ecx, edx
0x180069c48  jz      short loc_180069C6F
0x180069c4a  sub     ecx, r14d
0x180069c4d  jz      short loc_180069C6F
0x180069c4f  sub     ecx, r14d
0x180069c52  jz      loc_180069D64
0x180069c58  sub     ecx, r14d
0x180069c5b  jz      loc_180069D64
0x180069c61  sub     ecx, r14d
0x180069c64  jz      short loc_180069C6F
0x180069c66  sub     ecx, 13h
0x180069c69  jnz     loc_180069D7F
0x180069c6f  lea     ecx, [rbp+1]
0x180069c72  add     rcx, rsi; Str
0x180069c75  lea     rdx, Control; "\t\n\r "
0x180069c7c  call    cs:__imp_strspn
0x180069c82  inc     ebp
0x180069c84  add     ebp, eax
0x180069c86  jmp     loc_180069C00
0x180069c8b  mov     ecx, r15d
0x180069c8e  sub     ecx, 2Ch ; ','
0x180069c91  jz      loc_180069F78
0x180069c97  sub     ecx, r14d
0x180069c9a  jz      short loc_180069CC6
0x180069c9c  sub     ecx, r14d
0x180069c9f  jz      loc_180069F20
0x180069ca5  sub     ecx, r14d
0x180069ca8  jz      loc_180069D64
0x180069cae  sub     ecx, r14d
0x180069cb1  jz      short loc_180069CC6
0x180069cb3  sub     ecx, r14d
0x180069cb6  jz      short loc_180069CC6
0x180069cb8  sub     ecx, r14d
0x180069cbb  jz      short loc_180069CC6
0x180069cbd  cmp     ecx, r14d
0x180069cc0  jnz     loc_18006A645
0x180069cc6  xor     dl, dl
0x180069cc8  xor     r14b, r14b
0x180069ccb  cmp     [r11], r10b
0x180069cce  jg      loc_180069F3F
0x180069cd4  lea     r9d, [rbp+1]
0x180069cd8  mov     ecx, r9d
0x180069cdb  add     rcx, rsi
0x180069cde  cmp     [r11], r10b
0x180069ce1  jnz     loc_18006A421
0x180069ce7  movzx   r8d, byte ptr [rcx]
0x180069ceb  lea     eax, [r8-58h]
0x180069cef  test    al, 0DFh
0x180069cf1  jnz     loc_18006A40D
0x180069cf7  lea     eax, [rbp+2]
0x180069cfa  movzx   eax, byte ptr [rax+rsi]
0x180069cfe  test    byte ptr [rax+r12+0ADE90h], 8
0x180069d07  jz      loc_18006A40D
0x180069d0d  mov     byte ptr [rbx+31h], 1
0x180069d11  lea     edi, [rbp+3]
0x180069d14  mov     dl, 1
0x180069d16  jmp     loc_18006A3F9
0x180069d1b  or      r13d, 0FFFFFFFFh
0x180069d1f  cmp     r15d, 6Eh ; 'n'
0x180069d23  jbe     loc_18006A248
0x180069d29  mov     edx, r15d
0x180069d2c  sub     edx, 74h ; 't'
0x180069d2f  jz      loc_18006A203
0x180069d35  sub     edx, 7
0x180069d38  jz      loc_180069F8E
0x180069d3e  sub     edx, 2
0x180069d41  jz      loc_180069F83
0x180069d47  sub     edx, 45h ; 'E'
0x180069d4a  jz      short loc_180069D64
0x180069d4c  sub     edx, 1Fh
0x180069d4f  jz      short loc_180069D64
0x180069d51  sub     edx, r14d
0x180069d54  jz      short loc_180069D64
0x180069d56  sub     edx, r14d
0x180069d59  jz      short loc_180069D64
0x180069d5b  cmp     edx, 0Ch
0x180069d5e  jnz     loc_18006A645
0x180069d64  mov     rcx, r11
0x180069d67  call    json5Whitespace
0x180069d6c  test    eax, eax
0x180069d6e  jz      loc_18006A6EA
0x180069d74  add     ebp, eax
0x180069d76  mov     [rbx+31h], r14b
0x180069d7a  jmp     loc_180069C00
0x180069d7f  sub     ecx, 2
0x180069d82  jz      short loc_180069D91
0x180069d84  cmp     ecx, 5
0x180069d87  jnz     loc_18006A645
0x180069d8d  mov     [rbx+31h], r14b
0x180069d91  mov     r10b, 7
0x180069d94  mov     r11b, [r11]
0x180069d97  lea     r9d, [rbp+1]
0x180069d9b  mov     edi, r9d
0x180069d9e  lea     r12, __ImageBase
0x180069da5  xor     r15d, r15d
0x180069da8  mov     eax, edi
0x180069daa  movzx   ecx, byte ptr [rax+rsi]
0x180069dae  cmp     [rcx+r12+0BA610h], r15b
0x180069db6  jz      short loc_180069DE5
0x180069db8  lea     edx, [rdi+1]
0x180069dbb  movzx   ecx, byte ptr [rdx+rsi]
0x180069dbf  cmp     [rcx+r12+0BA610h], r15b
0x180069dc7  jz      short loc_180069DDE
0x180069dc9  lea     edx, [rdi+2]
0x180069dcc  movzx   ecx, byte ptr [rdx+rsi]
0x180069dd0  cmp     [rcx+r12+0BA610h], r15b
0x180069dd8  jnz     loc_180069E92
0x180069dde  mov     edi, edx
0x180069de0  mov     edx, 9
0x180069de5  mov     eax, edi
0x180069de7  mov     cl, [rax+rsi]
0x180069dea  cmp     cl, r11b
0x180069ded  jz      loc_180069EF4
0x180069df3  cmp     cl, 5Ch ; '\'
0x180069df6  jnz     loc_180069ECF
0x180069dfc  add     edi, r14d
0x180069dff  movsx   r8, byte ptr [rdi+rsi]
0x180069e04  cmp     r8b, 22h ; '"'
0x180069e08  jz      loc_180069EBF
0x180069e0e  lea     eax, [r8-5Ch]
0x180069e12  cmp     al, 18h
0x180069e14  ja      short loc_180069E24
0x180069e16  mov     ecx, 1440441h
0x180069e1b  bt      ecx, eax
0x180069e1e  jb      loc_180069EBF
0x180069e24  cmp     r8b, 2Fh ; '/'
0x180069e28  jz      loc_180069EBF
0x180069e2e  cmp     r8b, 75h ; 'u'
0x180069e32  jnz     short loc_180069E43
0x180069e34  lea     ecx, [rdi+1]
0x180069e37  add     rcx, rsi
0x180069e3a  call    jsonIs4Hex
0x180069e3f  test    eax, eax
0x180069e41  jnz     short loc_180069EBF
0x180069e43  cmp     r8b, 30h ; '0'
0x180069e47  ja      short loc_180069E59
0x180069e49  mov     rcx, 1008000000400h
0x180069e53  bt      rcx, r8
0x180069e57  jb      short loc_180069E8B
0x180069e59  cmp     r8b, 76h ; 'v'
0x180069e5d  jz      short loc_180069E8B
0x180069e5f  cmp     r8b, 0E2h
0x180069e63  jnz     short loc_180069E9F
0x180069e65  lea     eax, [rdi+1]
0x180069e68  cmp     byte ptr [rax+rsi], 80h
0x180069e6c  jnz     short loc_180069EB4
0x180069e6e  lea     eax, [rdi+2]
0x180069e71  mov     al, [rax+rsi]
0x180069e74  add     al, 58h ; 'X'
0x180069e76  cmp     al, r14b
0x180069e79  jbe     short loc_180069E8B
0x180069e7b  cmp     r8b, 0Dh
0x180069e7f  jnz     short loc_180069EB4
0x180069e81  lea     ecx, [rdi+1]
0x180069e84  cmp     byte ptr [rcx+rsi], 0Ah
0x180069e88  cmovz   edi, ecx
0x180069e8b  mov     edx, 9
0x180069e90  jmp     short loc_180069ED8
0x180069e92  add     edi, 3
0x180069e95  mov     edx, 9
0x180069e9a  jmp     loc_180069DA8
0x180069e9f  cmp     r8b, 78h ; 'x'
0x180069ea3  jnz     short loc_180069E7B
0x180069ea5  lea     ecx, [rdi+1]
0x180069ea8  add     rcx, rsi
0x180069eab  call    jsonIs2Hex
0x180069eb0  test    eax, eax
0x180069eb2  jnz     short loc_180069E8B
0x180069eb4  mov     [rbx+28h], edi
0x180069eb7  mov     eax, r13d
0x180069eba  jmp     loc_18006A6F4
0x180069ebf  mov     edx, 9
0x180069ec4  cmp     r10b, 7
0x180069ec8  jnz     short loc_180069EEC
0x180069eca  mov     r10b, 8
0x180069ecd  jmp     short loc_180069EEC
0x180069ecf  cmp     cl, 1Fh
0x180069ed2  jg      short loc_180069EE1
0x180069ed4  test    cl, cl
0x180069ed6  jz      short loc_180069EB4
0x180069ed8  mov     r10b, dl
0x180069edb  mov     [rbx+31h], r14b
0x180069edf  jmp     short loc_180069EEC
0x180069ee1  cmp     cl, 22h ; '"'
0x180069ee4  movzx   r10d, r10b
0x180069ee8  cmovz   r10d, edx
0x180069eec  add     edi, r14d
0x180069eef  jmp     loc_180069DA8
0x180069ef4  mov     r8d, edi
0x180069ef7  add     r9, rsi
0x180069efa  sub     r8d, ebp
0x180069efd  mov     dl, r10b
0x180069f00  sub     r8d, r14d
0x180069f03  mov     rcx, rbx
0x180069f06  call    jsonBlobAppendNode
0x180069f0b  jmp     loc_18006A1E5
0x180069f10  xor     eax, eax
0x180069f12  jmp     loc_18006A6F4
0x180069f17  mov     [rbx+31h], r14b
0x180069f1b  jmp     loc_180069CC6
0x180069f20  lea     eax, [rbp+1]
0x180069f23  movzx   eax, byte ptr [rax+rsi]
0x180069f27  test    byte ptr [rax+r12+0ADE90h], 4
0x180069f30  jz      loc_18006A6EA
0x180069f36  mov     [rbx+31h], r14b
0x180069f3a  mov     dl, 3
0x180069f3c  xor     r14b, r14b
0x180069f3f  mov     r15d, 1
0x180069f45  lea     r9d, [rbp+1]
0x180069f49  mov     edi, r9d
0x180069f4c  mov     eax, edi
0x180069f4e  movzx   ecx, byte ptr [rax+rsi]
0x180069f52  test    byte ptr [rcx+r12+0ADE90h], 4
0x180069f5b  jnz     loc_18006A5AD
0x180069f61  cmp     cl, 2Eh ; '.'
0x180069f64  jnz     loc_18006A536
0x180069f6a  test    dl, 2
0x180069f6d  jnz     loc_180069EB4
0x180069f73  jmp     loc_18006A5AA
0x180069f78  mov     r14d, 0FFFFFFFCh
0x180069f7e  jmp     loc_18006A6EE
0x180069f83  mov     r14d, 0FFFFFFFEh
0x180069f89  jmp     loc_18006A6EE
0x180069f8e  mov     r8d, [rbx+20h]
0x180069f92  xor     r9d, r9d
0x180069f95  mov     eax, [rbx+8]
0x180069f98  sub     r8d, ebp
0x180069f9b  mov     dl, 0Ch
0x180069f9d  mov     [rsp+68h+arg_18], eax
0x180069fa4  mov     rcx, rbx
0x180069fa7  call    jsonBlobAppendNode
0x180069fac  add     [rbx+2Ch], r14w
0x180069fb1  mov     eax, 3E8h
0x180069fb6  cmp     [rbx+2Ch], ax
0x180069fba  ja      loc_18006A6EA
0x180069fc0  mov     eax, [rbx+8]
0x180069fc3  lea     edi, [rbp+1]
0x180069fc6  mov     r14d, 0FFFFFFFCh
0x180069fcc  mov     [rsp+68h+arg_8], eax
0x180069fd0  lea     r12, __ImageBase
0x180069fd7  lea     r13d, [r14+5]
0x180069fdb  mov     r15d, [rbx+8]
0x180069fdf  mov     edx, edi
0x180069fe1  mov     rcx, rbx
0x180069fe4  mov     [rsp+68h+arg_10], r15d
0x180069fec  call    jsonTranslateTextToBlob
0x180069ff1  mov     ebp, eax
0x180069ff3  test    eax, eax
0x180069ff5  jg      loc_18006A0CA
0x180069ffb  cmp     eax, 0FFFFFFFEh
0x180069ffe  jz      loc_18006A1A8
0x18006a004  mov     ecx, edi
0x18006a006  add     rcx, rsi
0x18006a009  call    json5Whitespace
0x18006a00e  add     edi, eax
0x18006a010  mov     dword ptr [rsp+68h+arg_0], 7
0x18006a018  mov     r13d, edi
0x18006a01b  add     r13, rsi
0x18006a01e  movzx   eax, byte ptr [r13+0]
0x18006a023  test    byte ptr [rax+r12+0ADE90h], 42h
0x18006a02c  jnz     short loc_18006A05A
0x18006a02e  cmp     al, 5Ch ; '\'
0x18006a030  jnz     short loc_18006A04A
0x18006a032  lea     r9d, [rdi+1]
0x18006a036  mov     ecx, r9d
0x18006a039  lea     rdx, [rsp+68h+arg_0]
0x18006a03e  add     rcx, rsi
0x18006a041  call    jsonIs4HexB
0x18006a046  test    eax, eax
0x18006a048  jnz     short loc_18006A05E
  ... truncated ...
```
