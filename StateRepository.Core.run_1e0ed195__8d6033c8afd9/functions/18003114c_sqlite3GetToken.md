# sqlite3GetToken

- ea: `0x18003114c`
- end: `0x180031922`
- name: `sqlite3GetToken`
- size: `2006`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180030354`
- `0x180030d98`
- `0x18006f124`
- `0x18008dfb0`

## callees

- `0x180030cb4`
- `0x18003114c`

## pseudocode

```c
__int64 __fastcall sqlite3GetToken(unsigned __int8 *a1, int *a2)
{
  __int64 v2; // rdi
  int v3; // ebx
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  int i; // r11d
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  __int64 v12; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  unsigned int v26; // r8d
  unsigned int v27; // r8d
  unsigned int v28; // r8d
  bool v29; // zf
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  __int64 v32; // rax
  int v33; // r9d
  unsigned __int8 v34; // cl
  int j; // edx
  unsigned int v36; // r8d
  unsigned int v37; // r8d
  __int64 v38; // rcx
  unsigned __int8 v39; // al
  int v40; // eax
  unsigned __int8 *v41; // rax
  unsigned int v42; // ecx
  int v43; // edx
  __int64 v44; // r11
  __int64 v45; // rdx
  __int64 v46; // rax
  int v47; // edx
  unsigned __int8 v48; // cl
  unsigned __int8 v49; // al
  unsigned __int8 v50; // al
  int v51; // eax
  char v52; // al
  int v53; // edx
  int v54; // ecx
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx

  v2 = *a1;
  v3 = 0;
  v6 = *((unsigned __int8 *)qword_1800AA670 + v2);
  if ( v6 > 0xF )
  {
    if ( (unsigned __int8)v6 > 0x17u )
    {
      v13 = v6 - 24;
      if ( !v13 )
      {
        *a2 = 103;
        return 1;
      }
      v14 = v13 - 1;
      if ( !v14 )
      {
        *a2 = 115;
        return 1;
      }
      v15 = v14 - 1;
      if ( !v15 )
      {
        if ( (*((_BYTE *)&qword_18009E630 + a1[1]) & 4) != 0 )
          goto LABEL_25;
        *a2 = 142;
        return 1;
      }
      v21 = v15 - 1;
      if ( !v21 )
        goto LABEL_12;
      v22 = v21 - 2;
      if ( !v22 )
      {
        v20 = 0;
LABEL_48:
        *a2 = 185;
        return v20;
      }
      if ( v22 == 1 )
      {
        if ( a1[1] == 0xBB && a1[2] == 0xBF )
        {
          *a2 = 184;
          return 3;
        }
        goto LABEL_12;
      }
    }
    else
    {
      if ( (_BYTE)v6 == 23 )
      {
        *a2 = 25;
        return 1;
      }
      v16 = v6 - 16;
      if ( !v16 )
      {
        if ( a1[1] == 42 && a1[2] )
        {
          v40 = a1[2];
          for ( i = 3; ; ++i )
          {
            if ( v40 == 42 )
            {
              v41 = &a1[i];
              if ( *v41 == 47 )
              {
                ++i;
LABEL_166:
                *a2 = 184;
                return (unsigned int)i;
              }
            }
            else
            {
              v41 = &a1[i];
            }
            v40 = *v41;
            if ( !v40 )
              goto LABEL_166;
          }
        }
        *a2 = 110;
        return 1;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        *a2 = 22;
        return 1;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        *a2 = 23;
        return 1;
      }
      v19 = v18 - 1;
      if ( !v19 )
      {
        v20 = 1;
        *a2 = 1;
        return v20;
      }
      v36 = v19 - 1;
      if ( !v36 )
      {
        *a2 = 107;
        return 1;
      }
      v37 = v36 - 1;
      if ( !v37 )
      {
        *a2 = 109;
        return 1;
      }
      if ( v37 == 1 )
      {
        *a2 = 111;
        return 1;
      }
    }
    goto LABEL_65;
  }
  if ( v6 == 15 )
  {
    if ( a1[1] == 61 )
      goto LABEL_160;
LABEL_65:
    v20 = 1;
    goto LABEL_48;
  }
  if ( v6 == 7 )
  {
    for ( i = 1; (*((_BYTE *)&qword_18009E630 + a1[i]) & 1) != 0; ++i )
      ;
    *a2 = 184;
    return (unsigned int)i;
  }
  if ( v6 > 7 )
  {
    v23 = v6 - 8;
    if ( v23 )
    {
      v24 = v23 - 1;
      if ( !v24 )
      {
        v53 = *a1;
        i = 1;
        if ( (_DWORD)v2 != 93 )
        {
          do
          {
            v53 = a1[i];
            if ( !(_BYTE)v53 )
              break;
            ++i;
          }
          while ( v53 != 93 );
        }
        v54 = 60;
        if ( v53 != 93 )
          v54 = 185;
        *a2 = v54;
        return (unsigned int)i;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        if ( a1[1] == 124 )
        {
          *a2 = 112;
          return 2;
        }
        *a2 = 104;
        return 1;
      }
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 )
          {
            if ( v28 == 1 )
            {
              v29 = a1[1] == 61;
              *a2 = 54;
              LOBYTE(v3) = v29;
              return (unsigned int)(v3 + 1);
            }
            goto LABEL_65;
          }
          v49 = a1[1];
          if ( v49 == 61 )
          {
            *a2 = 58;
            return 2;
          }
          if ( v49 == 62 )
          {
            *a2 = 106;
            return 2;
          }
          *a2 = 55;
          return 1;
        }
        v39 = a1[1];
        if ( v39 == 61 )
        {
          *a2 = 56;
          return 2;
        }
        if ( v39 != 62 )
        {
          if ( v39 == 60 )
          {
            *a2 = 105;
            return 2;
          }
          *a2 = 57;
          return 1;
        }
LABEL_160:
        *a2 = 53;
        return 2;
      }
      v50 = a1[1];
      if ( v50 != 45 )
      {
        if ( v50 == 62 )
        {
          v52 = a1[2] - 62;
          *a2 = 113;
          return 3 - (unsigned int)(v52 != 0);
        }
        *a2 = 108;
        return 1;
      }
      v51 = a1[2];
      for ( j = 2; a1[j]; v51 = a1[++j] )
      {
        if ( v51 == 10 )
          break;
      }
      *a2 = 184;
      return (unsigned int)j;
    }
    v34 = a1[1];
    j = 1;
    while ( v34 )
    {
      if ( v34 == (_BYTE)v2 )
      {
        if ( a1[j + 1] != (_BYTE)v2 )
          break;
        ++j;
      }
      v34 = a1[++j];
    }
    if ( v34 == 39 )
    {
      *a2 = 118;
    }
    else
    {
      if ( !v34 )
      {
        *a2 = 185;
        return (unsigned int)j;
      }
      *a2 = 60;
    }
    return (unsigned int)(j + 1);
  }
  if ( !*((_BYTE *)qword_1800AA670 + v2) )
  {
    if ( a1[1] == 39 )
    {
      v46 = a1[2];
      *a2 = 155;
      v47 = 2;
      if ( (*((_BYTE *)&qword_18009E630 + v46) & 8) != 0 )
      {
        do
          ++v47;
        while ( (*((_BYTE *)&qword_18009E630 + a1[v47]) & 8) != 0 );
      }
      v48 = a1[v47];
      if ( v48 != 39 || (v47 & 1) != 0 )
      {
        *a2 = 185;
        if ( v48 )
        {
          do
          {
            if ( a1[v47] == 39 )
              break;
            ++v47;
          }
          while ( a1[v47] );
        }
      }
      v42 = v47 + 1;
      if ( !a1[v47] )
        return (unsigned int)v47;
      return v42;
    }
LABEL_12:
    i = 1;
    goto LABEL_13;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v10 = v7 - 1;
    if ( !v10 )
      goto LABEL_12;
    v11 = v10 - 1;
    if ( !v11 )
    {
LABEL_25:
      *a2 = 156;
      if ( (_BYTE)v2 == 48 && ((a1[1] - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_18009E630 + a1[2]) & 8) != 0 )
      {
        for ( i = 3; ; ++i )
        {
          v38 = a1[i];
          if ( (*((_BYTE *)&qword_18009E630 + v38) & 8) == 0 )
          {
            if ( (_BYTE)v38 != 95 )
              goto LABEL_31;
            *a2 = 183;
          }
        }
      }
      for ( i = 0; ; ++i )
      {
        v12 = a1[i];
        if ( (*((_BYTE *)&qword_18009E630 + v12) & 4) == 0 )
        {
          if ( (_BYTE)v12 != 95 )
          {
            if ( (_BYTE)v12 == 46 )
            {
              if ( *a2 == 156 )
                *a2 = 154;
              while ( 1 )
              {
                do
                  v55 = a1[++i];
                while ( (*((_BYTE *)&qword_18009E630 + v55) & 4) != 0 );
                if ( (_BYTE)v55 != 95 )
                  break;
                *a2 = 183;
              }
            }
            if ( ((a1[i] - 69) & 0xDF) == 0 )
            {
              v56 = a1[i + 1];
              if ( (*((_BYTE *)&qword_18009E630 + v56) & 4) != 0
                || (((_BYTE)v56 - 43) & 0xFD) == 0 && (*((_BYTE *)&qword_18009E630 + a1[i + 2]) & 4) != 0 )
              {
                if ( *a2 == 156 )
                  *a2 = 154;
                for ( i += 2; ; ++i )
                {
                  v57 = a1[i];
                  if ( (*((_BYTE *)&qword_18009E630 + v57) & 4) == 0 )
                  {
                    if ( (_BYTE)v57 != 95 )
                      break;
                    *a2 = 183;
                  }
                }
              }
            }
LABEL_31:
            if ( (*((_BYTE *)&qword_18009E630 + a1[i]) & 0x46) != 0 )
            {
              *a2 = 185;
              do
                ++i;
              while ( (*((_BYTE *)&qword_18009E630 + a1[i]) & 0x46) != 0 );
            }
            return (unsigned int)i;
          }
          *a2 = 183;
        }
      }
    }
    v30 = v11 - 1;
    if ( !v30 || (v31 = v30 - 1) == 0 )
    {
      *a2 = 157;
      v42 = 1;
      v43 = 0;
      while ( 1 )
      {
        v44 = a1[v42];
        if ( !(_BYTE)v44 )
          break;
        if ( (*((_BYTE *)&qword_18009E630 + v44) & 0x46) != 0 )
        {
          ++v43;
        }
        else
        {
          if ( (_BYTE)v44 == 40 && v43 > 0 )
          {
            do
            {
              v45 = a1[++v42];
              if ( !(_BYTE)v45 )
                goto LABEL_118;
            }
            while ( (*((_BYTE *)&qword_18009E630 + v45) & 1) == 0 && (_BYTE)v45 != 41 );
            if ( (_BYTE)v45 == 41 )
              return ++v42;
LABEL_118:
            *a2 = 185;
            return v42;
          }
          if ( (_BYTE)v44 != 58 || a1[v42 + 1] != 58 )
            break;
          ++v42;
        }
        ++v42;
      }
      if ( v43 )
        return v42;
      goto LABEL_118;
    }
    if ( v31 == 1 )
    {
      v32 = a1[1];
      v33 = 1;
      *a2 = 157;
      if ( (*((_BYTE *)&qword_18009E630 + v32) & 4) != 0 )
      {
        do
          ++v33;
        while ( (*((_BYTE *)&qword_18009E630 + a1[v33]) & 4) != 0 );
      }
      return (unsigned int)v33;
    }
    goto LABEL_65;
  }
  if ( *((_BYTE *)qword_1800AA670 + a1[1]) > 2u )
    goto LABEL_12;
  for ( i = 2; *((_BYTE *)qword_1800AA670 + a1[i]) <= 2u; ++i )
    ;
  if ( (*((_BYTE *)&qword_18009E630 + a1[i]) & 0x46) != 0 )
  {
    do
    {
      ++i;
LABEL_13:
      ;
    }
    while ( (*((_BYTE *)&qword_18009E630 + a1[i]) & 0x46) != 0 );
    *a2 = 60;
    return (unsigned int)i;
  }
  *a2 = 60;
  return keywordCode(a1, (unsigned int)i, a2);
}

