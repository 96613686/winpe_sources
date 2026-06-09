# CBlock_ReadScaleFactorData(CAacDecoderChannelInfo *,CDK_BITSTREAM *,uint)

- ea: `0x1800176d0`
- end: `0x180017b28`
- name: `?CBlock_ReadScaleFactorData@@YA?AW4AAC_DECODER_ERROR@@PEAUCAacDecoderChannelInfo@@PEAUCDK_BITSTREAM@@I@Z`
- size: `1112`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180014ae0`

## callees

- `0x1800110c0`
- `0x1800175b0`
- `0x1800176d0`
- `0x180017b30`

## pseudocode

```c
__int64 __fastcall CBlock_ReadScaleFactorData(__int64 a1, unsigned int *a2, __int64 a3)
{
  __int64 v3; // r14
  int v4; // r15d
  __int64 v5; // r10
  int v6; // ecx
  unsigned int v8; // r13d
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // r12d
  __int64 v12; // rsi
  unsigned int v13; // r10d
  __int64 v14; // r8
  unsigned int v15; // r9d
  unsigned int v16; // edx
  __int64 v17; // rsi
  int v18; // ebx
  unsigned int v19; // ecx
  unsigned __int8 v20; // r11
  __int64 v21; // r10
  __int64 v22; // r14
  __int64 v23; // r15
  unsigned int v24; // edx
  int v25; // r10d
  unsigned int v26; // r9d
  unsigned int v27; // r8d
  __int16 v28; // ax
  int v29; // ebp
  __int64 v31; // rdx
  unsigned int j; // ebx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r15
  __int64 v36; // r14
  __int64 v37; // r8
  __int64 i; // rbp
  int v39; // eax
  int v40; // ecx
  int v41; // esi
  unsigned int v42; // eax
  unsigned int v43; // ebp
  __int64 v44; // r10
  int v45; // ebp
  int v46; // ecx
  int v47; // ebx
  int v48; // eax
  unsigned int v49; // [rsp+20h] [rbp-68h]
  int v50; // [rsp+28h] [rbp-60h]
  __int64 v51; // [rsp+30h] [rbp-58h]
  __int64 v52; // [rsp+40h] [rbp-48h]
  unsigned int v54; // [rsp+A0h] [rbp+18h]
  int v55; // [rsp+A8h] [rbp+20h]

  v54 = a3;
  v3 = *(_QWORD *)(a1 + 1704);
  v4 = 0;
  v5 = a1;
  v6 = *(unsigned __int8 *)(a1 + 1688);
  v55 = 0;
  v8 = *(unsigned __int8 *)(v3 + 1380);
  v9 = v3 + 512;
  v10 = 0;
  v50 = v6;
LABEL_2:
  v49 = v10;
  v52 = v9;
  v51 = v3;
  if ( (int)v10 >= *(unsigned __int8 *)(v5 + 1680) )
    return 0;
  v11 = 0;
  while ( 1 )
  {
    if ( v11 >= v6 )
    {
      v9 += 16;
      v3 += 32;
      v10 = (unsigned int)(v10 + 1);
      goto LABEL_2;
    }
    v12 = v11;
    if ( !*(_BYTE *)(v11 + v9) )
    {
      v28 = 0;
LABEL_23:
      *(_WORD *)(v3 + 2 * v12) = v28;
      goto LABEL_24;
    }
    if ( *(_BYTE *)(v11 + v9) != 13 )
      break;
    if ( (a3 & 0x204300) != 0 )
      return 16386;
    v35 = *(_QWORD *)(v5 + 1704);
    v36 = (unsigned int)(v11 + 16 * v10);
    if ( *(_BYTE *)(v5 + 140) )
    {
      v37 = *a2;
      for ( i = 0; ; i = v43 >> 2 )
      {
        v39 = a2[1];
        v40 = 2 - v39;
        LOBYTE(v41) = 0;
        if ( 2 - v39 > 0 )
        {
          if ( v40 != 32 )
            v41 = (_DWORD)v37 << v40;
          v42 = CDK_get32(a2 + 2, v9, v37);
          v37 = v42;
          *a2 = v42;
          v39 = a2[1] + 32;
        }
        a2[1] = v39 - 2;
        v9 = ((unsigned __int8)v41 | (unsigned __int8)((unsigned __int64)(unsigned int)v37 >> ((unsigned __int8)v39 - 2)))
           & 3;
        v43 = *((unsigned __int16 *)&qword_1800BFAA0[i] + v9);
        if ( (v43 & 1) != 0 )
          break;
      }
      if ( (v43 & 2) != 0 )
        a2[1] = v39 - 2 + 1;
      v44 = a1;
      v45 = (v43 >> 2) - 60;
    }
    else
    {
      v47 = *(unsigned __int8 *)(v35 + 1380);
      v48 = CDKreadBits(a2, 9, a3);
      v44 = a1;
      v45 = v48 - 256;
      *(_BYTE *)(a1 + 140) = 1;
      *(_DWORD *)(a1 + 136) = v47 - 90;
    }
    *(_DWORD *)(v44 + 136) += v45;
    v46 = *(_DWORD *)(v44 + 136);
    if ( v46 <= -154 )
    {
      v46 = -154;
      *(_DWORD *)(v44 + 136) = -154;
    }
    else if ( v46 >= 229 )
    {
      v46 = 229;
    }
    *(_DWORD *)(v44 + 136) = v46;
    *(_WORD *)(v35 + 2 * v36) = v46;
    *(_BYTE *)(v44 + v36 + 8) = 1;
    v3 = v51;
LABEL_24:
    ++v11;
    v6 = v50;
    a3 = v54;
    v9 = v52;
    v5 = a1;
    v10 = v49;
    v4 = v55;
  }
  if ( (unsigned int)*(unsigned __int8 *)(v11 + v9) - 14 < 2 )
  {
    for ( j = *((unsigned __int16 *)qword_1800BFAA0 + (unsigned int)CDKread2Bits(a2, v9, a3, v10));
          (j & 1) == 0;
          j = *((unsigned __int16 *)&qword_1800BFAA0[(unsigned __int64)j >> 2]
              + (unsigned int)CDKread2Bits(a2, v31, v33, v34)) )
    {
      ;
    }
    if ( (j & 2) != 0 )
      ++a2[1];
    v55 = (j >> 2) + v4 - 60;
    v28 = v55 - 100;
    goto LABEL_23;
  }
  if ( (a3 & 0x4300) != 0 && !v11 && !(_DWORD)v10 )
    goto LABEL_21;
  v13 = *a2;
  v14 = 0;
  while ( 2 )
  {
    v15 = a2[1];
    if ( (int)(2 - v15) <= 0 )
    {
      v20 = 0;
    }
    else
    {
      v16 = a2[5];
      a2[2] -= 32;
      v16 += 32;
      v17 = *((_QWORD *)a2 + 3);
      v18 = v16 & 7;
      v19 = a2[9];
      v20 = v13 << (2 - v15);
      v21 = (v16 - 1) >> 3;
      a2[5] = v16 & (v19 - 1);
      v22 = (unsigned int)(v21 - 2);
      v23 = (unsigned int)(v21 - 1);
      if ( v16 > v19 )
      {
        v29 = a2[8] - 1;
        v24 = *(unsigned __int8 *)((v29 & (unsigned int)v21) + v17)
            | ((*(unsigned __int8 *)(((unsigned int)v23 & v29) + v17)
              | ((*(unsigned __int8 *)(((unsigned int)v22 & v29) + v17)
                | (*(unsigned __int8 *)((((_DWORD)v21 - 3) & (unsigned int)v29) + v17) << 8)) << 8)) << 8);
        if ( !v18 )
          goto LABEL_58;
        v25 = *(unsigned __int8 *)((v29 & (unsigned int)(v21 - 4)) + v17);
LABEL_14:
        v13 = (v24 >> (8 - v18)) | (v25 << (v18 + 24));
      }
      else
      {
        v24 = *(unsigned __int8 *)(v21 + v17)
            | ((*(unsigned __int8 *)(v23 + v17)
              | ((*(unsigned __int8 *)(v22 + v17) | (*(unsigned __int8 *)((unsigned int)(v21 - 3) + v17) << 8)) << 8)) << 8);
        if ( v18 )
        {
          v25 = *(unsigned __int8 *)((unsigned int)(v21 - 4) + v17);
          goto LABEL_14;
        }
LABEL_58:
        v13 = v24;
      }
      v15 += 32;
      *a2 = v13;
    }
    v26 = v15 - 2;
    a2[1] = v26;
    v27 = *((unsigned __int16 *)&qword_1800BFAA0[v14] + ((v20 | (unsigned __int8)((unsigned __int64)v13 >> v26)) & 3));
    if ( (v27 & 1) == 0 )
    {
      v14 = v27 >> 2;
      continue;
    }
    break;
  }
  if ( (v27 & 2) != 0 )
    a2[1] = v26 + 1;
  v3 = v51;
  v8 = (v27 >> 2) + v8 - 60;
  v12 = v11;
LABEL_21:
  if ( v8 <= 0xFF )
  {
    v28 = v8 - 100;
    goto LABEL_23;
  }
  return 16386;
}

