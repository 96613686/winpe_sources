# _readDrcExtensionV1

- ea: `0x180076548`
- end: `0x18007699b`
- name: `_readDrcExtensionV1`
- size: `1107`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1800777bc`

## callees

- `0x1800110c0`
- `0x18004dd14`
- `0x180075fec`
- `0x180076184`
- `0x180076548`
- `0x180076aa8`
- `0x180077a00`
- `0x180077c3c`
- `0x180077f28`
- `0x180096060`
- `0x18009606c`

## pseudocode

```c
__int64 __fastcall readDrcExtensionV1(_DWORD *a1, __int64 a2, __int64 a3)
{
  int v3; // r14d
  __int64 v6; // r8
  unsigned int v7; // eax
  int v8; // ebx
  bool v9; // zf
  int v10; // r12d
  int v11; // r15d
  int v12; // ebp
  unsigned int v13; // edx
  char v14; // al
  _OWORD *v15; // r14
  __int64 result; // rax
  __int64 v17; // r15
  __int64 v18; // rax
  _OWORD *v19; // rcx
  __int128 v20; // xmm1
  __int64 v21; // r8
  unsigned __int8 v22; // al
  __int64 v23; // r8
  int v24; // r15d
  int v25; // r13d
  int v26; // ebp
  char v27; // cl
  void *v28; // r12
  __int64 v29; // r14
  unsigned __int8 v30; // al
  int v31; // r12d
  int v32; // r13d
  unsigned int v33; // eax
  char v34; // cl
  _OWORD *v35; // r14
  int v36; // r9d
  __int64 v37; // r15
  __int64 v38; // rax
  _OWORD *v39; // rcx
  __int128 v40; // xmm1
  char v41; // dl
  __int64 v42; // r8
  int v43; // r15d
  int i; // r14d
  __int64 v45; // r8
  int v46; // r14d
  int v47; // [rsp+88h] [rbp+10h]

  v3 = *(unsigned __int8 *)(a2 + 21081);
  if ( (unsigned int)CDKreadBits(a1, 1, a3) != 1 )
  {
    v8 = 0;
    v9 = *(_BYTE *)(a2 + 9) == 0;
    *(_BYTE *)(a2 + 9) = 0;
    v12 = !v9 | v3;
    goto LABEL_15;
  }
  v7 = CDKreadBits(a1, 7, v6);
  v8 = 0;
  v6 = v7;
  v9 = *(_BYTE *)(a2 + 9) == (unsigned __int8)v7;
  *(_BYTE *)(a2 + 9) = v7;
  v10 = 0;
  v11 = *(unsigned __int8 *)(a2 + 8);
  v12 = v3 | !v9;
  v47 = v11;
  v13 = (unsigned __int8)(v7 + v11);
  v14 = 6;
  if ( v13 < 6 )
    v14 = v13;
  *(_BYTE *)(a2 + 10) = v14;
  if ( !(_BYTE)v6 )
  {
LABEL_15:
    if ( (unsigned int)CDKreadBits(a1, 1, v6) == 1 )
    {
      v22 = CDKreadBits(a1, 3, v21);
      v9 = *(_BYTE *)(a2 + 12) == v22;
      *(_BYTE *)(a2 + 12) = v22;
      v24 = 0;
      v25 = *(unsigned __int8 *)(a2 + 11);
      v26 = !v9 | v12;
      v27 = 2;
      if ( (unsigned __int8)(v22 + v25) < 2u )
        v27 = v22 + v25;
      *(_BYTE *)(a2 + 13) = v27;
      if ( v22 )
      {
        do
        {
          v28 = *(void **)(a2 + 21088);
          memset_0(v28, 0, 0x784u);
          result = readDrcCoefficientsUniDrc(a1, 1, v28);
          if ( (_DWORD)result )
            return result;
          if ( v24 + v25 < 2 )
          {
            v29 = 1924LL * (v24 + v25);
            if ( !v26 )
              v26 = memcmp_0(v28, (const void *)(v29 + a2 + 1612), 0x784u) != 0;
            memcpy_0((void *)(v29 + a2 + 1612), v28, 0x784u);
          }
        }
        while ( ++v24 < *(unsigned __int8 *)(a2 + 12) );
      }
      v30 = CDKreadBits(a1, 6, v23);
      v9 = *(_BYTE *)(a2 + 15) == v30;
      *(_BYTE *)(a2 + 15) = v30;
      v31 = 0;
      v32 = *(unsigned __int8 *)(a2 + 16);
      v12 = !v9 | v26;
      v33 = (unsigned __int8)(v30 + v32);
      v34 = 12;
      if ( v33 < 0xC )
        v34 = v33;
      *(_BYTE *)(a2 + 16) = v34;
      if ( v34 )
      {
        do
        {
          v35 = *(_OWORD **)(a2 + 21088);
          memset_0(v35, 0, 0x334u);
          LOBYTE(v36) = *(_BYTE *)(a2 + 17);
          result = readDrcInstructionsUniDrc((_DWORD)a1, 1, a2, v36, (__int64)v35);
          if ( (_DWORD)result )
            return result;
          if ( v31 + v32 < 12 )
          {
            v37 = 820LL * (v31 + v32);
            if ( !v12 )
              v12 = memcmp_0(v35, (const void *)(v37 + a2 + 5460), 0x334u) != 0;
            v38 = 6;
            v39 = (_OWORD *)(v37 + a2 + 5460);
            do
            {
              *v39 = *v35;
              v39[1] = v35[1];
              v39[2] = v35[2];
              v39[3] = v35[3];
              v39[4] = v35[4];
              v39[5] = v35[5];
              v39[6] = v35[6];
              v40 = v35[7];
              v35 += 8;
              v39[7] = v40;
              v39 += 8;
              --v38;
            }
            while ( v38 );
            *v39 = *v35;
            v39[1] = v35[1];
            v39[2] = v35[2];
            *((_DWORD *)v39 + 12) = *((_DWORD *)v35 + 12);
          }
        }
        while ( ++v31 < *(unsigned __int8 *)(a2 + 16) );
      }
    }
    else
    {
      v41 = *(_BYTE *)(a2 + 12);
      *(_BYTE *)(a2 + 12) = 0;
      v9 = *(_BYTE *)(a2 + 15) == 0;
      *(_BYTE *)(a2 + 15) = 0;
      LOBYTE(v12) = (v41 != 0 || !v9) | v12;
    }
    if ( (unsigned int)CDKreadBits(a1, 1, v21) == 1 )
    {
      v43 = CDKreadBits(a1, 4, v42);
      for ( i = 0; i < v43; ++i )
        skipLoudEqInstructions(a1);
    }
    if ( (unsigned int)CDKreadBits(a1, 1, v42) == 1 )
    {
      skipEqCoefficients(a1);
      v46 = CDKreadBits(a1, 4, v45);
      if ( v46 > 0 )
      {
        do
        {
          skipEqInstructions(a1, a2);
          ++v8;
        }
        while ( v8 < v46 );
      }
    }
    *(_BYTE *)(a2 + 21081) = v12;
    return 0;
  }
  while ( 1 )
  {
    v15 = *(_OWORD **)(a2 + 21088);
    memset_0(v15, 0, 0x108u);
    result = readDownmixInstructions(a1, 1, a2 + 17, v15);
    if ( (_DWORD)result )
      return result;
    if ( v11 + v10 < 6 )
    {
      v17 = 264LL * (v11 + v10);
      if ( !v12 )
        v12 = memcmp_0(v15, (const void *)(v17 + a2 + 28), 0x108u) != 0;
      v18 = 2;
      v19 = (_OWORD *)(v17 + a2 + 28);
      do
      {
        *v19 = *v15;
        v19[1] = v15[1];
        v19[2] = v15[2];
        v19[3] = v15[3];
        v19[4] = v15[4];
        v19[5] = v15[5];
        v19[6] = v15[6];
        v20 = v15[7];
        v15 += 8;
        v19[7] = v20;
        v19 += 8;
        --v18;
      }
      while ( v18 );
      v11 = v47;
      *(_QWORD *)v19 = *(_QWORD *)v15;
    }
    if ( ++v10 >= *(unsigned __int8 *)(a2 + 9) )
      goto LABEL_15;
  }
}

