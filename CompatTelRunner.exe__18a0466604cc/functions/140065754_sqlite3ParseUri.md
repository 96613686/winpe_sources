# sqlite3ParseUri

- ea: `0x140065754`
- end: `0x140065c7f`
- name: `sqlite3ParseUri`
- size: `1323`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001d100`
- `0x14003bbec`

## callees

- `0x140065754`
- `0x14008ad20`
- `0x14008b820`
- `0x14008b8d0`
- `0x14008fc10`
- `0x1400a72fc`
- `0x1400a7308`

## string_xrefs

- `0x140065867`: `invalid uri authority: %.*s`
- `0x140065aa6`: `cache`
- `0x140065ad0`: `access`

## pseudocode

```c
__int64 __fastcall sqlite3ParseUri(
        const char *a1,
        const char *a2,
        unsigned int *a3,
        __int64 *a4,
        _QWORD *a5,
        __int64 *a6)
{
  unsigned int v6; // r12d
  const char *v8; // r13
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  _DWORD *v14; // rdi
  int v15; // r12d
  char *v16; // rdi
  int v17; // ecx
  const char *v18; // r8
  unsigned int v19; // r15d
  __int64 v20; // rax
  int v21; // r8d
  int v22; // r9d
  int v23; // edx
  __int64 v24; // r11
  __int64 v25; // rbx
  __int64 v26; // r10
  char v27; // dl
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  char *v32; // rcx
  __int64 v33; // rdx
  int v34; // edx
  char *v35; // r14
  unsigned int v36; // ebp
  __int64 v37; // rbp
  char **v38; // rsi
  const char *v39; // r12
  int v40; // ebx
  char v41; // al
  int v42; // ecx
  bool v43; // zf
  __int64 v44; // r13
  char *v45; // rdx
  int v46; // eax
  __int64 v47; // rax
  int v48; // ecx
  int v49; // ebx
  __int64 v50; // rax
  __int64 result; // rax
  _DWORD *v52; // rdi
  int v53; // [rsp+20h] [rbp-58h]
  int v54; // [rsp+24h] [rbp-54h]
  const char *v55; // [rsp+80h] [rbp+8h]
  unsigned int v56; // [rsp+88h] [rbp+10h]

  v55 = a1;
  v6 = *a3;
  v8 = a1;
  if ( a2 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v9 = v10 & 0x3FFFFFFF;
  }
  else
  {
    v9 = 0;
  }
  if ( (v6 & 0x40) == 0 && !byte_1400C84B6 || (unsigned int)v9 < 5 || *(_DWORD *)a2 != 1701603686 || a2[4] != 58 )
  {
    v52 = (_DWORD *)sqlite3_malloc64((unsigned int)(v9 + 8));
    if ( v52 )
    {
      *v52 = 0;
      v16 = (char *)(v52 + 1);
      if ( (_DWORD)v9 )
        memcpy_0(v16, a2, (unsigned int)v9);
      *(_DWORD *)&v16[v9] = 0;
      v56 = v6 & 0xFFFFFFBF;
      goto LABEL_109;
    }
    return 7;
  }
  v11 = (unsigned int)(v9 + 8);
  v12 = 0;
  do
  {
    v13 = a2[v12] == 38;
    v12 = (unsigned int)(v12 + 1);
    v11 += v13;
  }
  while ( (int)v12 < (int)v9 );
  v14 = (_DWORD *)sqlite3_malloc64(v11);
  if ( !v14 )
    return 7;
  v15 = v6 | 0x40;
  *v14 = 0;
  v16 = (char *)(v14 + 1);
  v56 = v15;
  v17 = 5;
  if ( a2[5] == 47 && a2[6] == 47 )
  {
    v18 = a2 + 7;
    v17 = 7;
    if ( a2[7] )
    {
      do
      {
        if ( a2[v17] == 47 )
          break;
        ++v17;
      }
      while ( a2[v17] );
      if ( v17 != 7 && (v17 != 16 || *(_QWORD *)v18 != 0x736F686C61636F6CLL || a2[15] != 116) )
      {
        v19 = 1;
        v20 = sqlite3_mprintf("invalid uri authority: %.*s", v17 - 7, v18);
        goto LABEL_111;
      }
    }
  }
  v21 = 0;
  v22 = 0;
  LOBYTE(v23) = a2[v17];
  if ( (_BYTE)v23 )
  {
    while ( 1 )
    {
      if ( (_BYTE)v23 == 35 )
      {
LABEL_62:
        v8 = v55;
        if ( v22 == 1 )
        {
          v29 = v21++;
          v16[v29] = 0;
        }
        break;
      }
      v24 = v17++;
      if ( (_BYTE)v23 == 37 )
      {
        v25 = (unsigned __int8)a2[v17];
        if ( (byte_1400B2300[v25] & 8) != 0 )
        {
          v26 = (unsigned __int8)a2[v24 + 2];
          if ( (byte_1400B2300[v26] & 8) != 0 )
          {
            v17 = v24 + 3;
            v23 = (((_BYTE)v26 - 7 * (((char)v26 >> 6) & 1)) & 0xF)
                + 16 * (((_BYTE)v25 - 7 * (((char)v25 >> 6) & 1)) & 0xF);
            if ( !v23 )
            {
              while ( 1 )
              {
                v27 = a2[v17];
                if ( !v27 || v27 == 35 || !v22 && v27 == 63 )
                  break;
                if ( v22 == 1 && (v27 == 61 || v27 == 38) || v22 == 2 && v27 == 38 )
                  break;
                ++v17;
              }
              goto LABEL_61;
            }
            goto LABEL_60;
          }
        }
      }
      if ( v22 == 1 )
      {
        if ( (_BYTE)v23 != 38 && (_BYTE)v23 != 61 )
          goto LABEL_60;
        if ( !v16[v21 - 1] )
        {
          while ( a2[v17] && a2[v17] != 35 && a2[v17 - 1] != 38 )
            ++v17;
          goto LABEL_61;
        }
        if ( (_BYTE)v23 == 38 )
          v16[v21++] = 0;
        else
          v22 = 2;
      }
      else
      {
        if ( (v22 || (_BYTE)v23 != 63) && (v22 != 2 || (_BYTE)v23 != 38) )
          goto LABEL_60;
        v22 = 1;
      }
      LOBYTE(v23) = 0;
LABEL_60:
      v28 = v21++;
      v16[v28] = v23;
LABEL_61:
      LOBYTE(v23) = a2[v17];
      if ( !(_BYTE)v23 )
        goto LABEL_62;
    }
  }
  *(_DWORD *)&v16[v21] = 0;
  if ( v16 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v16[v31] );
    v30 = v31 & 0x3FFFFFFF;
  }
  else
  {
    v30 = 0;
  }
  v32 = &v16[v30 + 1];
  if ( !*v32 )
  {
LABEL_109:
    v19 = 0;
    v50 = sqlite3_vfs_find(v8);
    *a4 = v50;
    if ( !v50 )
    {
      v19 = 1;
      v20 = sqlite3_mprintf("no such vfs: %s", v8);
      goto LABEL_111;
    }
    goto LABEL_112;
  }
  v19 = 3;
  while ( 1 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v32[v33] );
    v34 = v33 & 0x3FFFFFFF;
    v35 = &v32[v34 + 1];
    if ( v35 )
    {
      v37 = -1;
      do
        ++v37;
      while ( v35[v37] );
      v36 = v37 & 0x3FFFFFFF;
    }
    else
    {
      v36 = 0;
    }
    if ( v34 != 3 || *(_WORD *)v32 != 26230 || v32[2] != 115 )
      break;
    v8 = &v32[v34 + 1];
    v55 = v8;
