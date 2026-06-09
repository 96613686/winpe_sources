# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001210c`
- end: `0x1800123e6`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001133c`

## callees

- `0x18001210c`

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
0x18001210c  push    rbx
0x18001210e  push    rbp
0x18001210f  push    rsi
0x180012110  push    rdi
0x180012111  xor     eax, eax
0x180012113  xorps   xmm0, xmm0
0x180012116  mov     r11d, r8d
0x180012119  mov     rsi, rdx
0x18001211c  mov     r10, rcx
0x18001211f  mov     r9d, r8d
0x180012122  movups  xmmword ptr [rcx], xmm0
0x180012125  mov     [rcx+10h], rax
0x180012129  test    r8d, r8d
0x18001212c  jz      loc_180012310
0x180012132  sub     r9d, 1
0x180012136  jz      loc_180012257
0x18001213c  sub     r9d, 1
0x180012140  jz      loc_1800121DE
0x180012146  sub     r9d, 1
0x18001214a  jz      loc_1800121DE
0x180012150  sub     r9d, 1
0x180012154  jz      loc_180012310
0x18001215a  sub     r9d, 1
0x18001215e  jz      loc_180012257
0x180012164  sub     r9d, 1
0x180012168  jz      short loc_1800121DE
0x18001216a  cmp     r9d, 1
0x18001216e  jz      short loc_1800121DE
0x180012170  add     r8d, 0FFFFFEC0h
0x180012177  lea     ebx, [rax+1]
0x18001217a  cmp     r8d, 40h ; '@'
0x18001217e  jge     short loc_1800121C9
0x180012180  mov     eax, [rdx+4]
0x180012183  lea     ecx, [rbx+0Fh]
0x180012186  mov     r9d, r8d
0x180012189  shl     r9d, 5
0x18001218d  test    cl, al
0x18001218f  jz      short loc_1800121A2
0x180012191  mov     edx, eax
0x180012193  shr     edx, 5
0x180012196  and     edx, 3Fh
0x180012199  cmp     edx, r8d
0x18001219c  jnz     short loc_1800121A2
0x18001219e  mov     edx, ebx
0x1800121a0  jmp     short loc_1800121A4
0x1800121a2  xor     edx, edx
0x1800121a4  mov     [r10+10h], edx
0x1800121a8  mov     edx, r9d
0x1800121ab  xor     edx, eax
0x1800121ad  and     edx, 7E0h
0x1800121b3  xor     edx, eax
0x1800121b5  or      edx, ecx
0x1800121b7  lock cmpxchg [rsi+4], edx
0x1800121bc  jnz     short loc_18001218D
0x1800121be  cmp     dword ptr [r10+10h], 0
0x1800121c3  jnz     loc_1800123DE
0x1800121c9  mov     [r10+8], r11d
0x1800121cd  mov     [r10+4], ebx
0x1800121d1  mov     dword ptr [r10+0Ch], 0
0x1800121d9  jmp     loc_1800123DE
0x1800121de  xor     ecx, ecx
0x1800121e0  sub     r11d, 2
0x1800121e4  jz      short loc_18001220C
0x1800121e6  sub     r11d, 1
0x1800121ea  jz      short loc_180012205
0x1800121ec  sub     r11d, 3
0x1800121f0  jz      short loc_1800121FE
0x1800121f2  cmp     r11d, 1
0x1800121f6  jnz     short loc_180012211
0x1800121f8  lea     ecx, [r11+0Fh]
0x1800121fc  jmp     short loc_180012211
0x1800121fe  mov     ecx, 4
0x180012203  jmp     short loc_180012211
0x180012205  mov     ecx, 8
0x18001220a  jmp     short loc_180012211
0x18001220c  mov     ecx, 2
0x180012211  mov     edx, [rdx]
0x180012213  mov     ebx, 1
0x180012218  xor     eax, eax
0x18001221a  mov     r8d, ecx
0x18001221d  or      r8d, edx
0x180012220  cmp     r8d, edx
0x180012223  mov     r9d, r8d
0x180012226  setz    al
0x180012229  or      r9d, ebx
0x18001222c  cmp     r8d, edx
0x18001222f  mov     [r10+10h], eax
0x180012233  mov     eax, edx
0x180012235  cmovz   r9d, r8d
0x180012239  lock cmpxchg [rsi], r9d
0x18001223e  jz      short loc_180012244
0x180012240  mov     edx, eax
0x180012242  jmp     short loc_180012218
0x180012244  test    bl, r9b
0x180012247  jz      short loc_18001224D
0x180012249  test    bl, dl
0x18001224b  jz      short loc_18001224F
0x18001224d  xor     ebx, ebx
0x18001224f  mov     [r10], ebx
0x180012252  jmp     loc_1800123DE
0x180012257  mov     ecx, [rdx]
0x180012259  xor     r9d, r9d
0x18001225c  cmp     r11d, 5
0x180012260  mov     ebx, 1
0x180012265  setz    r9b
0x180012269  mov     eax, ecx
0x18001226b  mov     dword ptr [r10+4], 0
0x180012273  or      eax, ebx
0x180012275  mov     edx, eax
0x180012277  shr     edx, 16h
0x18001227a  and     edx, ebx
0x18001227c  cmp     edx, r9d
0x18001227f  jz      short loc_1800122C1
0x180012281  mov     r8d, eax
0x180012284  shr     r8d, 0Fh
0x180012288  and     r8d, 7Fh
0x18001228c  jbe     short loc_1800122A6
0x18001228e  cmp     r11d, ebx
0x180012291  mov     [r10+4], r8d
0x180012295  mov     edx, 5
0x18001229a  cmovnz  edx, ebx
0x18001229d  and     eax, 0FFC07FFFh
0x1800122a2  mov     [r10+8], edx
0x1800122a6  xor     r8d, r8d
0x1800122a9  mov     edx, 400000h
0x1800122ae  cmp     r11d, 5
0x1800122b2  cmovz   r8d, edx
0x1800122b6  mov     edx, eax
0x1800122b8  btr     edx, 16h
0x1800122bc  mov     eax, r8d
0x1800122bf  or      eax, edx
0x1800122c1  mov     edx, eax
0x1800122c3  shr     edx, 0Fh
0x1800122c6  and     edx, 7Fh
0x1800122c9  lea     r8d, [rdx+1]
0x1800122cd  cmp     r8d, 7Fh
0x1800122d1  ja      short loc_1800122D8
0x1800122d3  cmp     r8d, edx
0x1800122d6  jnb     short loc_1800122E3
0x1800122d8  mov     r8d, ebx
0x1800122db  mov     [r10+8], r11d
0x1800122df  mov     [r10+4], edx
0x1800122e3  shl     r8d, 0Fh
0x1800122e7  xor     r8d, eax
0x1800122ea  and     r8d, 3F8000h
0x1800122f1  xor     r8d, eax
0x1800122f4  mov     eax, ecx
0x1800122f6  lock cmpxchg [rsi], r8d
0x1800122fb  jz      short loc_180012304
0x1800122fd  mov     ecx, eax
0x1800122ff  jmp     loc_180012269
0x180012304  not     ecx
0x180012306  and     ecx, ebx
0x180012308  mov     [r10], ecx
0x18001230b  jmp     loc_1800123D6
0x180012310  mov     edx, [rdx]
0x180012312  xor     ebp, ebp
0x180012314  lea     ecx, [rbp+4]
0x180012317  cmp     r11d, ecx
0x18001231a  lea     ebx, [rcx-3]
0x18001231d  setz    bpl
0x180012321  mov     eax, edx
0x180012323  mov     dword ptr [r10+4], 0
0x18001232b  or      eax, ebx
0x18001232d  mov     r8d, eax
0x180012330  shr     r8d, 0Eh
0x180012334  and     r8d, ebx
0x180012337  cmp     r8d, ebp
0x18001233a  jz      short loc_180012383
0x18001233c  mov     edi, eax
0x18001233e  shr     edi, 5
0x180012341  and     edi, 1FFh
0x180012347  jbe     short loc_180012365
0x180012349  mov     r8d, r11d
0x18001234c  mov     [r10+4], edi
0x180012350  neg     r8d
0x180012353  sbb     r9d, r9d
0x180012356  not     r9d
0x180012359  and     r9d, ecx
0x18001235c  mov     [r10+8], r9d
0x180012360  and     eax, 0FFFFC01Fh
0x180012365  xor     r9d, r9d
0x180012368  mov     r8d, 4000h
0x18001236e  cmp     r11d, ecx
0x180012371  cmovz   r9d, r8d
0x180012375  mov     r8d, eax
0x180012378  btr     r8d, 0Eh
0x18001237d  mov     eax, r9d
0x180012380  or      eax, r8d
0x180012383  mov     r8d, eax
0x180012386  shr     r8d, 5
0x18001238a  and     r8d, 1FFh
0x180012391  lea     r9d, [r8+1]
0x180012395  cmp     r9d, 1FFh
0x18001239c  ja      short loc_1800123A3
0x18001239e  cmp     r9d, r8d
0x1800123a1  jnb     short loc_1800123AE
0x1800123a3  mov     r9d, ebx
0x1800123a6  mov     [r10+8], r11d
0x1800123aa  mov     [r10+4], r8d
0x1800123ae  shl     r9d, 5
0x1800123b2  xor     r9d, eax
0x1800123b5  and     r9d, 3FE0h
0x1800123bc  xor     r9d, eax
0x1800123bf  mov     eax, edx
0x1800123c1  lock cmpxchg [rsi], r9d
0x1800123c6  jz      short loc_1800123CF
0x1800123c8  mov     edx, eax
0x1800123ca  jmp     loc_180012321
0x1800123cf  not     edx
0x1800123d1  and     edx, ebx
0x1800123d3  mov     [r10], edx
0x1800123d6  mov     dword ptr [r10+10h], 0
0x1800123de  mov     rax, r10
0x1800123e1  pop     rdi
0x1800123e2  pop     rsi
0x1800123e3  pop     rbp
0x1800123e4  pop     rbx
0x1800123e5  retn
```