```

## disassembly

```asm
0x180076548  push    rbx
0x18007654a  push    rbp
0x18007654b  push    rsi
0x18007654c  push    rdi
0x18007654d  push    r12
0x18007654f  push    r13
0x180076551  push    r14
0x180076553  push    r15
0x180076555  sub     rsp, 38h
0x180076559  movzx   r14d, byte ptr [rdx+5259h]
0x180076561  mov     rdi, rdx
0x180076564  mov     edx, 1
0x180076569  mov     rsi, rcx
0x18007656c  call    CDKreadBits
0x180076571  cmp     eax, 1
0x180076574  jnz     loc_1800766B0
0x18007657a  lea     edx, [rax+6]
0x18007657d  mov     rcx, rsi
0x180076580  call    CDKreadBits
0x180076585  xor     ebx, ebx
0x180076587  mov     r8d, eax
0x18007658a  cmp     [rdi+9], al
0x18007658d  mov     ebp, ebx
0x18007658f  mov     [rdi+9], r8b
0x180076593  mov     r12d, ebx
0x180076596  movzx   r15d, byte ptr [rdi+8]
0x18007659b  setnz   bpl
0x18007659f  or      ebp, r14d
0x1800765a2  mov     [rsp+78h+arg_8], r15d
0x1800765aa  lea     ecx, [rax+r15]
0x1800765ae  movzx   edx, cl
0x1800765b1  lea     eax, [rbx+6]
0x1800765b4  cmp     edx, eax
0x1800765b6  cmovb   eax, edx
0x1800765b9  mov     [rdi+0Ah], al
0x1800765bc  test    r8b, r8b
0x1800765bf  jz      loc_1800766C2
0x1800765c5  mov     r14, [rdi+5260h]
0x1800765cc  xor     edx, edx; Val
0x1800765ce  mov     rcx, r14; void *
0x1800765d1  mov     r8d, 108h; Size
0x1800765d7  call    memset_0
0x1800765dc  mov     r9, r14
0x1800765df  lea     r8, [rdi+11h]
0x1800765e3  mov     edx, 1
0x1800765e8  mov     rcx, rsi
0x1800765eb  call    _readDownmixInstructions
0x1800765f0  test    eax, eax
0x1800765f2  jnz     loc_180076989
0x1800765f8  lea     eax, [r15+r12]
0x1800765fc  cmp     eax, 6
0x1800765ff  jge     loc_18007669E
0x180076605  cdqe
0x180076607  imul    r15, rax, 108h
0x18007660e  test    ebp, ebp
0x180076610  jnz     short loc_18007662F
0x180076612  lea     rdx, [rdi+1Ch]
0x180076616  mov     r8d, 108h; Size
0x18007661c  add     rdx, r15; Buf2
0x18007661f  mov     rcx, r14; Buf1
0x180076622  call    memcmp_0
0x180076627  test    eax, eax
0x180076629  mov     ebp, ebx
0x18007662b  setnz   bpl
0x18007662f  mov     eax, 2
0x180076634  lea     rcx, [rdi+1Ch]
0x180076638  add     rcx, r15
0x18007663b  lea     edx, [rax+7Eh]
0x18007663e  movups  xmm0, xmmword ptr [r14]
0x180076642  movups  xmmword ptr [rcx], xmm0
0x180076645  movups  xmm1, xmmword ptr [r14+10h]
0x18007664a  movups  xmmword ptr [rcx+10h], xmm1
0x18007664e  movups  xmm0, xmmword ptr [r14+20h]
0x180076653  movups  xmmword ptr [rcx+20h], xmm0
0x180076657  movups  xmm1, xmmword ptr [r14+30h]
0x18007665c  movups  xmmword ptr [rcx+30h], xmm1
0x180076660  movups  xmm0, xmmword ptr [r14+40h]
0x180076665  movups  xmmword ptr [rcx+40h], xmm0
0x180076669  movups  xmm1, xmmword ptr [r14+50h]
0x18007666e  movups  xmmword ptr [rcx+50h], xmm1
0x180076672  movups  xmm0, xmmword ptr [r14+60h]
0x180076677  movups  xmmword ptr [rcx+60h], xmm0
0x18007667b  movups  xmm1, xmmword ptr [r14+70h]
0x180076680  add     r14, rdx
0x180076683  movups  xmmword ptr [rcx+70h], xmm1
0x180076687  add     rcx, rdx
0x18007668a  sub     rax, 1
0x18007668e  jnz     short loc_18007663E
0x180076690  mov     rax, [r14]
0x180076693  mov     r15d, [rsp+78h+arg_8]
0x18007669b  mov     [rcx], rax
0x18007669e  movzx   eax, byte ptr [rdi+9]
0x1800766a2  inc     r12d
0x1800766a5  cmp     r12d, eax
0x1800766a8  jl      loc_1800765C5
0x1800766ae  jmp     short loc_1800766C2
0x1800766b0  xor     ebx, ebx
0x1800766b2  mov     ebp, r14d
0x1800766b5  cmp     [rdi+9], bl
0x1800766b8  mov     eax, ebx
0x1800766ba  mov     [rdi+9], bl
0x1800766bd  setnz   al
0x1800766c0  or      ebp, eax
0x1800766c2  mov     edx, 1
0x1800766c7  mov     rcx, rsi
0x1800766ca  call    CDKreadBits
0x1800766cf  cmp     eax, 1
0x1800766d2  jnz     loc_1800768E7
0x1800766d8  lea     edx, [rax+2]
0x1800766db  mov     rcx, rsi
0x1800766de  call    CDKreadBits
0x1800766e3  cmp     [rdi+0Ch], al
0x1800766e6  mov     ecx, ebx
0x1800766e8  mov     [rdi+0Ch], al
0x1800766eb  mov     r15d, ebx
0x1800766ee  movzx   r13d, byte ptr [rdi+0Bh]
0x1800766f3  setnz   cl
0x1800766f6  or      ebp, ecx
0x1800766f8  lea     ecx, [rax+r13]
0x1800766fc  movzx   edx, cl
0x1800766ff  mov     ecx, 2
0x180076704  cmp     edx, ecx
0x180076706  cmovb   ecx, edx
0x180076709  mov     [rdi+0Dh], cl
0x18007670c  test    al, al
0x18007670e  jz      loc_1800767A1
0x180076714  mov     r12, [rdi+5260h]
0x18007671b  xor     edx, edx; Val
0x18007671d  mov     rcx, r12; void *
0x180076720  mov     r8d, 784h; Size
0x180076726  call    memset_0
0x18007672b  mov     r8, r12
0x18007672e  mov     edx, 1
0x180076733  mov     rcx, rsi
0x180076736  call    _readDrcCoefficientsUniDrc
0x18007673b  test    eax, eax
0x18007673d  jnz     loc_180076989
0x180076743  lea     eax, [r15+r13]
0x180076747  cmp     eax, 2
0x18007674a  jge     short loc_180076791
0x18007674c  cdqe
0x18007674e  imul    r14, rax, 784h
0x180076755  test    ebp, ebp
0x180076757  jnz     short loc_180076779
0x180076759  lea     rdx, [rdi+64Ch]
0x180076760  mov     r8d, 784h; Size
0x180076766  add     rdx, r14; Buf2
0x180076769  mov     rcx, r12; Buf1
0x18007676c  call    memcmp_0
0x180076771  test    eax, eax
0x180076773  mov     ebp, ebx
0x180076775  setnz   bpl
0x180076779  lea     rcx, [rdi+64Ch]
0x180076780  mov     rdx, r12; Src
0x180076783  add     rcx, r14; void *
0x180076786  mov     r8d, 784h; Size
0x18007678c  call    memcpy_0
0x180076791  movzx   eax, byte ptr [rdi+0Ch]
0x180076795  inc     r15d
0x180076798  cmp     r15d, eax
0x18007679b  jl      loc_180076714
0x1800767a1  mov     edx, 6
0x1800767a6  mov     rcx, rsi
0x1800767a9  call    CDKreadBits
0x1800767ae  cmp     [rdi+0Fh], al
0x1800767b1  mov     ecx, ebx
0x1800767b3  mov     [rdi+0Fh], al
0x1800767b6  mov     r12d, ebx
0x1800767b9  movzx   r13d, byte ptr [rdi+10h]
0x1800767be  setnz   cl
0x1800767c1  or      ebp, ecx
0x1800767c3  lea     ecx, [rax+r13]
0x1800767c7  movzx   eax, cl
0x1800767ca  mov     ecx, 0Ch
0x1800767cf  cmp     eax, ecx
0x1800767d1  cmovb   ecx, eax
0x1800767d4  mov     [rdi+10h], cl
0x1800767d7  test    cl, cl
0x1800767d9  jz      loc_180076905
0x1800767df  mov     r14, [rdi+5260h]
0x1800767e6  xor     edx, edx; Val
0x1800767e8  mov     rcx, r14; void *
0x1800767eb  mov     r8d, 334h; Size
0x1800767f1  call    memset_0
0x1800767f6  mov     r9b, [rdi+11h]
0x1800767fa  mov     r8, rdi
0x1800767fd  mov     edx, 1
0x180076802  mov     [rsp+78h+var_58], r14
0x180076807  mov     rcx, rsi
0x18007680a  call    _readDrcInstructionsUniDrc
0x18007680f  test    eax, eax
0x180076811  jnz     loc_180076989
0x180076817  lea     eax, [r12+r13]
0x18007681b  cmp     eax, 0Ch
0x18007681e  jge     loc_1800768D5
0x180076824  cdqe
0x180076826  imul    r15, rax, 334h
0x18007682d  test    ebp, ebp
0x18007682f  jnz     short loc_180076851
0x180076831  lea     rdx, [rdi+1554h]
0x180076838  mov     r8d, 334h; Size
0x18007683e  add     rdx, r15; Buf2
0x180076841  mov     rcx, r14; Buf1
0x180076844  call    memcmp_0
0x180076849  test    eax, eax
0x18007684b  mov     ebp, ebx
0x18007684d  setnz   bpl
0x180076851  mov     eax, 6
0x180076856  lea     rcx, [rdi+1554h]
0x18007685d  add     rcx, r15
0x180076860  lea     edx, [rax+7Ah]
0x180076863  movups  xmm0, xmmword ptr [r14]
0x180076867  movups  xmmword ptr [rcx], xmm0
0x18007686a  movups  xmm1, xmmword ptr [r14+10h]
0x18007686f  movups  xmmword ptr [rcx+10h], xmm1
0x180076873  movups  xmm0, xmmword ptr [r14+20h]
0x180076878  movups  xmmword ptr [rcx+20h], xmm0
0x18007687c  movups  xmm1, xmmword ptr [r14+30h]
0x180076881  movups  xmmword ptr [rcx+30h], xmm1
0x180076885  movups  xmm0, xmmword ptr [r14+40h]
0x18007688a  movups  xmmword ptr [rcx+40h], xmm0
0x18007688e  movups  xmm1, xmmword ptr [r14+50h]
0x180076893  movups  xmmword ptr [rcx+50h], xmm1
0x180076897  movups  xmm0, xmmword ptr [r14+60h]
0x18007689c  movups  xmmword ptr [rcx+60h], xmm0
0x1800768a0  movups  xmm1, xmmword ptr [r14+70h]
0x1800768a5  add     r14, rdx
0x1800768a8  movups  xmmword ptr [rcx+70h], xmm1
0x1800768ac  add     rcx, rdx
0x1800768af  sub     rax, 1
0x1800768b3  jnz     short loc_180076863
0x1800768b5  movups  xmm0, xmmword ptr [r14]
0x1800768b9  movups  xmmword ptr [rcx], xmm0
0x1800768bc  movups  xmm1, xmmword ptr [r14+10h]
0x1800768c1  movups  xmmword ptr [rcx+10h], xmm1
0x1800768c5  movups  xmm0, xmmword ptr [r14+20h]
0x1800768ca  movups  xmmword ptr [rcx+20h], xmm0
0x1800768ce  mov     eax, [r14+30h]
0x1800768d2  mov     [rcx+30h], eax
0x1800768d5  movzx   eax, byte ptr [rdi+10h]
0x1800768d9  inc     r12d
0x1800768dc  cmp     r12d, eax
0x1800768df  jl      loc_1800767DF
0x1800768e5  jmp     short loc_180076905
0x1800768e7  mov     dl, [rdi+0Ch]
0x1800768ea  mov     ecx, ebx
0x1800768ec  mov     [rdi+0Ch], bl
0x1800768ef  mov     al, [rdi+0Fh]
0x1800768f2  test    al, al
0x1800768f4  mov     [rdi+0Fh], bl
0x1800768f7  mov     eax, ebx
0x1800768f9  setnz   cl
0x1800768fc  test    dl, dl
0x1800768fe  setnz   al
0x180076901  or      ecx, eax
0x180076903  or      ebp, ecx
0x180076905  mov     edx, 1
0x18007690a  mov     rcx, rsi
0x18007690d  call    CDKreadBits
0x180076912  mov     r12d, 4
0x180076918  cmp     eax, 1
0x18007691b  jnz     short loc_180076942
0x18007691d  mov     edx, r12d
0x180076920  mov     rcx, rsi
0x180076923  call    CDKreadBits
0x180076928  mov     r15d, eax
0x18007692b  mov     r14d, ebx
0x18007692e  test    eax, eax
0x180076930  jle     short loc_180076942
0x180076932  mov     rcx, rsi
0x180076935  call    _skipLoudEqInstructions
0x18007693a  inc     r14d
0x18007693d  cmp     r14d, r15d
0x180076940  jl      short loc_180076932
0x180076942  mov     edx, 1
0x180076947  mov     rcx, rsi
0x18007694a  call    CDKreadBits
0x18007694f  cmp     eax, 1
0x180076952  jnz     short loc_180076980
0x180076954  mov     rcx, rsi
0x180076957  call    _skipEqCoefficients
0x18007695c  mov     edx, r12d
0x18007695f  mov     rcx, rsi
0x180076962  call    CDKreadBits
0x180076967  mov     r14d, eax
0x18007696a  test    eax, eax
0x18007696c  jle     short loc_180076980
0x18007696e  mov     rdx, rdi
0x180076971  mov     rcx, rsi
0x180076974  call    _skipEqInstructions
0x180076979  inc     ebx
0x18007697b  cmp     ebx, r14d
0x18007697e  jl      short loc_18007696E
0x180076980  mov     [rdi+5259h], bpl
0x180076987  xor     eax, eax
0x180076989  add     rsp, 38h
0x18007698d  pop     r15
0x18007698f  pop     r14
0x180076991  pop     r13
0x180076993  pop     r12
  ... truncated ...
```