```

## disassembly

```asm
0x1800176d0  mov     [rsp+arg_8], rbx
0x1800176d5  mov     [rsp+arg_10], r8d
0x1800176da  mov     [rsp+arg_0], rcx
0x1800176df  push    rbp
0x1800176e0  push    rsi
0x1800176e1  push    rdi
0x1800176e2  push    r12
0x1800176e4  push    r13
0x1800176e6  push    r14
0x1800176e8  push    r15
0x1800176ea  sub     rsp, 50h
0x1800176ee  mov     r14, [rcx+6A8h]
0x1800176f5  xor     r15d, r15d
0x1800176f8  mov     rbx, cs:off_180098870
0x1800176ff  mov     r10, rcx
0x180017702  movzx   ecx, byte ptr [rcx+698h]
0x180017709  mov     rdi, rdx
0x18001770c  mov     [rsp+88h+arg_18], r15d
0x180017714  mov     rbp, rbx
0x180017717  movzx   r13d, byte ptr [r14+564h]
0x18001771f  lea     rdx, [r14+200h]
0x180017726  mov     [rsp+88h+var_50], rbx
0x18001772b  xor     r9d, r9d
0x18001772e  mov     [rsp+88h+var_60], ecx
0x180017732  movzx   eax, byte ptr [r10+690h]
0x18001773a  mov     [rsp+88h+var_68], r9d
0x18001773f  mov     [rsp+88h+var_48], rdx
0x180017744  mov     [rsp+88h+var_58], r14
0x180017749  cmp     r9d, eax
0x18001774c  jge     loc_18001794E
0x180017752  xor     r12d, r12d
0x180017755  cmp     r12d, ecx
0x180017758  jge     loc_180017979
0x18001775e  movsxd  rsi, r12d
0x180017761  movzx   ecx, byte ptr [rsi+rdx]
0x180017765  test    ecx, ecx
0x180017767  jz      loc_1800178E8
0x18001776d  sub     ecx, 0Dh
0x180017770  jz      loc_180017969
0x180017776  sub     ecx, 1
0x180017779  jz      loc_180017989
0x18001777f  cmp     ecx, 1
0x180017782  jz      loc_180017989
0x180017788  test    r8d, 4300h
0x18001778f  jnz     loc_180017B09
0x180017795  mov     r10d, [rdi]
0x180017798  xor     r8d, r8d
0x18001779b  mov     r9d, [rdi+4]
0x18001779f  mov     ecx, 2
0x1800177a4  sub     ecx, r9d
0x1800177a7  test    ecx, ecx
0x1800177a9  jle     loc_1800178E0
0x1800177af  mov     edx, [rdi+14h]
0x1800177b2  add     dword ptr [rdi+8], 0FFFFFFE0h
0x1800177b6  add     edx, 20h ; ' '
0x1800177b9  mov     rsi, [rdi+18h]
0x1800177bd  mov     ebx, edx
0x1800177bf  shl     r10d, cl
0x1800177c2  and     ebx, 7
0x1800177c5  mov     ecx, [rdi+24h]
0x1800177c8  mov     r11d, r10d
0x1800177cb  lea     r10d, [rdx-1]
0x1800177cf  shr     r10d, 3
0x1800177d3  lea     eax, [rcx-1]
0x1800177d6  and     eax, edx
0x1800177d8  mov     [rdi+14h], eax
0x1800177db  lea     ebp, [r10-3]
0x1800177df  lea     r14d, [r10-2]
0x1800177e3  lea     r15d, [r10-1]
0x1800177e7  cmp     edx, ecx
0x1800177e9  ja      loc_1800178EC
0x1800177ef  movzx   ecx, byte ptr [r14+rsi]
0x1800177f4  movzx   edx, byte ptr [rbp+rsi+0]
0x1800177f9  shl     edx, 8
0x1800177fc  or      edx, ecx
0x1800177fe  movzx   ecx, byte ptr [r15+rsi]
0x180017803  shl     edx, 8
0x180017806  or      edx, ecx
0x180017808  movzx   ecx, byte ptr [r10+rsi]
0x18001780d  shl     edx, 8
0x180017810  or      edx, ecx
0x180017812  test    ebx, ebx
0x180017814  jz      loc_180017B20
0x18001781a  lea     eax, [r10-4]
0x18001781e  movzx   r10d, byte ptr [rax+rsi]
0x180017823  lea     ecx, [rbx+18h]
0x180017826  shl     r10d, cl
0x180017829  mov     ecx, 8
0x18001782e  sub     ecx, ebx
0x180017830  shr     edx, cl
0x180017832  or      r10d, edx
0x180017835  mov     rbp, [rsp+88h+var_50]
0x18001783a  add     r9d, 20h ; ' '
0x18001783e  mov     [rdi], r10d
0x180017841  add     r9d, 0FFFFFFFEh
0x180017845  mov     edx, r10d
0x180017848  movzx   ecx, r9b
0x18001784c  mov     [rdi+4], r9d
0x180017850  shr     rdx, cl
0x180017853  mov     eax, r11d
0x180017856  or      rdx, rax
0x180017859  and     edx, 3
0x18001785c  lea     rcx, [rdx+r8*4]
0x180017860  movzx   r8d, word ptr [rbp+rcx*2+0]
0x180017866  test    r8b, 1
0x18001786a  jnz     short loc_180017875
0x18001786c  shr     r8d, 2
0x180017870  jmp     loc_18001779B
0x180017875  test    r8b, 2
0x180017879  jz      short loc_180017882
0x18001787b  lea     eax, [r9+1]
0x18001787f  mov     [rdi+4], eax
0x180017882  mov     r14, [rsp+88h+var_58]
0x180017887  add     r13d, 0FFFFFFC4h
0x18001788b  shr     r8d, 2
0x18001788f  add     r13d, r8d
0x180017892  movsxd  rsi, r12d
0x180017895  cmp     r13d, 0FFh
0x18001789c  ja      loc_180017972
0x1800178a2  lea     eax, [r13-64h]
0x1800178a6  mov     [r14+rsi*2], ax
0x1800178ab  mov     rbx, cs:off_180098870
0x1800178b2  inc     r12d
0x1800178b5  mov     ecx, [rsp+88h+var_60]
0x1800178b9  mov     r8d, [rsp+88h+arg_10]
0x1800178c1  mov     rdx, [rsp+88h+var_48]
0x1800178c6  mov     r10, [rsp+88h+arg_0]
0x1800178ce  mov     r9d, [rsp+88h+var_68]
0x1800178d3  mov     r15d, [rsp+88h+arg_18]
0x1800178db  jmp     loc_180017755
0x1800178e0  xor     r11d, r11d
0x1800178e3  jmp     loc_180017841
0x1800178e8  xor     eax, eax
0x1800178ea  jmp     short loc_1800178A6
0x1800178ec  mov     eax, [rdi+20h]
0x1800178ef  dec     eax
0x1800178f1  mov     [rsp+88h+var_64], eax
0x1800178f5  mov     ecx, eax
0x1800178f7  mov     eax, ebp
0x1800178f9  mov     ebp, [rsp+88h+var_64]
0x1800178fd  and     rcx, rax
0x180017900  mov     eax, r14d
0x180017903  movzx   edx, byte ptr [rcx+rsi]
0x180017907  mov     ecx, ebp
0x180017909  and     rcx, rax
0x18001790c  shl     edx, 8
0x18001790f  movzx   eax, byte ptr [rcx+rsi]
0x180017913  mov     ecx, ebp
0x180017915  or      edx, eax
0x180017917  mov     eax, r15d
0x18001791a  and     rcx, rax
0x18001791d  shl     edx, 8
0x180017920  movzx   eax, byte ptr [rcx+rsi]
0x180017924  or      edx, eax
0x180017926  mov     ecx, r10d
0x180017929  and     rcx, rbp
0x18001792c  shl     edx, 8
0x18001792f  movzx   eax, byte ptr [rcx+rsi]
0x180017933  or      edx, eax
0x180017935  test    ebx, ebx
0x180017937  jz      loc_180017B20
0x18001793d  lea     ecx, [r10-4]
0x180017941  and     rcx, rbp
0x180017944  movzx   r10d, byte ptr [rcx+rsi]
0x180017949  jmp     loc_180017823
0x18001794e  xor     eax, eax
0x180017950  mov     rbx, [rsp+88h+arg_8]
0x180017958  add     rsp, 50h
0x18001795c  pop     r15
0x18001795e  pop     r14
0x180017960  pop     r13
0x180017962  pop     r12
0x180017964  pop     rdi
0x180017965  pop     rsi
0x180017966  pop     rbp
0x180017967  retn
0x180017969  test    r8d, 204300h
0x180017970  jz      short loc_1800179DE
0x180017972  mov     eax, 4002h
0x180017977  jmp     short loc_180017950
0x180017979  add     rdx, 10h
0x18001797d  add     r14, 20h ; ' '
0x180017981  inc     r9d
0x180017984  jmp     loc_180017732
0x180017989  mov     rcx, rdi
0x18001798c  call    CDKread2Bits
0x180017991  mov     eax, eax
0x180017993  movzx   ebx, word ptr [rbp+rax*2+0]
0x180017998  test    bl, 1
0x18001799b  jnz     short loc_1800179BB
0x18001799d  mov     rcx, rdi
0x1800179a0  call    CDKread2Bits
0x1800179a5  mov     ecx, eax
0x1800179a7  mov     eax, ebx
0x1800179a9  shr     rax, 2
0x1800179ad  lea     rax, [rcx+rax*4]
0x1800179b1  movzx   ebx, word ptr [rbp+rax*2+0]
0x1800179b6  test    bl, 1
0x1800179b9  jz      short loc_18001799D
0x1800179bb  test    bl, 2
0x1800179be  jz      short loc_1800179C3
0x1800179c0  inc     dword ptr [rdi+4]
0x1800179c3  shr     ebx, 2
0x1800179c6  add     r15d, 0FFFFFFC4h
0x1800179ca  add     r15d, ebx
0x1800179cd  mov     [rsp+88h+arg_18], r15d
0x1800179d5  lea     eax, [r15-64h]
0x1800179d9  jmp     loc_1800178A6
0x1800179de  mov     r15, [r10+6A8h]
0x1800179e5  mov     r14d, r9d
0x1800179e8  shl     r14d, 4
0x1800179ec  add     r14d, r12d
0x1800179ef  cmp     byte ptr [r10+8Ch], 0
0x1800179f7  jz      loc_180017ACF
0x1800179fd  mov     r8d, [rdi]
0x180017a00  xor     ebp, ebp
0x180017a02  mov     eax, [rdi+4]
0x180017a05  mov     ecx, 2
0x180017a0a  sub     ecx, eax
0x180017a0c  xor     esi, esi
0x180017a0e  test    ecx, ecx
0x180017a10  jle     short loc_180017A30
0x180017a12  cmp     ecx, 20h ; ' '
0x180017a15  jz      short loc_180017A1C
0x180017a17  mov     esi, r8d
0x180017a1a  shl     esi, cl
0x180017a1c  lea     rcx, [rdi+8]
0x180017a20  call    CDK_get32
0x180017a25  mov     r8d, eax
0x180017a28  mov     [rdi], eax
0x180017a2a  mov     eax, [rdi+4]
0x180017a2d  add     eax, 20h ; ' '
0x180017a30  lea     r9d, [rax-2]
0x180017a34  mov     edx, r8d
0x180017a37  movzx   ecx, r9b
0x180017a3b  mov     [rdi+4], r9d
0x180017a3f  shr     rdx, cl
0x180017a42  mov     eax, esi
0x180017a44  or      rdx, rax
0x180017a47  and     edx, 3
0x180017a4a  lea     rcx, [rdx+rbp*4]
0x180017a4e  movzx   ebp, word ptr [rbx+rcx*2]
0x180017a52  test    bpl, 1
0x180017a56  jz      short loc_180017AB2
0x180017a58  test    bpl, 2
0x180017a5c  jz      short loc_180017A65
0x180017a5e  lea     eax, [r9+1]
0x180017a62  mov     [rdi+4], eax
0x180017a65  mov     r10, [rsp+88h+arg_0]
0x180017a6d  shr     ebp, 2
0x180017a70  sub     ebp, 3Ch ; '<'
0x180017a73  add     [r10+88h], ebp
0x180017a7a  mov     ecx, [r10+88h]
0x180017a81  cmp     ecx, 0FFFFFF66h
0x180017a87  jle     short loc_180017AC1
0x180017a89  cmp     ecx, 0E5h
0x180017a8f  jge     short loc_180017ABA
0x180017a91  mov     rbp, [rsp+88h+var_50]
0x180017a96  mov     [r10+88h], ecx
0x180017a9d  mov     [r15+r14*2], cx
0x180017aa2  mov     byte ptr [r10+r14+8], 1
0x180017aa8  mov     r14, [rsp+88h+var_58]
0x180017aad  jmp     loc_1800178AB
0x180017ab2  shr     ebp, 2
0x180017ab5  jmp     loc_180017A02
0x180017aba  mov     ecx, 0E5h
0x180017abf  jmp     short loc_180017A91
0x180017ac1  mov     ecx, 0FFFFFF66h
0x180017ac6  mov     [r10+88h], ecx
0x180017acd  jmp     short loc_180017A91
0x180017acf  movzx   ebx, byte ptr [r15+564h]
0x180017ad7  mov     edx, 9
0x180017adc  mov     rcx, rdi
0x180017adf  call    CDKreadBits
0x180017ae4  mov     r10, [rsp+88h+arg_0]
0x180017aec  sub     ebx, 5Ah ; 'Z'
0x180017aef  lea     ebp, [rax-100h]
0x180017af5  mov     byte ptr [r10+8Ch], 1
0x180017afd  mov     [r10+88h], ebx
0x180017b04  jmp     loc_180017A73
0x180017b09  test    r12d, r12d
0x180017b0c  jnz     loc_180017795
0x180017b12  test    r9d, r9d
0x180017b15  jz      loc_180017895
0x180017b1b  jmp     loc_180017795
0x180017b20  mov     r10d, edx
0x180017b23  jmp     loc_180017835
```
