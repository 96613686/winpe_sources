# sqlite3FindTable

- ea: `0x18007c190`
- end: `0x18007c812`
- name: `sqlite3FindTable`
- size: `1666`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x180009820`
- `0x18000b610`
- `0x18000f6d0`
- `0x180025700`
- `0x180051bf0`
- `0x18005b110`
- `0x180063bb0`
- `0x180064610`
- `0x180064b60`
- `0x18006bad0`
- `0x18006fc70`
- `0x18007d540`
- `0x180087d40`
- `0x18008c9f0`
- `0x180094940`
- `0x18009b840`
- `0x18009c7d0`
- `0x1800a4310`

## callees

- `0x18003c1a0`
- `0x18007c190`
- `0x18009d3a0`

## string_xrefs

- `0x18007c398`: `sqlite_temp_master`
- `0x18007c404`: `sqlite_temp_master`
- `0x18007c742`: `sqlite_temp_master`
- `0x18007c7b4`: `sqlite_temp_master`

## pseudocode

```c
__int64 __fastcall sqlite3FindTable(__int64 a1, unsigned __int8 *a2, _BYTE *a3)
{
  _BYTE *v3; // r10
  int v6; // r11d
  unsigned int v7; // edi
  int i; // esi
  _BYTE *v9; // r8
  unsigned __int8 *j; // r9
  __int64 v11; // rdx
  __int64 v12; // rax
  const char *k; // r8
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rbp
  __int64 v17; // r11
  int v18; // edx
  const char *v19; // r8
  unsigned __int8 *v20; // r9
  __int64 v21; // rcx
  _BYTE *v22; // r10
  _BYTE *v23; // r9
  char *m; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 result; // rax
  _BYTE *v28; // r9
  char *n; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // r11
  __int64 v33; // r8
  const char *v34; // rdx
  unsigned __int8 v35; // al
  int v36; // ecx
  __int64 *v37; // r10
  int v38; // r11d
  _BYTE *v39; // r8
  const char *ii; // r9
  __int64 v41; // rdx
  __int64 v42; // rax
  char *jj; // rdx
  __int64 v44; // r8
  __int64 v45; // rax
  __int64 v46; // r11
  __int64 v47; // r8
  const char *v48; // rdx
  unsigned __int8 v49; // al
  int v50; // ecx
  int v51; // r11d
  _BYTE *v52; // r8
  const char *kk; // r9
  __int64 v54; // rdx
  __int64 v55; // rax
  int mm; // ebx
  int v57; // edx
  const char *v58; // r8
  unsigned __int8 *v59; // r9
  __int64 v60; // rcx
  _BYTE *v61; // r9
  _BYTE *v62; // r10
  char *nn; // rdx
  __int64 v64; // r8
  __int64 v65; // rax
  __int64 v66; // r11
  __int64 v67; // r8
  const char *v68; // rdx
  unsigned int v69; // edi
  unsigned __int8 v70; // al
  int v71; // ecx
  int v72; // r11d
  _BYTE *v73; // r8
  const char *i1; // r9
  __int64 v75; // rdx
  __int64 v76; // rax
  char *i2; // rdx
  __int64 v78; // r8
  __int64 v79; // rax
  __int64 v80; // r11
  __int64 v81; // r8
  const char *v82; // rax
  unsigned int v83; // edi
  unsigned __int8 v84; // cl
  int v85; // edx
  int v86; // r11d
  _BYTE *v87; // r8
  const char *i3; // r9
  __int64 v89; // rdx
  __int64 v90; // rax

  v3 = a3;
  if ( a3 )
  {
    v6 = *(_DWORD *)(a1 + 40);
    v7 = 0;
    for ( i = 0; i < v6; ++i )
    {
      v9 = v3;
      for ( j = *(unsigned __int8 **)(32LL * i + *(_QWORD *)(a1 + 32)); ; ++j )
      {
        while ( 1 )
        {
          v11 = (unsigned __int8)*v9;
          v12 = *j;
          if ( (_DWORD)v11 != (_DWORD)v12 )
            break;
          if ( !*v9 )
            goto LABEL_10;
          ++v9;
          ++j;
        }
        if ( *((unsigned __int8 *)qword_180114680 + v11) != *((unsigned __int8 *)qword_180114680 + v12) )
          break;
        ++v9;
      }
    }
LABEL_10:
    if ( i < v6 )
      goto LABEL_15;
    for ( k = "main"; ; ++k )
    {
      v14 = (unsigned __int8)*v3;
      v15 = *(unsigned __int8 *)k;
      if ( (_DWORD)v14 == (_DWORD)v15 )
      {
        if ( !*v3 )
        {
          i = 0;
LABEL_15:
          v16 = 32LL * i;
          v17 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(a1 + 32) + v16 + 24) + 8LL, a2, 0) + 16);
          if ( v17 || !a2 )
            return v17;
          v18 = 7;
          v19 = "sqlite_";
          v20 = a2;
          do
          {
            v21 = *v20;
            --v18;
            if ( !(_BYTE)v21
              || *((_BYTE *)qword_180114680 + v21) != *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v19) )
            {
              goto LABEL_22;
            }
            ++v20;
            ++v19;
          }
          while ( v18 > 0 );
          --v18;
LABEL_22:
          if ( v18 >= 0
            && *((unsigned __int8 *)qword_180114680 + *v20) != *((unsigned __int8 *)qword_180114680
                                                               + *(unsigned __int8 *)v19) )
          {
            return v17;
          }
          v22 = a2 + 7;
          if ( i == 1 )
          {
            v23 = a2 + 7;
            for ( m = "temp_schema"; ; ++m )
            {
              while ( 1 )
              {
                v25 = (unsigned __int8)*v23;
                v26 = (unsigned __int8)*m;
                if ( (_DWORD)v25 != (_DWORD)v26 )
                  break;
                if ( !*v23 )
                  goto LABEL_41;
                ++v23;
                ++m;
              }
              if ( *((unsigned __int8 *)qword_180114680 + v25) != *((unsigned __int8 *)qword_180114680 + v26) )
                break;
              ++v23;
            }
            v28 = a2 + 7;
            for ( n = "schema"; ; ++n )
            {
              while ( 1 )
              {
                v30 = (unsigned __int8)*v28;
                v31 = (unsigned __int8)*n;
                if ( (_DWORD)v30 != (_DWORD)v31 )
                  break;
                if ( !*v28 )
                  goto LABEL_41;
                ++v28;
                ++n;
              }
              if ( *((unsigned __int8 *)qword_180114680 + v30) != *((unsigned __int8 *)qword_180114680 + v31) )
                break;
              ++v28;
            }
            if ( !(unsigned int)sqlite3StrICmp(a2 + 7, "master") )
            {
LABEL_41:
              v32 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL);
              v33 = *(_QWORD *)(v32 + 24);
              if ( v33 )
              {
                v34 = "sqlite_temp_master";
                v35 = 115;
                do
                {
                  ++v34;
                  v36 = *((unsigned __int8 *)qword_180114680 + v35);
                  v35 = *v34;
                  v7 = -1640531535 * (v7 + v36);
                }
                while ( *v34 );
                v37 = *(__int64 **)(v33 + 16LL * (v7 % *(_DWORD *)(v32 + 8)) + 8);
                v38 = *(_DWORD *)(v33 + 16LL * (v7 % *(_DWORD *)(v32 + 8)));
              }
              else
              {
                v37 = *(__int64 **)(v32 + 16);
                v38 = *(_DWORD *)(v32 + 12);
              }
              if ( v38 )
              {
                while ( 1 )
                {
                  v39 = (_BYTE *)v37[3];
                  for ( ii = "sqlite_temp_master"; ; ++ii )
                  {
                    while ( 1 )
                    {
                      v41 = (unsigned __int8)*v39;
                      v42 = *(unsigned __int8 *)ii;
                      if ( (_DWORD)v41 != (_DWORD)v42 )
                        break;
                      if ( !*v39 )
                        return v37[2];
                      ++v39;
                      ++ii;
                    }
                    if ( *((unsigned __int8 *)qword_180114680 + v41) != *((unsigned __int8 *)qword_180114680 + v42) )
                      break;
                    ++v39;
                  }
                  if ( !--v38 )
                    break;
                  v37 = (__int64 *)*v37;
                }
              }
              goto LABEL_125;
            }
            return v17;
          }
          for ( jj = "schema"; ; ++jj )
          {
            v44 = (unsigned __int8)*v22;
            v45 = (unsigned __int8)*jj;
            if ( (_DWORD)v44 == (_DWORD)v45 )
            {
              if ( !*v22 )
              {
                v46 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + v16 + 24);
                v47 = *(_QWORD *)(v46 + 24);
                if ( v47 )
                {
                  v48 = "sqlite_master";
                  v49 = 115;
                  do
                  {
                    ++v48;
                    v50 = *((unsigned __int8 *)qword_180114680 + v49);
                    v49 = *v48;
                    v7 = -1640531535 * (v7 + v50);
                  }
                  while ( *v48 );
                  v37 = *(__int64 **)(v47 + 16LL * (v7 % *(_DWORD *)(v46 + 8)) + 8);
                  v51 = *(_DWORD *)(v47 + 16LL * (v7 % *(_DWORD *)(v46 + 8)));
                }
                else
                {
                  v37 = *(__int64 **)(v46 + 16);
                  v51 = *(_DWORD *)(v46 + 12);
                }
                if ( v51 )
                {
                  while ( 1 )
                  {
                    v52 = (_BYTE *)v37[3];
                    for ( kk = "sqlite_master"; ; ++kk )
                    {
                      while ( 1 )
                      {
                        v54 = (unsigned __int8)*v52;
                        v55 = *(unsigned __int8 *)kk;
                        if ( (_DWORD)v54 != (_DWORD)v55 )
                          break;
                        if ( !*v52 )
                          return v37[2];
                        ++v52;
                        ++kk;
                      }
                      if ( *((unsigned __int8 *)qword_180114680 + v54) != *((unsigned __int8 *)qword_180114680 + v55) )
                        break;
                      ++v52;
                    }
                    if ( !--v51 )
                      break;
                    v37 = (__int64 *)*v37;
                  }
                }
LABEL_125:
                v37 = qword_18013FD98;
                return v37[2];
              }
            }
            else if ( *((unsigned __int8 *)qword_180114680 + v44) != *((unsigned __int8 *)qword_180114680 + v45) )
            {
              return v17;
            }
            ++v22;
          }
        }
      }
      else if ( *((unsigned __int8 *)qword_180114680 + v14) != *((unsigned __int8 *)qword_180114680 + v15) )
      {
        return 0;
      }
      ++v3;
    }
  }
  result = *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL) + 8LL, a2, 0) + 16);
  if ( !result )
  {
    v17 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL) + 8LL, a2, 0) + 16);
    if ( v17 )
      return v17;
    for ( mm = 2; mm < *(_DWORD *)(a1 + 40); ++mm )
    {
      v17 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * mm + *(_QWORD *)(a1 + 32) + 24) + 8LL, a2, 0) + 16);
      if ( v17 )
        return v17;
    }
    if ( a2 )
    {
      v57 = 7;
      v58 = "sqlite_";
      v59 = a2;
      while ( 1 )
      {
        v60 = *v59;
        --v57;
        if ( !(_BYTE)v60 || *((_BYTE *)qword_180114680 + v60) != *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v58) )
          break;
        ++v59;
        ++v58;
        if ( v57 <= 0 )
        {
          --v57;
          break;
        }
      }
      if ( v57 < 0
        || *((unsigned __int8 *)qword_180114680 + *v59) == *((unsigned __int8 *)qword_180114680 + *(unsigned __int8 *)v58) )
      {
        v61 = a2 + 7;
        v62 = a2 + 7;
        for ( nn = "schema"; ; ++nn )
        {
          v64 = (unsigned __int8)*v62;
          v65 = (unsigned __int8)*nn;
          if ( (_DWORD)v64 == (_DWORD)v65 )
          {
            if ( !*v62 )
            {
              v66 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL);
              v67 = *(_QWORD *)(v66 + 24);
              if ( v67 )
              {
                v68 = "sqlite_master";
                v69 = 0;
                v70 = 115;
                do
                {
                  ++v68;
                  v71 = *((unsigned __int8 *)qword_180114680 + v70);
                  v70 = *v68;
                  v69 = -1640531535 * (v69 + v71);
                }
                while ( *v68 );
                v37 = *(__int64 **)(v67 + 16LL * (v69 % *(_DWORD *)(v66 + 8)) + 8);
                v72 = *(_DWORD *)(v67 + 16LL * (v69 % *(_DWORD *)(v66 + 8)));
              }
              else
              {
                v37 = *(__int64 **)(v66 + 16);
                v72 = *(_DWORD *)(v66 + 12);
              }
              if ( !v72 )
                goto LABEL_125;
              while ( 1 )
              {
                v73 = (_BYTE *)v37[3];
                for ( i1 = "sqlite_master"; ; ++i1 )
                {
                  while ( 1 )
                  {
                    v75 = (unsigned __int8)*v73;
                    v76 = *(unsigned __int8 *)i1;
                    if ( (_DWORD)v75 != (_DWORD)v76 )
                      break;
                    if ( !*v73 )
                      return v37[2];
                    ++v73;
                    ++i1;
                  }
                  if ( *((unsigned __int8 *)qword_180114680 + v75) != *((unsigned __int8 *)qword_180114680 + v76) )
                    break;
                  ++v73;
                }
                if ( !--v72 )
                  goto LABEL_125;
                v37 = (__int64 *)*v37;
              }
            }
          }
          else if ( *((unsigned __int8 *)qword_180114680 + v64) != *((unsigned __int8 *)qword_180114680 + v65) )
          {
            for ( i2 = "temp_schema"; ; ++i2 )
            {
              v78 = (unsigned __int8)*v61;
              v79 = (unsigned __int8)*i2;
              if ( (_DWORD)v78 == (_DWORD)v79 )
              {
                if ( !*v61 )
                {
                  v80 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL);
                  v81 = *(_QWORD *)(v80 + 24);
                  if ( v81 )
                  {
                    v82 = "sqlite_temp_master";
                    v83 = 0;
                    v84 = 115;
                    do
                    {
                      ++v82;
                      v85 = *((unsigned __int8 *)qword_180114680 + v84);
                      v84 = *v82;
                      v83 = -1640531535 * (v83 + v85);
                    }
                    while ( *v82 );
                    v37 = *(__int64 **)(v81 + 16LL * (v83 % *(_DWORD *)(v80 + 8)) + 8);
                    v86 = *(_DWORD *)(v81 + 16LL * (v83 % *(_DWORD *)(v80 + 8)));
                  }
                  else
                  {
                    v37 = *(__int64 **)(v80 + 16);
                    v86 = *(_DWORD *)(v80 + 12);
                  }
                  if ( !v86 )
                    goto LABEL_125;
                  while ( 1 )
                  {
                    v87 = (_BYTE *)v37[3];
                    for ( i3 = "sqlite_temp_master"; ; ++i3 )
                    {
                      while ( 1 )
                      {
                        v89 = (unsigned __int8)*v87;
                        v90 = *(unsigned __int8 *)i3;
                        if ( (_DWORD)v89 != (_DWORD)v90 )
                          break;
                        if ( !*v87 )
                          return v37[2];
                        ++v87;
                        ++i3;
                      }
                      if ( *((unsigned __int8 *)qword_180114680 + v89) != *((unsigned __int8 *)qword_180114680 + v90) )
                        break;
                      ++v87;
                    }
                    if ( !--v86 )
                      goto LABEL_125;
                    v37 = (__int64 *)*v37;
                  }
                }
              }
              else if ( *((unsigned __int8 *)qword_180114680 + v78) != *((unsigned __int8 *)qword_180114680 + v79) )
              {
                return v17;
              }
              ++v61;
            }
          }
          ++v62;
        }
      }
    }
    return v17;
  }
  return result;
}

