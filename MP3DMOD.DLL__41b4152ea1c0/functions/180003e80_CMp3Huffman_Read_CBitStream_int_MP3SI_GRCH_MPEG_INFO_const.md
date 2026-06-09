# CMp3Huffman::Read(CBitStream &,int *,MP3SI_GRCH &,MPEG_INFO const &)

- ea: `0x180003e80`
- end: `0x18000421c`
- name: `?Read@CMp3Huffman@@QEAAXAEAVCBitStream@@PEAHAEAUMP3SI_GRCH@@AEBUMPEG_INFO@@@Z`
- size: `924`
- prototype: `void __fastcall(CMp3Huffman *this, struct CBitStream *, int *, struct MP3SI_GRCH *, const struct MPEG_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b80`

## callees

- `0x180003e80`
- `0x180004230`
- `0x1800042f0`

## pseudocode

```c
void __fastcall CMp3Huffman::Read(
        CMp3Huffman *this,
        struct CBitStream *a2,
        int *a3,
        struct MP3SI_GRCH *a4,
        const struct MPEG_INFO *a5)
{
  const struct MPEG_INFO *v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // r8d
  int v13; // edx
  int v14; // ebx
  int v15; // edi
  int v16; // eax
  int v17; // eax
  int BigValues; // eax
  int Count1Area; // eax
  bool v20; // zf
  int v21; // r9d
  __int64 v22; // rax
  BOOL v23; // eax
  __int64 v24; // rdx
  int v25; // r10d
  int v26; // r9d
  __int64 v27; // rdx
  int v28; // eax
  int i; // ecx
  int j; // r9d
  __int64 v31; // rcx
  int v32; // edx
  int v33; // r8d
  int v34; // edx
  __int64 v35; // rcx
  int v36; // eax
  int v37; // edx
  int v38; // r8d
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  int v42[2]; // [rsp+30h] [rbp-38h] BYREF
  int v43; // [rsp+38h] [rbp-30h]

  if ( *((_DWORD *)a4 + 4) && *((_DWORD *)a4 + 5) == 2 )
  {
    v9 = a5;
    v39 = *((int *)a5 + 6);
    if ( *((_DWORD *)a4 + 6) )
    {
      v40 = *((int *)a5 + 1) + 3 * v39;
      if ( *((_BYTE *)a5 + 32) )
        v12 = *((_DWORD *)&sfBandIndex + 37 * v40 + *((int *)a4 + 13) + 1);
      else
        v12 = *((_DWORD *)&sfBandIndex + 37 * v40 + 6)
            + 2 * (*((_DWORD *)&sfBandIndex + 37 * v40 + 27) - *((_DWORD *)&sfBandIndex + 37 * v40 + 26));
    }
    else
    {
      v12 = 3 * *((_DWORD *)&sfBandIndex + 111 * v39 + 37 * *((int *)a5 + 1) + (*((_DWORD *)a4 + 13) + 1) / 3 + 23);
    }
    v13 = 576;
  }
  else
  {
    v9 = a5;
    v10 = 37 * (*((int *)a5 + 1) + 3LL * *((int *)a5 + 6));
    v11 = *((int *)a4 + 13);
    v12 = *((_DWORD *)&sfBandIndex + v10 + v11 + 1);
    v13 = *((_DWORD *)&sfBandIndex + v10 + (int)v11 + *((_DWORD *)a4 + 14) + 2);
  }
  v14 = *(_DWORD *)a4;
  v15 = *((_DWORD *)a4 + 17);
  v16 = 2 * *((_DWORD *)a4 + 1);
  v43 = v16;
  if ( v16 >= v12 )
    v16 = v12;
  v42[0] = v16;
  v17 = v43;
  if ( v43 >= v13 )
    v17 = v13;
  v42[1] = v17;
  BigValues = CHuffmanDecoder::ReadBigValues(this, a2, a3, (const int *)a4 + 7, v42);
  Count1Area = CHuffmanDecoder::ReadCount1Area(this, a2, a3, v15 + 32, BigValues, v14);
  v20 = *((_DWORD *)a4 + 4) == 0;
  v21 = Count1Area;
  *((_DWORD *)a4 + 19) = Count1Area;
  if ( v20 || *((_DWORD *)a4 + 5) != 2 )
  {
    *((_DWORD *)a4 + 20) = 1;
LABEL_9:
    v22 = 0;
    do
    {
      if ( v21 <= *((_DWORD *)&sfBandIndex + 111 * *((int *)v9 + 6) + 37 * *((int *)v9 + 1) + v22) )
        break;
      v22 = (unsigned int)(v22 + 1);
    }
    while ( (int)v22 < 22 );
    *((_DWORD *)a4 + 21) = v22;
    return;
  }
  if ( *((_DWORD *)a4 + 6) )
  {
    v41 = 28;
    if ( !*((_BYTE *)v9 + 32) )
      v41 = 20;
    v23 = v21 <= *(_DWORD *)((char *)&sfBandIndex + 444 * *((int *)v9 + 6) + 148 * *((int *)v9 + 1) + v41);
  }
  else
  {
    v23 = 0;
  }
  *((_DWORD *)a4 + 20) = v23;
  if ( v23 )
    goto LABEL_9;
  v24 = 0;
  do
  {
    if ( v21 <= 3 * dword_18001413C[111 * *((int *)v9 + 6) + 37 * *((int *)v9 + 1) + v24] )
      break;
    v24 = (unsigned int)(v24 + 1);
  }
  while ( (int)v24 < 13 );
  *((_DWORD *)a4 + 22) = v24;
  v25 = v24 - 1;
  v26 = v24 - 1;
  *((_DWORD *)a4 + 23) = v24;
  *((_DWORD *)a4 + 24) = v24;
  *((_DWORD *)a4 + 25) = v24;
  while ( v26 >= 0 )
  {
    v27 = v26 + 37 * (*((int *)v9 + 1) + 3LL * *((int *)v9 + 6));
    v28 = *((_DWORD *)&sfBandIndex + v27 + 23);
    for ( i = 3 * v28; i < 3 * v28 + *((_DWORD *)&sfBandIndex + v27 + 24) - v28; ++i )
    {
      if ( a3[i] )
      {
        *((_DWORD *)a4 + 23) = v26 + 1;
        goto LABEL_28;
      }
    }
    --v26;
  }
LABEL_28:
  for ( j = v25; j >= 0; --j )
  {
    v31 = j + 37 * (*((int *)v9 + 1) + 3LL * *((int *)v9 + 6));
    v32 = *((_DWORD *)&sfBandIndex + v31 + 23);
    LODWORD(v31) = *((_DWORD *)&sfBandIndex + v31 + 24) - v32;
    v33 = v32 + v31 + 2 * v32;
    v34 = v33 + v31;
    while ( v33 < v34 )
    {
      if ( a3[v33] )
      {
        *((_DWORD *)a4 + 24) = j + 1;
        goto LABEL_35;
      }
      ++v33;
    }
  }
LABEL_35:
  while ( v25 >= 0 )
  {
    v35 = v25 + 37 * (*((int *)v9 + 1) + 3LL * *((int *)v9 + 6));
    v36 = *((_DWORD *)&sfBandIndex + v35 + 23);
    LODWORD(v35) = *((_DWORD *)&sfBandIndex + v35 + 24) - v36;
    v37 = 3 * v36 + 2 * v35;
    v38 = v35 + v37;
    while ( v37 < v38 )
    {
      if ( a3[v37] )
      {
        *((_DWORD *)a4 + 25) = v25 + 1;
        return;
      }
      ++v37;
    }
    --v25;
  }
}

```

