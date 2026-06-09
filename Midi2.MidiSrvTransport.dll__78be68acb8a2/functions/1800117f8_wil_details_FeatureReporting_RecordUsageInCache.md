# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800117f8`
- end: `0x180011ad2`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000feec`

## callees

- `0x1800117f8`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // edx
  unsigned __int32 v9; // ett
  int v10; // ecx
  signed __int32 v11; // edx
  int v12; // ebx
  signed __int32 v13; // r9d
  signed __int32 v14; // eax
  signed __int32 v15; // ecx
  BOOL v16; // r9d
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // edx
  unsigned int v21; // r8d
  signed __int32 v22; // eax
  signed __int32 v23; // edx
  BOOL v24; // ebp
  unsigned int v25; // eax
  int v26; // r9d
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  signed __int32 v29; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v23 = *a2;
      v24 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v25 = v23 | 1;
        if ( (((v23 | 1u) >> 14) & 1) != v24 )
        {
          if ( ((v25 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v25 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v25 = v23 & 0xFFFFC01E | 1;
          }
          v26 = 0;
          if ( a3 == 4 )
            v26 = 0x4000;
          v25 = v25 & 0xFFFFBFFF | v26;
        }
        v27 = (v25 >> 5) & 0x1FF;
        v28 = v27 + 1;
        if ( v27 + 1 > 0x1FF || v28 < v27 )
        {
          LOWORD(v28) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v27;
        }
        v29 = _InterlockedCompareExchange(
                a2,
                v25 ^ ((unsigned __int16)v25 ^ (unsigned __int16)(32 * v28)) & 0x3FE0,
                v23);
        if ( v23 == v29 )
          break;
        v23 = v29;
      }
      *(_DWORD *)a1 = (v23 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v15 = *a2;
      v16 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v17 = v15 | 1;
        if ( (((v15 | 1u) >> 22) & 1) != v16 )
        {
          if ( ((v17 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v17 >> 15) & 0x7F;
            v18 = 5;
            if ( a3 != 1 )
              v18 = 1;
            v17 = v15 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v18;
          }
          v19 = 0;
          if ( a3 == 5 )
            v19 = 0x400000;
          v17 = v17 & 0xFFBFFFFF | v19;
        }
        v20 = (v17 >> 15) & 0x7F;
        v21 = v20 + 1;
        if ( v20 + 1 > 0x7F || v21 < v20 )
        {
          v21 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v20;
        }
        v22 = _InterlockedCompareExchange(a2, v17 ^ (v17 ^ (v21 << 15)) & 0x3F8000, v15);
        if ( v15 == v22 )
          break;
        v15 = v22;
      }
      *(_DWORD *)a1 = (v15 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v6 = a3 - 320;
    if ( v6 >= 64 )
      goto LABEL_16;
    v7 = *((_DWORD *)a2 + 1);
    do
    {
      v8 = (v7 & 0x10) != 0 && ((v7 >> 5) & 0x3F) == v6;
      *(_DWORD *)(a1 + 16) = v8;
      v9 = v7;
      v7 = _InterlockedCompareExchange(
             a2 + 1,
             v7 ^ ((unsigned __int16)v7 ^ (unsigned __int16)(32 * v6)) & 0x7E0 | 0x10,
             v7);
    }
    while ( v9 != v7 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v10 = 0;
  switch ( a3 )
  {
    case 2:
      v10 = 2;
      break;
    case 3:
      v10 = 8;
      break;
    case 6:
      v10 = 4;
      break;
    case 7:
      v10 = 16;
      break;
  }
  v11 = *a2;
  v12 = 1;
  while ( 1 )
  {
    v13 = v11 | v10 | 1;
    *(_DWORD *)(a1 + 16) = (v11 | v10) == v11;
    if ( (v11 | v10) == v11 )
      v13 = v11 | v10;
    v14 = _InterlockedCompareExchange(a2, v13, v11);
    if ( v11 == v14 )
      break;
    v11 = v14;
  }
  if ( (v13 & 1) == 0 || (v11 & 1) != 0 )
    v12 = 0;
  *(_DWORD *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x1800117f8  push    rbx
0x1800117fa  push    rbp
0x1800117fb  push    rsi
0x1800117fc  push    rdi
0x1800117fd  xor     eax, eax
0x1800117ff  xorps   xmm0, xmm0
0x180011802  mov     r11d, r8d
0x180011805  mov     rsi, rdx
0x180011808  mov     r10, rcx
0x18001180b  mov     r9d, r8d
0x18001180e  movups  xmmword ptr [rcx], xmm0
0x180011811  mov     [rcx+10h], rax
0x180011815  test    r8d, r8d
0x180011818  jz      loc_1800119FC
0x18001181e  sub     r9d, 1
0x180011822  jz      loc_180011943
0x180011828  sub     r9d, 1
0x18001182c  jz      loc_1800118CA
0x180011832  sub     r9d, 1
0x180011836  jz      loc_1800118CA
0x18001183c  sub     r9d, 1
0x180011840  jz      loc_1800119FC
0x180011846  sub     r9d, 1
0x18001184a  jz      loc_180011943
0x180011850  sub     r9d, 1
0x180011854  jz      short loc_1800118CA
0x180011856  cmp     r9d, 1
0x18001185a  jz      short loc_1800118CA
0x18001185c  add     r8d, 0FFFFFEC0h
0x180011863  lea     ebx, [rax+1]
0x180011866  cmp     r8d, 40h ; '@'
0x18001186a  jge     short loc_1800118B5
0x18001186c  mov     eax, [rdx+4]
0x18001186f  lea     ecx, [rbx+0Fh]
0x180011872  mov     r9d, r8d
0x180011875  shl     r9d, 5
0x180011879  test    cl, al
0x18001187b  jz      short loc_18001188E
0x18001187d  mov     edx, eax
0x18001187f  shr     edx, 5
0x180011882  and     edx, 3Fh
0x180011885  cmp     edx, r8d
0x180011888  jnz     short loc_18001188E
0x18001188a  mov     edx, ebx
0x18001188c  jmp     short loc_180011890
0x18001188e  xor     edx, edx
0x180011890  mov     [r10+10h], edx
0x180011894  mov     edx, r9d
0x180011897  xor     edx, eax
0x180011899  and     edx, 7E0h
0x18001189f  xor     edx, eax
0x1800118a1  or      edx, ecx
0x1800118a3  lock cmpxchg [rsi+4], edx
0x1800118a8  jnz     short loc_180011879
0x1800118aa  cmp     dword ptr [r10+10h], 0
0x1800118af  jnz     loc_180011ACA
0x1800118b5  mov     [r10+8], r11d
0x1800118b9  mov     [r10+4], ebx
0x1800118bd  mov     dword ptr [r10+0Ch], 0
0x1800118c5  jmp     loc_180011ACA
0x1800118ca  xor     ecx, ecx
0x1800118cc  sub     r11d, 2
0x1800118d0  jz      short loc_1800118F8
0x1800118d2  sub     r11d, 1
0x1800118d6  jz      short loc_1800118F1
0x1800118d8  sub     r11d, 3
0x1800118dc  jz      short loc_1800118EA
0x1800118de  cmp     r11d, 1
0x1800118e2  jnz     short loc_1800118FD
0x1800118e4  lea     ecx, [r11+0Fh]
0x1800118e8  jmp     short loc_1800118FD
0x1800118ea  mov     ecx, 4
0x1800118ef  jmp     short loc_1800118FD
0x1800118f1  mov     ecx, 8
0x1800118f6  jmp     short loc_1800118FD
0x1800118f8  mov     ecx, 2
0x1800118fd  mov     edx, [rdx]
0x1800118ff  mov     ebx, 1
0x180011904  xor     eax, eax
0x180011906  mov     r8d, ecx
0x180011909  or      r8d, edx
0x18001190c  cmp     r8d, edx
0x18001190f  mov     r9d, r8d
0x180011912  setz    al
0x180011915  or      r9d, ebx
0x180011918  cmp     r8d, edx
0x18001191b  mov     [r10+10h], eax
0x18001191f  mov     eax, edx
0x180011921  cmovz   r9d, r8d
0x180011925  lock cmpxchg [rsi], r9d
0x18001192a  jz      short loc_180011930
0x18001192c  mov     edx, eax
0x18001192e  jmp     short loc_180011904
0x180011930  test    bl, r9b
0x180011933  jz      short loc_180011939
0x180011935  test    bl, dl
0x180011937  jz      short loc_18001193B
0x180011939  xor     ebx, ebx
0x18001193b  mov     [r10], ebx
0x18001193e  jmp     loc_180011ACA
0x180011943  mov     ecx, [rdx]
0x180011945  xor     r9d, r9d
0x180011948  cmp     r11d, 5
0x18001194c  mov     ebx, 1
0x180011951  setz    r9b
0x180011955  mov     eax, ecx
0x180011957  mov     dword ptr [r10+4], 0
0x18001195f  or      eax, ebx
0x180011961  mov     edx, eax
0x180011963  shr     edx, 16h
0x180011966  and     edx, ebx
0x180011968  cmp     edx, r9d
0x18001196b  jz      short loc_1800119AD
0x18001196d  mov     r8d, eax
0x180011970  shr     r8d, 0Fh
0x180011974  and     r8d, 7Fh
0x180011978  jbe     short loc_180011992
0x18001197a  cmp     r11d, ebx
0x18001197d  mov     [r10+4], r8d
0x180011981  mov     edx, 5
0x180011986  cmovnz  edx, ebx
0x180011989  and     eax, 0FFC07FFFh
0x18001198e  mov     [r10+8], edx
0x180011992  xor     r8d, r8d
0x180011995  mov     edx, 400000h
0x18001199a  cmp     r11d, 5
0x18001199e  cmovz   r8d, edx
0x1800119a2  mov     edx, eax
0x1800119a4  btr     edx, 16h
0x1800119a8  mov     eax, r8d
0x1800119ab  or      eax, edx
0x1800119ad  mov     edx, eax
0x1800119af  shr     edx, 0Fh
0x1800119b2  and     edx, 7Fh
0x1800119b5  lea     r8d, [rdx+1]
0x1800119b9  cmp     r8d, 7Fh
0x1800119bd  ja      short loc_1800119C4
0x1800119bf  cmp     r8d, edx
0x1800119c2  jnb     short loc_1800119CF
0x1800119c4  mov     r8d, ebx
0x1800119c7  mov     [r10+8], r11d
0x1800119cb  mov     [r10+4], edx
0x1800119cf  shl     r8d, 0Fh
0x1800119d3  xor     r8d, eax
0x1800119d6  and     r8d, 3F8000h
0x1800119dd  xor     r8d, eax
0x1800119e0  mov     eax, ecx
0x1800119e2  lock cmpxchg [rsi], r8d
0x1800119e7  jz      short loc_1800119F0
0x1800119e9  mov     ecx, eax
0x1800119eb  jmp     loc_180011955
0x1800119f0  not     ecx
0x1800119f2  and     ecx, ebx
0x1800119f4  mov     [r10], ecx
0x1800119f7  jmp     loc_180011AC2
0x1800119fc  mov     edx, [rdx]
0x1800119fe  xor     ebp, ebp
0x180011a00  lea     ecx, [rbp+4]
0x180011a03  cmp     r11d, ecx
0x180011a06  lea     ebx, [rcx-3]
0x180011a09  setz    bpl
0x180011a0d  mov     eax, edx
0x180011a0f  mov     dword ptr [r10+4], 0
0x180011a17  or      eax, ebx
0x180011a19  mov     r8d, eax
0x180011a1c  shr     r8d, 0Eh
0x180011a20  and     r8d, ebx
0x180011a23  cmp     r8d, ebp
0x180011a26  jz      short loc_180011A6F
0x180011a28  mov     edi, eax
0x180011a2a  shr     edi, 5
0x180011a2d  and     edi, 1FFh
0x180011a33  jbe     short loc_180011A51
0x180011a35  mov     r8d, r11d
0x180011a38  mov     [r10+4], edi
0x180011a3c  neg     r8d
0x180011a3f  sbb     r9d, r9d
0x180011a42  not     r9d
0x180011a45  and     r9d, ecx
0x180011a48  mov     [r10+8], r9d
0x180011a4c  and     eax, 0FFFFC01Fh
0x180011a51  xor     r9d, r9d
0x180011a54  mov     r8d, 4000h
0x180011a5a  cmp     r11d, ecx
0x180011a5d  cmovz   r9d, r8d
0x180011a61  mov     r8d, eax
0x180011a64  btr     r8d, 0Eh
0x180011a69  mov     eax, r9d
0x180011a6c  or      eax, r8d
0x180011a6f  mov     r8d, eax
0x180011a72  shr     r8d, 5
0x180011a76  and     r8d, 1FFh
0x180011a7d  lea     r9d, [r8+1]
0x180011a81  cmp     r9d, 1FFh
0x180011a88  ja      short loc_180011A8F
0x180011a8a  cmp     r9d, r8d
0x180011a8d  jnb     short loc_180011A9A
0x180011a8f  mov     r9d, ebx
0x180011a92  mov     [r10+8], r11d
0x180011a96  mov     [r10+4], r8d
0x180011a9a  shl     r9d, 5
0x180011a9e  xor     r9d, eax
0x180011aa1  and     r9d, 3FE0h
0x180011aa8  xor     r9d, eax
0x180011aab  mov     eax, edx
0x180011aad  lock cmpxchg [rsi], r9d
0x180011ab2  jz      short loc_180011ABB
0x180011ab4  mov     edx, eax
0x180011ab6  jmp     loc_180011A0D
0x180011abb  not     edx
0x180011abd  and     edx, ebx
0x180011abf  mov     [r10], edx
0x180011ac2  mov     dword ptr [r10+10h], 0
0x180011aca  mov     rax, r10
0x180011acd  pop     rdi
0x180011ace  pop     rsi
0x180011acf  pop     rbp
0x180011ad0  pop     rbx
0x180011ad1  retn
```