```

## disassembly

```asm
0x18007c190  push    rbx
0x18007c192  push    rbp
0x18007c193  push    rsi
0x18007c194  push    rdi
0x18007c195  push    r14
0x18007c197  push    r15
0x18007c199  sub     rsp, 28h
0x18007c19d  mov     r10, r8
0x18007c1a0  mov     r14, rdx
0x18007c1a3  mov     r15, rcx
0x18007c1a6  test    r8, r8
0x18007c1a9  jz      loc_18007C53F
0x18007c1af  mov     r11d, [rcx+28h]
0x18007c1b3  lea     rbx, qword_180114680
0x18007c1ba  xor     edi, edi
0x18007c1bc  mov     esi, edi
0x18007c1be  test    r11d, r11d
0x18007c1c1  jle     short loc_18007C213
0x18007c1c3  mov     rbp, [rcx+20h]
0x18007c1c7  nop     word ptr [rax+rax+00000000h]
0x18007c1d0  movsxd  rax, esi
0x18007c1d3  mov     r8, r10
0x18007c1d6  shl     rax, 5
0x18007c1da  mov     r9, [rax+rbp]
0x18007c1de  xchg    ax, ax
0x18007c1e0  movzx   edx, byte ptr [r8]
0x18007c1e4  movzx   eax, byte ptr [r9]
0x18007c1e8  cmp     edx, eax
0x18007c1ea  jnz     short loc_18007C1F8
0x18007c1ec  test    edx, edx
0x18007c1ee  jz      short loc_18007C213
0x18007c1f0  inc     r8
0x18007c1f3  inc     r9
0x18007c1f6  jmp     short loc_18007C1E0
0x18007c1f8  movzx   ecx, byte ptr [rax+rbx]
0x18007c1fc  movzx   eax, byte ptr [rdx+rbx]
0x18007c200  cmp     eax, ecx
0x18007c202  jnz     short loc_18007C20C
0x18007c204  inc     r8
0x18007c207  inc     r9
0x18007c20a  jmp     short loc_18007C1E0
0x18007c20c  inc     esi
0x18007c20e  cmp     esi, r11d
0x18007c211  jl      short loc_18007C1D0
0x18007c213  cmp     esi, r11d
0x18007c216  jl      short loc_18007C23A
0x18007c218  lea     r8, aMain; "main"
0x18007c21f  nop
0x18007c220  movzx   edx, byte ptr [r10]
0x18007c224  movzx   eax, byte ptr [r8]
0x18007c228  cmp     edx, eax
0x18007c22a  jnz     loc_18007C2FD
0x18007c230  test    edx, edx
0x18007c232  jnz     loc_18007C309
0x18007c238  mov     esi, edi
0x18007c23a  mov     rax, [r15+20h]
0x18007c23e  xor     r8d, r8d
0x18007c241  movsxd  rbp, esi
0x18007c244  mov     rdx, r14
0x18007c247  shl     rbp, 5
0x18007c24b  mov     rcx, [rax+rbp+18h]
0x18007c250  add     rcx, 8
0x18007c254  call    findElementWithHash
0x18007c259  mov     r11, [rax+10h]
0x18007c25d  test    r11, r11
0x18007c260  jnz     loc_18007C802
0x18007c266  test    r14, r14
0x18007c269  jz      loc_18007C802
0x18007c26f  mov     edx, 7
0x18007c274  lea     r8, aSqlite_0; "sqlite_"
0x18007c27b  mov     r9, r14
0x18007c27e  xchg    ax, ax
0x18007c280  movzx   ecx, byte ptr [r9]
0x18007c284  dec     edx
0x18007c286  test    cl, cl
0x18007c288  jz      short loc_18007C2A3
0x18007c28a  movzx   eax, byte ptr [r8]
0x18007c28e  movzx   eax, byte ptr [rax+rbx]
0x18007c292  cmp     [rcx+rbx], al
0x18007c295  jnz     short loc_18007C2A3
0x18007c297  inc     r9
0x18007c29a  inc     r8
0x18007c29d  test    edx, edx
0x18007c29f  jg      short loc_18007C280
0x18007c2a1  dec     edx
0x18007c2a3  test    edx, edx
0x18007c2a5  js      short loc_18007C2BF
0x18007c2a7  movzx   eax, byte ptr [r8]
0x18007c2ab  movzx   ecx, byte ptr [rax+rbx]
0x18007c2af  movzx   eax, byte ptr [r9]
0x18007c2b3  movzx   eax, byte ptr [rax+rbx]
0x18007c2b7  cmp     eax, ecx
0x18007c2b9  jnz     loc_18007C802
0x18007c2bf  lea     r10, [r14+7]
0x18007c2c3  cmp     esi, 1
0x18007c2c6  jnz     loc_18007C44F
0x18007c2cc  mov     r9, r10
0x18007c2cf  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x18007c2d6  nop     word ptr [rax+rax+00000000h]
0x18007c2e0  movzx   r8d, byte ptr [r9]
0x18007c2e4  movzx   eax, byte ptr [rdx]
0x18007c2e7  cmp     r8d, eax
0x18007c2ea  jnz     short loc_18007C323
0x18007c2ec  test    r8d, r8d
0x18007c2ef  jz      loc_18007C387
0x18007c2f5  inc     r9
0x18007c2f8  inc     rdx
0x18007c2fb  jmp     short loc_18007C2E0
0x18007c2fd  movzx   ecx, byte ptr [rax+rbx]
0x18007c301  movzx   eax, byte ptr [rdx+rbx]
0x18007c305  cmp     eax, ecx
0x18007c307  jnz     short loc_18007C314
0x18007c309  inc     r10
0x18007c30c  inc     r8
0x18007c30f  jmp     loc_18007C220
0x18007c314  xor     eax, eax
0x18007c316  add     rsp, 28h
0x18007c31a  pop     r15
0x18007c31c  pop     r14
0x18007c31e  pop     rdi
0x18007c31f  pop     rsi
0x18007c320  pop     rbp
0x18007c321  pop     rbx
0x18007c322  retn
0x18007c323  movzx   ecx, byte ptr [rax+rbx]
0x18007c327  movzx   eax, byte ptr [r8+rbx]
0x18007c32c  cmp     eax, ecx
0x18007c32e  jnz     short loc_18007C338
0x18007c330  inc     r9
0x18007c333  inc     rdx
0x18007c336  jmp     short loc_18007C2E0
0x18007c338  mov     r9, r10
0x18007c33b  lea     rdx, aSqliteSchema+7; "schema"
0x18007c342  movzx   r8d, byte ptr [r9]
0x18007c346  movzx   eax, byte ptr [rdx]
0x18007c349  cmp     r8d, eax
0x18007c34c  jnz     short loc_18007C35B
0x18007c34e  test    r8d, r8d
0x18007c351  jz      short loc_18007C387
0x18007c353  inc     r9
0x18007c356  inc     rdx
0x18007c359  jmp     short loc_18007C342
0x18007c35b  movzx   ecx, byte ptr [rax+rbx]
0x18007c35f  movzx   eax, byte ptr [r8+rbx]
0x18007c364  cmp     eax, ecx
0x18007c366  jnz     short loc_18007C370
0x18007c368  inc     r9
0x18007c36b  inc     rdx
0x18007c36e  jmp     short loc_18007C342
0x18007c370  lea     rdx, aSqliteMaster+7; "master"
0x18007c377  mov     rcx, r10
0x18007c37a  call    sqlite3StrICmp
0x18007c37f  test    eax, eax
0x18007c381  jnz     loc_18007C802
0x18007c387  mov     rax, [r15+20h]
0x18007c38b  mov     r11, [rax+38h]
0x18007c38f  mov     r8, [r11+18h]
0x18007c393  test    r8, r8
0x18007c396  jz      short loc_18007C3E2
0x18007c398  lea     rdx, aSqliteTempMast; "sqlite_temp_master"
0x18007c39f  mov     al, 73h ; 's'
0x18007c3a1  nop     dword ptr [rax+00h]
0x18007c3a5  nop     word ptr [rax+rax+00000000h]
0x18007c3b0  movzx   eax, al
0x18007c3b3  lea     rdx, [rdx+1]
0x18007c3b7  movzx   ecx, byte ptr [rax+rbx]
0x18007c3bb  movzx   eax, byte ptr [rdx]
0x18007c3be  add     ecx, edi
0x18007c3c0  imul    edi, ecx, 9E3779B1h
0x18007c3c6  test    al, al
0x18007c3c8  jnz     short loc_18007C3B0
0x18007c3ca  xor     edx, edx
0x18007c3cc  mov     eax, edi
0x18007c3ce  div     dword ptr [r11+8]
0x18007c3d2  mov     ecx, edx
0x18007c3d4  add     rcx, rcx
0x18007c3d7  mov     r10, [r8+rcx*8+8]
0x18007c3dc  mov     r11d, [r8+rcx*8]
0x18007c3e0  jmp     short loc_18007C3EA
0x18007c3e2  mov     r10, [r11+10h]
0x18007c3e6  mov     r11d, [r11+0Ch]
0x18007c3ea  test    r11d, r11d
0x18007c3ed  jz      loc_18007C7F7
0x18007c3f3  nop     dword ptr [rax+00h]
0x18007c3f7  nop     word ptr [rax+rax+00000000h]
0x18007c400  mov     r8, [r10+18h]
0x18007c404  lea     r9, aSqliteTempMast; "sqlite_temp_master"
0x18007c40b  nop     dword ptr [rax+rax+00h]
0x18007c410  movzx   edx, byte ptr [r8]
0x18007c414  movzx   eax, byte ptr [r9]
0x18007c418  cmp     edx, eax
0x18007c41a  jnz     short loc_18007C42C
0x18007c41c  test    edx, edx
0x18007c41e  jz      loc_18007C7FE
0x18007c424  inc     r8
0x18007c427  inc     r9
0x18007c42a  jmp     short loc_18007C410
0x18007c42c  movzx   ecx, byte ptr [rax+rbx]
0x18007c430  movzx   eax, byte ptr [rdx+rbx]
0x18007c434  cmp     eax, ecx
0x18007c436  jnz     short loc_18007C440
0x18007c438  inc     r8
0x18007c43b  inc     r9
0x18007c43e  jmp     short loc_18007C410
0x18007c440  add     r11d, 0FFFFFFFFh
0x18007c444  jz      loc_18007C7F7
0x18007c44a  mov     r10, [r10]
0x18007c44d  jmp     short loc_18007C400
0x18007c44f  lea     rdx, aSqliteSchema+7; "schema"
0x18007c456  nop     word ptr [rax+rax+00000000h]
0x18007c460  movzx   r8d, byte ptr [r10]
0x18007c464  movzx   eax, byte ptr [rdx]
0x18007c467  cmp     r8d, eax
0x18007c46a  jnz     short loc_18007C4C2
0x18007c46c  test    r8d, r8d
0x18007c46f  jnz     short loc_18007C4D3
0x18007c471  mov     rax, [r15+20h]
0x18007c475  mov     r11, [rax+rbp+18h]
0x18007c47a  mov     r8, [r11+18h]
0x18007c47e  test    r8, r8
0x18007c481  jz      short loc_18007C4DB
0x18007c483  lea     rdx, aSqliteMaster; "sqlite_master"
0x18007c48a  mov     al, 73h ; 's'
0x18007c48c  nop     dword ptr [rax+00h]
0x18007c490  movzx   eax, al
0x18007c493  lea     rdx, [rdx+1]
0x18007c497  movzx   ecx, byte ptr [rax+rbx]
0x18007c49b  movzx   eax, byte ptr [rdx]
0x18007c49e  add     ecx, edi
0x18007c4a0  imul    edi, ecx, 9E3779B1h
0x18007c4a6  test    al, al
0x18007c4a8  jnz     short loc_18007C490
0x18007c4aa  xor     edx, edx
0x18007c4ac  mov     eax, edi
0x18007c4ae  div     dword ptr [r11+8]
0x18007c4b2  mov     ecx, edx
0x18007c4b4  add     rcx, rcx
0x18007c4b7  mov     r10, [r8+rcx*8+8]
0x18007c4bc  mov     r11d, [r8+rcx*8]
0x18007c4c0  jmp     short loc_18007C4E3
0x18007c4c2  movzx   ecx, byte ptr [rax+rbx]
0x18007c4c6  movzx   eax, byte ptr [r8+rbx]
0x18007c4cb  cmp     eax, ecx
0x18007c4cd  jnz     loc_18007C802
0x18007c4d3  inc     r10
0x18007c4d6  inc     rdx
0x18007c4d9  jmp     short loc_18007C460
0x18007c4db  mov     r10, [r11+10h]
0x18007c4df  mov     r11d, [r11+0Ch]
0x18007c4e3  test    r11d, r11d
0x18007c4e6  jz      loc_18007C7F7
0x18007c4ec  nop     dword ptr [rax+00h]
0x18007c4f0  mov     r8, [r10+18h]
0x18007c4f4  lea     r9, aSqliteMaster; "sqlite_master"
0x18007c4fb  nop     dword ptr [rax+rax+00h]
0x18007c500  movzx   edx, byte ptr [r8]
0x18007c504  movzx   eax, byte ptr [r9]
0x18007c508  cmp     edx, eax
0x18007c50a  jnz     short loc_18007C51C
0x18007c50c  test    edx, edx
0x18007c50e  jz      loc_18007C7FE
0x18007c514  inc     r8
0x18007c517  inc     r9
0x18007c51a  jmp     short loc_18007C500
0x18007c51c  movzx   ecx, byte ptr [rax+rbx]
0x18007c520  movzx   eax, byte ptr [rdx+rbx]
0x18007c524  cmp     eax, ecx
0x18007c526  jnz     short loc_18007C530
0x18007c528  inc     r8
0x18007c52b  inc     r9
0x18007c52e  jmp     short loc_18007C500
0x18007c530  add     r11d, 0FFFFFFFFh
0x18007c534  jz      loc_18007C7F7
0x18007c53a  mov     r10, [r10]
0x18007c53d  jmp     short loc_18007C4F0
0x18007c53f  mov     rax, [rcx+20h]
0x18007c543  xor     r8d, r8d
0x18007c546  mov     rcx, [rax+38h]
0x18007c54a  add     rcx, 8
0x18007c54e  call    findElementWithHash
0x18007c553  mov     rax, [rax+10h]
0x18007c557  test    rax, rax
0x18007c55a  jnz     loc_18007C805
0x18007c560  mov     rax, [r15+20h]
0x18007c564  xor     r8d, r8d
0x18007c567  mov     rdx, r14
0x18007c56a  mov     rcx, [rax+18h]
0x18007c56e  add     rcx, 8
0x18007c572  call    findElementWithHash
0x18007c577  mov     r11, [rax+10h]
0x18007c57b  test    r11, r11
0x18007c57e  jnz     loc_18007C802
0x18007c584  mov     ebx, 2
0x18007c589  cmp     [r15+28h], ebx
0x18007c58d  jle     short loc_18007C5C4
0x18007c58f  nop
0x18007c590  mov     rax, [r15+20h]
0x18007c594  xor     r8d, r8d
0x18007c597  movsxd  rcx, ebx
0x18007c59a  mov     rdx, r14
  ... truncated ...
```
