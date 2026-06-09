# jsonTranslateTextToBlob

- ea: `0x180086c60`
- end: `0x180087789`
- name: `jsonTranslateTextToBlob`
- size: `2857`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180082ea4`
- `0x180086188`
- `0x180086c60`

## callees

- `0x18003d760`
- `0x180081b9c`
- `0x1800827b8`
- `0x180082898`
- `0x1800828bc`
- `0x180084530`
- `0x18008455c`
- `0x18008458c`
- `0x180086c60`
- `0x1800af5f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180086d00`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x1800871f5`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x1800873e5`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180086d00`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x1800871f5`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x1800873e5`

## pseudocode

```c
__int64 __fastcall jsonTranslateTextToBlob(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 v5; // r13
  __int64 v6; // rdx
  _BYTE *v7; // r11
  unsigned int v8; // r15d
  char v9; // dl
  char v10; // r14
  unsigned int v11; // r9d
  unsigned __int8 *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdi
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
  unsigned int v27; // r8d
  unsigned int v28; // r15d
  int v29; // eax
  __int64 v30; // rbp
  __int64 v31; // rax
  int v32; // r9d
  unsigned __int8 *v33; // rcx
  __int64 v34; // r15
  __int64 v35; // rcx
  int v36; // eax
  int v37; // eax
  char v38; // al
  int v39; // eax
  int v40; // eax
  bool v41; // zf
  __int64 v42; // rdx
  unsigned int v43; // r13d
  int v44; // r15d
  __int64 v45; // rax
  int v46; // eax
  __int64 v47; // rdi
  char *v48; // rax
  const char *v49; // r9
  char v50; // al
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // r8
  char v55; // cl
  __int64 v56; // rax
  __int64 v57; // r14
  __int64 v58; // rdi
  unsigned int v59; // r13d
  _BYTE *v60; // [rsp+70h] [rbp+8h] BYREF
  int v61; // [rsp+78h] [rbp+10h]
  unsigned int v62; // [rsp+80h] [rbp+18h]
  unsigned int v63; // [rsp+88h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 16);
  LODWORD(v5) = -1;
  while ( 1 )
  {
    v6 = 9;
    v7 = (_BYTE *)(v2 + a2);
    v60 = v7;
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
          if ( (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(a2 + 1 + v2)) & 4) != 0 )
          {
            *(_BYTE *)(a1 + 49) = 1;
            v9 = 3;
            v10 = 0;
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
        v57 = 0;
        while ( 1 )
        {
          v58 = 12 * v57;
          if ( (_BYTE)v8 == byte_1800B2C10[24 * v57] || (_BYTE)v8 == byte_1800B2C10[v58 * 2 + 1] )
          {
            v59 = SLOBYTE(word_1800B2C12[12 * v57]);
            if ( !(unsigned int)sqlite3_strnicmp(v7, off_1800B2C18[3 * v57], v59) )
            {
              v5 = a2 + v59;
              if ( (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(v5 + v2)) & 6) == 0 )
                break;
            }
          }
          v57 = (unsigned int)(v57 + 1);
          if ( (unsigned int)v57 >= 5 )
            goto LABEL_230;
          v7 = v60;
        }
        if ( HIBYTE(word_1800B2C12[v58]) == 5 )
          jsonBlobAppendNode((__int64 *)a1, 5, 5u, "9e999");
        else
          jsonBlobAppendOneByte(a1, 0);
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
        v15 = json5Whitespace(v2 + a2);
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
        LODWORD(v14) = a2 + 1;
        while ( 2 )
        {
          while ( 2 )
          {
            if ( *((_BYTE *)qword_1800C11D0 + *(unsigned __int8 *)((unsigned int)v14 + v2)) )
            {
              v19 = (unsigned int)(v14 + 1);
              if ( *((_BYTE *)qword_1800C11D0 + *(unsigned __int8 *)(v19 + v2)) )
              {
                v19 = (unsigned int)(v14 + 2);
                if ( *((_BYTE *)qword_1800C11D0 + *(unsigned __int8 *)(v19 + v2)) )
                {
                  LODWORD(v14) = v14 + 3;
                  v6 = 9;
                  continue;
                }
              }
              LODWORD(v14) = v19;
              v6 = 9;
            }
            break;
          }
          v20 = *(_BYTE *)((unsigned int)v14 + v2);
          if ( v20 == v17 )
          {
            jsonBlobAppendNode((__int64 *)a1, v16, v14 - a2 - 1, (const void *)(v2 + v18));
            return (unsigned int)(v14 + 1);
          }
          if ( v20 == 92 )
          {
            v14 = (unsigned int)(v14 + 1);
            v21 = *(char *)(v14 + v2);
            if ( (_BYTE)v21 == 34
              || (unsigned __int8)(v21 - 92) <= 0x18u && (v22 = 21234753, _bittest(&v22, v21 - 92))
              || (_BYTE)v21 == 47
              || (_BYTE)v21 == 117 && (unsigned int)jsonIs4Hex(v2 + (unsigned int)(v14 + 1)) )
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
                    if ( *(_BYTE *)((unsigned int)(v14 + 1) + v2) != 0x80 )
                      goto LABEL_66;
                    if ( (unsigned __int8)(*(_BYTE *)((unsigned int)(v14 + 2) + v2) + 88) > 1u )
                    {
LABEL_59:
                      if ( (_BYTE)v21 != 13 )
                        goto LABEL_66;
                      if ( *(_BYTE *)((unsigned int)(v14 + 1) + v2) == 10 )
                        LODWORD(v14) = v14 + 1;
                    }
                  }
                  else
                  {
                    if ( (_BYTE)v21 != 120 )
                      goto LABEL_59;
                    if ( !(unsigned int)jsonIs2Hex(v2 + (unsigned int)(v14 + 1), v6) )
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
          LODWORD(v14) = v14 + 1;
          continue;
        }
    }
  }
  LODWORD(v5) = -1;
  if ( v8 > 0x6E )
  {
    switch ( v8 )
    {
      case 't':
        if ( strncmp_0((const char *)(v2 + a2), "true", 4u) )
          goto LABEL_230;
        v14 = a2 + 4;
        v42 = *(unsigned __int8 *)(v14 + v2);
        if ( (*((_BYTE *)&qword_1800B4FF0 + v42) & 6) != 0 )
          goto LABEL_230;
        LOBYTE(v42) = 1;
        goto LABEL_136;
      case '{':
        v27 = *(_DWORD *)(a1 + 32) - a2;
        v63 = *(_DWORD *)(a1 + 8);
        jsonBlobAppendNode((__int64 *)a1, 12, v27, 0);
        if ( ++*(_WORD *)(a1 + 44) > 0x3E8u )
          goto LABEL_230;
        LODWORD(v14) = a2 + 1;
        v61 = *(_DWORD *)(a1 + 8);
        while ( 2 )
        {
          v28 = *(_DWORD *)(a1 + 8);
          v62 = v28;
          v29 = jsonTranslateTextToBlob(a1, (unsigned int)v14);
          LODWORD(v30) = v29;
          if ( v29 <= 0 )
          {
            if ( v29 == -2 )
            {
              v40 = v61;
              LODWORD(v14) = *(_DWORD *)(a1 + 40);
              if ( *(_DWORD *)(a1 + 8) != v61 )
                *(_BYTE *)(a1 + 49) = 1;
              goto LABEL_127;
            }
            LODWORD(v14) = json5Whitespace(v2 + (unsigned int)v14) + v14;
            LODWORD(v60) = 7;
            v31 = *(unsigned __int8 *)(v2 + (unsigned int)v14);
            if ( (*((_BYTE *)&qword_1800B4FF0 + v31) & 0x42) != 0 )
            {
              v32 = v14 + 1;
            }
            else if ( (_BYTE)v31 != 92 || !(unsigned int)jsonIs4HexB(v2 + (unsigned int)(v14 + 1), &v60) )
            {
              goto LABEL_95;
            }
            do
            {
              while ( 1 )
              {
                LODWORD(v30) = v32;
                v33 = (unsigned __int8 *)(v2 + v32);
                v34 = *v33;
                if ( (*((_BYTE *)&qword_1800B4FF0 + v34) & 0x46) == 0 || (unsigned int)json5Whitespace((__int64)v33) )
                  break;
                v32 = v30 + 1;
              }
            }
            while ( (_BYTE)v34 == 92 && (unsigned int)jsonIs4HexB(v2 + (int)v30 + 1, &v60) );
            jsonBlobAppendNode((__int64 *)a1, (char)v60, v30 - v14, (const void *)(v2 + (unsigned int)v14));
            v28 = v62;
            *(_BYTE *)(a1 + 49) = 1;
          }
          if ( *(_BYTE *)(a1 + 47) )
            return 0xFFFFFFFFLL;
          if ( (unsigned __int8)((*(_BYTE *)(v28 + *(_QWORD *)a1) & 0xF) - 7) > 3u )
            goto LABEL_96;
          if ( *(_BYTE *)((unsigned int)v30 + v2) != 58 )
          {
            if ( !*((_BYTE *)&qword_1800BD6E0 + *(unsigned __int8 *)((unsigned int)v30 + v2)) )
              goto LABEL_111;
            do
            {
              v30 = (unsigned int)(v30 + 1);
              v35 = *(unsigned __int8 *)(v30 + v2);
            }
            while ( *((_BYTE *)&qword_1800BD6E0 + v35) );
            LODWORD(v60) = v30;
            if ( (_BYTE)v35 != 58 )
            {
LABEL_111:
              v36 = jsonTranslateTextToBlob(a1, (unsigned int)v30);
              if ( v36 != -5 )
              {
                v41 = v36 == -1;
LABEL_131:
                if ( !v41 )
                  *(_DWORD *)(a1 + 40) = v30;
                return 0xFFFFFFFFLL;
              }
              LODWORD(v30) = *(_DWORD *)(a1 + 40);
            }
          }
          LODWORD(v30) = v30 + 1;
          v37 = jsonTranslateTextToBlob(a1, (unsigned int)v30);
          v14 = (unsigned int)v37;
          if ( v37 <= 0 )
          {
            v41 = v37 == -1;
            goto LABEL_131;
          }
          v38 = *(_BYTE *)((unsigned int)v37 + v2);
          if ( v38 != 44 )
          {
            if ( v38 == 125 )
              goto LABEL_126;
            _mm_lfence();
            if ( !*((_BYTE *)&qword_1800BD6E0 + *(unsigned __int8 *)(v14 + v2)) )
              goto LABEL_119;
            LODWORD(v14) = v14 + strspn((const char *)(v2 + (unsigned int)(v14 + 1)), "\t\n\r ") + 1;
            if ( *(_BYTE *)((unsigned int)v14 + v2) != 44 )
            {
              if ( *(_BYTE *)((unsigned int)v14 + v2) == 125 )
                goto LABEL_126;
LABEL_119:
              v39 = jsonTranslateTextToBlob(a1, (unsigned int)v14);
              if ( v39 != -4 )
              {
                if ( v39 == -2 )
                {
                  LODWORD(v14) = *(_DWORD *)(a1 + 40);
LABEL_126:
                  v40 = v61;
LABEL_127:
                  jsonBlobChangePayloadSize(a1, v63, *(_DWORD *)(a1 + 8) - v40);
                  --*(_WORD *)(a1 + 44);
                  return (unsigned int)(v14 + 1);
                }
LABEL_96:
                *(_DWORD *)(a1 + 40) = v14;
                return 0xFFFFFFFFLL;
              }
              LODWORD(v14) = *(_DWORD *)(a1 + 40);
            }
          }
          LODWORD(v14) = v14 + 1;
          LODWORD(v60) = v14;
          continue;
        }
      case '}':
        v26 = -2;
        goto LABEL_231;
    }
    if ( v8 != 194 && v8 != 225 && v8 != 226 && v8 != 227 && v8 != 239 )
      goto LABEL_219;
    goto LABEL_35;
  }
  if ( v8 == 110 )
  {
    if ( strncmp_0((const char *)(v2 + a2), "null", 4u)
      || (v14 = a2 + 4, (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(v14 + v2)) & 6) != 0) )
    {
      v7 = v60;
      goto LABEL_219;
    }
    v42 = 0;
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
      v14 = a2 + 5;
      if ( (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(v14 + v2)) & 6) != 0 )
        goto LABEL_230;
      LOBYTE(v42) = 2;
LABEL_136:
      jsonBlobAppendOneByte(a1, v42);
      return (unsigned int)v14;
    }
    v43 = *(_DWORD *)(a1 + 8);
    jsonBlobAppendNode((__int64 *)a1, 11, *(_DWORD *)(a1 + 32) - a2, 0);
    if ( *(_BYTE *)(a1 + 47) )
      return 0xFFFFFFFFLL;
    if ( ++*(_WORD *)(a1 + 44) > 0x3E8u )
      goto LABEL_230;
    v44 = *(_DWORD *)(a1 + 8);
    LODWORD(v14) = a2 + 1;
    LODWORD(v30) = jsonTranslateTextToBlob(a1, a2 + 1);
    if ( (int)v30 <= 0 )
    {
LABEL_163:
      if ( (_DWORD)v30 != -3 )
      {
LABEL_95:
        if ( (_DWORD)v30 != -1 )
          goto LABEL_96;
        return 0xFFFFFFFFLL;
      }
      LODWORD(v14) = *(_DWORD *)(a1 + 40);
      if ( *(_DWORD *)(a1 + 8) != v44 )
        *(_BYTE *)(a1 + 49) = 1;
LABEL_166:
      jsonBlobChangePayloadSize(a1, v43, *(_DWORD *)(a1 + 8) - v44);
      --*(_WORD *)(a1 + 44);
      return (unsigned int)(v14 + 1);
    }
    while ( 2 )
    {
      LODWORD(v14) = v30;
      v45 = *(unsigned __int8 *)((unsigned int)v30 + v2);
      if ( (_BYTE)v45 != 44 )
      {
        if ( (_BYTE)v45 == 93 )
          goto LABEL_166;
        if ( !*((_BYTE *)&qword_1800BD6E0 + v45) )
          goto LABEL_160;
        v14 = (unsigned int)v30 + (unsigned int)strspn((const char *)(v2 + (unsigned int)(v30 + 1)), "\t\n\r ") + 1;
        if ( *(_BYTE *)(v14 + v2) != 44 )
        {
          if ( *(_BYTE *)(v14 + v2) == 93 )
            goto LABEL_166;
LABEL_160:
          v46 = jsonTranslateTextToBlob(a1, (unsigned int)v14);
          if ( v46 != -4 )
          {
            if ( v46 != -3 )
              goto LABEL_96;
            LODWORD(v14) = *(_DWORD *)(a1 + 40);
            goto LABEL_166;
          }
          LODWORD(v14) = *(_DWORD *)(a1 + 40);
        }
      }
      LODWORD(v14) = v14 + 1;
      LODWORD(v30) = jsonTranslateTextToBlob(a1, (unsigned int)v14);
      if ( (int)v30 <= 0 )
        goto LABEL_163;
      continue;
    }
  }
LABEL_21:
  v9 = 0;
  v10 = 0;
  if ( (char)*v7 > 48 )
    goto LABEL_81;
  v11 = a2 + 1;
  v12 = (unsigned __int8 *)(v2 + a2 + 1);
  if ( *v7 == 48 )
  {
    v13 = *v12;
    if ( (((_BYTE)v13 - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(a2 + 2 + v2)) & 8) != 0 )
    {
      *(_BYTE *)(a1 + 49) = 1;
      v14 = a2 + 3;
      v9 = 1;
      while ( (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(v14 + v2)) & 8) != 0 )
        v14 = (unsigned int)(v14 + 1);
      goto LABEL_212;
    }
    if ( (*((_BYTE *)&qword_1800B4FF0 + v13) & 4) == 0 )
      goto LABEL_81;
LABEL_186:
    *(_DWORD *)(a1 + 40) = v11;
    return (unsigned int)v5;
  }
  v47 = *v12;
  if ( (*((_BYTE *)&qword_1800B4FF0 + v47) & 4) != 0 )
  {
    if ( (_BYTE)v47 != 48 )
      goto LABEL_81;
    v51 = *(unsigned __int8 *)(a2 + 2 + v2);
    if ( (*((_BYTE *)&qword_1800B4FF0 + v51) & 4) != 0 )
      goto LABEL_186;
    if ( (((_BYTE)v51 - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(a2 + 3 + v2)) & 8) != 0 )
    {
      *(_BYTE *)(a1 + 49) = 1;
      v14 = a2 + 4;
      v9 = 1;
      while ( (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(v14 + v2)) & 8) != 0 )
        v14 = (unsigned int)(v14 + 1);
      goto LABEL_212;
    }
  }
  else
  {
    if ( (((_BYTE)v47 - 73) & 0xDF) == 0 )
    {
      if ( !(unsigned int)sqlite3_strnicmp(v12, "inf", 3) )
      {
        v48 = v60;
        *(_BYTE *)(a1 + 49) = 1;
        v49 = "-9e999";
        v50 = *v48;
        if ( v50 != 45 )
          v49 = "9e999";
        jsonBlobAppendNode((__int64 *)a1, 5, 6 - (v50 != 45), v49);
        return a2 + ((unsigned int)sqlite3_strnicmp(v2 + a2 + 4, "inity", 5) != 0 ? 4 : 9);
      }
      v7 = v60;
    }
    if ( (_BYTE)v47 != 46 )
      goto LABEL_230;
    *(_BYTE *)(a1 + 49) = 1;
    v9 = 1;
  }
LABEL_81:
  v11 = a2 + 1;
  LODWORD(v14) = a2 + 1;
  while ( 2 )
  {
    v25 = *(unsigned __int8 *)((unsigned int)v14 + v2);
    if ( (*((_BYTE *)&qword_1800B4FF0 + v25) & 4) != 0 )
      goto LABEL_206;
    if ( (_BYTE)v25 == 46 )
    {
      if ( (v9 & 2) != 0 )
        goto LABEL_66;
      goto LABEL_205;
    }
    v52 = (unsigned int)(v14 - 1);
    if ( (((_BYTE)v25 - 69) & 0xDF) == 0 )
    {
      if ( *(char *)(v52 + v2) < 48 )
      {
        if ( *(_BYTE *)(v52 + v2) != 46 )
          goto LABEL_66;
        v53 = (unsigned int)(v14 - 2);
        if ( (unsigned int)v53 < a2 || (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(v53 + v2)) & 4) == 0 )
          goto LABEL_66;
        *(_BYTE *)(a1 + 49) = 1;
        v9 |= 1u;
      }
      if ( v10 )
        goto LABEL_66;
      v54 = (unsigned int)(v14 + 1);
      v55 = *(_BYTE *)(v54 + v2);
      if ( v55 == 43 || v55 == 45 )
      {
        LODWORD(v14) = v14 + 1;
        v55 = *(_BYTE *)((unsigned int)(v54 + 1) + v2);
      }
      if ( (unsigned __int8)(v55 - 48) > 9u )
        goto LABEL_66;
      v10 = 1;
LABEL_205:
      v9 |= 2u;
LABEL_206:
      LODWORD(v14) = v14 + 1;
      continue;
    }
    break;
  }
  if ( *(char *)(v52 + v2) < 48 )
  {
    if ( *(_BYTE *)(v52 + v2) != 46
      || (v56 = (unsigned int)(v14 - 2), (unsigned int)v56 < a2)
      || (*((_BYTE *)&qword_1800B4FF0 + *(unsigned __int8 *)(v56 + v2)) & 4) == 0 )
    {
LABEL_66:
      *(_DWORD *)(a1 + 40) = v14;
      return (unsigned int)v5;
    }
    *(_BYTE *)(a1 + 49) = 1;
    v9 |= 1u;
  }
LABEL_212:
  if ( *v7 == 43 )
    a2 = v11;
  jsonBlobAppendNode((__int64 *)a1, v9 + 3, v14 - a2, (const void *)(v2 + a2));
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180086c60  push    rbx
0x180086c62  push    rbp
0x180086c63  push    rsi
0x180086c64  push    rdi
0x180086c65  push    r12
0x180086c67  push    r13
0x180086c69  push    r14
0x180086c6b  push    r15
0x180086c6d  sub     rsp, 28h
0x180086c71  mov     rsi, [rcx+10h]
0x180086c75  mov     ebp, edx
0x180086c77  mov     rbx, rcx
0x180086c7a  mov     r14d, 1
0x180086c80  or      r13d, 0FFFFFFFFh
0x180086c84  mov     edx, 9
0x180086c89  mov     r11d, ebp
0x180086c8c  lea     r12, __ImageBase
0x180086c93  add     r11, rsi
0x180086c96  mov     r10b, 30h ; '0'
0x180086c99  mov     [rsp+68h+arg_0], r11
0x180086c9e  movzx   r15d, byte ptr [r11]
0x180086ca2  cmp     r15d, 34h ; '4'
0x180086ca6  ja      loc_180086D9F
0x180086cac  jz      loc_180086D4A
0x180086cb2  cmp     r15d, 2Bh ; '+'
0x180086cb6  ja      short loc_180086D0F
0x180086cb8  jz      loc_180086F9B
0x180086cbe  mov     ecx, r15d
0x180086cc1  test    r15d, r15d
0x180086cc4  jz      loc_180086F94
0x180086cca  sub     ecx, edx
0x180086ccc  jz      short loc_180086CF3
0x180086cce  sub     ecx, r14d
0x180086cd1  jz      short loc_180086CF3
0x180086cd3  sub     ecx, r14d
0x180086cd6  jz      loc_180086DE8
0x180086cdc  sub     ecx, r14d
0x180086cdf  jz      loc_180086DE8
0x180086ce5  sub     ecx, r14d
0x180086ce8  jz      short loc_180086CF3
0x180086cea  sub     ecx, 13h
0x180086ced  jnz     loc_180086E03
0x180086cf3  lea     ecx, [rbp+1]
0x180086cf6  add     rcx, rsi; Str
0x180086cf9  lea     rdx, Control; "\t\n\r "
0x180086d00  call    cs:__imp_strspn
0x180086d06  inc     ebp
0x180086d08  add     ebp, eax
0x180086d0a  jmp     loc_180086C84
0x180086d0f  mov     ecx, r15d
0x180086d12  sub     ecx, 2Ch ; ','
0x180086d15  jz      loc_180086FFC
0x180086d1b  sub     ecx, r14d
0x180086d1e  jz      short loc_180086D4A
0x180086d20  sub     ecx, r14d
0x180086d23  jz      loc_180086FA4
0x180086d29  sub     ecx, r14d
0x180086d2c  jz      loc_180086DE8
0x180086d32  sub     ecx, r14d
0x180086d35  jz      short loc_180086D4A
0x180086d37  sub     ecx, r14d
0x180086d3a  jz      short loc_180086D4A
0x180086d3c  sub     ecx, r14d
0x180086d3f  jz      short loc_180086D4A
0x180086d41  cmp     ecx, r14d
0x180086d44  jnz     loc_1800876C9
0x180086d4a  xor     dl, dl
0x180086d4c  xor     r14b, r14b
0x180086d4f  cmp     [r11], r10b
0x180086d52  jg      loc_180086FC3
0x180086d58  lea     r9d, [rbp+1]
0x180086d5c  mov     ecx, r9d
0x180086d5f  add     rcx, rsi
0x180086d62  cmp     [r11], r10b
0x180086d65  jnz     loc_1800874A5
0x180086d6b  movzx   r8d, byte ptr [rcx]
0x180086d6f  lea     eax, [r8-58h]
0x180086d73  test    al, 0DFh
0x180086d75  jnz     loc_180087491
0x180086d7b  lea     eax, [rbp+2]
0x180086d7e  movzx   eax, byte ptr [rax+rsi]
0x180086d82  test    byte ptr [rax+r12+0B4FF0h], 8
0x180086d8b  jz      loc_180087491
0x180086d91  mov     byte ptr [rbx+31h], 1
0x180086d95  lea     edi, [rbp+3]
0x180086d98  mov     dl, 1
0x180086d9a  jmp     loc_18008747D
0x180086d9f  or      r13d, 0FFFFFFFFh
0x180086da3  cmp     r15d, 6Eh ; 'n'
0x180086da7  jbe     loc_1800872CC
0x180086dad  mov     edx, r15d
0x180086db0  sub     edx, 74h ; 't'
0x180086db3  jz      loc_180087287
0x180086db9  sub     edx, 7
0x180086dbc  jz      loc_180087012
0x180086dc2  sub     edx, 2
0x180086dc5  jz      loc_180087007
0x180086dcb  sub     edx, 45h ; 'E'
0x180086dce  jz      short loc_180086DE8
0x180086dd0  sub     edx, 1Fh
0x180086dd3  jz      short loc_180086DE8
0x180086dd5  sub     edx, r14d
0x180086dd8  jz      short loc_180086DE8
0x180086dda  sub     edx, r14d
0x180086ddd  jz      short loc_180086DE8
0x180086ddf  cmp     edx, 0Ch
0x180086de2  jnz     loc_1800876C9
0x180086de8  mov     rcx, r11
0x180086deb  call    json5Whitespace
0x180086df0  test    eax, eax
0x180086df2  jz      loc_18008776E
0x180086df8  add     ebp, eax
0x180086dfa  mov     [rbx+31h], r14b
0x180086dfe  jmp     loc_180086C84
0x180086e03  sub     ecx, 2
0x180086e06  jz      short loc_180086E15
0x180086e08  cmp     ecx, 5
0x180086e0b  jnz     loc_1800876C9
0x180086e11  mov     [rbx+31h], r14b
0x180086e15  mov     r10b, 7
0x180086e18  mov     r11b, [r11]
0x180086e1b  lea     r9d, [rbp+1]
0x180086e1f  mov     edi, r9d
0x180086e22  lea     r12, __ImageBase
0x180086e29  xor     r15d, r15d
0x180086e2c  mov     eax, edi
0x180086e2e  movzx   ecx, byte ptr [rax+rsi]
0x180086e32  cmp     [rcx+r12+0C11D0h], r15b
0x180086e3a  jz      short loc_180086E69
0x180086e3c  lea     edx, [rdi+1]
0x180086e3f  movzx   ecx, byte ptr [rdx+rsi]
0x180086e43  cmp     [rcx+r12+0C11D0h], r15b
0x180086e4b  jz      short loc_180086E62
0x180086e4d  lea     edx, [rdi+2]
0x180086e50  movzx   ecx, byte ptr [rdx+rsi]
0x180086e54  cmp     [rcx+r12+0C11D0h], r15b
0x180086e5c  jnz     loc_180086F16
0x180086e62  mov     edi, edx
0x180086e64  mov     edx, 9
0x180086e69  mov     eax, edi
0x180086e6b  mov     cl, [rax+rsi]
0x180086e6e  cmp     cl, r11b
0x180086e71  jz      loc_180086F78
0x180086e77  cmp     cl, 5Ch ; '\'
0x180086e7a  jnz     loc_180086F53
0x180086e80  add     edi, r14d
0x180086e83  movsx   r8, byte ptr [rdi+rsi]
0x180086e88  cmp     r8b, 22h ; '"'
0x180086e8c  jz      loc_180086F43
0x180086e92  lea     eax, [r8-5Ch]
0x180086e96  cmp     al, 18h
0x180086e98  ja      short loc_180086EA8
0x180086e9a  mov     ecx, 1440441h
0x180086e9f  bt      ecx, eax
0x180086ea2  jb      loc_180086F43
0x180086ea8  cmp     r8b, 2Fh ; '/'
0x180086eac  jz      loc_180086F43
0x180086eb2  cmp     r8b, 75h ; 'u'
0x180086eb6  jnz     short loc_180086EC7
0x180086eb8  lea     ecx, [rdi+1]
0x180086ebb  add     rcx, rsi
0x180086ebe  call    jsonIs4Hex
0x180086ec3  test    eax, eax
0x180086ec5  jnz     short loc_180086F43
0x180086ec7  cmp     r8b, 30h ; '0'
0x180086ecb  ja      short loc_180086EDD
0x180086ecd  mov     rcx, 1008000000400h
0x180086ed7  bt      rcx, r8
0x180086edb  jb      short loc_180086F0F
0x180086edd  cmp     r8b, 76h ; 'v'
0x180086ee1  jz      short loc_180086F0F
0x180086ee3  cmp     r8b, 0E2h
0x180086ee7  jnz     short loc_180086F23
0x180086ee9  lea     eax, [rdi+1]
0x180086eec  cmp     byte ptr [rax+rsi], 80h
0x180086ef0  jnz     short loc_180086F38
0x180086ef2  lea     eax, [rdi+2]
0x180086ef5  mov     al, [rax+rsi]
0x180086ef8  add     al, 58h ; 'X'
0x180086efa  cmp     al, r14b
0x180086efd  jbe     short loc_180086F0F
0x180086eff  cmp     r8b, 0Dh
0x180086f03  jnz     short loc_180086F38
0x180086f05  lea     ecx, [rdi+1]
0x180086f08  cmp     byte ptr [rcx+rsi], 0Ah
0x180086f0c  cmovz   edi, ecx
0x180086f0f  mov     edx, 9
0x180086f14  jmp     short loc_180086F5C
0x180086f16  add     edi, 3
0x180086f19  mov     edx, 9
0x180086f1e  jmp     loc_180086E2C
0x180086f23  cmp     r8b, 78h ; 'x'
0x180086f27  jnz     short loc_180086EFF
0x180086f29  lea     ecx, [rdi+1]
0x180086f2c  add     rcx, rsi
0x180086f2f  call    jsonIs2Hex
0x180086f34  test    eax, eax
0x180086f36  jnz     short loc_180086F0F
0x180086f38  mov     [rbx+28h], edi
0x180086f3b  mov     eax, r13d
0x180086f3e  jmp     loc_180087778
0x180086f43  mov     edx, 9
0x180086f48  cmp     r10b, 7
0x180086f4c  jnz     short loc_180086F70
0x180086f4e  mov     r10b, 8
0x180086f51  jmp     short loc_180086F70
0x180086f53  cmp     cl, 1Fh
0x180086f56  jg      short loc_180086F65
0x180086f58  test    cl, cl
0x180086f5a  jz      short loc_180086F38
0x180086f5c  mov     r10b, dl
0x180086f5f  mov     [rbx+31h], r14b
0x180086f63  jmp     short loc_180086F70
0x180086f65  cmp     cl, 22h ; '"'
0x180086f68  movzx   r10d, r10b
0x180086f6c  cmovz   r10d, edx
0x180086f70  add     edi, r14d
0x180086f73  jmp     loc_180086E2C
0x180086f78  mov     r8d, edi
0x180086f7b  add     r9, rsi
0x180086f7e  sub     r8d, ebp
0x180086f81  mov     dl, r10b
0x180086f84  sub     r8d, r14d
0x180086f87  mov     rcx, rbx
0x180086f8a  call    jsonBlobAppendNode
0x180086f8f  jmp     loc_180087269
0x180086f94  xor     eax, eax
0x180086f96  jmp     loc_180087778
0x180086f9b  mov     [rbx+31h], r14b
0x180086f9f  jmp     loc_180086D4A
0x180086fa4  lea     eax, [rbp+1]
0x180086fa7  movzx   eax, byte ptr [rax+rsi]
0x180086fab  test    byte ptr [rax+r12+0B4FF0h], 4
0x180086fb4  jz      loc_18008776E
0x180086fba  mov     [rbx+31h], r14b
0x180086fbe  mov     dl, 3
0x180086fc0  xor     r14b, r14b
0x180086fc3  mov     r15d, 1
0x180086fc9  lea     r9d, [rbp+1]
0x180086fcd  mov     edi, r9d
0x180086fd0  mov     eax, edi
0x180086fd2  movzx   ecx, byte ptr [rax+rsi]
0x180086fd6  test    byte ptr [rcx+r12+0B4FF0h], 4
0x180086fdf  jnz     loc_180087631
0x180086fe5  cmp     cl, 2Eh ; '.'
0x180086fe8  jnz     loc_1800875BA
0x180086fee  test    dl, 2
0x180086ff1  jnz     loc_180086F38
0x180086ff7  jmp     loc_18008762E
0x180086ffc  mov     r14d, 0FFFFFFFCh
0x180087002  jmp     loc_180087772
0x180087007  mov     r14d, 0FFFFFFFEh
0x18008700d  jmp     loc_180087772
0x180087012  mov     r8d, [rbx+20h]
0x180087016  xor     r9d, r9d
0x180087019  mov     eax, [rbx+8]
0x18008701c  sub     r8d, ebp
0x18008701f  mov     dl, 0Ch
0x180087021  mov     [rsp+68h+arg_18], eax
0x180087028  mov     rcx, rbx
0x18008702b  call    jsonBlobAppendNode
0x180087030  add     [rbx+2Ch], r14w
0x180087035  mov     eax, 3E8h
0x18008703a  cmp     [rbx+2Ch], ax
0x18008703e  ja      loc_18008776E
0x180087044  mov     eax, [rbx+8]
0x180087047  lea     edi, [rbp+1]
0x18008704a  mov     r14d, 0FFFFFFFCh
0x180087050  mov     [rsp+68h+arg_8], eax
0x180087054  lea     r12, __ImageBase
0x18008705b  lea     r13d, [r14+5]
0x18008705f  mov     r15d, [rbx+8]
0x180087063  mov     edx, edi
0x180087065  mov     rcx, rbx
0x180087068  mov     [rsp+68h+arg_10], r15d
0x180087070  call    jsonTranslateTextToBlob
0x180087075  mov     ebp, eax
0x180087077  test    eax, eax
0x180087079  jg      loc_18008714E
0x18008707f  cmp     eax, 0FFFFFFFEh
0x180087082  jz      loc_18008722C
0x180087088  mov     ecx, edi
0x18008708a  add     rcx, rsi
0x18008708d  call    json5Whitespace
0x180087092  add     edi, eax
0x180087094  mov     dword ptr [rsp+68h+arg_0], 7
0x18008709c  mov     r13d, edi
0x18008709f  add     r13, rsi
0x1800870a2  movzx   eax, byte ptr [r13+0]
0x1800870a7  test    byte ptr [rax+r12+0B4FF0h], 42h
0x1800870b0  jnz     short loc_1800870DE
0x1800870b2  cmp     al, 5Ch ; '\'
0x1800870b4  jnz     short loc_1800870CE
0x1800870b6  lea     r9d, [rdi+1]
0x1800870ba  mov     ecx, r9d
0x1800870bd  lea     rdx, [rsp+68h+arg_0]
0x1800870c2  add     rcx, rsi
0x1800870c5  call    jsonIs4HexB
0x1800870ca  test    eax, eax
0x1800870cc  jnz     short loc_1800870E2
  ... truncated ...
```
