# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000c420`
- end: `0x14000c6fa`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400096c8`

## callees

- `0x14000c420`

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
0x14000c420  push    rbx
0x14000c422  push    rbp
0x14000c423  push    rsi
0x14000c424  push    rdi
0x14000c425  xor     eax, eax
0x14000c427  xorps   xmm0, xmm0
0x14000c42a  mov     r11d, r8d
0x14000c42d  mov     rsi, rdx
0x14000c430  mov     r10, rcx
0x14000c433  mov     r9d, r8d
0x14000c436  movups  xmmword ptr [rcx], xmm0
0x14000c439  mov     [rcx+10h], rax
0x14000c43d  test    r8d, r8d
0x14000c440  jz      loc_14000C624
0x14000c446  sub     r9d, 1
0x14000c44a  jz      loc_14000C56B
0x14000c450  sub     r9d, 1
0x14000c454  jz      loc_14000C4F2
0x14000c45a  sub     r9d, 1
0x14000c45e  jz      loc_14000C4F2
0x14000c464  sub     r9d, 1
0x14000c468  jz      loc_14000C624
0x14000c46e  sub     r9d, 1
0x14000c472  jz      loc_14000C56B
0x14000c478  sub     r9d, 1
0x14000c47c  jz      short loc_14000C4F2
0x14000c47e  cmp     r9d, 1
0x14000c482  jz      short loc_14000C4F2
0x14000c484  add     r8d, 0FFFFFEC0h
0x14000c48b  lea     ebx, [rax+1]
0x14000c48e  cmp     r8d, 40h ; '@'
0x14000c492  jge     short loc_14000C4DD
0x14000c494  mov     eax, [rdx+4]
0x14000c497  lea     ecx, [rbx+0Fh]
0x14000c49a  mov     r9d, r8d
0x14000c49d  shl     r9d, 5
0x14000c4a1  test    cl, al
0x14000c4a3  jz      short loc_14000C4B6
0x14000c4a5  mov     edx, eax
0x14000c4a7  shr     edx, 5
0x14000c4aa  and     edx, 3Fh
0x14000c4ad  cmp     edx, r8d
0x14000c4b0  jnz     short loc_14000C4B6
0x14000c4b2  mov     edx, ebx
0x14000c4b4  jmp     short loc_14000C4B8
0x14000c4b6  xor     edx, edx
0x14000c4b8  mov     [r10+10h], edx
0x14000c4bc  mov     edx, r9d
0x14000c4bf  xor     edx, eax
0x14000c4c1  and     edx, 7E0h
0x14000c4c7  xor     edx, eax
0x14000c4c9  or      edx, ecx
0x14000c4cb  lock cmpxchg [rsi+4], edx
0x14000c4d0  jnz     short loc_14000C4A1
0x14000c4d2  cmp     dword ptr [r10+10h], 0
0x14000c4d7  jnz     loc_14000C6F2
0x14000c4dd  mov     [r10+8], r11d
0x14000c4e1  mov     [r10+4], ebx
0x14000c4e5  mov     dword ptr [r10+0Ch], 0
0x14000c4ed  jmp     loc_14000C6F2
0x14000c4f2  xor     ecx, ecx
0x14000c4f4  sub     r11d, 2
0x14000c4f8  jz      short loc_14000C520
0x14000c4fa  sub     r11d, 1
0x14000c4fe  jz      short loc_14000C519
0x14000c500  sub     r11d, 3
0x14000c504  jz      short loc_14000C512
0x14000c506  cmp     r11d, 1
0x14000c50a  jnz     short loc_14000C525
0x14000c50c  lea     ecx, [r11+0Fh]
0x14000c510  jmp     short loc_14000C525
0x14000c512  mov     ecx, 4
0x14000c517  jmp     short loc_14000C525
0x14000c519  mov     ecx, 8
0x14000c51e  jmp     short loc_14000C525
0x14000c520  mov     ecx, 2
0x14000c525  mov     edx, [rdx]
0x14000c527  mov     ebx, 1
0x14000c52c  xor     eax, eax
0x14000c52e  mov     r8d, ecx
0x14000c531  or      r8d, edx
0x14000c534  cmp     r8d, edx
0x14000c537  mov     r9d, r8d
0x14000c53a  setz    al
0x14000c53d  or      r9d, ebx
0x14000c540  cmp     r8d, edx
0x14000c543  mov     [r10+10h], eax
0x14000c547  mov     eax, edx
0x14000c549  cmovz   r9d, r8d
0x14000c54d  lock cmpxchg [rsi], r9d
0x14000c552  jz      short loc_14000C558
0x14000c554  mov     edx, eax
0x14000c556  jmp     short loc_14000C52C
0x14000c558  test    bl, r9b
0x14000c55b  jz      short loc_14000C561
0x14000c55d  test    bl, dl
0x14000c55f  jz      short loc_14000C563
0x14000c561  xor     ebx, ebx
0x14000c563  mov     [r10], ebx
0x14000c566  jmp     loc_14000C6F2
0x14000c56b  mov     ecx, [rdx]
0x14000c56d  xor     r9d, r9d
0x14000c570  cmp     r11d, 5
0x14000c574  mov     ebx, 1
0x14000c579  setz    r9b
0x14000c57d  mov     eax, ecx
0x14000c57f  mov     dword ptr [r10+4], 0
0x14000c587  or      eax, ebx
0x14000c589  mov     edx, eax
0x14000c58b  shr     edx, 16h
0x14000c58e  and     edx, ebx
0x14000c590  cmp     edx, r9d
0x14000c593  jz      short loc_14000C5D5
0x14000c595  mov     r8d, eax
0x14000c598  shr     r8d, 0Fh
0x14000c59c  and     r8d, 7Fh
0x14000c5a0  jbe     short loc_14000C5BA
0x14000c5a2  cmp     r11d, ebx
0x14000c5a5  mov     [r10+4], r8d
0x14000c5a9  mov     edx, 5
0x14000c5ae  cmovnz  edx, ebx
0x14000c5b1  and     eax, 0FFC07FFFh
0x14000c5b6  mov     [r10+8], edx
0x14000c5ba  xor     r8d, r8d
0x14000c5bd  mov     edx, 400000h
0x14000c5c2  cmp     r11d, 5
0x14000c5c6  cmovz   r8d, edx
0x14000c5ca  mov     edx, eax
0x14000c5cc  btr     edx, 16h
0x14000c5d0  mov     eax, r8d
0x14000c5d3  or      eax, edx
0x14000c5d5  mov     edx, eax
0x14000c5d7  shr     edx, 0Fh
0x14000c5da  and     edx, 7Fh
0x14000c5dd  lea     r8d, [rdx+1]
0x14000c5e1  cmp     r8d, 7Fh
0x14000c5e5  ja      short loc_14000C5EC
0x14000c5e7  cmp     r8d, edx
0x14000c5ea  jnb     short loc_14000C5F7
0x14000c5ec  mov     r8d, ebx
0x14000c5ef  mov     [r10+8], r11d
0x14000c5f3  mov     [r10+4], edx
0x14000c5f7  shl     r8d, 0Fh
0x14000c5fb  xor     r8d, eax
0x14000c5fe  and     r8d, 3F8000h
0x14000c605  xor     r8d, eax
0x14000c608  mov     eax, ecx
0x14000c60a  lock cmpxchg [rsi], r8d
0x14000c60f  jz      short loc_14000C618
0x14000c611  mov     ecx, eax
0x14000c613  jmp     loc_14000C57D
0x14000c618  not     ecx
0x14000c61a  and     ecx, ebx
0x14000c61c  mov     [r10], ecx
0x14000c61f  jmp     loc_14000C6EA
0x14000c624  mov     edx, [rdx]
0x14000c626  xor     ebp, ebp
0x14000c628  lea     ecx, [rbp+4]
0x14000c62b  cmp     r11d, ecx
0x14000c62e  lea     ebx, [rcx-3]
0x14000c631  setz    bpl
0x14000c635  mov     eax, edx
0x14000c637  mov     dword ptr [r10+4], 0
0x14000c63f  or      eax, ebx
0x14000c641  mov     r8d, eax
0x14000c644  shr     r8d, 0Eh
0x14000c648  and     r8d, ebx
0x14000c64b  cmp     r8d, ebp
0x14000c64e  jz      short loc_14000C697
0x14000c650  mov     edi, eax
0x14000c652  shr     edi, 5
0x14000c655  and     edi, 1FFh
0x14000c65b  jbe     short loc_14000C679
0x14000c65d  mov     r8d, r11d
0x14000c660  mov     [r10+4], edi
0x14000c664  neg     r8d
0x14000c667  sbb     r9d, r9d
0x14000c66a  not     r9d
0x14000c66d  and     r9d, ecx
0x14000c670  mov     [r10+8], r9d
0x14000c674  and     eax, 0FFFFC01Fh
0x14000c679  xor     r9d, r9d
0x14000c67c  mov     r8d, 4000h
0x14000c682  cmp     r11d, ecx
0x14000c685  cmovz   r9d, r8d
0x14000c689  mov     r8d, eax
0x14000c68c  btr     r8d, 0Eh
0x14000c691  mov     eax, r9d
0x14000c694  or      eax, r8d
0x14000c697  mov     r8d, eax
0x14000c69a  shr     r8d, 5
0x14000c69e  and     r8d, 1FFh
0x14000c6a5  lea     r9d, [r8+1]
0x14000c6a9  cmp     r9d, 1FFh
0x14000c6b0  ja      short loc_14000C6B7
0x14000c6b2  cmp     r9d, r8d
0x14000c6b5  jnb     short loc_14000C6C2
0x14000c6b7  mov     r9d, ebx
0x14000c6ba  mov     [r10+8], r11d
0x14000c6be  mov     [r10+4], r8d
0x14000c6c2  shl     r9d, 5
0x14000c6c6  xor     r9d, eax
0x14000c6c9  and     r9d, 3FE0h
0x14000c6d0  xor     r9d, eax
0x14000c6d3  mov     eax, edx
0x14000c6d5  lock cmpxchg [rsi], r9d
0x14000c6da  jz      short loc_14000C6E3
0x14000c6dc  mov     edx, eax
0x14000c6de  jmp     loc_14000C635
0x14000c6e3  not     edx
0x14000c6e5  and     edx, ebx
0x14000c6e7  mov     [r10], edx
0x14000c6ea  mov     dword ptr [r10+10h], 0
0x14000c6f2  mov     rax, r10
0x14000c6f5  pop     rdi
0x14000c6f6  pop     rsi
0x14000c6f7  pop     rbp
0x14000c6f8  pop     rbx
0x14000c6f9  retn
```
