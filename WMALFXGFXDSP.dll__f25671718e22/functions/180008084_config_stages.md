# config_stages

- ea: `0x180008084`
- end: `0x1800087e3`
- name: `config_stages`
- size: `1887`
- prototype: `char __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007ff4`

## callees

- `0x180008084`

## pseudocode

```c
char __fastcall config_stages(__int64 a1, __int64 a2, int a3)
{
  int v3; // r13d
  int v6; // r12d
  unsigned int v7; // r8d
  float v8; // xmm0_4
  int v9; // eax
  int v10; // r11d
  void (__fastcall *v11)(float *, unsigned int, char *, char *); // rax
  int v12; // r15d
  int v13; // edi
  int v14; // r11d
  int v15; // esi
  double v16; // xmm0_8
  int v17; // r9d
  int i; // r8d
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // r10d
  __int64 v22; // rcx
  int v23; // eax
  __int64 (__fastcall *v24)(); // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // r11
  int v29; // ebx
  char v30; // r10
  int v31; // ecx
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // ecx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx

  v3 = *(_DWORD *)(a1 + 564);
  if ( *(_DWORD *)(a1 + 452) )
  {
    v23 = *(_DWORD *)(a1 + 456);
    v7 = 1;
    v6 = *(_DWORD *)(a1 + 472);
    *(_QWORD *)(a2 + 16) = a1;
    if ( v23 )
    {
      *(_DWORD *)a2 = 0;
      v24 = phantom_matrix_wrap;
    }
    else
    {
      *(_DWORD *)a2 = 1;
      v24 = remove_phantom_zeroes;
    }
    *(_QWORD *)(a2 + 8) = v24;
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 540);
    v7 = 0;
  }
  *(_DWORD *)(a2 + 212) = 1065353216;
  *(_DWORD *)(a2 + 208) = 0;
  if ( ((unsigned __int8)~(_BYTE)a3 & *(_BYTE *)(a1 + 40) & 8) != 0 )
  {
    v8 = *(float *)(a1 + 88);
    *(float *)(a2 + 212) = v8;
  }
  else
  {
    v8 = FLOAT_1_0;
  }
  v9 = *(_DWORD *)(a1 + 892);
  if ( (v9 || *(_DWORD *)(a1 + 684)) && ((a3 & 1) == 0 || v9 && !*(_DWORD *)(a1 + 688)) )
    *(float *)(a2 + 212) = v8 * *(float *)(a1 + 632);
  v10 = 0;
  LODWORD(v11) = ~a3 & *(_DWORD *)(a1 + 40);
  if ( ((unsigned __int16)v11 & 0x100) != 0 )
  {
    v10 = *(_DWORD *)(a1 + 332) >> 1;
    *(_DWORD *)(a2 + 208) = v10;
  }
  if ( (*(_BYTE *)(a1 + 40) & 1) != 0 )
  {
    if ( *(_DWORD *)(a1 + 680) )
    {
      LOBYTE(v11) = (a3 & 1) == 0;
      if ( (((*(_BYTE *)(a1 + 40) & 0x30) == 0) & (unsigned __int8)v11) != 0 )
        *(_DWORD *)(a2 + 208) = v10 + *(_DWORD *)(a1 + 872);
    }
  }
  if ( (a3 & 0x40) != 0 && *(_DWORD *)(a1 + 904) )
  {
    v33 = 32LL * v7++;
    *(_DWORD *)(v33 + a2) = (*(_DWORD *)(a1 + 52) & 1) == 0;
    *(_QWORD *)(v33 + a2 + 8) = spkrcorr_wrap;
    v11 = *(void (__fastcall **)(float *, unsigned int, char *, char *))(a1 + 56);
    *(_QWORD *)(v33 + a2 + 16) = v11;
  }
  if ( *(_DWORD *)(a1 + 892) )
    *(_DWORD *)(a2 + 204) = 1;
  v12 = 2;
  if ( (*(_BYTE *)(a1 + 40) & 2) == 0 )
  {
    v13 = *(_DWORD *)(a1 + 544);
    v14 = *(_DWORD *)(a1 + 540);
    LOBYTE(v11) = 0;
    v15 = v13;
    if ( *(_DWORD *)(a1 + 908) && (a3 & 1) != 0 && *(_DWORD *)(a1 + 680) && (a3 & 0x30) == 0 )
    {
      if ( *(_QWORD *)(a1 + 704) )
      {
        v14 = *(_DWORD *)(a1 + 564);
        v15 = *(_DWORD *)(a1 + 568);
      }
      else
      {
        v34 = *(_DWORD *)(a1 + 568);
        LOBYTE(v11) = v34 & ~(_BYTE)v13;
        v15 = *(_DWORD *)(a1 + 592) | v34 & 8;
        if ( ((unsigned __int8)v11 & 8) != 0 )
          ++v14;
        if ( ((unsigned __int8)v13 & (unsigned __int8)~(_BYTE)v34 & 8) != 0 )
          --v14;
      }
      if ( v7 >= 6 )
        return (char)v11;
      LOBYTE(v11) = a1 + 88;
      v35 = 32LL * v7++;
      *(_DWORD *)(v35 + a2) = 0;
      *(_QWORD *)(v35 + a2 + 8) = FBM_wrap;
      *(_QWORD *)(v35 + a2 + 16) = a1 + 600;
      *(_DWORD *)(a2 + 200) = 1;
    }
    if ( (*(_BYTE *)(a1 + 40) & 0x10) != 0 )
    {
      if ( v7 >= 6 )
        return (char)v11;
      v22 = 32LL * v7;
      *(_DWORD *)(v22 + a2) = 0;
      *(_QWORD *)(v22 + a2 + 8) = &vrheadphone;
      v11 = *(void (__fastcall **)(float *, unsigned int, char *, char *))(a1 + 496);
    }
    else
    {
      if ( (*(_BYTE *)(a1 + 40) & 0x20) == 0 )
      {
        if ( (a3 & 1) != 0 && *(_DWORD *)(a1 + 688) && (a3 & 0x30) == 0 )
        {
          if ( *(_DWORD *)(a1 + 680) )
            goto LABEL_19;
          if ( !*(_DWORD *)(a1 + 264) || (*(_BYTE *)(a1 + 40) & 2) == 0 )
          {
            if ( v7 >= 6 )
              return (char)v11;
            v36 = 32LL * v7++;
            if ( ((*(_DWORD *)(a1 + 568) ^ v15) & 0xFFFFFFF7) != 0 )
            {
              *(_DWORD *)(v36 + a2) = v14 == *(_DWORD *)(a1 + 564);
              v11 = (void (__fastcall *)(float *, unsigned int, char *, char *))channel_matrix_just_rbm_wrap;
            }
            else
            {
              *(_DWORD *)(v36 + a2) = 1;
              v11 = (void (__fastcall *)(float *, unsigned int, char *, char *))reverseBM;
            }
            *(_QWORD *)(v36 + a2 + 8) = v11;
            *(_QWORD *)(v36 + a2 + 16) = a1;
            goto LABEL_19;
          }
          if ( v7 >= 6 )
            return (char)v11;
          v27 = 32LL * v7;
          *(_DWORD *)(v27 + a2) = v14 == *(_DWORD *)(a1 + 564);
          v11 = (void (__fastcall *)(float *, unsigned int, char *, char *))nospkrfill;
        }
        else
        {
          if ( v15 == *(_DWORD *)(a1 + 568) || (a3 & 0x80u) != 0 )
          {
LABEL_19:
            if ( !*(_DWORD *)(a1 + 908) && (a3 & 1) != 0 && *(_DWORD *)(a1 + 680) && (a3 & 0x30) == 0 )
            {
              if ( v7 >= 6 )
                return (char)v11;
              LOBYTE(v11) = a1 + 88;
              v37 = 32LL * v7++;
              *(_DWORD *)(v37 + a2) = 0;
              *(_QWORD *)(v37 + a2 + 8) = FBM_wrap;
              *(_QWORD *)(v37 + a2 + 16) = a1 + 600;
              *(_DWORD *)(a2 + 200) = 0;
            }
            goto LABEL_21;
          }
          if ( v7 >= 6 )
            return (char)v11;
          v27 = 32LL * v7;
          *(_DWORD *)(v27 + a2) = v14 == *(_DWORD *)(a1 + 564);
          v11 = *(void (__fastcall **)(float *, unsigned int, char *, char *))(a1 + 1464);
        }
        *(_QWORD *)(v27 + a2 + 16) = a1;
        *(_QWORD *)(v27 + a2 + 8) = v11;
LABEL_44:
        ++v7;
        goto LABEL_19;
      }
      if ( v7 >= 6 )
        return (char)v11;
      v22 = 32LL * v7;
      *(_DWORD *)(v22 + a2) = 0;
      *(_QWORD *)(v22 + a2 + 8) = ltrtfolddown;
      v11 = *(void (__fastcall **)(float *, unsigned int, char *, char *))(a1 + 504);
    }
    *(_QWORD *)(v22 + a2 + 16) = v11;
    goto LABEL_44;
  }
  *(_QWORD *)(a2 + 200) = 0;
  if ( v7 >= 6 )
    return (char)v11;
  v25 = 32LL * v7++;
  *(_QWORD *)(v25 + a2 + 8) = &spkrfill;
  LOBYTE(v11) = a1 - 120;
  *(_QWORD *)(v25 + a2 + 16) = a1 + 136;
  *(_DWORD *)(v25 + a2) = 0;
  if ( (a3 & 1) != 0 && *(_DWORD *)(a1 + 680) && (a3 & 0x30) == 0 && !*(_DWORD *)(a1 + 908) )
  {
    if ( v7 >= 6 )
      return (char)v11;
    v26 = 32LL * v7;
    LOBYTE(v11) = a1 + 88;
    ++v7;
    *(_DWORD *)(v26 + a2) = 0;
    *(_QWORD *)(v26 + a2 + 8) = FBM_wrap;
    *(_QWORD *)(v26 + a2 + 16) = a1 + 600;
  }
LABEL_21:
  if ( (a3 & 0x40) != 0 && !*(_DWORD *)(a1 + 904) )
  {
    if ( v7 >= 6 )
      return (char)v11;
    v38 = 32LL * v7++;
    *(_DWORD *)(v38 + a2) = (*(_DWORD *)(a1 + 52) & 1) == 0;
    *(_QWORD *)(v38 + a2 + 8) = spkrcorr_wrap;
    v11 = *(void (__fastcall **)(float *, unsigned int, char *, char *))(a1 + 56);
    *(_QWORD *)(v38 + a2 + 16) = v11;
  }
  if ( (a3 & 8) != 0 )
  {
    if ( (int)v7 >= 6 )
      return (char)v11;
    v39 = 32LL * (int)v7++;
    *(_DWORD *)(v39 + a2) = *(_QWORD *)(a1 + 72) == 0;
    *(_QWORD *)(v39 + a2 + 8) = &roomcorr_wrap;
    LOBYTE(v11) = a1 + 64;
    *(_QWORD *)(v39 + a2 + 16) = a1 + 64;
  }
  if ( (a3 & 0x200) == 0 )
    *(_DWORD *)(a2 + 212) = 1065353216;
  if ( *(_DWORD *)(a2 + 208) )
  {
    if ( (int)v7 >= 6 )
      return (char)v11;
    v11 = delaygain;
  }
  else
  {
    v16 = *(float *)(a2 + 212);
    if ( v16 >= 0.99 && v16 <= 1.01 )
      goto LABEL_28;
    if ( (int)v7 >= 6 )
      return (char)v11;
    v11 = (void (__fastcall *)(float *, unsigned int, char *, char *))gain;
  }
  v32 = 32LL * (int)v7++;
  *(_QWORD *)(v32 + a2 + 8) = v11;
  LOBYTE(v11) = a1 + 104;
  *(_QWORD *)(v32 + a2 + 16) = a1 + 104;
  *(_DWORD *)(v32 + a2) = 1;
LABEL_28:
  if ( (a3 & 0x100) != 0 )
  {
    if ( (int)v7 >= 6 )
      return (char)v11;
    v19 = 32LL * (int)v7++;
    *(_QWORD *)(v19 + a2 + 8) = &LEQ_process;
    LOBYTE(v11) = a1 + 16;
    *(_QWORD *)(v19 + a2 + 16) = a1 + 272;
    *(_DWORD *)(v19 + a2) = 0;
  }
  if ( *(_DWORD *)(a1 + 448) )
  {
    if ( (int)v7 >= 6 )
      return (char)v11;
    v3 = *(_DWORD *)(a1 + 464);
    v11 = (void (__fastcall *)(float *, unsigned int, char *, char *))(32LL * (int)v7++);
    *(_DWORD *)((char *)v11 + a2) = 0;
    *(_QWORD *)((char *)v11 + a2 + 8) = add_phantom_zeroes;
    *(_QWORD *)((char *)v11 + a2 + 16) = a1;
  }
  *(_DWORD *)(a2 + 192) = v7;
  v17 = 1;
  if ( v6 != v3 )
  {
    LODWORD(v28) = -1;
    v29 = v7 - 1;
    v30 = 0;
    if ( (int)(v7 - 1) >= 0 )
    {
      do
      {
        v31 = *(_DWORD *)(32LL * (unsigned int)v29 + a2);
        LODWORD(v11) = v29;
        if ( !v31 )
          LODWORD(v11) = v28;
        v28 = (int)v11;
        LOBYTE(v11) = v30 + 1;
        if ( !v31 )
          ++v30;
        --v29;
      }
      while ( v29 >= 0 );
      if ( (_DWORD)v28 != -1 && (v30 & 1) == 0 )
      {
        LOBYTE(v11) = 32 * v28;
        *(_DWORD *)(32 * v28 + a2) = 0;
      }
    }
  }
  for ( i = v7 - 1; i >= 0; *(_DWORD *)(v20 + a2 + 24) = v21 )
  {
    v20 = 32LL * (unsigned int)i;
    *(_DWORD *)(v20 + a2 + 28) = v17;
    if ( *(_DWORD *)(v20 + a2) )
    {
      v21 = v17;
    }
    else if ( i || v6 == v3 )
    {
      LODWORD(v11) = v12;
      v21 = v12;
      v12 = v17;
      v17 = (int)v11;
    }
    else
    {
      v21 = 0;
    }
    --i;
  }
  return (char)v11;
}

```