LABEL_108:
    v32 = &v35[v36 + 1];
    if ( !*v32 )
      goto LABEL_109;
  }
  if ( v34 == 5 )
  {
    v38 = 0;
    v39 = 0;
    v40 = 0;
    if ( *(_DWORD *)v32 == 1751343459 && v32[4] == 101 )
    {
      v40 = 393216;
      v38 = &off_1400C8100;
      v39 = "cache";
    }
    goto LABEL_90;
  }
  if ( v34 != 4 )
  {
    v38 = 0;
    v40 = 0;
    v39 = 0;
LABEL_90:
    v54 = v40;
    if ( v38 )
      goto LABEL_91;
    LOBYTE(v15) = v56;
LABEL_107:
    v8 = v55;
    goto LABEL_108;
  }
  if ( *(_DWORD *)v32 != 1701080941 )
    goto LABEL_107;
  v41 = v15;
  v38 = &off_1400C8130;
  v40 = 135;
  v39 = "access";
  v54 = v41 & 0x87;
LABEL_91:
  v42 = 0;
  v43 = *v38 == 0;
  while ( 2 )
  {
    v53 = v42;
    if ( v43 )
      goto LABEL_102;
    v44 = 2LL * v42;
    v45 = v38[2 * v42];
    if ( v45 )
    {
      v47 = -1;
      do
        ++v47;
      while ( v45[v47] );
      v46 = v47 & 0x3FFFFFFF;
    }
    else
    {
      v46 = 0;
    }
    if ( v36 != v46 )
    {
LABEL_100:
      v43 = v38[2 * ++v42] == 0;
      continue;
    }
    break;
  }
  if ( memcmp_0(v35, v45, v36) )
  {
    v42 = v53;
    goto LABEL_100;
  }
  v48 = (int)v38[v44 + 1];
  if ( !v48 )
  {
LABEL_102:
    v19 = 1;
    v20 = sqlite3_mprintf("no such %s mode: %s", v39, v35);
    goto LABEL_111;
  }
  if ( (int)(v48 & 0xFFFFFF7F) <= v54 )
  {
    v49 = ~v40;
    LOBYTE(v15) = v48 | v49 & v56;
    v56 = v48 | v49 & v56;
    goto LABEL_107;
  }
  v20 = sqlite3_mprintf("%s mode not allowed: %s", v39, v35);
