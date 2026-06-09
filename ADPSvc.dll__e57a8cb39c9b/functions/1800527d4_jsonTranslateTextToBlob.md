# jsonTranslateTextToBlob

- ea: `0x1800527d4`
- end: `0x18005339c`
- name: `jsonTranslateTextToBlob`
- size: `3016`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004e400`
- `0x180051a5c`
- `0x1800527d4`

## callees

- `0x18004d164`
- `0x18004ddbc`
- `0x18004de9c`
- `0x18004e138`
- `0x18004fb40`
- `0x1800527d4`
- `0x1800ada30`
- `0x1800c6e90`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180052879`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180052d9f`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180052fbe`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180052879`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180052d9f`
- `api-ms-win-crt-string-l1-1-0!strspn` at `0x180052fbe`

## pseudocode

```c
__int64 __fastcall jsonTranslateTextToBlob(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  unsigned int v3; // ebp
  __int64 v4; // rbx
  _BYTE *v5; // r11
  unsigned int v6; // edi
  char v7; // r14
  unsigned int v8; // r9d
  unsigned __int8 *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdi
  __int64 v12; // rdx
  int v13; // eax
  char v14; // r10
  char v15; // r12
  char v16; // cl
  unsigned __int64 v17; // r9
  int v18; // ecx
  __int64 v19; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // r14
  unsigned int v24; // r12d
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rbp
  __int64 v28; // rdx
  __int64 v29; // rax
  int v30; // r9d
  char v31; // r14
  unsigned __int8 *v32; // r13
  __int64 v33; // r12
  __int64 v34; // rcx
  int v35; // eax
  int v36; // eax
  char v37; // al
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rdx
  bool v41; // zf
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rax
  unsigned int v45; // r13d
  int v46; // r12d
  __int64 v47; // rax
  int v48; // eax
  __int64 v49; // rdi
  const char *v50; // r9
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // r8
  char v55; // cl
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // r12
  __int64 v59; // r14
  unsigned int v60; // r13d
  __int64 v61; // rdx
  __int64 v62; // r13
  __int64 v63; // rax
  unsigned int v64; // [rsp+20h] [rbp-58h]
  unsigned __int8 *v65; // [rsp+28h] [rbp-50h]
  int v67; // [rsp+88h] [rbp+10h]
  _BYTE *v68; // [rsp+90h] [rbp+18h]
  char v69; // [rsp+90h] [rbp+18h]
  unsigned int v70; // [rsp+98h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 16);
  v3 = a2;
  v4 = a1;
  while ( 1 )
  {
    v5 = (_BYTE *)(v2 + v3);
    v68 = v5;
    v6 = (unsigned __int8)*v5;
    if ( v6 > 0x34 )
      break;
    if ( v6 == 52 )
      goto LABEL_21;
    if ( v6 > 0x2B )
    {
      switch ( v6 )
      {
        case ',':
          LODWORD(v23) = -4;
          goto LABEL_245;
        case '-':
          goto LABEL_21;
        case '.':
          if ( (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v3 + 1 + v2)) & 4) != 0 )
          {
            *(_BYTE *)(v4 + 49) = 1;
            LOBYTE(a2) = 3;
            v7 = 0;
            goto LABEL_82;
          }
LABEL_244:
          LODWORD(v23) = -1;
LABEL_245:
          *(_DWORD *)(v4 + 40) = v3;
          return (unsigned int)v23;
      }
      if ( v6 != 47 )
      {
        if ( v6 == 48 || v6 == 49 || v6 - 50 <= 1 )
          goto LABEL_21;
LABEL_231:
        v58 = 0;
        while ( 1 )
        {
          v59 = 12 * v58;
          if ( (_BYTE)v6 == byte_1800CCBE0[24 * v58] || (_BYTE)v6 == byte_1800CCBE0[v59 * 2 + 1] )
          {
            v60 = SLOBYTE(word_1800CCBE2[12 * v58]);
            if ( !(unsigned int)sqlite3_strnicmp(v5, *(&off_1800CCBE8 + 3 * v58), v60) )
            {
              v62 = v3 + v60;
              if ( (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v62 + v2)) & 6) == 0 )
                break;
            }
          }
          v58 = (unsigned int)(v58 + 1);
          if ( (unsigned int)v58 >= 5 )
            goto LABEL_244;
          v5 = v68;
        }
        if ( HIBYTE(word_1800CCBE2[v59]) == 5 )
        {
          LOBYTE(v61) = 5;
          jsonBlobAppendNode(v4, v61, 5, "9e999");
        }
        else
        {
          v63 = *(unsigned int *)(v4 + 8);
          if ( (unsigned int)v63 < *(_DWORD *)(v4 + 12) )
          {
            *(_BYTE *)(v63 + *(_QWORD *)v4) = 0;
            ++*(_DWORD *)(v4 + 8);
          }
          else
          {
            jsonBlobExpandAndAppendOneByte(v4, 0);
          }
        }
        *(_BYTE *)(v4 + 49) = 1;
        return (unsigned int)v62;
      }
      goto LABEL_35;
    }
    if ( v6 == 43 )
    {
      *(_BYTE *)(v4 + 49) = 1;
      goto LABEL_21;
    }
    if ( !*v5 )
      return 0;
    switch ( v6 )
    {
      case 9u:
      case 0xAu:
        goto LABEL_13;
      case 0xBu:
      case 0xCu:
LABEL_35:
        v13 = json5Whitespace(v2 + v3, a2);
        if ( !v13 )
          goto LABEL_244;
        v3 += v13;
        *(_BYTE *)(v4 + 49) = 1;
        break;
      case 0xDu:
      case 0x20u:
LABEL_13:
        v3 += strspn((const char *)(v2 + v3 + 1), "\t\n\r ") + 1;
        break;
      default:
        if ( v6 != 34 )
        {
          if ( v6 != 39 )
            goto LABEL_231;
          *(_BYTE *)(v4 + 49) = 1;
        }
        v14 = 7;
        v15 = *v5;
        LODWORD(v11) = v3 + 1;
        while ( 2 )
        {
          while ( 2 )
          {
            if ( *((_BYTE *)qword_1800FEC70 + *(unsigned __int8 *)((unsigned int)v11 + v2)) )
            {
              a2 = (unsigned int)(v11 + 1);
              if ( *((_BYTE *)qword_1800FEC70 + *(unsigned __int8 *)(a2 + v2)) )
              {
                a2 = (unsigned int)(v11 + 2);
                if ( *((_BYTE *)qword_1800FEC70 + *(unsigned __int8 *)(a2 + v2)) )
                {
                  LODWORD(v11) = v11 + 3;
                  continue;
                }
              }
              LODWORD(v11) = a2;
            }
            break;
          }
          v16 = *(_BYTE *)((unsigned int)v11 + v2);
          if ( v16 == v15 )
          {
            LOBYTE(a2) = v14;
            jsonBlobAppendNode(v4, a2, (unsigned int)v11 - v3 - 1, v2 + v3 + 1);
            return (unsigned int)(v11 + 1);
          }
          if ( v16 == 92 )
          {
            v11 = (unsigned int)(v11 + 1);
            v17 = *(char *)(v11 + v2);
            if ( (_BYTE)v17 == 34
              || (unsigned __int8)(v17 - 92) <= 0x18u && (v18 = 21234753, _bittest(&v18, v17 - 92))
              || (_BYTE)v17 == 47
              || (_BYTE)v17 == 117 && (unsigned int)jsonIs4Hex(v2 + (unsigned int)(v11 + 1)) )
            {
              if ( v14 == 7 )
                v14 = 8;
            }
            else
            {
              if ( (unsigned __int8)v17 > 0x30u || (v19 = 0x1008000000400LL, !_bittest64(&v19, v17)) )
              {
                if ( (_BYTE)v17 != 118 )
                {
                  if ( (_BYTE)v17 == 0xE2 )
                  {
                    if ( *(_BYTE *)((unsigned int)(v11 + 1) + v2) != 0x80
                      || *(_BYTE *)((unsigned int)(v11 + 2) + v2) != 0xA8
                      && *(_BYTE *)((unsigned int)(v11 + 2) + v2) != 0xA9 )
                    {
                      goto LABEL_59;
                    }
                  }
                  else
                  {
                    v21 = (unsigned int)(v11 + 1);
                    if ( (_BYTE)v17 != 120 )
                      goto LABEL_65;
                    v21 = (unsigned int)(v11 + 1);
                    if ( (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v21 + v2)) & 8) == 0 )
                      goto LABEL_59;
                    if ( (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v21 + v2 + 1)) & 8) == 0 )
                    {
LABEL_65:
                      if ( (_BYTE)v17 != 13 )
                        goto LABEL_59;
                      if ( *(_BYTE *)(v21 + v2) == 10 )
                        LODWORD(v11) = v21;
                    }
                  }
                }
              }
LABEL_73:
              v14 = 9;
              *(_BYTE *)(v4 + 49) = 1;
            }
          }
          else
          {
            if ( v16 <= 31 )
            {
              if ( !v16 )
                goto LABEL_59;
              goto LABEL_73;
            }
            if ( v16 == 34 )
              v14 = 9;
          }
          LODWORD(v11) = v11 + 1;
          continue;
        }
    }
  }
  if ( v6 > 0x6E )
  {
    if ( v6 == 116 )
    {
      if ( strncmp_0((const char *)(v2 + v3), "true", 4u) )
        goto LABEL_244;
      v11 = v3 + 4;
      if ( (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v11 + v2)) & 6) != 0 )
        goto LABEL_244;
      v43 = *(unsigned int *)(v4 + 8);
      if ( (unsigned int)v43 >= *(_DWORD *)(v4 + 12) )
      {
        LOBYTE(v42) = 1;
        goto LABEL_140;
      }
      *(_BYTE *)(v43 + *(_QWORD *)v4) = 1;
LABEL_142:
      ++*(_DWORD *)(v4 + 8);
      return (unsigned int)v11;
    }
    v12 = v6 - 123;
    if ( v6 == 123 )
    {
      LODWORD(v12) = 12;
      v64 = *(_DWORD *)(v4 + 8);
      jsonBlobAppendNode(v4, v12, *(_DWORD *)(v4 + 32) - v3, 0);
      if ( ++*(_WORD *)(v4 + 44) > 0x3E8u )
        goto LABEL_244;
      LODWORD(v11) = v3 + 1;
      v67 = *(_DWORD *)(v4 + 8);
LABEL_91:
      v24 = *(_DWORD *)(v4 + 8);
      v70 = v24;
      v25 = jsonTranslateTextToBlob(v4, (unsigned int)v11);
      LODWORD(v27) = v25;
      if ( v25 > 0 )
        goto LABEL_108;
      if ( v25 == -2 )
      {
        LODWORD(v11) = *(_DWORD *)(v4 + 40);
        if ( *(_DWORD *)(v4 + 8) != v67 )
          *(_BYTE *)(v4 + 49) = 1;
        goto LABEL_129;
      }
      LODWORD(v11) = json5Whitespace(v2 + (unsigned int)v11, v26) + v11;
      v65 = (unsigned __int8 *)(v2 + (unsigned int)v11);
      v29 = *v65;
      if ( (*((_BYTE *)&qword_1800FB500 + v29) & 0x42) != 0 )
      {
        v69 = 7;
        v30 = v11 + 1;
      }
      else
      {
        if ( (_BYTE)v29 != 92
          || *(_BYTE *)((unsigned int)(v11 + 1) + v2) != 117
          || !(unsigned int)jsonIs4Hex((unsigned int)(v11 + 1) + v2 + 1) )
        {
          goto LABEL_177;
        }
        v69 = 8;
      }
      v31 = v69;
      for ( LODWORD(v27) = v30; ; LODWORD(v27) = v27 + 1 )
      {
        v32 = (unsigned __int8 *)(v2 + (int)v27);
        v33 = *v32;
        if ( (*((_BYTE *)&qword_1800FB500 + v33) & 0x46) == 0 || (unsigned int)json5Whitespace(v2 + (int)v27, v28) )
        {
          if ( (_BYTE)v33 != 92 || v32[1] != 117 || !(unsigned int)jsonIs4Hex(v32 + 2) )
          {
            v4 = a1;
            LOBYTE(v28) = v31;
            jsonBlobAppendNode(a1, v28, (unsigned int)(v27 - v11), v65);
            v24 = v70;
            *(_BYTE *)(a1 + 49) = 1;
LABEL_108:
            if ( *(_BYTE *)(v4 + 47) )
              return 0xFFFFFFFFLL;
            if ( (unsigned __int8)((*(_BYTE *)(v24 + *(_QWORD *)v4) & 0xF) - 7) > 3u )
              goto LABEL_59;
            if ( *(_BYTE *)((unsigned int)v27 + v2) != 58 )
            {
              if ( !*((_BYTE *)&qword_1800FA940 + *(unsigned __int8 *)((unsigned int)v27 + v2)) )
                goto LABEL_114;
              do
              {
                v27 = (unsigned int)(v27 + 1);
                v34 = *(unsigned __int8 *)(v27 + v2);
              }
              while ( *((_BYTE *)&qword_1800FA940 + v34) );
              if ( (_BYTE)v34 != 58 )
              {
LABEL_114:
                v35 = jsonTranslateTextToBlob(v4, (unsigned int)v27);
                if ( v35 == -5 )
                {
                  LODWORD(v27) = *(_DWORD *)(v4 + 40);
                  goto LABEL_116;
                }
                v41 = v35 == -1;
LABEL_134:
                if ( !v41 )
                  *(_DWORD *)(v4 + 40) = v27;
                return 0xFFFFFFFFLL;
              }
            }
LABEL_116:
            LODWORD(v27) = v27 + 1;
            v36 = jsonTranslateTextToBlob(v4, (unsigned int)v27);
            v11 = (unsigned int)v36;
            if ( v36 <= 0 )
            {
              v41 = v36 == -1;
              goto LABEL_134;
            }
            v37 = *(_BYTE *)((unsigned int)v36 + v2);
            if ( v37 != 44 )
            {
              if ( v37 == 125 )
                goto LABEL_129;
              _mm_lfence();
              if ( !*((_BYTE *)&qword_1800FA940 + *(unsigned __int8 *)(v11 + v2)) )
                goto LABEL_122;
              v38 = (unsigned int)strspn((const char *)(v2 + (unsigned int)(v11 + 1)), "\t\n\r ") + (_DWORD)v11 + 1;
              LODWORD(v11) = v38;
              if ( *(_BYTE *)(v38 + v2) != 44 )
              {
                if ( *(_BYTE *)(v38 + v2) != 125 )
                {
LABEL_122:
                  v39 = jsonTranslateTextToBlob(v4, (unsigned int)v11);
                  if ( v39 == -4 )
                  {
                    LODWORD(v11) = *(_DWORD *)(v4 + 40);
                    goto LABEL_124;
                  }
                  if ( v39 != -2 )
                    goto LABEL_59;
                  LODWORD(v11) = *(_DWORD *)(v4 + 40);
                }
LABEL_129:
                v40 = v64;
LABEL_130:
                jsonBlobChangePayloadSize(v4, v40);
                --*(_WORD *)(v4 + 44);
                return (unsigned int)(v11 + 1);
              }
            }
LABEL_124:
            LODWORD(v11) = v11 + 1;
            goto LABEL_91;
          }
          v31 = 8;
        }
      }
    }
    if ( v6 == 125 )
    {
      LODWORD(v23) = -2;
      goto LABEL_245;
    }
    a2 = v6 - 194;
    if ( v6 != 194 )
    {
      a2 = v6 - 225;
      if ( v6 != 225 )
      {
        a2 = v6 - 226;
        if ( v6 != 226 )
        {
          a2 = v6 - 227;
          if ( v6 != 227 && v6 != 239 )
            goto LABEL_231;
        }
      }
    }
    goto LABEL_35;
  }
  if ( v6 == 110 )
  {
    if ( !strncmp_0((const char *)(v2 + v3), "null", 4u) )
    {
      v23 = v3 + 4;
      if ( (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v23 + v2)) & 6) == 0 )
      {
        v57 = *(unsigned int *)(v4 + 8);
        if ( (unsigned int)v57 < *(_DWORD *)(v4 + 12) )
        {
          *(_BYTE *)(v57 + *(_QWORD *)v4) = 0;
          ++*(_DWORD *)(v4 + 8);
        }
        else
        {
          jsonBlobExpandAndAppendOneByte(v4, 0);
        }
        return (unsigned int)v23;
      }
    }
    v5 = v68;
    goto LABEL_231;
  }
  if ( v6 != 53 && v6 != 54 && v6 != 55 && v6 != 56 && v6 != 57 )
  {
    if ( v6 == 58 )
    {
      LODWORD(v23) = -5;
      goto LABEL_245;
    }
    if ( v6 != 91 )
    {
      if ( v6 == 93 )
      {
        LODWORD(v23) = -3;
        goto LABEL_245;
      }
      if ( v6 != 102 )
        goto LABEL_231;
      if ( strncmp_0((const char *)(v2 + v3), "false", 5u) )
        goto LABEL_244;
      v11 = v3 + 5;
      if ( (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v11 + v2)) & 6) != 0 )
        goto LABEL_244;
      v44 = *(unsigned int *)(v4 + 8);
      if ( (unsigned int)v44 < *(_DWORD *)(v4 + 12) )
      {
        *(_BYTE *)(v44 + *(_QWORD *)v4) = 2;
        goto LABEL_142;
      }
      LOBYTE(v42) = 2;
LABEL_140:
      jsonBlobExpandAndAppendOneByte(v4, v42);
      return (unsigned int)v11;
    }
    v45 = *(_DWORD *)(v4 + 8);
    LOBYTE(a2) = 11;
    jsonBlobAppendNode(v4, a2, *(_DWORD *)(v4 + 32) - v3, 0);
    if ( *(_BYTE *)(v4 + 47) )
      return 0xFFFFFFFFLL;
    if ( ++*(_WORD *)(v4 + 44) > 0x3E8u )
      goto LABEL_244;
    v46 = *(_DWORD *)(v4 + 8);
    LODWORD(v11) = v3 + 1;
    LODWORD(v27) = jsonTranslateTextToBlob(v4, v3 + 1);
    if ( (int)v27 <= 0 )
    {
LABEL_171:
      if ( (_DWORD)v27 != -3 )
      {
LABEL_177:
        if ( (_DWORD)v27 != -1 )
          goto LABEL_59;
        return 0xFFFFFFFFLL;
      }
      LODWORD(v11) = *(_DWORD *)(v4 + 40);
      if ( *(_DWORD *)(v4 + 8) != v46 )
        *(_BYTE *)(v4 + 49) = 1;
LABEL_174:
      v40 = v45;
      goto LABEL_130;
    }
    while ( 2 )
    {
      LODWORD(v11) = v27;
      v47 = *(unsigned __int8 *)((unsigned int)v27 + v2);
      if ( (_BYTE)v47 != 44 )
      {
        if ( (_BYTE)v47 == 93 )
          goto LABEL_174;
        if ( !*((_BYTE *)&qword_1800FA940 + v47) )
          goto LABEL_168;
        v11 = (unsigned int)v27 + (unsigned int)strspn((const char *)(v2 + (unsigned int)(v27 + 1)), "\t\n\r ") + 1;
        if ( *(_BYTE *)(v11 + v2) != 44 )
        {
          if ( *(_BYTE *)(v11 + v2) == 93 )
            goto LABEL_174;
LABEL_168:
          v48 = jsonTranslateTextToBlob(v4, (unsigned int)v11);
          if ( v48 != -4 )
          {
            if ( v48 != -3 )
              goto LABEL_59;
            LODWORD(v11) = *(_DWORD *)(v4 + 40);
            goto LABEL_174;
          }
          LODWORD(v11) = *(_DWORD *)(v4 + 40);
        }
      }
      LODWORD(v11) = v11 + 1;
      LODWORD(v27) = jsonTranslateTextToBlob(v4, (unsigned int)v11);
      if ( (int)v27 <= 0 )
        goto LABEL_171;
      continue;
    }
  }
LABEL_21:
  LOBYTE(a2) = 0;
  v7 = 0;
  if ( (char)*v5 > 48 )
    goto LABEL_82;
  v8 = v3 + 1;
  v9 = (unsigned __int8 *)(v2 + v3 + 1);
  if ( *v5 == 48 )
  {
    v10 = *v9;
    if ( (((_BYTE)v10 - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v3 + 2 + v2)) & 8) != 0 )
    {
      *(_BYTE *)(v4 + 49) = 1;
      v11 = v3 + 3;
      LOBYTE(a2) = 1;
      while ( (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v11 + v2)) & 8) != 0 )
        v11 = (unsigned int)(v11 + 1);
LABEL_222:
      if ( *v5 == 43 )
        v3 = v8;
      LOBYTE(a2) = a2 + 3;
      jsonBlobAppendNode(v4, a2, (unsigned int)v11 - v3, v2 + v3);
      return (unsigned int)v11;
    }
    if ( (*((_BYTE *)&qword_1800FB500 + v10) & 4) == 0 )
      goto LABEL_82;
LABEL_196:
    *(_DWORD *)(v4 + 40) = v8;
    return 0xFFFFFFFFLL;
  }
  v49 = *v9;
  if ( (*((_BYTE *)&qword_1800FB500 + v49) & 4) == 0 )
  {
    if ( (((_BYTE)v49 - 73) & 0xDF) == 0 )
    {
      if ( !(unsigned int)sqlite3_strnicmp(v9, "inf", 3) )
      {
        *(_BYTE *)(v4 + 49) = 1;
        v50 = "-9e999";
        LOBYTE(a2) = 5;
        if ( *v68 != 45 )
          v50 = "9e999";
        jsonBlobAppendNode(v4, a2, 6 - (unsigned int)(*v68 != 45), v50);
        return v3 + ((unsigned int)sqlite3_strnicmp(v2 + v3 + 4, "inity", 5) != 0 ? 4 : 9);
      }
      v5 = v68;
    }
    if ( (_BYTE)v49 != 46 )
      goto LABEL_244;
    *(_BYTE *)(v4 + 49) = 1;
    LOBYTE(a2) = 1;
    goto LABEL_82;
  }
  if ( (_BYTE)v49 != 48 )
    goto LABEL_82;
  v51 = *(unsigned __int8 *)(v3 + 2 + v2);
  if ( (*((_BYTE *)&qword_1800FB500 + v51) & 4) != 0 )
    goto LABEL_196;
  if ( (((_BYTE)v51 - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v3 + 3 + v2)) & 8) != 0 )
  {
    *(_BYTE *)(v4 + 49) = 1;
    v11 = v3 + 4;
    LOBYTE(a2) = 1;
    while ( (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v11 + v2)) & 8) != 0 )
      v11 = (unsigned int)(v11 + 1);
    goto LABEL_222;
  }
LABEL_82:
  v8 = v3 + 1;
  LODWORD(v11) = v3 + 1;
  while ( 2 )
  {
    v22 = *(unsigned __int8 *)((unsigned int)v11 + v2);
    if ( (*((_BYTE *)&qword_1800FB500 + v22) & 4) != 0 )
      goto LABEL_216;
    if ( (_BYTE)v22 == 46 )
    {
      if ( (a2 & 2) != 0 )
        goto LABEL_59;
      goto LABEL_215;
    }
    v52 = (unsigned int)(v11 - 1);
    if ( (((_BYTE)v22 - 69) & 0xDF) == 0 )
    {
      if ( *(char *)(v52 + v2) < 48 )
      {
        if ( *(_BYTE *)(v52 + v2) != 46 )
          goto LABEL_59;
        v53 = (unsigned int)(v11 - 2);
        if ( (unsigned int)v53 < v3 || (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v53 + v2)) & 4) == 0 )
          goto LABEL_59;
        *(_BYTE *)(v4 + 49) = 1;
        LOBYTE(a2) = a2 | 1;
      }
      if ( v7 )
        goto LABEL_59;
      v54 = (unsigned int)(v11 + 1);
      v55 = *(_BYTE *)(v54 + v2);
      if ( v55 == 43 || v55 == 45 )
      {
        LODWORD(v11) = v11 + 1;
        v55 = *(_BYTE *)((unsigned int)(v54 + 1) + v2);
      }
      if ( (unsigned __int8)(v55 - 48) > 9u )
        goto LABEL_59;
      v7 = 1;
LABEL_215:
      LOBYTE(a2) = a2 | 2;
LABEL_216:
      LODWORD(v11) = v11 + 1;
      continue;
    }
    break;
  }
  if ( *(char *)(v52 + v2) >= 48 )
    goto LABEL_222;
  if ( *(_BYTE *)(v52 + v2) == 46 )
  {
    v56 = (unsigned int)(v11 - 2);
    if ( (unsigned int)v56 >= v3 && (*((_BYTE *)&qword_1800FB500 + *(unsigned __int8 *)(v56 + v2)) & 4) != 0 )
    {
      *(_BYTE *)(v4 + 49) = 1;
      LOBYTE(a2) = a2 | 1;
      goto LABEL_222;
    }
  }
LABEL_59:
  *(_DWORD *)(v4 + 40) = v11;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800527d4  mov     [rsp+arg_0], rcx
0x1800527d9  push    rbx
0x1800527da  push    rbp
0x1800527db  push    rsi
0x1800527dc  push    rdi
0x1800527dd  push    r12
0x1800527df  push    r13
0x1800527e1  push    r14
0x1800527e3  push    r15
0x1800527e5  sub     rsp, 38h
0x1800527e9  mov     rsi, [rcx+10h]
0x1800527ed  mov     ebp, edx
0x1800527ef  mov     rbx, rcx
0x1800527f2  mov     r12d, 1
0x1800527f8  mov     r8d, 9
0x1800527fe  mov     r11d, ebp
0x180052801  lea     r15, cs:180000000h
0x180052808  add     r11, rsi
0x18005280b  lea     r10d, [r8-5]
0x18005280f  mov     [rsp+78h+arg_10], r11
0x180052817  mov     r13b, 30h ; '0'
0x18005281a  movzx   edi, byte ptr [r11]
0x18005281e  cmp     edi, 34h ; '4'
0x180052821  ja      loc_180052918
0x180052827  jz      loc_1800528C2
0x18005282d  cmp     edi, 2Bh ; '+'
0x180052830  ja      short loc_180052888
0x180052832  jz      loc_180052B1A
0x180052838  mov     ecx, edi
0x18005283a  test    edi, edi
0x18005283c  jz      loc_180052B13
0x180052842  sub     ecx, r8d
0x180052845  jz      short loc_18005286C
0x180052847  sub     ecx, r12d
0x18005284a  jz      short loc_18005286C
0x18005284c  sub     ecx, r12d
0x18005284f  jz      loc_18005295B
0x180052855  sub     ecx, r12d
0x180052858  jz      loc_18005295B
0x18005285e  sub     ecx, r12d
0x180052861  jz      short loc_18005286C
0x180052863  sub     ecx, 13h
0x180052866  jnz     loc_180052976
0x18005286c  lea     ecx, [rbp+1]
0x18005286f  add     rcx, rsi; Str
0x180052872  lea     rdx, Control; "\t\n\r "
0x180052879  call    cs:__imp_strspn
0x18005287f  inc     ebp
0x180052881  add     ebp, eax
0x180052883  jmp     loc_1800527F8
0x180052888  mov     ecx, edi
0x18005288a  sub     ecx, 2Ch ; ','
0x18005288d  jz      loc_180052B73
0x180052893  sub     ecx, r12d
0x180052896  jz      short loc_1800528C2
0x180052898  sub     ecx, r12d
0x18005289b  jz      loc_180052B23
0x1800528a1  sub     ecx, r12d
0x1800528a4  jz      loc_18005295B
0x1800528aa  sub     ecx, r12d
0x1800528ad  jz      short loc_1800528C2
0x1800528af  sub     ecx, r12d
0x1800528b2  jz      short loc_1800528C2
0x1800528b4  sub     ecx, r12d
0x1800528b7  jz      short loc_1800528C2
0x1800528b9  cmp     ecx, r12d
0x1800528bc  jnz     loc_1800532C2
0x1800528c2  xor     dl, dl
0x1800528c4  xor     r14b, r14b
0x1800528c7  cmp     [r11], r13b
0x1800528ca  jg      loc_180052B41
0x1800528d0  lea     r9d, [rbp+1]
0x1800528d4  mov     ecx, r9d
0x1800528d7  add     rcx, rsi
0x1800528da  cmp     [r11], r13b
0x1800528dd  jnz     loc_180053077
0x1800528e3  movzx   r8d, byte ptr [rcx]
0x1800528e7  lea     eax, [r8-58h]
0x1800528eb  test    al, 0DFh
0x1800528ed  jnz     loc_180053064
0x1800528f3  lea     eax, [rbp+2]
0x1800528f6  movzx   eax, byte ptr [rax+rsi]
0x1800528fa  test    byte ptr [rax+r15+0FB500h], 8
0x180052903  jz      loc_180053064
0x180052909  mov     [rbx+31h], r12b
0x18005290d  lea     edi, [rbp+3]
0x180052910  mov     dl, r12b
0x180052913  jmp     loc_180053050
0x180052918  cmp     edi, 6Eh ; 'n'
0x18005291b  jbe     loc_180052E92
0x180052921  mov     edx, edi
0x180052923  sub     edx, 74h ; 't'
0x180052926  jz      loc_180052E3B
0x18005292c  sub     edx, 7
0x18005292f  jz      loc_180052B89
0x180052935  sub     edx, 2
0x180052938  jz      loc_180052B7E
0x18005293e  sub     edx, 45h ; 'E'
0x180052941  jz      short loc_18005295B
0x180052943  sub     edx, 1Fh
0x180052946  jz      short loc_18005295B
0x180052948  sub     edx, r12d
0x18005294b  jz      short loc_18005295B
0x18005294d  sub     edx, r12d
0x180052950  jz      short loc_18005295B
0x180052952  cmp     edx, 0Ch
0x180052955  jnz     loc_1800532C2
0x18005295b  mov     rcx, r11
0x18005295e  call    json5Whitespace
0x180052963  test    eax, eax
0x180052965  jz      loc_180053381
0x18005296b  add     ebp, eax
0x18005296d  mov     [rbx+31h], r12b
0x180052971  jmp     loc_1800527F8
0x180052976  sub     ecx, 2
0x180052979  jz      short loc_180052988
0x18005297b  cmp     ecx, 5
0x18005297e  jnz     loc_1800532C2
0x180052984  mov     [rbx+31h], r12b
0x180052988  mov     r10b, 7
0x18005298b  mov     r12b, [r11]
0x18005298e  lea     r14d, [rbp+1]
0x180052992  mov     edi, r14d
0x180052995  lea     r15, cs:180000000h
0x18005299c  mov     eax, edi
0x18005299e  movzx   ecx, byte ptr [rax+rsi]
0x1800529a2  cmp     byte ptr [rcx+r15+0FEC70h], 0
0x1800529ab  jz      short loc_1800529D7
0x1800529ad  lea     edx, [rdi+1]
0x1800529b0  movzx   ecx, byte ptr [rdx+rsi]
0x1800529b4  cmp     byte ptr [rcx+r15+0FEC70h], 0
0x1800529bd  jz      short loc_1800529D5
0x1800529bf  lea     edx, [rdi+2]
0x1800529c2  movzx   ecx, byte ptr [rdx+rsi]
0x1800529c6  cmp     byte ptr [rcx+r15+0FEC70h], 0
0x1800529cf  jnz     loc_180052A83
0x1800529d5  mov     edi, edx
0x1800529d7  mov     eax, edi
0x1800529d9  mov     cl, [rax+rsi]
0x1800529dc  cmp     cl, r12b
0x1800529df  jz      loc_180052AF4
0x1800529e5  cmp     cl, 5Ch ; '\'
0x1800529e8  jnz     loc_180052AD0
0x1800529ee  inc     edi
0x1800529f0  movsx   r9, byte ptr [rdi+rsi]
0x1800529f5  cmp     r9b, 22h ; '"'
0x1800529f9  jz      loc_180052AC5
0x1800529ff  lea     eax, [r9-5Ch]
0x180052a03  cmp     al, 18h
0x180052a05  ja      short loc_180052A15
0x180052a07  mov     ecx, 1440441h
0x180052a0c  bt      ecx, eax
0x180052a0f  jb      loc_180052AC5
0x180052a15  cmp     r9b, 2Fh ; '/'
0x180052a19  jz      loc_180052AC5
0x180052a1f  cmp     r9b, 75h ; 'u'
0x180052a23  jnz     short loc_180052A3E
0x180052a25  lea     ecx, [rdi+1]
0x180052a28  add     rcx, rsi
0x180052a2b  call    jsonIs4Hex
0x180052a30  mov     r8d, 9
0x180052a36  test    eax, eax
0x180052a38  jnz     loc_180052AC5
0x180052a3e  cmp     r9b, r13b
0x180052a41  ja      short loc_180052A57
0x180052a43  mov     rcx, 1008000000400h
0x180052a4d  bt      rcx, r9
0x180052a51  jb      loc_180052AD9
0x180052a57  cmp     r9b, 76h ; 'v'
0x180052a5b  jz      short loc_180052AD9
0x180052a5d  cmp     r9b, 0E2h
0x180052a61  jnz     short loc_180052A8B
0x180052a63  lea     eax, [rdi+1]
0x180052a66  cmp     byte ptr [rax+rsi], 80h
0x180052a6a  jnz     short loc_180052A78
0x180052a6c  lea     eax, [rdi+2]
0x180052a6f  mov     al, [rax+rsi]
0x180052a72  add     al, 58h ; 'X'
0x180052a74  cmp     al, 1
0x180052a76  jbe     short loc_180052AD9
0x180052a78  mov     [rbx+28h], edi
0x180052a7b  or      eax, 0FFFFFFFFh
0x180052a7e  jmp     loc_18005338B
0x180052a83  add     edi, 3
0x180052a86  jmp     loc_18005299C
0x180052a8b  lea     ecx, [rdi+1]
0x180052a8e  cmp     r9b, 78h ; 'x'
0x180052a92  jnz     short loc_180052AB6
0x180052a94  lea     ecx, [rdi+1]
0x180052a97  movzx   eax, byte ptr [rcx+rsi]
0x180052a9b  test    byte ptr [rax+r15+0FB500h], 8
0x180052aa4  jz      short loc_180052A78
0x180052aa6  movzx   eax, byte ptr [rcx+rsi+1]
0x180052aab  test    byte ptr [rax+r15+0FB500h], 8
0x180052ab4  jnz     short loc_180052AD9
0x180052ab6  cmp     r9b, 0Dh
0x180052aba  jnz     short loc_180052A78
0x180052abc  cmp     byte ptr [rcx+rsi], 0Ah
0x180052ac0  cmovz   edi, ecx
0x180052ac3  jmp     short loc_180052AD9
0x180052ac5  cmp     r10b, 7
0x180052ac9  jnz     short loc_180052AED
0x180052acb  mov     r10b, 8
0x180052ace  jmp     short loc_180052AED
0x180052ad0  cmp     cl, 1Fh
0x180052ad3  jg      short loc_180052AE2
0x180052ad5  test    cl, cl
0x180052ad7  jz      short loc_180052A78
0x180052ad9  mov     r10b, r8b
0x180052adc  mov     byte ptr [rbx+31h], 1
0x180052ae0  jmp     short loc_180052AED
0x180052ae2  cmp     cl, 22h ; '"'
0x180052ae5  movzx   r10d, r10b
0x180052ae9  cmovz   r10d, r8d
0x180052aed  inc     edi
0x180052aef  jmp     loc_18005299C
0x180052af4  mov     r8d, edi
0x180052af7  mov     r9d, r14d
0x180052afa  sub     r8d, ebp
0x180052afd  add     r9, rsi
0x180052b00  dec     r8d
0x180052b03  mov     dl, r10b
0x180052b06  mov     rcx, rbx
0x180052b09  call    jsonBlobAppendNode
0x180052b0e  jmp     loc_180052E1D
0x180052b13  xor     eax, eax
0x180052b15  jmp     loc_18005338B
0x180052b1a  mov     [rbx+31h], r12b
0x180052b1e  jmp     loc_1800528C2
0x180052b23  lea     eax, [rbp+1]
0x180052b26  movzx   eax, byte ptr [rax+rsi]
0x180052b2a  test    [rax+r15+0FB500h], r10b
0x180052b32  jz      loc_180053381
0x180052b38  mov     [rbx+31h], r12b
0x180052b3c  mov     dl, 3
0x180052b3e  xor     r14b, r14b
0x180052b41  lea     r9d, [rbp+1]
0x180052b45  mov     edi, r9d
0x180052b48  mov     eax, edi
0x180052b4a  movzx   ecx, byte ptr [rax+rsi]
0x180052b4e  test    [rcx+r15+0FB500h], r10b
0x180052b56  jnz     loc_180053209
0x180052b5c  cmp     cl, 2Eh ; '.'
0x180052b5f  jnz     loc_180053193
0x180052b65  test    dl, 2
0x180052b68  jnz     loc_180052A78
0x180052b6e  jmp     loc_180053206
0x180052b73  mov     r14d, 0FFFFFFFCh
0x180052b79  jmp     loc_180053385
0x180052b7e  mov     r14d, 0FFFFFFFEh
0x180052b84  jmp     loc_180053385
0x180052b89  mov     r8d, [rbx+20h]
0x180052b8d  xor     r9d, r9d
0x180052b90  mov     eax, [rbx+8]
0x180052b93  sub     r8d, ebp
0x180052b96  mov     dl, 0Ch
0x180052b98  mov     [rsp+78h+var_58], eax
0x180052b9c  mov     rcx, rbx
0x180052b9f  call    jsonBlobAppendNode
0x180052ba4  add     [rbx+2Ch], r12w
0x180052ba9  mov     eax, 3E8h
0x180052bae  cmp     [rbx+2Ch], ax
0x180052bb2  ja      loc_180053381
0x180052bb8  mov     eax, [rbx+8]
0x180052bbb  lea     edi, [rbp+1]
0x180052bbe  mov     [rsp+78h+arg_8], eax
0x180052bc5  lea     r15, cs:180000000h
0x180052bcc  mov     r14d, 0FFFFFFFCh
0x180052bd2  mov     r13d, r12d
0x180052bd5  mov     r12d, [rbx+8]
0x180052bd9  mov     edx, edi
0x180052bdb  mov     rcx, rbx
0x180052bde  mov     [rsp+78h+arg_18], r12d
0x180052be6  call    jsonTranslateTextToBlob
0x180052beb  mov     ebp, eax
0x180052bed  test    eax, eax
0x180052bef  jg      loc_180052CF1
0x180052bf5  cmp     eax, 0FFFFFFFEh
0x180052bf8  jz      loc_180052DD9
0x180052bfe  mov     ecx, edi
0x180052c00  add     rcx, rsi
0x180052c03  call    json5Whitespace
0x180052c08  add     edi, eax
0x180052c0a  mov     eax, edi
0x180052c0c  add     rax, rsi
0x180052c0f  mov     [rsp+78h+var_50], rax
0x180052c14  movzx   eax, byte ptr [rax]
0x180052c17  test    byte ptr [rax+r15+0FB500h], 42h
0x180052c20  jnz     short loc_180052C5D
0x180052c22  cmp     al, 5Ch ; '\'
0x180052c24  jnz     loc_180053034
0x180052c2a  lea     r9d, [rdi+1]
0x180052c2e  cmp     byte ptr [r9+rsi], 75h ; 'u'
0x180052c33  mov     eax, r9d
0x180052c36  jnz     loc_180053034
0x180052c3c  lea     rcx, [rsi+1]
0x180052c40  add     rcx, rax
0x180052c43  call    jsonIs4Hex
0x180052c48  test    eax, eax
0x180052c4a  jz      loc_180053034
  ... truncated ...
```