```

## disassembly

```asm
0x18003114c  mov     [rsp+arg_0], rbx
0x180031151  mov     [rsp+arg_8], rbp
0x180031156  push    rdi
0x180031157  sub     rsp, 20h
0x18003115b  movzx   edi, byte ptr [rcx]
0x18003115e  lea     rbp, cs:180000000h
0x180031165  xor     ebx, ebx
0x180031167  mov     r9, rdx
0x18003116a  mov     r10, rcx
0x18003116d  movzx   r8d, byte ptr [rdi+rbp+0AA670h]
0x180031176  cmp     r8d, 0Fh
0x18003117a  ja      loc_18003123D
0x180031180  jz      loc_180031458
0x180031186  cmp     r8d, 7
0x18003118a  jz      loc_18003125A
0x180031190  ja      loc_1800313BB
0x180031196  test    r8d, r8d
0x180031199  jz      loc_180031664
0x18003119f  sub     r8d, 1
0x1800311a3  jnz     loc_180031283
0x1800311a9  movzx   eax, byte ptr [rcx+1]
0x1800311ad  lea     edx, [rbx+2]
0x1800311b0  lea     r8d, [rbx+1]
0x1800311b4  cmp     [rax+rbp+0AA670h], dl
0x1800311bb  ja      short loc_18003120E
0x1800311bd  movzx   eax, byte ptr [rcx+2]
0x1800311c1  mov     r11d, edx
0x1800311c4  cmp     [rax+rbp+0AA670h], dl
0x1800311cb  ja      short loc_1800311E1
0x1800311cd  add     r11d, r8d
0x1800311d0  movsxd  rax, r11d
0x1800311d3  movzx   ecx, byte ptr [rax+r10]
0x1800311d8  cmp     [rcx+rbp+0AA670h], dl
0x1800311df  jbe     short loc_1800311CD
0x1800311e1  movsxd  rax, r11d
0x1800311e4  movzx   ecx, byte ptr [rax+r10]
0x1800311e9  test    byte ptr [rcx+rbp+9E630h], 46h
0x1800311f1  jnz     loc_18003127E
0x1800311f7  mov     r8, r9
0x1800311fa  mov     dword ptr [r9], 3Ch ; '<'
0x180031201  mov     edx, r11d
0x180031204  mov     rcx, r10
0x180031207  call    keywordCode
0x18003120c  jmp     short loc_18003122D
0x18003120e  mov     r11d, r8d
0x180031211  movsxd  rax, r11d
0x180031214  movzx   ecx, byte ptr [rax+r10]
0x180031219  test    byte ptr [rcx+rbp+9E630h], 46h
0x180031221  jnz     short loc_18003127E
0x180031223  mov     dword ptr [r9], 3Ch ; '<'
0x18003122a  mov     eax, r11d
0x18003122d  mov     rbx, [rsp+28h+arg_0]
0x180031232  mov     rbp, [rsp+28h+arg_8]
0x180031237  add     rsp, 20h
0x18003123b  pop     rdi
0x18003123c  retn
0x18003123d  cmp     r8b, 17h
0x180031241  ja      loc_18003132C
0x180031247  jnz     loc_180031363
0x18003124d  mov     dword ptr [rdx], 19h
0x180031253  mov     eax, 1
0x180031258  jmp     short loc_18003122D
0x18003125a  movzx   eax, byte ptr [rcx+1]
0x18003125e  mov     r8d, 1
0x180031264  mov     r11d, r8d
0x180031267  test    [rax+rbp+9E630h], r8b
0x18003126f  jnz     loc_1800316D7
0x180031275  mov     dword ptr [r9], 0B8h
0x18003127c  jmp     short loc_18003122A
0x18003127e  add     r11d, r8d
0x180031281  jmp     short loc_180031211
0x180031283  sub     r8d, 1
0x180031287  jz      loc_180031879
0x18003128d  sub     r8d, 1
0x180031291  jnz     loc_180031414
0x180031297  mov     edx, 9Ch
0x18003129c  mov     [r9], edx
0x18003129f  cmp     dil, 30h ; '0'
0x1800312a3  jz      loc_180031508
0x1800312a9  mov     r11d, ebx
0x1800312ac  mov     r8d, 1
0x1800312b2  mov     ebx, 0B7h
0x1800312b7  movsxd  rax, r11d
0x1800312ba  movzx   ecx, byte ptr [rax+r10]
0x1800312bf  test    byte ptr [rcx+rbp+9E630h], 4
0x1800312c7  jnz     loc_180031887
0x1800312cd  cmp     cl, 5Fh ; '_'
0x1800312d0  jz      loc_180031884
0x1800312d6  mov     edi, 9Ah
0x1800312db  cmp     cl, 2Eh ; '.'
0x1800312de  jz      loc_18003188F
0x1800312e4  movsxd  rcx, r11d
0x1800312e7  mov     al, [rcx+r10]
0x1800312eb  sub     al, 45h ; 'E'
0x1800312ed  test    al, 0DFh
0x1800312ef  jz      loc_1800318BA
0x1800312f5  movsxd  rax, r11d
0x1800312f8  movzx   ecx, byte ptr [rax+r10]
0x1800312fd  test    byte ptr [rcx+rbp+9E630h], 46h
0x180031305  jz      loc_18003122A
0x18003130b  mov     dword ptr [r9], 0B9h
0x180031312  add     r11d, r8d
0x180031315  movsxd  rcx, r11d
0x180031318  movzx   edx, byte ptr [rcx+r10]
0x18003131d  test    byte ptr [rdx+rbp+9E630h], 46h
0x180031325  jnz     short loc_180031312
0x180031327  jmp     loc_18003122A
0x18003132c  sub     r8d, 18h
0x180031330  jz      loc_1800314EE
0x180031336  sub     r8d, 1
0x18003133a  jz      loc_180031917
0x180031340  sub     r8d, 1
0x180031344  jnz     short loc_180031396
0x180031346  movzx   eax, byte ptr [rcx+1]
0x18003134a  test    byte ptr [rax+rbp+9E630h], 4
0x180031352  jnz     loc_180031297
0x180031358  mov     dword ptr [rdx], 8Eh
0x18003135e  jmp     loc_180031253
0x180031363  sub     r8d, 10h
0x180031367  jz      loc_180031589
0x18003136d  sub     r8d, 1
0x180031371  jz      loc_18003144D
0x180031377  sub     r8d, 1
0x18003137b  jz      loc_1800314E3
0x180031381  sub     r8d, 1
0x180031385  jnz     loc_1800314C4
0x18003138b  mov     r8d, 1
0x180031391  mov     [rdx], r8d
0x180031394  jmp     short loc_1800313B3
0x180031396  sub     r8d, 1
0x18003139a  jz      loc_180031879
0x1800313a0  sub     r8d, 2
0x1800313a4  jnz     loc_180031854
0x1800313aa  mov     r8d, ebx
0x1800313ad  mov     dword ptr [rdx], 0B9h
0x1800313b3  mov     eax, r8d
0x1800313b6  jmp     loc_18003122D
0x1800313bb  sub     r8d, 8
0x1800313bf  jz      loc_180031484
0x1800313c5  sub     r8d, 1
0x1800313c9  jz      loc_1800317BE
0x1800313cf  sub     r8d, 1
0x1800313d3  jz      loc_1800317A2
0x1800313d9  sub     r8d, 1
0x1800313dd  jz      loc_180031744
0x1800313e3  sub     r8d, 1
0x1800313e7  jz      loc_180031558
0x1800313ed  sub     r8d, 1
0x1800313f1  jz      loc_1800316F1
0x1800313f7  cmp     r8d, 1
0x1800313fb  jnz     short loc_180031462
0x1800313fd  cmp     byte ptr [rcx+1], 3Dh ; '='
0x180031401  mov     eax, r8d
0x180031404  mov     dword ptr [rdx], 36h ; '6'
0x18003140a  setz    bl
0x18003140d  add     eax, ebx
0x18003140f  jmp     loc_18003122D
0x180031414  sub     r8d, 1
0x180031418  jz      loc_1800315CA
0x18003141e  sub     r8d, 1
0x180031422  jz      loc_1800315CA
0x180031428  cmp     r8d, 1
0x18003142c  jnz     short loc_180031462
0x18003142e  movzx   eax, byte ptr [rcx+1]
0x180031432  mov     r9d, r8d
0x180031435  mov     dword ptr [rdx], 9Dh
0x18003143b  test    byte ptr [rax+rbp+9E630h], 4
0x180031443  jnz     short loc_18003146D
0x180031445  mov     eax, r9d
0x180031448  jmp     loc_18003122D
0x18003144d  mov     dword ptr [rdx], 16h
0x180031453  jmp     loc_180031253
0x180031458  cmp     byte ptr [rcx+1], 3Dh ; '='
0x18003145c  jz      loc_180031803
0x180031462  mov     r8d, 1
0x180031468  jmp     loc_1800313AD
0x18003146d  add     r9d, r8d
0x180031470  movsxd  rcx, r9d
0x180031473  movzx   edx, byte ptr [rcx+r10]
0x180031478  test    byte ptr [rdx+rbp+9E630h], 4
0x180031480  jz      short loc_180031445
0x180031482  jmp     short loc_18003146D
0x180031484  mov     cl, [rcx+1]
0x180031487  mov     r8d, 1
0x18003148d  mov     edx, r8d
0x180031490  jmp     short loc_1800314A5
0x180031492  cmp     cl, dil
0x180031495  jz      loc_180031573
0x18003149b  add     edx, r8d
0x18003149e  movsxd  rax, edx
0x1800314a1  mov     cl, [rax+r10]
0x1800314a5  test    cl, cl
0x1800314a7  jnz     short loc_180031492
0x1800314a9  cmp     cl, 27h ; '''
0x1800314ac  jz      loc_1800317F7
0x1800314b2  test    cl, cl
0x1800314b4  jnz     short loc_1800314F9
0x1800314b6  mov     dword ptr [r9], 0B9h
0x1800314bd  mov     eax, edx
0x1800314bf  jmp     loc_18003122D
0x1800314c4  sub     r8d, 1
0x1800314c8  jz      loc_180031823
0x1800314ce  sub     r8d, 1
0x1800314d2  jnz     loc_18003180E
0x1800314d8  mov     dword ptr [rdx], 6Dh ; 'm'
0x1800314de  jmp     loc_180031253
0x1800314e3  mov     dword ptr [rdx], 17h
0x1800314e9  jmp     loc_180031253
0x1800314ee  mov     dword ptr [rdx], 67h ; 'g'
0x1800314f4  jmp     loc_180031253
0x1800314f9  mov     dword ptr [r9], 3Ch ; '<'
0x180031500  lea     eax, [rdx+1]
0x180031503  jmp     loc_18003122D
0x180031508  mov     al, [rcx+1]
0x18003150b  sub     al, 58h ; 'X'
0x18003150d  test    al, 0DFh
0x18003150f  jnz     loc_1800312A9
0x180031515  movzx   eax, byte ptr [rcx+2]
0x180031519  test    byte ptr [rax+rbp+9E630h], 8
0x180031521  jz      loc_1800312A9
0x180031527  mov     r11d, 3
0x18003152d  lea     r8d, [r11-2]
0x180031531  movsxd  rax, r11d
0x180031534  movzx   ecx, byte ptr [rax+r10]
0x180031539  test    byte ptr [rcx+rbp+9E630h], 8
0x180031541  jnz     short loc_180031553
0x180031543  cmp     cl, 5Fh ; '_'
0x180031546  jnz     loc_1800312F5
0x18003154c  mov     dword ptr [r9], 0B7h
0x180031553  add     r11d, r8d
0x180031556  jmp     short loc_180031531
0x180031558  mov     al, [rcx+1]
0x18003155b  cmp     al, 3Dh ; '='
0x18003155d  jnz     loc_18003171D
0x180031563  mov     dword ptr [rdx], 38h ; '8'
0x180031569  mov     eax, 2
0x18003156e  jmp     loc_18003122D
0x180031573  movsxd  rax, edx
0x180031576  cmp     [rax+r10+1], dil
0x18003157b  jnz     loc_1800314A9
0x180031581  add     edx, r8d
0x180031584  jmp     loc_18003149B
0x180031589  cmp     byte ptr [rcx+1], 2Ah ; '*'
0x18003158d  jnz     loc_180031849
0x180031593  cmp     [rcx+2], bl
0x180031596  jz      loc_180031849
0x18003159c  movzx   eax, byte ptr [rcx+2]
0x1800315a0  mov     r11d, 3
0x1800315a6  lea     r8d, [r11-2]
0x1800315aa  movsxd  rcx, r11d
0x1800315ad  cmp     eax, 2Ah ; '*'
0x1800315b0  jz      loc_18003182E
0x1800315b6  lea     rax, [rcx+r10]
0x1800315ba  movzx   eax, byte ptr [rax]
0x1800315bd  test    eax, eax
0x1800315bf  jz      loc_18003183E
0x1800315c5  add     r11d, r8d
0x1800315c8  jmp     short loc_1800315AA
0x1800315ca  mov     r8d, 1
0x1800315d0  mov     dword ptr [r9], 9Dh
0x1800315d7  mov     ecx, r8d
0x1800315da  mov     edx, ebx
0x1800315dc  movsxd  rax, ecx
0x1800315df  movzx   r11d, byte ptr [rax+r10]
0x1800315e4  test    r11b, r11b
0x1800315e7  jz      short loc_180031643
0x1800315e9  test    byte ptr [r11+rbp+9E630h], 46h
0x1800315f2  jz      short loc_1800315F9
0x1800315f4  add     edx, r8d
0x1800315f7  jmp     short loc_180031616
0x1800315f9  cmp     r11b, 28h ; '('
0x1800315fd  jnz     short loc_180031603
0x1800315ff  test    edx, edx
0x180031601  jg      short loc_18003161B
0x180031603  cmp     r11b, 3Ah ; ':'
0x180031607  jnz     short loc_180031643
0x180031609  movsxd  rax, ecx
0x18003160c  cmp     [rax+r10+1], r11b
0x180031611  jnz     short loc_180031643
0x180031613  add     ecx, r8d
0x180031616  add     ecx, r8d
0x180031619  jmp     short loc_1800315DC
0x18003161b  add     ecx, r8d
0x18003161e  movsxd  rax, ecx
0x180031621  movzx   edx, byte ptr [rax+r10]
0x180031626  test    dl, dl
0x180031628  jz      short loc_180031647
0x18003162a  test    [rdx+rbp+9E630h], r8b
0x180031632  jnz     short loc_180031639
0x180031634  cmp     dl, 29h ; ')'
0x180031637  jnz     short loc_18003161B
0x180031639  cmp     dl, 29h ; ')'
0x18003163c  jnz     short loc_180031647
0x18003163e  add     ecx, r8d
0x180031641  jmp     short loc_18003165D
0x180031643  test    edx, edx
0x180031645  jnz     short loc_18003165D
0x180031647  mov     dword ptr [r9], 0B9h
0x18003164e  jmp     short loc_18003165D
0x180031650  movsxd  rax, edx
  ... truncated ...
```