LABEL_111:
  *a6 = v20;
  sqlite3_free_filename(v16);
  v16 = 0;
LABEL_112:
  *a3 = v56;
  result = v19;
  *a5 = v16;
  return result;
}

```

## disassembly

```asm
0x140065754  mov     [rsp+arg_18], r9
0x140065759  mov     [rsp+arg_10], r8
0x14006575e  mov     [rsp+arg_0], rcx
0x140065763  push    rbx
0x140065764  push    rbp
0x140065765  push    rsi
0x140065766  push    rdi
0x140065767  push    r12
0x140065769  push    r13
0x14006576b  push    r14
0x14006576d  push    r15
0x14006576f  sub     rsp, 38h
0x140065773  mov     r12d, [r8]
0x140065776  mov     rsi, rdx
0x140065779  mov     r13, rcx
0x14006577c  test    rdx, rdx
0x14006577f  jnz     short loc_140065785
0x140065781  xor     ebx, ebx
0x140065783  jmp     short loc_140065798
0x140065785  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140065789  inc     rbx
0x14006578c  cmp     byte ptr [rdx+rbx], 0
0x140065790  jnz     short loc_140065789
0x140065792  and     ebx, 3FFFFFFFh
0x140065798  mov     ebp, 1
0x14006579d  test    r12b, 40h
0x1400657a1  jnz     short loc_1400657B0
0x1400657a3  cmp     cs:byte_1400C84B6, 0
0x1400657aa  jz      loc_140065C38
0x1400657b0  cmp     ebx, 5
0x1400657b3  jb      loc_140065C38
0x1400657b9  cmp     dword ptr [rdx], 656C6966h
0x1400657bf  jnz     loc_140065C38
0x1400657c5  cmp     byte ptr [rdx+4], 3Ah ; ':'
0x1400657c9  jnz     loc_140065C38
0x1400657cf  lea     ecx, [rbx+8]
0x1400657d2  xor     r8d, r8d
0x1400657d5  mov     r14b, 26h ; '&'
0x1400657d8  xor     edx, edx
0x1400657da  cmp     [r8+rsi], r14b
0x1400657de  setz    dl
0x1400657e1  add     r8d, ebp
0x1400657e4  add     rcx, rdx
0x1400657e7  cmp     r8d, ebx
0x1400657ea  jl      short loc_1400657D8
0x1400657ec  call    sqlite3_malloc64
0x1400657f1  mov     rdi, rax
0x1400657f4  test    rax, rax
0x1400657f7  jz      loc_140065C48
0x1400657fd  xor     eax, eax
0x1400657ff  or      r12d, 40h
0x140065803  mov     [rdi], eax
0x140065805  mov     dl, 2Fh ; '/'
0x140065807  add     rdi, 4
0x14006580b  mov     [rsp+78h+arg_8], r12d
0x140065813  lea     ecx, [rax+5]
0x140065816  cmp     [rsi+5], dl
0x140065819  jnz     short loc_140065878
0x14006581b  cmp     [rsi+6], dl
0x14006581e  jnz     short loc_140065878
0x140065820  lea     r8, [rsi+7]
0x140065824  lea     ecx, [rax+7]
0x140065827  cmp     [r8], al
0x14006582a  jz      short loc_140065878
0x14006582c  movsxd  rax, ecx
0x14006582f  cmp     [rax+rsi], dl
0x140065832  jz      short loc_14006583F
0x140065834  add     ecx, ebp
0x140065836  movsxd  rax, ecx
0x140065839  cmp     byte ptr [rax+rsi], 0
0x14006583d  jnz     short loc_14006582C
0x14006583f  cmp     ecx, 7
0x140065842  jz      short loc_140065878
0x140065844  cmp     ecx, 10h
0x140065847  jnz     short loc_140065861
0x140065849  mov     rax, 736F686C61636F6Ch
0x140065853  cmp     rax, [r8]
0x140065856  jnz     short loc_140065861
0x140065858  lea     eax, [rcx+64h]
0x14006585b  cmp     al, [r8+8]
0x14006585f  jz      short loc_140065878
0x140065861  lea     edx, [rcx-7]
0x140065864  mov     r15d, ebp
0x140065867  lea     rcx, aInvalidUriAuth; "invalid uri authority: %.*s"
0x14006586e  call    sqlite3_mprintf
0x140065873  jmp     loc_140065BDF
0x140065878  movsxd  rax, ecx
0x14006587b  xor     r8d, r8d
0x14006587e  xor     r9d, r9d
0x140065881  mov     dl, [rax+rsi]
0x140065884  test    dl, dl
0x140065886  jz      loc_1400659E8
0x14006588c  mov     r15b, 23h ; '#'
0x14006588f  lea     r13, byte_1400B2300
0x140065896  cmp     dl, r15b
0x140065899  jz      loc_1400659D1
0x14006589f  movsxd  r11, ecx
0x1400658a2  add     ecx, ebp
0x1400658a4  cmp     dl, 25h ; '%'
0x1400658a7  jnz     loc_140065954
0x1400658ad  movsxd  rax, ecx
0x1400658b0  movzx   ebx, byte ptr [rax+rsi]
0x1400658b4  test    byte ptr [rbx+r13], 8
0x1400658b9  jz      loc_140065954
0x1400658bf  movzx   r10d, byte ptr [r11+rsi+2]
0x1400658c5  test    byte ptr [r10+r13], 8
0x1400658ca  jz      loc_140065954
0x1400658d0  mov     al, bl
0x1400658d2  mov     dl, bl
0x1400658d4  sar     al, 6
0x1400658d7  and     al, bpl
0x1400658da  movzx   eax, al
0x1400658dd  imul    ecx, eax, 7
0x1400658e0  mov     al, r10b
0x1400658e3  sar     al, 6
0x1400658e6  and     al, bpl
0x1400658e9  movzx   eax, al
0x1400658ec  sub     dl, cl
0x1400658ee  imul    ecx, eax, 7
0x1400658f1  mov     al, r10b
0x1400658f4  and     edx, 0Fh
0x1400658f7  shl     edx, 4
0x1400658fa  sub     al, cl
0x1400658fc  lea     ecx, [r11+3]
0x140065900  and     eax, 0Fh
0x140065903  add     edx, eax
0x140065905  jnz     loc_1400659BA
0x14006590b  jmp     short loc_140065948
0x14006590d  cmp     dl, r15b
0x140065910  jz      loc_1400659C3
0x140065916  test    r9d, r9d
0x140065919  jnz     short loc_140065924
0x14006591b  cmp     dl, 3Fh ; '?'
0x14006591e  jz      loc_1400659C3
0x140065924  cmp     r9d, ebp
0x140065927  jnz     short loc_14006593B
0x140065929  cmp     dl, 3Dh ; '='
0x14006592c  jz      loc_1400659C3
0x140065932  cmp     dl, r14b
0x140065935  jz      loc_1400659C3
0x14006593b  cmp     r9d, 2
0x14006593f  jnz     short loc_140065946
0x140065941  cmp     dl, r14b
0x140065944  jz      short loc_1400659C3
0x140065946  add     ecx, ebp
0x140065948  movsxd  rax, ecx
0x14006594b  mov     dl, [rax+rsi]
0x14006594e  test    dl, dl
0x140065950  jnz     short loc_14006590D
0x140065952  jmp     short loc_1400659C3
0x140065954  cmp     r9d, ebp
0x140065957  jnz     short loc_1400659A0
0x140065959  cmp     dl, r14b
0x14006595c  jz      short loc_140065963
0x14006595e  cmp     dl, 3Dh ; '='
0x140065961  jnz     short loc_1400659BA
0x140065963  movsxd  rax, r8d
0x140065966  cmp     byte ptr [rax+rdi-1], 0
0x14006596b  jz      short loc_14006598D
0x14006596d  cmp     dl, r14b
0x140065970  jnz     short loc_140065998
0x140065972  mov     byte ptr [rax+rdi], 0
0x140065976  add     r8d, ebp
0x140065979  jmp     short loc_1400659B8
0x14006597b  movsxd  rax, ecx
0x14006597e  cmp     [rax+rsi], r15b
0x140065982  jz      short loc_1400659C3
0x140065984  cmp     [rax+rsi-1], r14b
0x140065989  jz      short loc_1400659C3
0x14006598b  add     ecx, ebp
0x14006598d  movsxd  rax, ecx
0x140065990  cmp     byte ptr [rax+rsi], 0
0x140065994  jnz     short loc_14006597B
0x140065996  jmp     short loc_1400659C3
0x140065998  mov     r9d, 2
0x14006599e  jmp     short loc_1400659B8
0x1400659a0  test    r9d, r9d
0x1400659a3  jnz     short loc_1400659AA
0x1400659a5  cmp     dl, 3Fh ; '?'
0x1400659a8  jz      short loc_1400659B5
0x1400659aa  cmp     r9d, 2
0x1400659ae  jnz     short loc_1400659BA
0x1400659b0  cmp     dl, r14b
0x1400659b3  jnz     short loc_1400659BA
0x1400659b5  mov     r9d, ebp
0x1400659b8  xor     dl, dl
0x1400659ba  movsxd  rax, r8d
0x1400659bd  add     r8d, ebp
0x1400659c0  mov     [rax+rdi], dl
0x1400659c3  movsxd  rax, ecx
0x1400659c6  mov     dl, [rax+rsi]
0x1400659c9  test    dl, dl
0x1400659cb  jnz     loc_140065896
0x1400659d1  mov     r13, [rsp+78h+arg_0]
0x1400659d9  cmp     r9d, ebp
0x1400659dc  jnz     short loc_1400659E8
0x1400659de  movsxd  rax, r8d
0x1400659e1  add     r8d, ebp
0x1400659e4  mov     byte ptr [rax+rdi], 0
0x1400659e8  xor     ecx, ecx
0x1400659ea  movsxd  rax, r8d
0x1400659ed  mov     [rax+rdi], ecx
0x1400659f0  test    rdi, rdi
0x1400659f3  jnz     short loc_1400659F9
0x1400659f5  xor     eax, eax
0x1400659f7  jmp     short loc_140065A0A
0x1400659f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400659fd  inc     rax
0x140065a00  cmp     [rdi+rax], cl
0x140065a03  jnz     short loc_1400659FD
0x140065a05  and     eax, 3FFFFFFFh
0x140065a0a  lea     rcx, [rax+1]
0x140065a0e  add     rcx, rdi
0x140065a11  cmp     byte ptr [rcx], 0
0x140065a14  jz      loc_140065BB2
0x140065a1a  mov     r15d, 3
0x140065a20  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140065a24  inc     rdx
0x140065a27  cmp     byte ptr [rcx+rdx], 0
0x140065a2b  jnz     short loc_140065A24
0x140065a2d  and     edx, 3FFFFFFFh
0x140065a33  lea     r14d, [rdx+1]
0x140065a37  add     r14, rcx
0x140065a3a  jnz     short loc_140065A40
0x140065a3c  xor     ebp, ebp
0x140065a3e  jmp     short loc_140065A54
0x140065a40  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140065a44  inc     rbp
0x140065a47  cmp     byte ptr [r14+rbp], 0
0x140065a4c  jnz     short loc_140065A44
0x140065a4e  and     ebp, 3FFFFFFFh
0x140065a54  cmp     edx, r15d
0x140065a57  jnz     short loc_140065A7D
0x140065a59  mov     eax, 6676h
0x140065a5e  cmp     ax, [rcx]
0x140065a61  jnz     short loc_140065A7D
0x140065a63  mov     eax, 73h ; 's'
0x140065a68  cmp     al, [rcx+2]
0x140065a6b  jnz     short loc_140065A7D
0x140065a6d  mov     r13, r14
0x140065a70  mov     [rsp+78h+arg_0], r14
0x140065a78  jmp     loc_140065B9E
0x140065a7d  cmp     edx, 5
0x140065a80  jnz     short loc_140065AAF
0x140065a82  xor     esi, esi
0x140065a84  xor     r12d, r12d
0x140065a87  xor     ebx, ebx
0x140065a89  mov     eax, 68636163h
0x140065a8e  cmp     eax, [rcx]
0x140065a90  jnz     short loc_140065AE6
0x140065a92  lea     eax, [rdx+60h]
0x140065a95  cmp     al, [rcx+4]
0x140065a98  jnz     short loc_140065AE6
0x140065a9a  mov     ebx, 60000h
0x140065a9f  lea     rsi, off_1400C8100; "shared"
0x140065aa6  lea     r12, aCache; "cache"
0x140065aad  jmp     short loc_140065AE6
0x140065aaf  cmp     edx, 4
0x140065ab2  jnz     short loc_140065ADF
0x140065ab4  mov     eax, 65646F6Dh
0x140065ab9  cmp     eax, [rcx]
0x140065abb  jnz     loc_140065B96
0x140065ac1  mov     eax, r12d
0x140065ac4  lea     rsi, off_1400C8130; "ro"
0x140065acb  mov     ebx, 87h
0x140065ad0  lea     r12, aAccess; "access"
0x140065ad7  and     eax, ebx
0x140065ad9  mov     [rsp+78h+var_54], eax
0x140065add  jmp     short loc_140065AF3
0x140065adf  xor     esi, esi
0x140065ae1  xor     ebx, ebx
0x140065ae3  xor     r12d, r12d
0x140065ae6  mov     [rsp+78h+var_54], ebx
0x140065aea  test    rsi, rsi
0x140065aed  jz      loc_140065B8E
0x140065af3  xor     ecx, ecx
0x140065af5  cmp     [rsi], rcx
0x140065af8  jmp     short loc_140065B43
0x140065afa  movsxd  r13, ecx
0x140065afd  add     r13, r13
0x140065b00  mov     rdx, [rsi+r13*8]; Buf2
0x140065b04  test    rdx, rdx
0x140065b07  jnz     short loc_140065B0D
0x140065b09  xor     eax, eax
0x140065b0b  jmp     short loc_140065B1F
0x140065b0d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140065b11  inc     rax
0x140065b14  cmp     byte ptr [rdx+rax], 0
0x140065b18  jnz     short loc_140065B11
0x140065b1a  and     eax, 3FFFFFFFh
0x140065b1f  cmp     ebp, eax
0x140065b21  jnz     short loc_140065B36
0x140065b23  mov     r8d, ebp; Size
0x140065b26  mov     rcx, r14; Buf1
0x140065b29  call    memcmp_0
0x140065b2e  test    eax, eax
0x140065b30  jz      short loc_140065B5B
0x140065b32  mov     ecx, [rsp+78h+var_58]
0x140065b36  inc     ecx
0x140065b38  movsxd  rax, ecx
  ... truncated ...
```
