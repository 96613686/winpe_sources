# CopyFont

- ea: `0x180036b00`
- end: `0x180036ff5`
- name: `CopyFont`
- size: `1269`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180036b00`
- `0x180037140`
- `0x18003725c`
- `0x18003739c`
- `0x180038180`
- `0x180038b18`
- `0x180038c4c`
- `0x18003d7e4`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall CopyFont(int *a1, __int64 a2, __int64 a3, double a4)
{
  _BYTE *v6; // r14
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  unsigned int v10; // esi
  unsigned int v11; // ebp
  _BYTE *v12; // r12
  _OWORD *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rsi
  __int16 v17; // bp
  __int16 v18; // si
  _BYTE *v19; // rax
  _BYTE *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rax
  __int64 v23; // rdx
  _BYTE *v24; // rcx
  __int64 v25; // rdx
  _BYTE *v26; // rax
  _BYTE *v27; // rax
  _BYTE *v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  _OWORD *v32; // rax
  _OWORD *v33; // rcx
  __int128 v34; // xmm1
  __int16 BaseFont; // ax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v41; // rcx
  __int64 v42; // [rsp+80h] [rbp+8h] BYREF

  if ( a1[2] < 3 )
    return 0;
  v6 = *(_BYTE **)(a2 + 16);
  if ( !v6 || !*v6 )
    return 0;
  v7 = *a1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 != 1 )
          return 0;
        v10 = 112;
      }
      else
      {
        v10 = 512;
      }
    }
    else
    {
      v10 = 104;
    }
    v11 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 6) + 8LL) + 8LL);
  }
  else
  {
    v10 = 376;
    v11 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 6) + 8LL) + 16LL);
  }
  v12 = *(_BYTE **)(a2 + 40);
  v13 = (_OWORD *)UFLNewPtr(*((_QWORD *)a1 + 4), 208);
  v14 = (__int64)v13;
  if ( !v13 )
    return 0;
  *v13 = *(_OWORD *)a1;
  v13[1] = *((_OWORD *)a1 + 1);
  v13[2] = *((_OWORD *)a1 + 2);
  v13[3] = *((_OWORD *)a1 + 3);
  v13[4] = *((_OWORD *)a1 + 4);
  v13[5] = *((_OWORD *)a1 + 5);
  v13[6] = *((_OWORD *)a1 + 6);
  v13[7] = *((_OWORD *)a1 + 7);
  v13[8] = *((_OWORD *)a1 + 8);
  v13[9] = *((_OWORD *)a1 + 9);
  v13[10] = *((_OWORD *)a1 + 10);
  v13[11] = *((_OWORD *)a1 + 11);
  v13[12] = *((_OWORD *)a1 + 12);
  if ( (unsigned __int16)NewFont(v13, v10, v11) )
  {
    vDeleteFont(v14);
LABEL_75:
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v14 + 32) + 8LL))(
      v14 - 8,
      *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL));
    return 0;
  }
  v15 = -1;
  *(_QWORD *)(v14 + 56) = 0;
  v16 = -1;
  *(_QWORD *)(v14 + 72) = 0;
  v17 = 0;
  *(_QWORD *)(v14 + 80) = 0;
  do
    ++v16;
  while ( v6[v16] );
  v18 = v16 + 1;
  if ( v12 )
  {
    do
      ++v15;
    while ( v12[v15] );
    v17 = v15 + 1;
  }
  v19 = (_BYTE *)UFLNewPtr(*(_QWORD *)(v14 + 32), (unsigned int)(v17 + v18));
  *(_QWORD *)(v14 + 56) = v19;
  v20 = v19;
  if ( v19 )
  {
    v21 = 2147483646;
    if ( v18 )
    {
      if ( (unsigned __int64)v18 <= 0x7FFFFFFF )
      {
        v22 = 2147483646;
        v23 = v18;
        do
        {
          if ( !v22 )
            break;
          if ( !*v6 )
            break;
          *v20++ = *v6++;
          --v22;
          --v23;
        }
        while ( v23 );
        v19 = v20 - 1;
        if ( v23 )
          v19 = v20;
      }
      *v19 = 0;
    }
    if ( v12 )
    {
      v24 = (_BYTE *)(v18 + *(_QWORD *)(v14 + 56));
      v25 = v17;
      *(_QWORD *)(v14 + 72) = v24;
      if ( v17 )
      {
        if ( (unsigned __int64)v17 > 0x7FFFFFFF )
        {
          *v24 = 0;
        }
        else
        {
          do
          {
            if ( !v21 )
              break;
            if ( !*v12 )
              break;
            *v24++ = *v12++;
            --v21;
            --v25;
          }
          while ( v25 );
          v26 = v24 - 1;
          if ( v25 )
            v26 = v24;
          *v26 = 0;
        }
      }
    }
  }
  v27 = *(_BYTE **)(v14 + 56);
  if ( !v27 || !*v27 )
  {
    vDeleteFont(v14);
    goto LABEL_73;
  }
  v28 = *(_BYTE **)(v14 + 72);
  if ( v28 && *v28 )
    v29 = 0;
  else
    v29 = UFLNewPtr(*(_QWORD *)(v14 + 32), 32);
  *(_QWORD *)(v14 + 80) = v29;
  *(_QWORD *)(v14 + 16) = *(_QWORD *)(a2 + 24);
  if ( ((*(_DWORD *)a2 - 5) & 0xFFFFFFF6) != 0 )
    goto LABEL_55;
  *(_DWORD *)(v14 + 4) = *(_DWORD *)a2;
  if ( (unsigned int)(*(_DWORD *)a2 - 5) <= 1 )
  {
    v30 = UFLNewPtr(*(_QWORD *)(v14 + 32), 376);
    if ( v30 )
    {
      v31 = 2;
      v32 = *(_OWORD **)(*((_QWORD *)a1 + 6) + 8LL);
      v33 = (_OWORD *)v30;
      do
      {
        *v33 = *v32;
        v33[1] = v32[1];
        v33[2] = v32[2];
        v33[3] = v32[3];
        v33[4] = v32[4];
        v33[5] = v32[5];
        v33[6] = v32[6];
        v34 = v32[7];
        v32 += 8;
        v33[7] = v34;
        v33 += 8;
        --v31;
      }
      while ( v31 );
      *v33 = *v32;
      v33[1] = v32[1];
      v33[2] = v32[2];
      v33[3] = v32[3];
      v33[4] = v32[4];
      v33[5] = v32[5];
      v33[6] = v32[6];
      *((_QWORD *)v33 + 14) = *((_QWORD *)v32 + 14);
      *(_QWORD *)(v30 + 80) = *(_QWORD *)(a2 + 8);
      *(_QWORD *)(*(_QWORD *)(v14 + 48) + 8LL) = v30;
      goto LABEL_54;
    }
    vDeleteFont(v14);
    v36 = *(_QWORD *)(v14 + 72);
    if ( v36 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v14 + 32) + 8LL))(
        v36 - 8,
        *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL));
LABEL_73:
    v41 = *(_QWORD *)(v14 + 56);
    if ( v41 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v14 + 32) + 8LL))(
        v41 - 8,
        *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL));
    goto LABEL_75;
  }
LABEL_54:
  *(_DWORD *)(v14 + 8) = 2;
LABEL_55:
  if ( ((*(_DWORD *)a2 - 5) & 0xFFFFFFF6) != 0 )
  {
    BaseFont = ReEncodePSFont(a1, *(_QWORD *)(v14 + 56), *(_QWORD *)(v14 + 72));
  }
  else
  {
    v42 = 0;
    HostFontValidateUFO(v14, &v42);
    if ( (unsigned int)(*(_DWORD *)(v14 + 4) - 13) <= 1 )
      BaseFont = T42CreateBaseFont(v14, 0, 0, a4, (const char *)v42);
    else
      BaseFont = CFFCreateBaseFont(v14, 0, 0, (const char *)v42);
  }
  if ( BaseFont )
  {
    vDeleteFont(v14);
    if ( (unsigned int)(*(_DWORD *)a2 - 5) <= 1 )
    {
      v37 = *(_QWORD *)(*(_QWORD *)(v14 + 48) + 8LL);
      if ( v37 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v14 + 32) + 8LL))(
          v37 - 8,
          *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL));
    }
    v38 = *(_QWORD *)(v14 + 80);
    if ( v38 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v14 + 32) + 8LL))(
        v38 - 8,
        *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL));
    v39 = *(_QWORD *)(v14 + 56);
    if ( v39 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v14 + 32) + 8LL))(
        v39 - 8,
        *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL));
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v14 + 32) + 8LL))(
      v14 - 8,
      *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL));
    return 0;
  }
  return v14;
}

```