## disassembly

```asm
0x180008084  push    rbx
0x180008086  push    rbp
0x180008087  push    rsi
0x180008088  push    rdi
0x180008089  push    r12
0x18000808b  push    r13
0x18000808d  push    r14
0x18000808f  push    r15
0x180008091  mov     r13d, [rcx+234h]
0x180008098  xor     edi, edi
0x18000809a  mov     ebx, r8d
0x18000809d  mov     r9, rcx
0x1800080a0  cmp     [rcx+1C4h], edi
0x1800080a6  jnz     loc_18000830A
0x1800080ac  mov     r12d, [rcx+21Ch]
0x1800080b3  mov     r8d, edi
0x1800080b6  mov     r10d, ebx
0x1800080b9  mov     dword ptr [rdx+0D4h], 3F800000h
0x1800080c3  mov     [rdx+0D0h], edi
0x1800080c9  not     r10d
0x1800080cc  mov     eax, [rcx+28h]
0x1800080cf  and     eax, r10d
0x1800080d2  test    al, 8
0x1800080d4  jnz     loc_1800084EB
0x1800080da  movss   xmm0, cs:__real@3f800000
0x1800080e2  mov     eax, [rcx+37Ch]
0x1800080e8  test    eax, eax
0x1800080ea  jnz     loc_1800084FD
0x1800080f0  cmp     [rcx+2ACh], edi
0x1800080f6  jnz     loc_1800084FD
0x1800080fc  mov     eax, [rcx+28h]
0x1800080ff  mov     r11d, edi
0x180008102  and     eax, r10d
0x180008105  bt      eax, 8
0x180008109  jb      loc_18000852C
0x18000810f  test    byte ptr [rcx+28h], 1
0x180008113  jnz     loc_180008542
0x180008119  mov     r14d, ebx
0x18000811c  lea     r11, spkrcorr_wrap
0x180008123  and     r14d, 40h
0x180008127  jnz     loc_180008579
0x18000812d  cmp     [r9+37Ch], edi
0x180008134  jnz     loc_1800085AF
0x18000813a  mov     r15d, 2
0x180008140  lea     r10d, [r15+4]
0x180008144  test    [r9+28h], r15b
0x180008148  jnz     loc_18000833B
0x18000814e  mov     edi, [r9+220h]
0x180008155  lea     rbp, FBM_wrap
0x18000815c  mov     r11d, [r9+21Ch]
0x180008163  xor     eax, eax
0x180008165  mov     esi, edi
0x180008167  cmp     [r9+38Ch], eax
0x18000816e  jnz     loc_1800085BE
0x180008174  xor     edi, edi
0x180008176  test    byte ptr [r9+28h], 10h
0x18000817b  jnz     loc_1800082B3
0x180008181  test    byte ptr [r9+28h], 20h
0x180008186  jnz     loc_1800082E2
0x18000818c  test    bl, 1
0x18000818f  jnz     loc_18000865A
0x180008195  cmp     esi, [r9+238h]
0x18000819c  jnz     loc_1800083CF
0x1800081a2  cmp     [r9+38Ch], edi
0x1800081a9  jnz     short loc_1800081B4
0x1800081ab  test    bl, 1
0x1800081ae  jnz     loc_18000870E
0x1800081b4  lea     r11, spkrcorr_wrap
0x1800081bb  test    r14d, r14d
0x1800081be  jnz     loc_180008756
0x1800081c4  test    bl, 8
0x1800081c7  jnz     loc_180008795
0x1800081cd  bt      ebx, 9
0x1800081d1  jb      short loc_1800081DD
0x1800081d3  mov     dword ptr [rdx+0D4h], 3F800000h
0x1800081dd  cmp     [rdx+0D0h], edi
0x1800081e3  jnz     loc_1800087CE
0x1800081e9  movss   xmm0, dword ptr [rdx+0D4h]
0x1800081f1  cvtps2pd xmm0, xmm0
0x1800081f4  comisd  xmm0, cs:__real@3fefae147ae147ae
0x1800081fc  jb      loc_180008472
0x180008202  comisd  xmm0, cs:__real@3ff028f5c28f5c29
0x18000820a  ja      loc_180008472
0x180008210  bt      ebx, 8
0x180008214  jb      short loc_18000824B
0x180008216  cmp     [r9+1C0h], edi
0x18000821d  jnz     loc_1800084A6
0x180008223  mov     [rdx+0C0h], r8d
0x18000822a  mov     r9d, 1
0x180008230  cmp     r12d, r13d
0x180008233  jnz     loc_180008414
0x180008239  sub     r8d, r9d
0x18000823c  jns     short loc_180008277
0x18000823e  pop     r15
0x180008240  pop     r14
0x180008242  pop     r13
0x180008244  pop     r12
0x180008246  pop     rdi
0x180008247  pop     rsi
0x180008248  pop     rbp
0x180008249  pop     rbx
0x18000824a  retn
0x18000824b  cmp     r8d, r10d
0x18000824e  jge     short loc_18000823E
0x180008250  movsxd  rcx, r8d
0x180008253  lea     rax, LEQ_process
0x18000825a  shl     rcx, 5
0x18000825e  inc     r8d
0x180008261  mov     [rcx+rdx+8], rax
0x180008266  lea     rax, [r9+110h]
0x18000826d  mov     [rcx+rdx+10h], rax
0x180008272  mov     [rcx+rdx], edi
0x180008275  jmp     short loc_180008216
0x180008277  mov     ecx, r8d
0x18000827a  shl     rcx, 5
0x18000827e  mov     [rcx+rdx+1Ch], r9d
0x180008283  cmp     [rcx+rdx], edi
0x180008286  jnz     loc_18000840C
0x18000828c  test    r8d, r8d
0x18000828f  jnz     short loc_18000829A
0x180008291  cmp     r12d, r13d
0x180008294  jnz     loc_18000846A
0x18000829a  mov     eax, r15d
0x18000829d  mov     r10d, r15d
0x1800082a0  mov     r15d, r9d
0x1800082a3  mov     r9d, eax
0x1800082a6  sub     r8d, 1
0x1800082aa  mov     [rcx+rdx+18h], r10d
0x1800082af  js      short loc_18000823E
0x1800082b1  jmp     short loc_180008277
0x1800082b3  cmp     r8d, r10d
0x1800082b6  jnb     short loc_18000823E
0x1800082b8  lea     rax, vrheadphone
0x1800082bf  mov     ecx, r8d
0x1800082c2  shl     rcx, 5
0x1800082c6  mov     [rcx+rdx], edi
0x1800082c9  mov     [rcx+rdx+8], rax
0x1800082ce  mov     rax, [r9+1F0h]
0x1800082d5  mov     [rcx+rdx+10h], rax
0x1800082da  inc     r8d
0x1800082dd  jmp     loc_1800081A2
0x1800082e2  cmp     r8d, r10d
0x1800082e5  jnb     loc_18000823E
0x1800082eb  lea     rax, ltrtfolddown
0x1800082f2  mov     ecx, r8d
0x1800082f5  shl     rcx, 5
0x1800082f9  mov     [rcx+rdx], edi
0x1800082fc  mov     [rcx+rdx+8], rax
0x180008301  mov     rax, [r9+1F8h]
0x180008308  jmp     short loc_1800082D5
0x18000830a  mov     eax, [rcx+1C8h]
0x180008310  mov     r8d, 1
0x180008316  mov     r12d, [rcx+1D8h]
0x18000831d  mov     [rdx+10h], r9
0x180008321  test    eax, eax
0x180008323  jz      loc_1800084D9
0x180008329  mov     [rdx], edi
0x18000832b  lea     rax, phantom_matrix_wrap
0x180008332  mov     [rdx+8], rax
0x180008336  jmp     loc_1800080B6
0x18000833b  mov     [rdx+0C8h], rdi
0x180008342  cmp     r8d, r10d
0x180008345  jnb     loc_18000823E
0x18000834b  mov     ecx, r8d
0x18000834e  lea     rax, spkrfill
0x180008355  shl     rcx, 5
0x180008359  inc     r8d
0x18000835c  mov     [rcx+rdx+8], rax
0x180008361  lea     rax, [r9+88h]
0x180008368  mov     [rcx+rdx+10h], rax
0x18000836d  mov     [rcx+rdx], edi
0x180008370  test    bl, 1
0x180008373  jz      loc_1800081BB
0x180008379  cmp     [r9+2A8h], edi
0x180008380  jz      loc_1800081BB
0x180008386  test    bl, 30h
0x180008389  jnz     loc_1800081BB
0x18000838f  cmp     [r9+38Ch], edi
0x180008396  jnz     loc_1800081BB
0x18000839c  cmp     r8d, r10d
0x18000839f  jnb     loc_18000823E
0x1800083a5  mov     ecx, r8d
0x1800083a8  lea     rbp, FBM_wrap
0x1800083af  shl     rcx, 5
0x1800083b3  lea     rax, [r9+258h]
0x1800083ba  inc     r8d
0x1800083bd  mov     [rcx+rdx], edi
0x1800083c0  mov     [rcx+rdx+8], rbp
0x1800083c5  mov     [rcx+rdx+10h], rax
0x1800083ca  jmp     loc_1800081BB
0x1800083cf  test    bl, bl
0x1800083d1  js      loc_1800081A2
0x1800083d7  cmp     r8d, r10d
0x1800083da  jnb     loc_18000823E
0x1800083e0  mov     eax, edi
0x1800083e2  mov     ecx, r8d
0x1800083e5  shl     rcx, 5
0x1800083e9  cmp     r11d, [r9+234h]
0x1800083f0  setz    al
0x1800083f3  mov     [rcx+rdx], eax
0x1800083f6  mov     rax, [r9+5B8h]
0x1800083fd  mov     [rcx+rdx+10h], r9
0x180008402  mov     [rcx+rdx+8], rax
0x180008407  jmp     loc_1800082DA
0x18000840c  mov     r10d, r9d
0x18000840f  jmp     loc_1800082A6
0x180008414  or      r11d, 0FFFFFFFFh
0x180008418  lea     ebx, [r8-1]
0x18000841c  mov     r10d, edi
0x18000841f  test    ebx, ebx
0x180008421  js      loc_180008239
0x180008427  mov     eax, ebx
0x180008429  shl     rax, 5
0x18000842d  mov     ecx, [rax+rdx]
0x180008430  test    ecx, ecx
0x180008432  mov     eax, ebx
0x180008434  cmovz   eax, r11d
0x180008438  movsxd  r11, eax
0x18000843b  lea     eax, [r10+1]
0x18000843f  cmovz   r10d, eax
0x180008443  sub     ebx, r9d
0x180008446  jns     short loc_180008427
0x180008448  cmp     r11d, 0FFFFFFFFh
0x18000844c  jz      loc_180008239
0x180008452  test    r9b, r10b
0x180008455  jnz     loc_180008239
0x18000845b  mov     rax, r11
0x18000845e  shl     rax, 5
0x180008462  mov     [rax+rdx], edi
0x180008465  jmp     loc_180008239
0x18000846a  mov     r10d, edi
0x18000846d  jmp     loc_1800082A6
0x180008472  cmp     r8d, r10d
0x180008475  jge     loc_18000823E
0x18000847b  lea     rax, gain
0x180008482  movsxd  rcx, r8d
0x180008485  shl     rcx, 5
0x180008489  inc     r8d
0x18000848c  mov     [rcx+rdx+8], rax
0x180008491  lea     rax, [r9+68h]
0x180008495  mov     [rcx+rdx+10h], rax
0x18000849a  mov     dword ptr [rcx+rdx], 1
0x1800084a1  jmp     loc_180008210
0x1800084a6  cmp     r8d, r10d
0x1800084a9  jge     loc_18000823E
0x1800084af  mov     r13d, [r9+1D0h]
0x1800084b6  lea     rcx, add_phantom_zeroes
0x1800084bd  movsxd  rax, r8d
0x1800084c0  shl     rax, 5
0x1800084c4  inc     r8d
0x1800084c7  mov     [rax+rdx], edi
0x1800084ca  mov     [rax+rdx+8], rcx
0x1800084cf  mov     [rax+rdx+10h], r9
0x1800084d4  jmp     loc_180008223
0x1800084d9  mov     dword ptr [rdx], 1
0x1800084df  lea     rax, remove_phantom_zeroes
0x1800084e6  jmp     loc_180008332
0x1800084eb  movss   xmm0, dword ptr [rcx+58h]
0x1800084f0  movss   dword ptr [rdx+0D4h], xmm0
0x1800084f8  jmp     loc_1800080E2
0x1800084fd  test    r10b, 1
0x180008501  jnz     short loc_180008517
0x180008503  test    eax, eax
0x180008505  jz      loc_1800080FC
0x18000850b  cmp     [rcx+2B0h], edi
0x180008511  jnz     loc_1800080FC
0x180008517  mulss   xmm0, dword ptr [rcx+278h]
0x18000851f  movss   dword ptr [rdx+0D4h], xmm0
0x180008527  jmp     loc_1800080FC
0x18000852c  mov     r11d, [rcx+14Ch]
0x180008533  shr     r11d, 1
0x180008536  mov     [rdx+0D0h], r11d
0x18000853d  jmp     loc_18000810F
0x180008542  cmp     [rcx+2A8h], edi
0x180008548  jz      loc_180008119
0x18000854e  test    byte ptr [rcx+28h], 30h
0x180008552  setz    cl
0x180008555  test    r10b, 1
0x180008559  setnz   al
0x18000855c  test    al, cl
0x18000855e  jz      loc_180008119
0x180008564  mov     ecx, [r9+368h]
0x18000856b  add     ecx, r11d
0x18000856e  mov     [rdx+0D0h], ecx
0x180008574  jmp     loc_180008119
0x180008579  cmp     [r9+388h], edi
0x180008580  jz      loc_18000812D
0x180008586  mov     eax, [r9+34h]
0x18000858a  mov     ecx, r8d
0x18000858d  not     eax
0x18000858f  shl     rcx, 5
0x180008593  and     eax, 1
0x180008596  inc     r8d
0x180008599  mov     [rcx+rdx], eax
0x18000859c  mov     [rcx+rdx+8], r11
0x1800085a1  mov     rax, [r9+38h]
0x1800085a5  mov     [rcx+rdx+10h], rax
0x1800085aa  jmp     loc_18000812D
0x1800085af  mov     dword ptr [rdx+0CCh], 1
0x1800085b9  jmp     loc_18000813A
  ... truncated ...
```
