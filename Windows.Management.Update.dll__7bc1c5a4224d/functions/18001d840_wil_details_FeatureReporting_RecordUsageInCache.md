# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001d840`
- end: `0x18001db1a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c5d8`

## callees

- `0x18001d840`

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
0x18001d840  push    rbx
0x18001d842  push    rbp
0x18001d843  push    rsi
0x18001d844  push    rdi
0x18001d845  xor     eax, eax
0x18001d847  xorps   xmm0, xmm0
0x18001d84a  mov     r11d, r8d
0x18001d84d  mov     rsi, rdx
0x18001d850  mov     r10, rcx
0x18001d853  mov     r9d, r8d
0x18001d856  movups  xmmword ptr [rcx], xmm0
0x18001d859  mov     [rcx+10h], rax
0x18001d85d  test    r8d, r8d
0x18001d860  jz      loc_18001DA44
0x18001d866  sub     r9d, 1
0x18001d86a  jz      loc_18001D98B
0x18001d870  sub     r9d, 1
0x18001d874  jz      loc_18001D912
0x18001d87a  sub     r9d, 1
0x18001d87e  jz      loc_18001D912
0x18001d884  sub     r9d, 1
0x18001d888  jz      loc_18001DA44
0x18001d88e  sub     r9d, 1
0x18001d892  jz      loc_18001D98B
0x18001d898  sub     r9d, 1
0x18001d89c  jz      short loc_18001D912
0x18001d89e  cmp     r9d, 1
0x18001d8a2  jz      short loc_18001D912
0x18001d8a4  add     r8d, 0FFFFFEC0h
0x18001d8ab  lea     ebx, [rax+1]
0x18001d8ae  cmp     r8d, 40h ; '@'
0x18001d8b2  jge     short loc_18001D8FD
0x18001d8b4  mov     eax, [rdx+4]
0x18001d8b7  lea     ecx, [rbx+0Fh]
0x18001d8ba  mov     r9d, r8d
0x18001d8bd  shl     r9d, 5
0x18001d8c1  test    cl, al
0x18001d8c3  jz      short loc_18001D8D6
0x18001d8c5  mov     edx, eax
0x18001d8c7  shr     edx, 5
0x18001d8ca  and     edx, 3Fh
0x18001d8cd  cmp     edx, r8d
0x18001d8d0  jnz     short loc_18001D8D6
0x18001d8d2  mov     edx, ebx
0x18001d8d4  jmp     short loc_18001D8D8
0x18001d8d6  xor     edx, edx
0x18001d8d8  mov     [r10+10h], edx
0x18001d8dc  mov     edx, r9d
0x18001d8df  xor     edx, eax
0x18001d8e1  and     edx, 7E0h
0x18001d8e7  xor     edx, eax
0x18001d8e9  or      edx, ecx
0x18001d8eb  lock cmpxchg [rsi+4], edx
0x18001d8f0  jnz     short loc_18001D8C1
0x18001d8f2  cmp     dword ptr [r10+10h], 0
0x18001d8f7  jnz     loc_18001DB12
0x18001d8fd  mov     [r10+8], r11d
0x18001d901  mov     [r10+4], ebx
0x18001d905  mov     dword ptr [r10+0Ch], 0
0x18001d90d  jmp     loc_18001DB12
0x18001d912  xor     ecx, ecx
0x18001d914  sub     r11d, 2
0x18001d918  jz      short loc_18001D940
0x18001d91a  sub     r11d, 1
0x18001d91e  jz      short loc_18001D939
0x18001d920  sub     r11d, 3
0x18001d924  jz      short loc_18001D932
0x18001d926  cmp     r11d, 1
0x18001d92a  jnz     short loc_18001D945
0x18001d92c  lea     ecx, [r11+0Fh]
0x18001d930  jmp     short loc_18001D945
0x18001d932  mov     ecx, 4
0x18001d937  jmp     short loc_18001D945
0x18001d939  mov     ecx, 8
0x18001d93e  jmp     short loc_18001D945
0x18001d940  mov     ecx, 2
0x18001d945  mov     edx, [rdx]
0x18001d947  mov     ebx, 1
0x18001d94c  xor     eax, eax
0x18001d94e  mov     r8d, ecx
0x18001d951  or      r8d, edx
0x18001d954  cmp     r8d, edx
0x18001d957  mov     r9d, r8d
0x18001d95a  setz    al
0x18001d95d  or      r9d, ebx
0x18001d960  cmp     r8d, edx
0x18001d963  mov     [r10+10h], eax
0x18001d967  mov     eax, edx
0x18001d969  cmovz   r9d, r8d
0x18001d96d  lock cmpxchg [rsi], r9d
0x18001d972  jz      short loc_18001D978
0x18001d974  mov     edx, eax
0x18001d976  jmp     short loc_18001D94C
0x18001d978  test    bl, r9b
0x18001d97b  jz      short loc_18001D981
0x18001d97d  test    bl, dl
0x18001d97f  jz      short loc_18001D983
0x18001d981  xor     ebx, ebx
0x18001d983  mov     [r10], ebx
0x18001d986  jmp     loc_18001DB12
0x18001d98b  mov     ecx, [rdx]
0x18001d98d  xor     r9d, r9d
0x18001d990  cmp     r11d, 5
0x18001d994  mov     ebx, 1
0x18001d999  setz    r9b
0x18001d99d  mov     eax, ecx
0x18001d99f  mov     dword ptr [r10+4], 0
0x18001d9a7  or      eax, ebx
0x18001d9a9  mov     edx, eax
0x18001d9ab  shr     edx, 16h
0x18001d9ae  and     edx, ebx
0x18001d9b0  cmp     edx, r9d
0x18001d9b3  jz      short loc_18001D9F5
0x18001d9b5  mov     r8d, eax
0x18001d9b8  shr     r8d, 0Fh
0x18001d9bc  and     r8d, 7Fh
0x18001d9c0  jbe     short loc_18001D9DA
0x18001d9c2  cmp     r11d, ebx
0x18001d9c5  mov     [r10+4], r8d
0x18001d9c9  mov     edx, 5
0x18001d9ce  cmovnz  edx, ebx
0x18001d9d1  and     eax, 0FFC07FFFh
0x18001d9d6  mov     [r10+8], edx
0x18001d9da  xor     r8d, r8d
0x18001d9dd  mov     edx, 400000h
0x18001d9e2  cmp     r11d, 5
0x18001d9e6  cmovz   r8d, edx
0x18001d9ea  mov     edx, eax
0x18001d9ec  btr     edx, 16h
0x18001d9f0  mov     eax, r8d
0x18001d9f3  or      eax, edx
0x18001d9f5  mov     edx, eax
0x18001d9f7  shr     edx, 0Fh
0x18001d9fa  and     edx, 7Fh
0x18001d9fd  lea     r8d, [rdx+1]
0x18001da01  cmp     r8d, 7Fh
0x18001da05  ja      short loc_18001DA0C
0x18001da07  cmp     r8d, edx
0x18001da0a  jnb     short loc_18001DA17
0x18001da0c  mov     r8d, ebx
0x18001da0f  mov     [r10+8], r11d
0x18001da13  mov     [r10+4], edx
0x18001da17  shl     r8d, 0Fh
0x18001da1b  xor     r8d, eax
0x18001da1e  and     r8d, 3F8000h
0x18001da25  xor     r8d, eax
0x18001da28  mov     eax, ecx
0x18001da2a  lock cmpxchg [rsi], r8d
0x18001da2f  jz      short loc_18001DA38
0x18001da31  mov     ecx, eax
0x18001da33  jmp     loc_18001D99D
0x18001da38  not     ecx
0x18001da3a  and     ecx, ebx
0x18001da3c  mov     [r10], ecx
0x18001da3f  jmp     loc_18001DB0A
0x18001da44  mov     edx, [rdx]
0x18001da46  xor     ebp, ebp
0x18001da48  lea     ecx, [rbp+4]
0x18001da4b  cmp     r11d, ecx
0x18001da4e  lea     ebx, [rcx-3]
0x18001da51  setz    bpl
0x18001da55  mov     eax, edx
0x18001da57  mov     dword ptr [r10+4], 0
0x18001da5f  or      eax, ebx
0x18001da61  mov     r8d, eax
0x18001da64  shr     r8d, 0Eh
0x18001da68  and     r8d, ebx
0x18001da6b  cmp     r8d, ebp
0x18001da6e  jz      short loc_18001DAB7
0x18001da70  mov     edi, eax
0x18001da72  shr     edi, 5
0x18001da75  and     edi, 1FFh
0x18001da7b  jbe     short loc_18001DA99
0x18001da7d  mov     r8d, r11d
0x18001da80  mov     [r10+4], edi
0x18001da84  neg     r8d
0x18001da87  sbb     r9d, r9d
0x18001da8a  not     r9d
0x18001da8d  and     r9d, ecx
0x18001da90  mov     [r10+8], r9d
0x18001da94  and     eax, 0FFFFC01Fh
0x18001da99  xor     r9d, r9d
0x18001da9c  mov     r8d, 4000h
0x18001daa2  cmp     r11d, ecx
0x18001daa5  cmovz   r9d, r8d
0x18001daa9  mov     r8d, eax
0x18001daac  btr     r8d, 0Eh
0x18001dab1  mov     eax, r9d
0x18001dab4  or      eax, r8d
0x18001dab7  mov     r8d, eax
0x18001daba  shr     r8d, 5
0x18001dabe  and     r8d, 1FFh
0x18001dac5  lea     r9d, [r8+1]
0x18001dac9  cmp     r9d, 1FFh
0x18001dad0  ja      short loc_18001DAD7
0x18001dad2  cmp     r9d, r8d
0x18001dad5  jnb     short loc_18001DAE2
0x18001dad7  mov     r9d, ebx
0x18001dada  mov     [r10+8], r11d
0x18001dade  mov     [r10+4], r8d
0x18001dae2  shl     r9d, 5
0x18001dae6  xor     r9d, eax
0x18001dae9  and     r9d, 3FE0h
0x18001daf0  xor     r9d, eax
0x18001daf3  mov     eax, edx
0x18001daf5  lock cmpxchg [rsi], r9d
0x18001dafa  jz      short loc_18001DB03
0x18001dafc  mov     edx, eax
0x18001dafe  jmp     loc_18001DA55
0x18001db03  not     edx
0x18001db05  and     edx, ebx
0x18001db07  mov     [r10], edx
0x18001db0a  mov     dword ptr [r10+10h], 0
0x18001db12  mov     rax, r10
0x18001db15  pop     rdi
0x18001db16  pop     rsi
0x18001db17  pop     rbp
0x18001db18  pop     rbx
0x18001db19  retn
```