## disassembly

```asm
0x180003e80  mov     rax, rsp
0x180003e83  mov     [rax+8], rcx
0x180003e87  push    rbp
0x180003e88  push    rsi
0x180003e89  push    r12
0x180003e8b  push    r14
0x180003e8d  push    r15
0x180003e8f  sub     rsp, 40h
0x180003e93  cmp     dword ptr [r9+10h], 0
0x180003e98  mov     rsi, r9
0x180003e9b  mov     [rax+10h], rbx
0x180003e9f  mov     rbp, r8
0x180003ea2  mov     [rax+18h], rdi
0x180003ea6  mov     r10, rcx
0x180003ea9  mov     [rax+20h], r13
0x180003ead  mov     r13, rdx
0x180003eb0  jnz     loc_18000412B
0x180003eb6  mov     r15, [rsp+68h+arg_20]
0x180003ebe  lea     r12, ?sfBandIndex@@3QAY02$$CBU_unnamed_type_SF_BAND_INDEX_@@A; _unnamed_type_SF_BAND_INDEX_ const (near * sfBandIndex)[3]
0x180003ec5  movsxd  rax, dword ptr [r15+18h]
0x180003ec9  lea     rcx, [rax+rax*2]
0x180003ecd  movsxd  rax, dword ptr [r15+4]
0x180003ed1  add     rcx, rax
0x180003ed4  imul    rdx, rcx, 25h ; '%'
0x180003ed8  movsxd  rcx, dword ptr [r9+34h]
0x180003edc  lea     rax, [rdx+rcx]
0x180003ee0  mov     r8d, [r12+rax*4+4]
0x180003ee5  mov     eax, [r9+38h]
0x180003ee9  add     eax, ecx
0x180003eeb  movsxd  rcx, eax
0x180003eee  add     rcx, rdx
0x180003ef1  mov     edx, [r12+rcx*4+8]
0x180003ef6  mov     ecx, [r9+4]
0x180003efa  mov     ebx, [r9]
0x180003efd  add     ecx, ecx
0x180003eff  mov     edi, [r9+44h]
0x180003f03  cmp     ecx, r8d
0x180003f06  mov     eax, ecx
0x180003f08  mov     [rsp+68h+var_30], ecx
0x180003f0c  cmovge  eax, r8d
0x180003f10  cmp     ecx, edx
0x180003f12  mov     [rsp+68h+var_38], eax
0x180003f16  mov     r8, rbp; int *
0x180003f19  mov     eax, ecx
0x180003f1b  mov     rcx, r10; this
0x180003f1e  cmovge  eax, edx
0x180003f21  add     r9, 1Ch; int *
0x180003f25  mov     [rsp+68h+var_34], eax
0x180003f29  mov     rdx, r13; struct CBitStream *
0x180003f2c  lea     rax, [rsp+68h+var_38]
0x180003f31  mov     [rsp+68h+var_48], rax; int *
0x180003f36  call    ?ReadBigValues@CHuffmanDecoder@@AEAAHAEAVCBitStream@@PEAHPEBH2@Z; CHuffmanDecoder::ReadBigValues(CBitStream &,int *,int const *,int const *)
0x180003f3b  mov     rcx, [rsp+68h+arg_0]; this
0x180003f40  lea     r9d, [rdi+20h]; int
0x180003f44  mov     r8, rbp; int *
0x180003f47  mov     [rsp+68h+var_40], ebx; int
0x180003f4b  mov     rdx, r13; struct CBitStream *
0x180003f4e  mov     dword ptr [rsp+68h+var_48], eax; int
0x180003f52  call    ?ReadCount1Area@CHuffmanDecoder@@AEAAHAEAVCBitStream@@PEAHHHH@Z; CHuffmanDecoder::ReadCount1Area(CBitStream &,int *,int,int,int)
0x180003f57  cmp     dword ptr [rsi+10h], 0
0x180003f5b  mov     r9d, eax
0x180003f5e  mov     r13, [rsp+68h+arg_18]
0x180003f66  mov     rdi, [rsp+68h+arg_10]
0x180003f6e  mov     rbx, [rsp+68h+arg_8]
0x180003f73  mov     [rsi+4Ch], eax
0x180003f76  jnz     short loc_180003FB7
0x180003f78  mov     dword ptr [rsi+50h], 1
0x180003f7f  movsxd  rcx, dword ptr [r15+18h]
0x180003f83  xor     eax, eax
0x180003f85  lea     rdx, [rcx+rcx*2]
0x180003f89  movsxd  rcx, dword ptr [r15+4]
0x180003f8d  add     rdx, rcx
0x180003f90  imul    r8, rdx, 94h
0x180003f97  add     r8, r12
0x180003f9a  cmp     r9d, [r8+rax*4]
0x180003f9e  jle     short loc_180003FA7
0x180003fa0  inc     eax
0x180003fa2  cmp     eax, 16h
0x180003fa5  jl      short loc_180003F9A
0x180003fa7  mov     [rsi+54h], eax
0x180003faa  add     rsp, 40h
0x180003fae  pop     r15
0x180003fb0  pop     r14
0x180003fb2  pop     r12
0x180003fb4  pop     rsi
0x180003fb5  pop     rbp
0x180003fb6  retn
0x180003fb7  cmp     dword ptr [rsi+14h], 2
0x180003fbb  jnz     short loc_180003F78
0x180003fbd  cmp     dword ptr [rsi+18h], 0
0x180003fc1  jnz     loc_1800041E3
0x180003fc7  xor     eax, eax
0x180003fc9  mov     [rsi+50h], eax
0x180003fcc  test    eax, eax
0x180003fce  jnz     short loc_180003F7F
0x180003fd0  movsxd  rax, dword ptr [r15+18h]
0x180003fd4  xor     edx, edx
0x180003fd6  lea     rcx, [rax+rax*2]
0x180003fda  movsxd  rax, dword ptr [r15+4]
0x180003fde  add     rcx, rax
0x180003fe1  lea     rax, dword_18001413C
0x180003fe8  imul    r8, rcx, 94h
0x180003fef  add     r8, rax
0x180003ff2  mov     ecx, [r8+rdx*4]
0x180003ff6  lea     eax, [rcx+rcx*2]
0x180003ff9  cmp     r9d, eax
0x180003ffc  jle     short loc_180004005
0x180003ffe  inc     edx
0x180004000  cmp     edx, 0Dh
0x180004003  jl      short loc_180003FF2
0x180004005  mov     [rsi+58h], edx
0x180004008  lea     r10d, [rdx-1]
0x18000400c  mov     r9d, r10d
0x18000400f  mov     [rsi+5Ch], edx
0x180004012  mov     [rsi+60h], edx
0x180004015  mov     [rsi+64h], edx
0x180004018  test    r9d, r9d
0x18000401b  js      short loc_18000406E
0x18000401d  movsxd  rax, dword ptr [r15+18h]
0x180004021  lea     rcx, [rax+rax*2]
0x180004025  movsxd  rax, dword ptr [r15+4]
0x180004029  add     rcx, rax
0x18000402c  movsxd  rax, r9d
0x18000402f  imul    rdx, rcx, 25h ; '%'
0x180004033  add     rdx, rax
0x180004036  mov     eax, [r12+rdx*4+5Ch]
0x18000403b  mov     r8d, [r12+rdx*4+60h]
0x180004040  sub     r8d, eax
0x180004043  lea     ecx, [rax+rax*2]
0x180004046  add     r8d, ecx
0x180004049  nop     dword ptr [rax+00000000h]
0x180004050  cmp     ecx, r8d
0x180004053  jge     loc_18000418B
0x180004059  movsxd  rax, ecx
0x18000405c  cmp     dword ptr [rbp+rax*4+0], 0
0x180004061  jnz     short loc_180004067
0x180004063  inc     ecx
0x180004065  jmp     short loc_180004050
0x180004067  lea     eax, [r9+1]
0x18000406b  mov     [rsi+5Ch], eax
0x18000406e  mov     r9d, r10d
0x180004071  test    r9d, r9d
0x180004074  js      short loc_1800040C5
0x180004076  movsxd  rax, dword ptr [r15+18h]
0x18000407a  lea     rcx, [rax+rax*2]
0x18000407e  movsxd  rax, dword ptr [r15+4]
0x180004082  add     rcx, rax
0x180004085  movsxd  rax, r9d
0x180004088  imul    rcx, 25h ; '%'
0x18000408c  add     rcx, rax
0x18000408f  mov     edx, [r12+rcx*4+5Ch]
0x180004094  mov     ecx, [r12+rcx*4+60h]
0x180004099  sub     ecx, edx
0x18000409b  lea     r8d, [rcx+rdx*2]
0x18000409f  add     r8d, edx
0x1800040a2  lea     edx, [r8+rcx]
0x1800040a6  cmp     r8d, edx
0x1800040a9  jge     loc_180004193
0x1800040af  movsxd  rax, r8d
0x1800040b2  cmp     dword ptr [rbp+rax*4+0], 0
0x1800040b7  jnz     short loc_1800040BE
0x1800040b9  inc     r8d
0x1800040bc  jmp     short loc_1800040A6
0x1800040be  lea     eax, [r9+1]
0x1800040c2  mov     [rsi+60h], eax
0x1800040c5  test    r10d, r10d
0x1800040c8  js      loc_180003FAA
0x1800040ce  movsxd  rax, dword ptr [r15+18h]
0x1800040d2  lea     rcx, [rax+rax*2]
0x1800040d6  movsxd  rax, dword ptr [r15+4]
0x1800040da  add     rcx, rax
0x1800040dd  movsxd  rax, r10d
0x1800040e0  imul    rcx, 25h ; '%'
0x1800040e4  add     rcx, rax
0x1800040e7  mov     eax, [r12+rcx*4+5Ch]
0x1800040ec  mov     ecx, [r12+rcx*4+60h]
0x1800040f1  sub     ecx, eax
0x1800040f3  lea     eax, [rax+rax*2]
0x1800040f6  lea     edx, [rax+rcx*2]
0x1800040f9  lea     r8d, [rcx+rdx]
0x1800040fd  nop     dword ptr [rax]
0x180004100  cmp     edx, r8d
0x180004103  jge     loc_18000419B
0x180004109  movsxd  rax, edx
0x18000410c  cmp     dword ptr [rbp+rax*4+0], 0
0x180004111  jnz     short loc_180004117
0x180004113  inc     edx
0x180004115  jmp     short loc_180004100
0x180004117  lea     eax, [r10+1]
0x18000411b  mov     [rsi+64h], eax
0x18000411e  add     rsp, 40h
0x180004122  pop     r15
0x180004124  pop     r14
0x180004126  pop     r12
0x180004128  pop     rsi
0x180004129  pop     rbp
0x18000412a  retn
0x18000412b  cmp     dword ptr [r9+14h], 2
0x180004130  jnz     loc_180003EB6
0x180004136  cmp     dword ptr [r9+18h], 0
0x18000413b  lea     r12, ?sfBandIndex@@3QAY02$$CBU_unnamed_type_SF_BAND_INDEX_@@A; _unnamed_type_SF_BAND_INDEX_ const (near * sfBandIndex)[3]
0x180004142  mov     r15, [rsp+68h+arg_20]
0x18000414a  movsxd  rax, dword ptr [r15+18h]
0x18000414e  jnz     short loc_1800041A3
0x180004150  lea     rcx, [rax+rax*2]
0x180004154  movsxd  rax, dword ptr [r15+4]
0x180004158  add     rcx, rax
0x18000415b  mov     eax, 55555556h
0x180004160  imul    r8, rcx, 25h ; '%'
0x180004164  mov     ecx, [r9+34h]
0x180004168  inc     ecx
0x18000416a  imul    ecx
0x18000416c  mov     eax, edx
0x18000416e  shr     eax, 1Fh
0x180004171  add     eax, edx
0x180004173  cdqe
0x180004175  add     r8, rax
0x180004178  mov     eax, [r12+r8*4+5Ch]
0x18000417d  lea     r8d, [rax+rax*2]
0x180004181  mov     edx, 240h
0x180004186  jmp     loc_180003EF6
0x18000418b  dec     r9d
0x18000418e  jmp     loc_180004018
0x180004193  dec     r9d
0x180004196  jmp     loc_180004071
0x18000419b  dec     r10d
0x18000419e  jmp     loc_1800040C5
0x1800041a3  lea     rdx, [rax+rax*2]
0x1800041a7  movsxd  rax, dword ptr [r15+4]
0x1800041ab  add     rdx, rax
0x1800041ae  cmp     byte ptr [r15+20h], 0
0x1800041b3  jz      short loc_1800041C7
0x1800041b5  movsxd  rcx, dword ptr [r9+34h]
0x1800041b9  imul    rax, rdx, 25h ; '%'
0x1800041bd  add     rcx, rax
0x1800041c0  mov     r8d, [r12+rcx*4+4]
0x1800041c5  jmp     short loc_180004181
0x1800041c7  imul    rax, rdx, 94h
0x1800041ce  mov     ecx, [rax+r12+6Ch]
0x1800041d3  sub     ecx, [rax+r12+68h]
0x1800041d8  mov     eax, [rax+r12+18h]
0x1800041dd  lea     r8d, [rax+rcx*2]
0x1800041e1  jmp     short loc_180004181
0x1800041e3  movsxd  rax, dword ptr [r15+18h]
0x1800041e7  lea     rcx, [rax+rax*2]
0x1800041eb  movsxd  rax, dword ptr [r15+4]
0x1800041ef  add     rcx, rax
0x1800041f2  mov     eax, 1Ch
0x1800041f7  imul    rdx, rcx, 94h
0x1800041fe  cmp     byte ptr [r15+20h], 0
0x180004203  mov     ecx, 14h
0x180004208  cmovz   eax, ecx
0x18000420b  add     rdx, rax
0x18000420e  xor     eax, eax
0x180004210  cmp     r9d, [rdx+r12]
0x180004214  setle   al
0x180004217  jmp     loc_180003FC9
```
