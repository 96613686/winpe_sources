# _readDrcInstructionsUniDrc

- ea: `0x180076aa8`
- end: `0x180076ff7`
- name: `_readDrcInstructionsUniDrc`
- size: `1359`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180076548`
- `0x1800783f8`

## callees

- `0x1800110c0`
- `0x18003a388`
- `0x18003b520`
- `0x18004d320`
- `0x180074784`
- `0x1800755fc`
- `0x180075728`
- `0x180076aa8`

## pseudocode

```c
__int64 __fastcall readDrcInstructionsUniDrc(
        _DWORD *a1,
        unsigned int a2,
        struct UNI_DRC_CONFIG *a3,
        unsigned __int8 a4,
        __int64 a5)
{
  struct UNI_DRC_CONFIG *v6; // rbp
  int v7; // r15d
  __int64 v9; // r8
  __int64 v10; // r14
  char v11; // al
  __int64 v12; // r8
  _BYTE *v13; // rdi
  char v14; // al
  __int64 v15; // r8
  char v16; // al
  int v17; // eax
  int v18; // edi
  __int64 v19; // rbp
  char v20; // di
  __int64 v21; // rax
  _BYTE *v22; // r12
  __int16 v23; // ax
  __int64 v24; // r8
  char v25; // al
  char v26; // al
  __int64 v27; // r8
  __int64 v28; // r8
  char v29; // al
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  char v33; // al
  __int64 v34; // r8
  struct DRC_COEFFICIENTS_UNI_DRC *v35; // r13
  int v36; // edi
  int v37; // ebp
  __int64 v38; // r14
  char v39; // al
  __int64 v40; // r8
  int v41; // eax
  int v42; // edx
  __int64 v43; // rcx
  __int64 result; // rax
  int v45; // r15d
  _BYTE *v46; // r8
  struct DOWNMIX_INSTRUCTIONS *v47; // rax
  int v48; // ebp
  char v49; // al
  __int64 v50; // r8
  char v51; // r14
  __int64 v52; // rax
  int v53; // edx
  int i; // ecx
  __int64 v55; // rax
  unsigned __int8 v56; // al
  int v57; // edx
  __int64 v58; // rcx
  _BYTE *v59; // rbp
  int v60; // edi
  __int64 v61; // rcx
  __int64 v62; // r8
  _BYTE *v64; // [rsp+48h] [rbp-90h]
  _BYTE v65[64]; // [rsp+50h] [rbp-88h] BYREF
  struct UNI_DRC_CONFIG *v66; // [rsp+90h] [rbp-48h] BYREF

  v6 = a3;
  v7 = a4;
  v66 = a3;
  *(_BYTE *)a5 = CDKreadBits(a1, 6, (__int64)a3);
  v10 = 4;
  if ( a2 )
    v11 = CDKreadBits(a1, 4, v9);
  else
    v11 = 2;
  *(_BYTE *)(a5 + 1) = v11;
  *(_BYTE *)(a5 + 2) = CDKreadBits(a1, 4, v9);
  v13 = (_BYTE *)(a5 + 5);
  v64 = (_BYTE *)(a5 + 5);
  if ( a2 && !(unsigned int)CDKreadBits(a1, 1, v12) )
  {
    *v13 = 0;
    v21 = a5;
    v20 = 1;
  }
  else
  {
    v14 = CDKreadBits(a1, 7, v12);
    *v13 = v14;
    if ( a2 )
      v16 = CDKreadBits(a1, 1, v15);
    else
      v16 = v14 != 0;
    *(_BYTE *)(a5 + 3) = v16;
    if ( (unsigned int)CDKreadBits(a1, 1, v15) )
    {
      v17 = CDKreadBits(a1, 3, v12);
      v18 = v17;
      if ( v17 + 1 > 8 )
        return 4294967199LL;
      v19 = 0;
      if ( v17 > 0 )
      {
        do
        {
          *(_BYTE *)(v19 + a5 + 6) = CDKreadBits(a1, 7, v12);
          v19 = (unsigned int)(v19 + 1);
        }
        while ( (int)v19 < v18 );
      }
      v6 = v66;
      v20 = v18 + 1;
    }
    else
    {
      v20 = 1;
    }
    v21 = 4;
    v10 = a5;
  }
  *(_BYTE *)(v10 + v21) = v20;
  v22 = (_BYTE *)(a5 + 800);
  v23 = CDKreadBits(a1, 16, v12);
  *(_WORD *)(a5 + 14) = v23;
  if ( (v23 & 0xC00) == 0 )
  {
    v25 = CDKreadBits(a1, 1, v24);
    *(_BYTE *)(a5 + 16) = v25;
    if ( v25 )
      *(float *)(a5 + 20) = (float)-(int)CDKreadBits(a1, 8, v24) * 0.125;
  }
  v26 = CDKreadBits(a1, 1, v24);
  *(_BYTE *)(a5 + 24) = v26;
  *(_WORD *)(a5 + 25) = -16128;
  if ( v26 == 1 )
  {
    *(_BYTE *)(a5 + 25) = CDKreadBits(a1, 6, v27) - 63;
    if ( (unsigned int)CDKreadBits(a1, 1, v28) == 1 )
      *(_BYTE *)(a5 + 26) = CDKreadBits(a1, 6, v27) - 63;
  }
  v29 = CDKreadBits(a1, 1, v27);
  *(_BYTE *)(a5 + 27) = v29;
  *(_BYTE *)(a5 + 28) = 0;
  v31 = 6;
  if ( !v29 )
    v31 = 1;
  *(_BYTE *)(a5 + 28) = CDKreadBits(a1, v31, v30);
  if ( a2 )
    v33 = CDKreadBits(a1, 1, v32);
  else
    v33 = 0;
  *(_BYTE *)(a5 + 29) = v33;
  v35 = selectDrcCoefficients(v6, *(unsigned __int8 *)(a5 + 2));
  *(_BYTE *)(a5 + 808) = v7;
  v36 = v7;
  if ( (*(_WORD *)(a5 + 14) & 0xC00) != 0 )
  {
    v37 = 0;
    v38 = a5 + 32;
    while ( v37 < v7 )
    {
      v39 = CDKreadBits(a1, 6, v34);
      if ( v37 >= 8 )
        return 4294967199LL;
      v22[v37] = v39 - 1;
      decodeDuckingModification(a1, v38 + 8LL * v37++);
      if ( (unsigned int)CDKreadBits(a1, 1, v40) == 1 )
      {
        v41 = CDKreadBits(a1, 5, v34);
        v42 = 0;
        v34 = (unsigned int)(v41 + 1);
        while ( v42 < (int)v34 )
        {
          if ( v37 >= 8 )
            return 4294967199LL;
          v43 = v37++;
          ++v42;
          v22[v43] = v22[v43 - 1];
          *(_QWORD *)(v38 + 8 * v43) = *(_QWORD *)(v38 + 8 * v43 - 8);
        }
      }
    }
    if ( v37 <= v7 )
      return deriveDrcChannelGroups(
               *(unsigned __int16 *)(a5 + 14),
               *(unsigned __int8 *)(a5 + 808),
               a5 + 800,
               a5 + 32,
               a5 + 809,
               a5 + 810,
               &v66,
               v65);
    return 4294967196LL;
  }
  v45 = 0;
  if ( a2 && !*(_BYTE *)(a5 + 3) )
  {
    v46 = (_BYTE *)(a5 + 5);
    goto LABEL_51;
  }
  v46 = (_BYTE *)(a5 + 5);
  if ( !*v64 || *v64 == 127 || *(_BYTE *)(a5 + 4) != 1 )
  {
    if ( !a2 )
    {
LABEL_52:
      if ( *v46 != 127 && *(_BYTE *)(a5 + 4) <= 1u )
        goto LABEL_56;
      *(_BYTE *)(a5 + 808) = 8;
      goto LABEL_55;
    }
LABEL_51:
    if ( !*(_BYTE *)(a5 + 3) )
      goto LABEL_56;
    goto LABEL_52;
  }
  if ( !*((_BYTE *)v6 + 10) )
  {
    v45 = 1;
LABEL_55:
    v36 = 1;
    goto LABEL_56;
  }
  v47 = selectDownmixInstructions(v6, (unsigned __int8)*v64);
  if ( !v47 )
    return 4294967196LL;
  v36 = *((unsigned __int8 *)v47 + 1);
  *(_BYTE *)(a5 + 808) = v36;
LABEL_56:
  v48 = 0;
  while ( v48 < v36 )
  {
    v49 = CDKreadBits(a1, 6, (__int64)v46);
    if ( v48 >= 8 )
      return 4294967199LL;
    v51 = v49 - 1;
    v52 = v48++;
    v22[v52] = v51;
    if ( (unsigned int)CDKreadBits(a1, 1, v50) == 1 )
    {
      v53 = CDKreadBits(a1, 5, (__int64)v46) + 1;
      if ( v45 )
        v36 = v53 + 1;
      for ( i = 0; i < v53; ++i )
      {
        if ( v48 >= 8 )
          return 4294967199LL;
        v55 = v48++;
        v22[v55] = v51;
      }
    }
  }
  if ( v48 > v36 )
    return 4294967196LL;
  if ( v45 )
  {
    *(_BYTE *)(a5 + 808) = v36;
    v56 = v36;
  }
  else
  {
    v56 = *(_BYTE *)(a5 + 808);
    LOBYTE(v36) = v56;
  }
  if ( *v64 == 127 || *(_BYTE *)(a5 + 4) > 1u )
  {
    v57 = 1;
    if ( v56 <= 1u )
    {
      LOBYTE(v36) = v56;
    }
    else
    {
      do
      {
        v58 = v57++;
        v22[v58] = *v22;
        v36 = *(unsigned __int8 *)(a5 + 808);
      }
      while ( v57 < v36 );
    }
  }
  v59 = (_BYTE *)(a5 + 809);
  result = deriveDrcChannelGroups(
             *(unsigned __int16 *)(a5 + 14),
             (unsigned __int8)v36,
             a5 + 800,
             0,
             a5 + 809,
             a5 + 810,
             &v66,
             0);
  if ( !(_DWORD)result )
  {
    v60 = 0;
    if ( *v59 )
    {
      do
      {
        if ( v35 && (v61 = *(char *)(v60 + a5 + 810), (int)v61 < *((unsigned __int8 *)v35 + 1453)) )
          v62 = *((unsigned __int8 *)v35 + 38 * v61 + 1462);
        else
          v62 = 1;
        decodeGainModification(a1, a2, v62, a5 + 32 + 96LL * v60++);
      }
      while ( v60 < (unsigned __int8)*v59 );
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180076aa8  mov     [rsp+arg_8], rbx
0x180076aad  push    rbp
0x180076aae  push    rsi
0x180076aaf  push    rdi
0x180076ab0  push    r12
0x180076ab2  push    r13
0x180076ab4  push    r14
0x180076ab6  push    r15
0x180076ab8  sub     rsp, 0A0h
0x180076abf  mov     rax, cs:__security_cookie
0x180076ac6  xor     rax, rsp
0x180076ac9  mov     [rsp+0D8h+var_40], rax
0x180076ad1  mov     rbx, [rsp+0D8h+arg_20]
0x180076ad9  mov     r13d, edx
0x180076adc  mov     [rsp+0D8h+var_98], edx
0x180076ae0  mov     rbp, r8
0x180076ae3  mov     edx, 6
0x180076ae8  movzx   r15d, r9b
0x180076aec  mov     [rsp+0D8h+var_48], r8
0x180076af4  mov     rsi, rcx
0x180076af7  call    CDKreadBits
0x180076afc  mov     [rbx], al
0x180076afe  mov     r14d, 4
0x180076b04  test    r13d, r13d
0x180076b07  jnz     short loc_180076B0D
0x180076b09  mov     al, 2
0x180076b0b  jmp     short loc_180076B18
0x180076b0d  mov     edx, r14d
0x180076b10  mov     rcx, rsi
0x180076b13  call    CDKreadBits
0x180076b18  mov     edx, r14d
0x180076b1b  mov     [rbx+1], al
0x180076b1e  mov     rcx, rsi
0x180076b21  call    CDKreadBits
0x180076b26  mov     [rbx+2], al
0x180076b29  lea     rdi, [rbx+5]
0x180076b2d  mov     [rsp+0D8h+var_90], rdi
0x180076b32  mov     r12d, 1
0x180076b38  test    r13d, r13d
0x180076b3b  jz      short loc_180076B50
0x180076b3d  mov     edx, r12d
0x180076b40  mov     rcx, rsi
0x180076b43  call    CDKreadBits
0x180076b48  test    eax, eax
0x180076b4a  jz      loc_180076BD9
0x180076b50  mov     edx, 7
0x180076b55  mov     rcx, rsi
0x180076b58  call    CDKreadBits
0x180076b5d  mov     [rdi], al
0x180076b5f  test    r13d, r13d
0x180076b62  jnz     short loc_180076B6B
0x180076b64  test    al, al
0x180076b66  setnz   al
0x180076b69  jmp     short loc_180076B76
0x180076b6b  mov     edx, r12d
0x180076b6e  mov     rcx, rsi
0x180076b71  call    CDKreadBits
0x180076b76  mov     edx, r12d
0x180076b79  mov     [rbx+3], al
0x180076b7c  mov     rcx, rsi
0x180076b7f  call    CDKreadBits
0x180076b84  test    eax, eax
0x180076b86  jz      short loc_180076BCE
0x180076b88  mov     edx, 3
0x180076b8d  mov     rcx, rsi
0x180076b90  call    CDKreadBits
0x180076b95  mov     edi, eax
0x180076b97  lea     ecx, [rax+1]
0x180076b9a  cmp     ecx, 8
0x180076b9d  jg      loc_180076EBB
0x180076ba3  xor     ebp, ebp
0x180076ba5  test    eax, eax
0x180076ba7  jle     short loc_180076BC1
0x180076ba9  mov     edx, 7
0x180076bae  mov     rcx, rsi
0x180076bb1  call    CDKreadBits
0x180076bb6  mov     [rbp+rbx+6], al
0x180076bba  add     ebp, r12d
0x180076bbd  cmp     ebp, edi
0x180076bbf  jl      short loc_180076BA9
0x180076bc1  mov     rbp, [rsp+0D8h+var_48]
0x180076bc9  add     dil, r12b
0x180076bcc  jmp     short loc_180076BD1
0x180076bce  mov     dil, r12b
0x180076bd1  mov     rax, r14
0x180076bd4  mov     r14, rbx
0x180076bd7  jmp     short loc_180076BE2
0x180076bd9  mov     byte ptr [rdi], 0
0x180076bdc  mov     rax, rbx
0x180076bdf  mov     dil, r12b
0x180076be2  mov     edx, 10h
0x180076be7  mov     [r14+rax], dil
0x180076beb  mov     rcx, rsi
0x180076bee  lea     r12, [rbx+320h]
0x180076bf5  call    CDKreadBits
0x180076bfa  mov     ecx, 0C00h
0x180076bff  mov     [rbx+0Eh], ax
0x180076c03  mov     r14d, 1
0x180076c09  test    cx, ax
0x180076c0c  jnz     short loc_180076C42
0x180076c0e  mov     edx, r14d
0x180076c11  mov     rcx, rsi
0x180076c14  call    CDKreadBits
0x180076c19  mov     [rbx+10h], al
0x180076c1c  test    al, al
0x180076c1e  jz      short loc_180076C42
0x180076c20  lea     edx, [r14+7]
0x180076c24  mov     rcx, rsi
0x180076c27  call    CDKreadBits
0x180076c2c  neg     eax
0x180076c2e  movd    xmm0, eax
0x180076c32  cvtdq2ps xmm0, xmm0
0x180076c35  mulss   xmm0, cs:__real@3e000000
0x180076c3d  movss   dword ptr [rbx+14h], xmm0
0x180076c42  mov     edx, r14d
0x180076c45  mov     rcx, rsi
0x180076c48  call    CDKreadBits
0x180076c4d  mov     [rbx+18h], al
0x180076c50  mov     word ptr [rbx+19h], 0C100h
0x180076c56  cmp     al, r14b
0x180076c59  jnz     short loc_180076C8F
0x180076c5b  mov     edx, 6
0x180076c60  mov     rcx, rsi
0x180076c63  call    CDKreadBits
0x180076c68  sub     al, 3Fh ; '?'
0x180076c6a  mov     edx, r14d
0x180076c6d  mov     rcx, rsi
0x180076c70  mov     [rbx+19h], al
0x180076c73  call    CDKreadBits
0x180076c78  cmp     eax, r14d
0x180076c7b  jnz     short loc_180076C8F
0x180076c7d  mov     edx, 6
0x180076c82  mov     rcx, rsi
0x180076c85  call    CDKreadBits
0x180076c8a  sub     al, 3Fh ; '?'
0x180076c8c  mov     [rbx+1Ah], al
0x180076c8f  mov     edx, r14d
0x180076c92  mov     rcx, rsi
0x180076c95  call    CDKreadBits
0x180076c9a  mov     [rbx+1Bh], al
0x180076c9d  mov     rcx, rsi
0x180076ca0  mov     byte ptr [rbx+1Ch], 0
0x180076ca4  mov     edx, 6
0x180076ca9  test    al, al
0x180076cab  jnz     short loc_180076CB0
0x180076cad  mov     edx, r14d
0x180076cb0  call    CDKreadBits
0x180076cb5  mov     [rbx+1Ch], al
0x180076cb8  test    r13d, r13d
0x180076cbb  jnz     short loc_180076CC1
0x180076cbd  xor     al, al
0x180076cbf  jmp     short loc_180076CCC
0x180076cc1  mov     edx, r14d
0x180076cc4  mov     rcx, rsi
0x180076cc7  call    CDKreadBits
0x180076ccc  mov     [rbx+1Dh], al
0x180076ccf  mov     rcx, rbp; struct UNI_DRC_CONFIG *
0x180076cd2  movzx   edx, byte ptr [rbx+2]; int
0x180076cd6  call    ?selectDrcCoefficients@@YAPEAUDRC_COEFFICIENTS_UNI_DRC@@PEAUUNI_DRC_CONFIG@@H@Z; selectDrcCoefficients(UNI_DRC_CONFIG *,int)
0x180076cdb  mov     r13, rax
0x180076cde  mov     [rbx+328h], r15b
0x180076ce5  mov     eax, 0C00h
0x180076cea  mov     edi, r15d
0x180076ced  test    [rbx+0Eh], ax
0x180076cf1  jz      loc_180076DD2
0x180076cf7  xor     ebp, ebp
0x180076cf9  lea     r14, [rbx+20h]
0x180076cfd  lea     r15d, [rbp+1]
0x180076d01  cmp     ebp, edi
0x180076d03  jge     short loc_180076D82
0x180076d05  mov     edx, 6
0x180076d0a  mov     rcx, rsi
0x180076d0d  call    CDKreadBits
0x180076d12  cmp     ebp, 8
0x180076d15  jge     loc_180076EBB
0x180076d1b  movsxd  rcx, ebp
0x180076d1e  sub     al, r15b
0x180076d21  mov     [rcx+r12], al
0x180076d25  lea     rdx, [r14+rcx*8]
0x180076d29  mov     rcx, rsi
0x180076d2c  call    _decodeDuckingModification
0x180076d31  mov     edx, r15d
0x180076d34  mov     rcx, rsi
0x180076d37  add     ebp, r15d
0x180076d3a  call    CDKreadBits
0x180076d3f  cmp     eax, r15d
0x180076d42  jnz     short loc_180076D01
0x180076d44  mov     edx, 5
0x180076d49  mov     rcx, rsi
0x180076d4c  call    CDKreadBits
0x180076d51  xor     edx, edx
0x180076d53  lea     r8d, [r15+rax]
0x180076d57  cmp     edx, r8d
0x180076d5a  jge     short loc_180076D01
0x180076d5c  cmp     ebp, 8
0x180076d5f  jge     loc_180076EBB
0x180076d65  movsxd  rcx, ebp
0x180076d68  add     ebp, r15d
0x180076d6b  add     edx, r15d
0x180076d6e  mov     al, [rcx+r12-1]
0x180076d73  mov     [rcx+r12], al
0x180076d77  mov     rax, [r14+rcx*8-8]
0x180076d7c  mov     [r14+rcx*8], rax
0x180076d80  jmp     short loc_180076D57
0x180076d82  jg      loc_180076EC7
0x180076d88  movzx   edx, byte ptr [rbx+328h]
0x180076d8f  lea     r8, [rsp+0D8h+var_88]
0x180076d94  movzx   ecx, word ptr [rbx+0Eh]
0x180076d98  lea     rax, [rbx+32Ah]
0x180076d9f  mov     [rsp+0D8h+var_A0], r8
0x180076da4  lea     r10, [rbx+329h]
0x180076dab  lea     r8, [rsp+0D8h+var_48]
0x180076db3  mov     r9, r14
0x180076db6  mov     [rsp+0D8h+var_A8], r8
0x180076dbb  mov     r8, r12
0x180076dbe  mov     [rsp+0D8h+var_B0], rax
0x180076dc3  mov     [rsp+0D8h+var_B8], r10
0x180076dc8  call    ?deriveDrcChannelGroups@@YA?AW4DRC_ERROR@@HHPEBCPEBUDUCKING_MODIFICATION@@PEAEPEAC3PEAU2@@Z; deriveDrcChannelGroups(int,int,signed char const *,DUCKING_MODIFICATION const *,uchar *,signed char *,signed char *,DUCKING_MODIFICATION *)
0x180076dcd  jmp     loc_180076FCB
0x180076dd2  mov     ecx, [rsp+0D8h+var_98]
0x180076dd6  xor     r15d, r15d
0x180076dd9  test    ecx, ecx
0x180076ddb  jz      short loc_180076DE3
0x180076ddd  cmp     [rbx+3], r15b
0x180076de1  jz      short loc_180076E2B
0x180076de3  mov     r8, [rsp+0D8h+var_90]
0x180076de8  movzx   eax, byte ptr [r8]
0x180076dec  test    al, al
0x180076dee  jz      short loc_180076E25
0x180076df0  cmp     al, 7Fh
0x180076df2  jz      short loc_180076E25
0x180076df4  cmp     [rbx+4], r14b
0x180076df8  jnz     short loc_180076E25
0x180076dfa  cmp     [rbp+0Ah], r15b
0x180076dfe  jz      short loc_180076E20
0x180076e00  mov     edx, eax; int
0x180076e02  mov     rcx, rbp; struct UNI_DRC_CONFIG *
0x180076e05  call    ?selectDownmixInstructions@@YAPEAUDOWNMIX_INSTRUCTIONS@@PEAUUNI_DRC_CONFIG@@H@Z; selectDownmixInstructions(UNI_DRC_CONFIG *,int)
0x180076e0a  test    rax, rax
0x180076e0d  jz      loc_180076EC7
0x180076e13  movzx   edi, byte ptr [rax+1]
0x180076e17  mov     [rbx+328h], dil
0x180076e1e  jmp     short loc_180076E4C
0x180076e20  mov     r15d, r14d
0x180076e23  jmp     short loc_180076E49
0x180076e25  test    ecx, ecx
0x180076e27  jz      short loc_180076E36
0x180076e29  jmp     short loc_180076E30
0x180076e2b  mov     r8, [rsp+0D8h+var_90]
0x180076e30  cmp     [rbx+3], r15b
0x180076e34  jz      short loc_180076E4C
0x180076e36  cmp     byte ptr [r8], 7Fh
0x180076e3a  jz      short loc_180076E42
0x180076e3c  cmp     [rbx+4], r14b
0x180076e40  jbe     short loc_180076E4C
0x180076e42  mov     byte ptr [rbx+328h], 8
0x180076e49  mov     edi, r14d
0x180076e4c  xor     ebp, ebp
0x180076e4e  jmp     short loc_180076E56
0x180076e50  mov     r14d, 1
0x180076e56  cmp     ebp, edi
0x180076e58  jge     short loc_180076EC5
0x180076e5a  mov     edx, 6
0x180076e5f  mov     rcx, rsi
0x180076e62  call    CDKreadBits
0x180076e67  cmp     ebp, 8
0x180076e6a  jge     short loc_180076EBB
0x180076e6c  sub     al, r14b
0x180076e6f  mov     edx, 1
0x180076e74  mov     r14b, al
0x180076e77  mov     rcx, rsi
0x180076e7a  movsxd  rax, ebp
0x180076e7d  inc     ebp
0x180076e7f  mov     [rax+r12], r14b
0x180076e83  call    CDKreadBits
0x180076e88  cmp     eax, 1
0x180076e8b  jnz     short loc_180076E50
0x180076e8d  lea     edx, [rax+4]
0x180076e90  mov     rcx, rsi
0x180076e93  call    CDKreadBits
0x180076e98  lea     edx, [rax+1]
0x180076e9b  test    r15d, r15d
0x180076e9e  jz      short loc_180076EA3
0x180076ea0  lea     edi, [rdx+1]
0x180076ea3  xor     ecx, ecx
0x180076ea5  cmp     ecx, edx
0x180076ea7  jge     short loc_180076E50
0x180076ea9  cmp     ebp, 8
0x180076eac  jge     short loc_180076EBB
0x180076eae  movsxd  rax, ebp
0x180076eb1  inc     ebp
0x180076eb3  inc     ecx
0x180076eb5  mov     [rax+r12], r14b
0x180076eb9  jmp     short loc_180076EA5
0x180076ebb  mov     eax, 0FFFFFF9Fh
0x180076ec0  jmp     loc_180076FCB
0x180076ec5  jle     short loc_180076ED1
0x180076ec7  mov     eax, 0FFFFFF9Ch
0x180076ecc  jmp     loc_180076FCB
0x180076ed1  test    r15d, r15d
  ... truncated ...
```
