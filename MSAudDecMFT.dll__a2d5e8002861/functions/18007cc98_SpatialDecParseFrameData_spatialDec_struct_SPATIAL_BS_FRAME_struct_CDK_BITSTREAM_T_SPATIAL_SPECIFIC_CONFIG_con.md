# SpatialDecParseFrameData(spatialDec_struct *,SPATIAL_BS_FRAME_struct *,CDK_BITSTREAM *,T_SPATIAL_SPECIFIC_CONFIG const *,UPMIXTYPE,int)

- ea: `0x18007cc98`
- end: `0x18007d2f0`
- name: `?SpatialDecParseFrameData@@YA?AW4SACDEC_ERROR@@PEAUspatialDec_struct@@PEAUSPATIAL_BS_FRAME_struct@@PEAUCDK_BITSTREAM@@PEBUT_SPATIAL_SPECIFIC_CONFIG@@W4UPMIXTYPE@@H@Z`
- size: `1624`
- prototype: `enum SACDEC_ERROR __high(struct spatialDec_struct *, struct SPATIAL_BS_FRAME_struct *, struct CDK_BITSTREAM *, const struct T_SPATIAL_SPECIFIC_CONFIG *, enum UPMIXTYPE, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180072810`
- `0x180072e5c`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x18002ce0c`
- `0x18004d320`
- `0x18004dce4`
- `0x18007cc98`
- `0x18007e068`
- `0x18007eb20`
- `0x18008a624`
- `0x18008b494`

## pseudocode

```c
__int64 __fastcall SpatialDecParseFrameData(__int64 *a1, __int64 a2, int *a3, int *a4, __int64 a5, int a6)
{
  __int64 v6; // rax
  __int64 *v7; // r13
  unsigned int v8; // ebp
  int *v9; // r14
  __int64 v12; // r8
  int v13; // r12d
  int v14; // ebx
  unsigned __int8 v15; // cl
  __int64 v16; // r8
  __int64 v17; // rdx
  int v18; // r12d
  int v19; // eax
  int v20; // ecx
  unsigned int v21; // r13d
  int i; // ebx
  int v23; // ecx
  int v24; // r9d
  __int64 v25; // rax
  int v26; // ecx
  char v27; // al
  int j; // ebx
  int k; // ebx
  int v30; // eax
  int v31; // edx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // r9
  int v35; // ecx
  __int64 v36; // rax
  int v37; // r12d
  unsigned __int8 v38; // al
  unsigned __int8 v39; // al
  int v40; // r13d
  int v41; // eax
  int v42; // r14d
  char v43; // al
  __int64 v44; // rcx
  int v45; // edx
  __int64 v46; // rcx
  __int64 v47; // r8
  int v48; // r12d
  __int64 v49; // r8
  __int64 v50; // r13
  char v51; // al
  int m; // ebx
  int n; // edx
  __int64 v54; // r8
  char v55; // al
  __int64 v56; // rbx
  char v57; // bl
  int v59; // [rsp+40h] [rbp-1A8h]
  _BYTE v60[4]; // [rsp+60h] [rbp-188h]
  int v61; // [rsp+64h] [rbp-184h]
  unsigned int v62; // [rsp+68h] [rbp-180h]
  int v63; // [rsp+6Ch] [rbp-17Ch]
  unsigned int v64; // [rsp+70h] [rbp-178h]
  __int64 *v65; // [rsp+78h] [rbp-170h]
  int *v66; // [rsp+80h] [rbp-168h]
  int v67[64]; // [rsp+90h] [rbp-158h] BYREF

  v6 = a4[4];
  v7 = a1;
  v65 = a1;
  v8 = 0;
  v9 = a4;
  v66 = a4;
  v62 = 0;
  v60[0] = byte_1800D0CE1[9 * v6];
  CDKsyncCache_0(a3);
  v13 = *v9;
  v64 = a3[2];
  v61 = v13;
  v63 = v13 & 6;
  if ( (v13 & 6) == 0 || *((_BYTE *)v9 + 166) )
  {
    v14 = CDKreadBits(a3, 1, v12);
    v17 = 1;
    if ( (v13 & 0x20) == 0 )
      v17 = 3;
    v15 = CDKreadBits(a3, v17, v16) + 1;
    *(_BYTE *)(a2 + 2) = v15;
    if ( v15 >= 9u )
      return v8;
  }
  else
  {
    v14 = 0;
    *(_BYTE *)(a2 + 2) = 1;
    v15 = 1;
  }
  if ( v9[11] <= 0 || v9[12] <= 0 )
  {
    v8 = -983;
    goto LABEL_96;
  }
  if ( v14 )
  {
    v18 = -1;
    if ( v9[2] <= 1 )
    {
      v20 = 0;
    }
    else
    {
      v19 = (int)o_log2f_0((float)v9[2]);
      v20 = 0;
      if ( v19 >= 0 )
        v20 = v19;
    }
    v21 = v20 + 1;
    if ( 1 << v20 >= v9[2] )
      v21 = v20;
    for ( i = 0; i < *(unsigned __int8 *)(a2 + 2); ++i )
    {
      v23 = CDKreadBits(a3, v21, v12);
      *(_DWORD *)(a2 + 4LL * i + 4) = v23;
      if ( v23 <= v18 || v23 >= v9[2] )
        goto LABEL_67;
      v18 = v23;
    }
    v13 = v61;
    v7 = v65;
  }
  else if ( v15 )
  {
    v24 = 0;
    do
    {
      v12 = (unsigned int)(v24 + 1);
      v25 = v24;
      v26 = v9[2] * (v24 + 1) / v15 - 1;
      v24 = v12;
      *(_DWORD *)(a2 + 4 * v25 + 4) = v26;
      v15 = *(_BYTE *)(a2 + 2);
    }
    while ( (int)v12 < v15 );
  }
  if ( v63 && a6 )
    v27 = 1;
  else
    v27 = CDKreadBits(a3, 1, v12);
  *(_BYTE *)a2 = v27;
  for ( j = 0; j < v9[13]; ++j )
  {
    v62 = ecDataDec(
            a2,
            v13,
            (_DWORD)a3,
            *(_DWORD *)(a2 + 2848) + 48 * j,
            a2 + 40,
            v7[57],
            0,
            j,
            v59,
            *((unsigned __int8 *)v9 + j + 182),
            *((_BYTE *)v9 + j + 176));
    v8 = v62;
    if ( v62 )
      goto LABEL_96;
  }
  for ( k = 0; k < v9[13]; ++k )
  {
    v62 = ecDataDec(
            a2,
            v13,
            (_DWORD)a3,
            *(_DWORD *)(a2 + 2856) + 48 * k,
            a2 + 1300,
            v7[58],
            1,
            k,
            v59,
            *((unsigned __int8 *)v9 + k + 182),
            0);
    v8 = v62;
    if ( v62 )
      goto LABEL_96;
  }
  if ( v9[4] == 7 && *((_BYTE *)v9 + 169) )
  {
    v30 = CDKreadBits(a3, 1, v12);
    *(_DWORD *)(a2 + 2880) = v30;
    if ( v30 )
    {
      v33 = CDKreadBits(a3, 1, v12);
      v34 = *(_QWORD *)(a2 + 2864);
      *(_DWORD *)(a2 + 2884) = v33;
      v62 = ecDataDec(
              a2,
              v13,
              (_DWORD)a3,
              v34,
              *(_QWORD *)(a2 + 2872),
              v7[60],
              2,
              0,
              v59,
              *((unsigned __int8 *)v9 + 181),
              0);
      v8 = v62;
      if ( v62 )
      {
LABEL_96:
        *(_BYTE *)(a2 + 2) = 0;
        return v8;
      }
    }
    else
    {
      v31 = 0;
      if ( *((_BYTE *)v9 + 181) )
      {
        do
        {
          v12 = 0;
          *(_BYTE *)(v31 + *(_QWORD *)v7[60]) = 0;
          if ( *(_BYTE *)(a2 + 2) )
          {
            do
            {
              v32 = (int)v12;
              v12 = (unsigned int)(v12 + 1);
              *(_BYTE *)(v31 + 28 * v32 + *(_QWORD *)(a2 + 2872)) = 0;
            }
            while ( (int)v12 < *(unsigned __int8 *)(a2 + 2) );
          }
          ++v31;
        }
        while ( v31 < *((unsigned __int8 *)v9 + 181) );
      }
      *(_DWORD *)(a2 + 2884) = 0;
    }
  }
  if ( *((_BYTE *)v9 + 166) || (v13 & 2) == 0 )
  {
    v37 = 0;
    if ( *(_BYTE *)(a2 + 2) )
    {
      do
      {
        v38 = CDKreadBits(a3, 2, v12);
        *(_BYTE *)(v37 + a2 + 2560) = v38;
        if ( v38 >= 2u )
          *(_BYTE *)(v37 + a2 + 2569) = CDKreadBits(a3, 2, v12);
        if ( *(_BYTE *)(v37 + a2 + 2560) == 3 )
        {
          v39 = CDKreadBits(a3, 2, v12);
          v40 = 0;
          *(_BYTE *)(v37 + a2 + 2578) = v39;
          v12 = *((unsigned __int8 *)&pbStrideTable + v39);
          v41 = (v9[3] - 1) / *((unsigned __int8 *)&pbStrideTable + v39) + 1;
          if ( v41 > 0 )
          {
            v42 = v41;
            do
            {
              v43 = CDKreadBits(a3, 1, v12);
              v44 = (unsigned int)v40++;
              *(_BYTE *)(28LL * v37 + v44 + a2 + 2587) = v43;
            }
            while ( v40 < v42 );
            v9 = v66;
          }
        }
        ++v37;
      }
      while ( v37 < *(unsigned __int8 *)(a2 + 2) );
      v8 = v62;
    }
    LOBYTE(v13) = v61;
  }
  else
  {
    v35 = 0;
    if ( *(_BYTE *)(a2 + 2) )
    {
      do
      {
        v36 = v35++;
        *(_BYTE *)(v36 + a2 + 2560) = 0;
      }
      while ( v35 < *(unsigned __int8 *)(a2 + 2) );
    }
  }
  if ( v9[9] == 3 && (v13 & 2) != 0 )
  {
    if ( (unsigned int)TsdRead((struct CDK_BITSTREAM *)a3, v9[2], (struct TSD_DATA *)(a2 + 3020)) )
    {
LABEL_67:
      v8 = -982;
      goto LABEL_96;
    }
  }
  else
  {
    *(_BYTE *)(a2 + 3020) = 0;
  }
  v45 = v60[0];
  v46 = 0;
  if ( v60[0] > 0 )
  {
    do
    {
      *(_BYTE *)(v46 + a2 + 3018) = 0;
      *(_BYTE *)(v46 + a2 + 2888) = 0;
      v46 = (unsigned int)(v46 + 1);
    }
    while ( (int)v46 < v45 );
  }
  if ( (unsigned int)(v9[9] - 1) <= 1 && (unsigned int)CDKreadBits(a3, 1, v12) )
  {
    v47 = v9[9];
    v48 = *((unsigned __int8 *)&(&kernels_20_to_71)[v47 + 16] + v9[4]);
    v49 = (unsigned int)(v47 - 1);
    if ( (_DWORD)v49 )
    {
      if ( (_DWORD)v49 != 1 )
      {
        v8 = -981;
        goto LABEL_96;
      }
      v50 = 0;
      if ( v48 )
      {
        do
        {
          v51 = CDKreadBits(a3, 1, v49);
          v60[v50] = v51;
          *(_BYTE *)(v50 + a2 + 2888) = v51;
          v50 = (unsigned int)(v50 + 1);
        }
        while ( (int)v50 < v48 );
      }
      for ( m = 0; m < v48; ++m )
      {
        if ( v60[m] )
        {
          if ( (unsigned int)huff_dec_reshape((struct CDK_BITSTREAM *)a3, v67, v9[2]) )
            goto LABEL_67;
          for ( n = 0; n < v9[2]; ++n )
          {
            v54 = n;
            if ( v67[n] < 0 )
              goto LABEL_67;
            v55 = v67[n];
            *(_BYTE *)(a2 + ((__int64)m << 6) + v54 + 2890) = v55;
          }
        }
      }
    }
    else
    {
      v56 = 0;
      if ( v48 )
      {
        do
        {
          *(_BYTE *)(v56 + a2 + 3018) = CDKreadBits(a3, 1, v49);
          v56 = (unsigned int)(v56 + 1);
        }
        while ( (int)v56 < v48 );
      }
    }
  }
  v57 = v61;
  if ( v9[6] )
  {
    v8 = parseArbitraryDownmixData((_DWORD)v65, (_DWORD)v9, v61, a2, (__int64)a3);
    if ( v8 )
      goto LABEL_96;
  }
  if ( (v57 & 2) == 0 )
    CDKbyteAlign_0(a3, v64);
  if ( v8 )
    goto LABEL_96;
  return v8;
}