## disassembly

```asm
0x180036b00  push    rbx
0x180036b02  push    rbp
0x180036b03  push    rsi
0x180036b04  push    rdi
0x180036b05  push    r12
0x180036b07  push    r13
0x180036b09  push    r14
0x180036b0b  push    r15
0x180036b0d  sub     rsp, 38h
0x180036b11  cmp     dword ptr [rcx+8], 3
0x180036b15  mov     r15, rdx
0x180036b18  mov     rdi, rcx
0x180036b1b  jl      loc_180036FE2
0x180036b21  mov     r14, [rdx+10h]
0x180036b25  xor     r13d, r13d
0x180036b28  test    r14, r14
0x180036b2b  jz      loc_180036FE2
0x180036b31  cmp     [r14], r13b
0x180036b34  jz      loc_180036FE2
0x180036b3a  mov     ecx, [rcx]
0x180036b3c  test    ecx, ecx
0x180036b3e  jz      short loc_180036B71
0x180036b40  sub     ecx, 1
0x180036b43  jz      short loc_180036B5F
0x180036b45  sub     ecx, 1
0x180036b48  jz      short loc_180036B58
0x180036b4a  cmp     ecx, 1
0x180036b4d  jnz     loc_180036FE2
0x180036b53  lea     esi, [rcx+6Fh]
0x180036b56  jmp     short loc_180036B64
0x180036b58  mov     esi, 200h
0x180036b5d  jmp     short loc_180036B64
0x180036b5f  mov     esi, 68h ; 'h'
0x180036b64  mov     rax, [rdi+30h]
0x180036b68  mov     rcx, [rax+8]
0x180036b6c  mov     ebp, [rcx+8]
0x180036b6f  jmp     short loc_180036B81
0x180036b71  mov     rax, [rdi+30h]
0x180036b75  mov     esi, 178h
0x180036b7a  mov     rcx, [rax+8]
0x180036b7e  mov     ebp, [rcx+10h]
0x180036b81  mov     r12, [rdx+28h]
0x180036b85  mov     edx, 0D0h
0x180036b8a  mov     rcx, [rdi+20h]
0x180036b8e  call    UFLNewPtr
0x180036b93  mov     rbx, rax
0x180036b96  test    rax, rax
0x180036b99  jz      loc_180036FE2
0x180036b9f  movups  xmm0, xmmword ptr [rdi]
0x180036ba2  mov     r8d, ebp
0x180036ba5  mov     edx, esi
0x180036ba7  mov     rcx, rax
0x180036baa  movups  xmmword ptr [rax], xmm0
0x180036bad  movups  xmm1, xmmword ptr [rdi+10h]
0x180036bb1  movups  xmmword ptr [rax+10h], xmm1
0x180036bb5  movups  xmm0, xmmword ptr [rdi+20h]
0x180036bb9  movups  xmmword ptr [rax+20h], xmm0
0x180036bbd  movups  xmm1, xmmword ptr [rdi+30h]
0x180036bc1  movups  xmmword ptr [rax+30h], xmm1
0x180036bc5  movups  xmm0, xmmword ptr [rdi+40h]
0x180036bc9  movups  xmmword ptr [rax+40h], xmm0
0x180036bcd  movups  xmm1, xmmword ptr [rdi+50h]
0x180036bd1  movups  xmmword ptr [rax+50h], xmm1
0x180036bd5  movups  xmm0, xmmword ptr [rdi+60h]
0x180036bd9  movups  xmmword ptr [rax+60h], xmm0
0x180036bdd  movups  xmm1, xmmword ptr [rdi+70h]
0x180036be1  movups  xmmword ptr [rax+70h], xmm1
0x180036be5  movups  xmm0, xmmword ptr [rdi+80h]
0x180036bec  movups  xmmword ptr [rax+80h], xmm0
0x180036bf3  movups  xmm1, xmmword ptr [rdi+90h]
0x180036bfa  movups  xmmword ptr [rax+90h], xmm1
0x180036c01  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180036c08  movups  xmmword ptr [rax+0A0h], xmm0
0x180036c0f  movups  xmm1, xmmword ptr [rdi+0B0h]
0x180036c16  movups  xmmword ptr [rax+0B0h], xmm1
0x180036c1d  movups  xmm0, xmmword ptr [rdi+0C0h]
0x180036c24  movups  xmmword ptr [rax+0C0h], xmm0
0x180036c2b  call    NewFont
0x180036c30  test    ax, ax
0x180036c33  jz      short loc_180036C42
0x180036c35  mov     rcx, rbx
0x180036c38  call    vDeleteFont
0x180036c3d  jmp     loc_180036FCD
0x180036c42  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036c46  mov     [rbx+38h], r13
0x180036c4a  mov     rsi, rax
0x180036c4d  mov     [rbx+48h], r13
0x180036c51  mov     ebp, r13d
0x180036c54  mov     [rbx+50h], r13
0x180036c58  inc     rsi
0x180036c5b  cmp     [r14+rsi], r13b
0x180036c5f  jnz     short loc_180036C58
0x180036c61  mov     ecx, 1
0x180036c66  add     si, cx
0x180036c69  test    r12, r12
0x180036c6c  jz      short loc_180036C7A
0x180036c6e  inc     rax
0x180036c71  cmp     [r12+rax], r13b
0x180036c75  jnz     short loc_180036C6E
0x180036c77  lea     ebp, [rcx+rax]
0x180036c7a  mov     rcx, [rbx+20h]
0x180036c7e  movsx   edx, si
0x180036c81  movsx   eax, bp
0x180036c84  add     edx, eax
0x180036c86  call    UFLNewPtr
0x180036c8b  mov     [rbx+38h], rax
0x180036c8f  mov     rcx, rax
0x180036c92  test    rax, rax
0x180036c95  jz      loc_180036D3E
0x180036c9b  mov     r11d, 7FFFFFFFh
0x180036ca1  movsx   r8, si
0x180036ca5  lea     r9d, [r11-1]
0x180036ca9  test    r8, r8
0x180036cac  jz      short loc_180036CE6
0x180036cae  cmp     r8, r11
0x180036cb1  ja      short loc_180036CE3
0x180036cb3  mov     eax, r9d
0x180036cb6  mov     rdx, r8
0x180036cb9  test    rax, rax
0x180036cbc  jz      short loc_180036CD8
0x180036cbe  mov     r10b, [r14]
0x180036cc1  test    r10b, r10b
0x180036cc4  jz      short loc_180036CD8
0x180036cc6  mov     [rcx], r10b
0x180036cc9  inc     r14
0x180036ccc  inc     rcx
0x180036ccf  dec     rax
0x180036cd2  sub     rdx, 1
0x180036cd6  jnz     short loc_180036CB9
0x180036cd8  test    rdx, rdx
0x180036cdb  lea     rax, [rcx-1]
0x180036cdf  cmovnz  rax, rcx
0x180036ce3  mov     [rax], r13b
0x180036ce6  test    r12, r12
0x180036ce9  jz      short loc_180036D3E
0x180036ceb  mov     rcx, [rbx+38h]
0x180036cef  add     rcx, r8
0x180036cf2  movsx   rdx, bp
0x180036cf6  mov     [rbx+48h], rcx
0x180036cfa  test    bp, bp
0x180036cfd  jz      short loc_180036D36
0x180036cff  cmp     rdx, r11
0x180036d02  ja      short loc_180036D3B
0x180036d04  test    r9, r9
0x180036d07  jz      short loc_180036D26
0x180036d09  mov     al, [r12]
0x180036d0d  test    al, al
0x180036d0f  jz      short loc_180036D26
0x180036d11  mov     [rcx], al
0x180036d13  mov     eax, 1
0x180036d18  add     rcx, rax
0x180036d1b  add     r12, rax
0x180036d1e  sub     r9, rax
0x180036d21  sub     rdx, rax
0x180036d24  jnz     short loc_180036D04
0x180036d26  test    rdx, rdx
0x180036d29  lea     rax, [rcx-1]
0x180036d2d  cmovnz  rax, rcx
0x180036d31  mov     [rax], r13b
0x180036d34  jmp     short loc_180036D3E
0x180036d36  test    rdx, rdx
0x180036d39  jz      short loc_180036D3E
0x180036d3b  mov     [rcx], r13b
0x180036d3e  mov     rax, [rbx+38h]
0x180036d42  test    rax, rax
0x180036d45  jz      loc_180036FA7
0x180036d4b  cmp     [rax], r13b
0x180036d4e  jz      loc_180036FA7
0x180036d54  mov     rax, [rbx+48h]
0x180036d58  test    rax, rax
0x180036d5b  jz      short loc_180036D67
0x180036d5d  cmp     [rax], r13b
0x180036d60  jz      short loc_180036D67
0x180036d62  mov     rax, r13
0x180036d65  jmp     short loc_180036D75
0x180036d67  mov     rcx, [rbx+20h]
0x180036d6b  mov     edx, 20h ; ' '
0x180036d70  call    UFLNewPtr
0x180036d75  mov     [rbx+50h], rax
0x180036d79  mov     ebp, 0FFFFFFF6h
0x180036d7e  mov     rax, [r15+18h]
0x180036d82  mov     [rbx+10h], rax
0x180036d86  mov     ecx, [r15]
0x180036d89  lea     eax, [rcx-5]
0x180036d8c  test    ebp, eax
0x180036d8e  jnz     loc_180036E72
0x180036d94  mov     [rbx+4], ecx
0x180036d97  mov     esi, 2
0x180036d9c  mov     eax, [r15]
0x180036d9f  sub     eax, 5
0x180036da2  cmp     eax, 1
0x180036da5  ja      loc_180036E6F
0x180036dab  mov     rcx, [rbx+20h]
0x180036daf  mov     edx, 178h
0x180036db4  call    UFLNewPtr
0x180036db9  mov     rdx, rax
0x180036dbc  test    rax, rax
0x180036dbf  jz      loc_180036E8E
0x180036dc5  mov     rcx, [rdi+30h]
0x180036dc9  lea     r9d, [rsi+7Eh]
0x180036dcd  mov     r8d, esi
0x180036dd0  mov     rax, [rcx+8]
0x180036dd4  mov     rcx, rdx
0x180036dd7  movups  xmm0, xmmword ptr [rax]
0x180036dda  movups  xmmword ptr [rcx], xmm0
0x180036ddd  movups  xmm1, xmmword ptr [rax+10h]
0x180036de1  movups  xmmword ptr [rcx+10h], xmm1
0x180036de5  movups  xmm0, xmmword ptr [rax+20h]
0x180036de9  movups  xmmword ptr [rcx+20h], xmm0
0x180036ded  movups  xmm1, xmmword ptr [rax+30h]
0x180036df1  movups  xmmword ptr [rcx+30h], xmm1
0x180036df5  movups  xmm0, xmmword ptr [rax+40h]
0x180036df9  movups  xmmword ptr [rcx+40h], xmm0
0x180036dfd  movups  xmm1, xmmword ptr [rax+50h]
0x180036e01  movups  xmmword ptr [rcx+50h], xmm1
0x180036e05  movups  xmm0, xmmword ptr [rax+60h]
0x180036e09  movups  xmmword ptr [rcx+60h], xmm0
0x180036e0d  movups  xmm1, xmmword ptr [rax+70h]
0x180036e11  add     rax, r9
0x180036e14  movups  xmmword ptr [rcx+70h], xmm1
0x180036e18  add     rcx, r9
0x180036e1b  sub     r8, 1
0x180036e1f  jnz     short loc_180036DD7
0x180036e21  movups  xmm0, xmmword ptr [rax]
0x180036e24  movups  xmmword ptr [rcx], xmm0
0x180036e27  movups  xmm1, xmmword ptr [rax+10h]
0x180036e2b  movups  xmmword ptr [rcx+10h], xmm1
0x180036e2f  movups  xmm0, xmmword ptr [rax+20h]
0x180036e33  movups  xmmword ptr [rcx+20h], xmm0
0x180036e37  movups  xmm1, xmmword ptr [rax+30h]
0x180036e3b  movups  xmmword ptr [rcx+30h], xmm1
0x180036e3f  movups  xmm0, xmmword ptr [rax+40h]
0x180036e43  movups  xmmword ptr [rcx+40h], xmm0
0x180036e47  movups  xmm1, xmmword ptr [rax+50h]
0x180036e4b  movups  xmmword ptr [rcx+50h], xmm1
0x180036e4f  movups  xmm0, xmmword ptr [rax+60h]
0x180036e53  movups  xmmword ptr [rcx+60h], xmm0
0x180036e57  mov     rax, [rax+70h]
0x180036e5b  mov     [rcx+70h], rax
0x180036e5f  mov     rax, [r15+8]
0x180036e63  mov     [rdx+50h], rax
0x180036e67  mov     rax, [rbx+30h]
0x180036e6b  mov     [rax+8], rdx
0x180036e6f  mov     [rbx+8], esi
0x180036e72  mov     eax, [r15]
0x180036e75  sub     eax, 5
0x180036e78  test    ebp, eax
0x180036e7a  jz      short loc_180036EBD
0x180036e7c  mov     r8, [rbx+48h]
0x180036e80  mov     rcx, rdi
0x180036e83  mov     rdx, [rbx+38h]
0x180036e87  call    ReEncodePSFont
0x180036e8c  jmp     short loc_180036F0C
0x180036e8e  mov     rcx, rbx
0x180036e91  call    vDeleteFont
0x180036e96  mov     rcx, [rbx+48h]
0x180036e9a  test    rcx, rcx
0x180036e9d  jz      loc_180036FAF
0x180036ea3  mov     rax, [rbx+20h]
0x180036ea7  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180036eab  mov     rdx, [rax+20h]
0x180036eaf  mov     rax, [rax+8]
0x180036eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036eb8  jmp     loc_180036FAF
0x180036ebd  lea     rdx, [rsp+78h+arg_0]
0x180036ec5  mov     [rsp+78h+arg_0], r13
0x180036ecd  mov     rcx, rbx
0x180036ed0  call    HostFontValidateUFO
0x180036ed5  mov     eax, [rbx+4]
0x180036ed8  xor     r8d, r8d
0x180036edb  sub     eax, 0Dh
0x180036ede  xor     edx, edx
0x180036ee0  mov     rcx, rbx; int
0x180036ee3  cmp     eax, 1
0x180036ee6  jbe     short loc_180036EF7
0x180036ee8  mov     r9, [rsp+78h+arg_0]
0x180036ef0  call    CFFCreateBaseFont
0x180036ef5  jmp     short loc_180036F0C
0x180036ef7  mov     rax, [rsp+78h+arg_0]
0x180036eff  xor     r9d, r9d
0x180036f02  mov     [rsp+78h+var_58], rax; __int64
0x180036f07  call    T42CreateBaseFont
0x180036f0c  movzx   ecx, ax
0x180036f0f  cmp     r13w, ax
0x180036f13  jz      loc_180036FA2
0x180036f19  mov     rcx, rbx
0x180036f1c  call    vDeleteFont
0x180036f21  mov     eax, [r15]
0x180036f24  sub     eax, 5
0x180036f27  cmp     eax, 1
0x180036f2a  ja      short loc_180036F4E
0x180036f2c  mov     rax, [rbx+30h]
0x180036f30  mov     rcx, [rax+8]
0x180036f34  test    rcx, rcx
0x180036f37  jz      short loc_180036F4E
0x180036f39  mov     rax, [rbx+20h]
0x180036f3d  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180036f41  mov     rdx, [rax+20h]
0x180036f45  mov     rax, [rax+8]
0x180036f49  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