```

## disassembly

```asm
0x18007cc98  push    rbx
0x18007cc9a  push    rbp
0x18007cc9b  push    rsi
0x18007cc9c  push    rdi
0x18007cc9d  push    r12
0x18007cc9f  push    r13
0x18007cca1  push    r14
0x18007cca3  push    r15
0x18007cca5  sub     rsp, 1A8h
0x18007ccac  mov     rax, cs:__security_cookie
0x18007ccb3  xor     rax, rsp
0x18007ccb6  mov     [rsp+1E8h+var_58], rax
0x18007ccbe  movsxd  rax, dword ptr [r9+10h]
0x18007ccc2  mov     r13, rcx
0x18007ccc5  mov     [rsp+1E8h+var_170], rcx
0x18007ccca  xor     ebp, ebp
0x18007cccc  mov     r14, r9
0x18007cccf  mov     [rsp+1E8h+var_168], r9
0x18007ccd7  mov     r15, r8
0x18007ccda  mov     [rsp+1E8h+var_180], ebp
0x18007ccde  lea     rcx, [rax+rax*8]
0x18007cce2  mov     rdi, rdx
0x18007cce5  lea     rax, __ImageBase
0x18007ccec  mov     al, [rcx+rax+0D0CE1h]
0x18007ccf3  mov     rcx, r8
0x18007ccf6  mov     [rsp+1E8h+var_188], al
0x18007ccfa  call    CDKsyncCache_0
0x18007ccff  mov     eax, [r15+8]
0x18007cd03  mov     r12d, [r14]
0x18007cd06  mov     [rsp+1E8h+var_178], eax
0x18007cd0a  mov     eax, r12d
0x18007cd0d  and     eax, 6
0x18007cd10  mov     [rsp+1E8h+var_184], r12d
0x18007cd15  mov     [rsp+1E8h+var_17C], eax
0x18007cd19  jz      short loc_18007CD32
0x18007cd1b  cmp     [r14+0A6h], bpl
0x18007cd22  jnz     short loc_18007CD32
0x18007cd24  lea     esi, [rbp+1]
0x18007cd27  xor     ebx, ebx
0x18007cd29  mov     [rdi+2], sil
0x18007cd2d  mov     cl, sil
0x18007cd30  jmp     short loc_18007CD65
0x18007cd32  mov     esi, 1
0x18007cd37  mov     rcx, r15
0x18007cd3a  mov     edx, esi
0x18007cd3c  call    CDKreadBits
0x18007cd41  mov     ebx, eax
0x18007cd43  mov     rcx, r15
0x18007cd46  mov     edx, esi
0x18007cd48  test    r12b, 20h
0x18007cd4c  jnz     short loc_18007CD51
0x18007cd4e  lea     edx, [rsi+2]
0x18007cd51  call    CDKreadBits
0x18007cd56  lea     ecx, [rsi+rax]
0x18007cd59  mov     [rdi+2], cl
0x18007cd5c  cmp     cl, 9
0x18007cd5f  jnb     loc_18007D2C9
0x18007cd65  cmp     [r14+2Ch], ebp
0x18007cd69  jle     loc_18007D2C0
0x18007cd6f  cmp     [r14+30h], ebp
0x18007cd73  jle     loc_18007D2C0
0x18007cd79  test    ebx, ebx
0x18007cd7b  jz      short loc_18007CDEC
0x18007cd7d  or      r12d, 0FFFFFFFFh
0x18007cd81  cmp     [r14+8], esi
0x18007cd85  jle     short loc_18007CDA2
0x18007cd87  movd    xmm0, dword ptr [r14+8]
0x18007cd8d  cvtdq2ps xmm0, xmm0; X
0x18007cd90  call    _o_log2f_0
0x18007cd95  cvttss2si eax, xmm0
0x18007cd99  xor     ecx, ecx
0x18007cd9b  test    eax, eax
0x18007cd9d  cmovns  ecx, eax
0x18007cda0  jmp     short loc_18007CDA4
0x18007cda2  xor     ecx, ecx
0x18007cda4  mov     eax, esi
0x18007cda6  lea     r13d, [rcx+1]
0x18007cdaa  shl     eax, cl
0x18007cdac  cmp     eax, [r14+8]
0x18007cdb0  cmovge  r13d, ecx
0x18007cdb4  xor     ebx, ebx
0x18007cdb6  movzx   eax, byte ptr [rdi+2]
0x18007cdba  cmp     ebx, eax
0x18007cdbc  jge     short loc_18007CE20
0x18007cdbe  mov     edx, r13d
0x18007cdc1  mov     rcx, r15
0x18007cdc4  call    CDKreadBits
0x18007cdc9  mov     ecx, eax
0x18007cdcb  movsxd  rax, ebx
0x18007cdce  mov     [rdi+rax*4+4], ecx
0x18007cdd2  cmp     ecx, r12d
0x18007cdd5  jle     loc_18007D144
0x18007cddb  cmp     ecx, [r14+8]
0x18007cddf  jge     loc_18007D144
0x18007cde5  mov     r12d, ecx
0x18007cde8  add     ebx, esi
0x18007cdea  jmp     short loc_18007CDB6
0x18007cdec  test    cl, cl
0x18007cdee  jz      short loc_18007CE2A
0x18007cdf0  xor     r9d, r9d
0x18007cdf3  movzx   ecx, cl
0x18007cdf6  lea     r8d, [r9+1]
0x18007cdfa  mov     eax, r8d
0x18007cdfd  imul    eax, [r14+8]
0x18007ce02  cdq
0x18007ce03  idiv    ecx
0x18007ce05  mov     ecx, eax
0x18007ce07  movsxd  rax, r9d
0x18007ce0a  sub     ecx, esi
0x18007ce0c  mov     r9d, r8d
0x18007ce0f  mov     [rdi+rax*4+4], ecx
0x18007ce13  movzx   eax, byte ptr [rdi+2]
0x18007ce17  mov     cl, al
0x18007ce19  cmp     r8d, eax
0x18007ce1c  jl      short loc_18007CDF3
0x18007ce1e  jmp     short loc_18007CE2A
0x18007ce20  mov     r12d, [rsp+1E8h+var_184]
0x18007ce25  mov     r13, [rsp+1E8h+var_170]
0x18007ce2a  cmp     [rsp+1E8h+var_17C], ebp
0x18007ce2e  jz      short loc_18007CE3E
0x18007ce30  cmp     [rsp+1E8h+arg_28], ebp
0x18007ce37  jz      short loc_18007CE3E
0x18007ce39  mov     al, sil
0x18007ce3c  jmp     short loc_18007CE48
0x18007ce3e  mov     edx, esi
0x18007ce40  mov     rcx, r15
0x18007ce43  call    CDKreadBits
0x18007ce48  mov     [rdi], al
0x18007ce4a  xor     ebx, ebx
0x18007ce4c  cmp     ebx, [r14+34h]
0x18007ce50  jge     short loc_18007CEBE
0x18007ce52  movsxd  rax, ebx
0x18007ce55  lea     rdx, [rdi+28h]
0x18007ce59  mov     r8, r15
0x18007ce5c  movzx   ecx, byte ptr [rax+r14+0B6h]
0x18007ce65  lea     r9, [rax+rax*2]
0x18007ce69  mov     al, [rax+r14+0B0h]
0x18007ce71  mov     [rsp+1E8h+var_198], al
0x18007ce75  mov     rax, [r13+1C8h]
0x18007ce7c  mov     [rsp+1E8h+var_1A0], ecx
0x18007ce80  mov     rcx, rdi
0x18007ce83  mov     [rsp+1E8h+var_1B0], ebx
0x18007ce87  mov     [rsp+1E8h+var_1B8], 0
0x18007ce8f  mov     [rsp+1E8h+var_1C0], rax
0x18007ce94  shl     r9, 4
0x18007ce98  add     r9, [rdi+0B20h]
0x18007ce9f  mov     [rsp+1E8h+var_1C8], rdx
0x18007cea4  mov     edx, r12d
0x18007cea7  call    ecDataDec
0x18007ceac  mov     [rsp+1E8h+var_180], eax
0x18007ceb0  mov     ebp, eax
0x18007ceb2  test    eax, eax
0x18007ceb4  jnz     loc_18007D2C5
0x18007ceba  add     ebx, esi
0x18007cebc  jmp     short loc_18007CE4C
0x18007cebe  xor     ebx, ebx
0x18007cec0  cmp     ebx, [r14+34h]
0x18007cec4  jge     short loc_18007CF2A
0x18007cec6  mov     [rsp+1E8h+var_198], 0
0x18007cecb  lea     rdx, [rdi+514h]
0x18007ced2  movsxd  rax, ebx
0x18007ced5  mov     r8, r15
0x18007ced8  movzx   ecx, byte ptr [rax+r14+0B6h]
0x18007cee1  lea     r9, [rax+rax*2]
0x18007cee5  mov     rax, [r13+1D0h]
0x18007ceec  mov     [rsp+1E8h+var_1A0], ecx
0x18007cef0  mov     rcx, rdi
0x18007cef3  mov     [rsp+1E8h+var_1B0], ebx
0x18007cef7  mov     [rsp+1E8h+var_1B8], esi
0x18007cefb  mov     [rsp+1E8h+var_1C0], rax
0x18007cf00  shl     r9, 4
0x18007cf04  add     r9, [rdi+0B28h]
0x18007cf0b  mov     [rsp+1E8h+var_1C8], rdx
0x18007cf10  mov     edx, r12d
0x18007cf13  call    ecDataDec
0x18007cf18  mov     [rsp+1E8h+var_180], eax
0x18007cf1c  mov     ebp, eax
0x18007cf1e  test    eax, eax
0x18007cf20  jnz     loc_18007D2C5
0x18007cf26  add     ebx, esi
0x18007cf28  jmp     short loc_18007CEC0
0x18007cf2a  cmp     dword ptr [r14+10h], 7
0x18007cf2f  jnz     loc_18007D024
0x18007cf35  cmp     byte ptr [r14+0A9h], 0
0x18007cf3d  jz      loc_18007D024
0x18007cf43  mov     edx, esi
0x18007cf45  mov     rcx, r15
0x18007cf48  call    CDKreadBits
0x18007cf4d  mov     [rdi+0B40h], eax
0x18007cf53  test    eax, eax
0x18007cf55  jnz     short loc_18007CFB8
0x18007cf57  xor     edx, edx
0x18007cf59  cmp     [r14+0B5h], dl
0x18007cf60  jbe     short loc_18007CFAC
0x18007cf62  mov     rax, [r13+1E0h]
0x18007cf69  xor     r8d, r8d
0x18007cf6c  movsxd  r9, edx
0x18007cf6f  mov     rcx, [rax]
0x18007cf72  mov     byte ptr [r9+rcx], 0
0x18007cf77  cmp     [rdi+2], r8b
0x18007cf7b  jbe     short loc_18007CF9E
0x18007cf7d  movsxd  rax, r8d
0x18007cf80  add     r8d, esi
0x18007cf83  imul    rcx, rax, 1Ch
0x18007cf87  mov     rax, [rdi+0B38h]
0x18007cf8e  add     rcx, r9
0x18007cf91  mov     byte ptr [rcx+rax], 0
0x18007cf95  movzx   eax, byte ptr [rdi+2]
0x18007cf99  cmp     r8d, eax
0x18007cf9c  jl      short loc_18007CF7D
0x18007cf9e  movzx   eax, byte ptr [r14+0B5h]
0x18007cfa6  add     edx, esi
0x18007cfa8  cmp     edx, eax
0x18007cfaa  jl      short loc_18007CF62
0x18007cfac  mov     dword ptr [rdi+0B44h], 0
0x18007cfb6  jmp     short loc_18007D024
0x18007cfb8  mov     edx, esi
0x18007cfba  mov     rcx, r15
0x18007cfbd  call    CDKreadBits
0x18007cfc2  mov     r9, [rdi+0B30h]
0x18007cfc9  mov     r8, r15
0x18007cfcc  mov     [rsp+1E8h+var_198], 0
0x18007cfd1  mov     edx, r12d
0x18007cfd4  mov     [rdi+0B44h], eax
0x18007cfda  mov     rcx, rdi
0x18007cfdd  movzx   eax, byte ptr [r14+0B5h]
0x18007cfe5  mov     [rsp+1E8h+var_1A0], eax
0x18007cfe9  mov     rax, [r13+1E0h]
0x18007cff0  mov     [rsp+1E8h+var_1B0], 0
0x18007cff8  mov     [rsp+1E8h+var_1B8], 2
0x18007d000  mov     [rsp+1E8h+var_1C0], rax
0x18007d005  mov     rax, [rdi+0B38h]
0x18007d00c  mov     [rsp+1E8h+var_1C8], rax
0x18007d011  call    ecDataDec
0x18007d016  mov     [rsp+1E8h+var_180], eax
0x18007d01a  mov     ebp, eax
0x18007d01c  test    eax, eax
0x18007d01e  jnz     loc_18007D2C5
0x18007d024  cmp     byte ptr [r14+0A6h], 0
0x18007d02c  jnz     short loc_18007D059
0x18007d02e  test    r12b, 2
0x18007d032  jz      short loc_18007D059
0x18007d034  xor     ecx, ecx
0x18007d036  cmp     [rdi+2], cl
0x18007d039  jbe     loc_18007D120
0x18007d03f  movsxd  rax, ecx
0x18007d042  add     ecx, esi
0x18007d044  mov     byte ptr [rax+rdi+0A00h], 0
0x18007d04c  movzx   eax, byte ptr [rdi+2]
0x18007d050  cmp     ecx, eax
0x18007d052  jl      short loc_18007D03F
0x18007d054  jmp     loc_18007D120
0x18007d059  xor     r12d, r12d
0x18007d05c  cmp     [rdi+2], r12b
0x18007d060  jbe     loc_18007D11B
0x18007d066  lea     rbp, __ImageBase
0x18007d06d  mov     edx, 2
0x18007d072  movsxd  rbx, r12d
0x18007d075  mov     rcx, r15
0x18007d078  call    CDKreadBits
0x18007d07d  mov     [rbx+rdi+0A00h], al
0x18007d084  cmp     al, 2
0x18007d086  jb      short loc_18007D09C
0x18007d088  mov     edx, 2
0x18007d08d  mov     rcx, r15
0x18007d090  call    CDKreadBits
0x18007d095  mov     [rbx+rdi+0A09h], al
0x18007d09c  cmp     byte ptr [rbx+rdi+0A00h], 3
0x18007d0a4  jnz     short loc_18007D107
0x18007d0a6  mov     edx, 2
0x18007d0ab  mov     rcx, r15
0x18007d0ae  call    CDKreadBits
0x18007d0b3  movzx   ecx, al
0x18007d0b6  xor     r13d, r13d
0x18007d0b9  mov     [rbx+rdi+0A12h], al
0x18007d0c0  mov     eax, [r14+0Ch]
0x18007d0c4  sub     eax, esi
0x18007d0c6  movzx   r8d, byte ptr [rcx+rbp+0D0808h]
0x18007d0cf  cdq
0x18007d0d0  idiv    r8d
0x18007d0d3  add     eax, esi
0x18007d0d5  test    eax, eax
0x18007d0d7  jle     short loc_18007D107
0x18007d0d9  imul    rbx, 1Ch
0x18007d0dd  mov     r14d, eax
0x18007d0e0  mov     edx, esi
0x18007d0e2  mov     rcx, r15
0x18007d0e5  call    CDKreadBits
0x18007d0ea  mov     ecx, r13d
0x18007d0ed  add     r13d, esi
0x18007d0f0  add     rcx, rbx
0x18007d0f3  mov     [rcx+rdi+0A1Bh], al
0x18007d0fa  cmp     r13d, r14d
0x18007d0fd  jl      short loc_18007D0E0
0x18007d0ff  mov     r14, [rsp+1E8h+var_168]
0x18007d107  movzx   eax, byte ptr [rdi+2]
0x18007d10b  add     r12d, esi
0x18007d10e  cmp     r12d, eax
0x18007d111  jl      loc_18007D06D
0x18007d117  mov     ebp, [rsp+1E8h+var_180]
  ... truncated ...
```
