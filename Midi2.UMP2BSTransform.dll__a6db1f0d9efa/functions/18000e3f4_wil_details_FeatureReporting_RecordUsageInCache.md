# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000e3f4`
- end: `0x18000e6ce`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c93c`

## callees

- `0x18000e3f4`

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
0x18000e3f4  push    rbx
0x18000e3f6  push    rbp
0x18000e3f7  push    rsi
0x18000e3f8  push    rdi
0x18000e3f9  xor     eax, eax
0x18000e3fb  xorps   xmm0, xmm0
0x18000e3fe  mov     r11d, r8d
0x18000e401  mov     rsi, rdx
0x18000e404  mov     r10, rcx
0x18000e407  mov     r9d, r8d
0x18000e40a  movups  xmmword ptr [rcx], xmm0
0x18000e40d  mov     [rcx+10h], rax
0x18000e411  test    r8d, r8d
0x18000e414  jz      loc_18000E5F8
0x18000e41a  sub     r9d, 1
0x18000e41e  jz      loc_18000E53F
0x18000e424  sub     r9d, 1
0x18000e428  jz      loc_18000E4C6
0x18000e42e  sub     r9d, 1
0x18000e432  jz      loc_18000E4C6
0x18000e438  sub     r9d, 1
0x18000e43c  jz      loc_18000E5F8
0x18000e442  sub     r9d, 1
0x18000e446  jz      loc_18000E53F
0x18000e44c  sub     r9d, 1
0x18000e450  jz      short loc_18000E4C6
0x18000e452  cmp     r9d, 1
0x18000e456  jz      short loc_18000E4C6
0x18000e458  add     r8d, 0FFFFFEC0h
0x18000e45f  lea     ebx, [rax+1]
0x18000e462  cmp     r8d, 40h ; '@'
0x18000e466  jge     short loc_18000E4B1
0x18000e468  mov     eax, [rdx+4]
0x18000e46b  lea     ecx, [rbx+0Fh]
0x18000e46e  mov     r9d, r8d
0x18000e471  shl     r9d, 5
0x18000e475  test    cl, al
0x18000e477  jz      short loc_18000E48A
0x18000e479  mov     edx, eax
0x18000e47b  shr     edx, 5
0x18000e47e  and     edx, 3Fh
0x18000e481  cmp     edx, r8d
0x18000e484  jnz     short loc_18000E48A
0x18000e486  mov     edx, ebx
0x18000e488  jmp     short loc_18000E48C
0x18000e48a  xor     edx, edx
0x18000e48c  mov     [r10+10h], edx
0x18000e490  mov     edx, r9d
0x18000e493  xor     edx, eax
0x18000e495  and     edx, 7E0h
0x18000e49b  xor     edx, eax
0x18000e49d  or      edx, ecx
0x18000e49f  lock cmpxchg [rsi+4], edx
0x18000e4a4  jnz     short loc_18000E475
0x18000e4a6  cmp     dword ptr [r10+10h], 0
0x18000e4ab  jnz     loc_18000E6C6
0x18000e4b1  mov     [r10+8], r11d
0x18000e4b5  mov     [r10+4], ebx
0x18000e4b9  mov     dword ptr [r10+0Ch], 0
0x18000e4c1  jmp     loc_18000E6C6
0x18000e4c6  xor     ecx, ecx
0x18000e4c8  sub     r11d, 2
0x18000e4cc  jz      short loc_18000E4F4
0x18000e4ce  sub     r11d, 1
0x18000e4d2  jz      short loc_18000E4ED
0x18000e4d4  sub     r11d, 3
0x18000e4d8  jz      short loc_18000E4E6
0x18000e4da  cmp     r11d, 1
0x18000e4de  jnz     short loc_18000E4F9
0x18000e4e0  lea     ecx, [r11+0Fh]
0x18000e4e4  jmp     short loc_18000E4F9
0x18000e4e6  mov     ecx, 4
0x18000e4eb  jmp     short loc_18000E4F9
0x18000e4ed  mov     ecx, 8
0x18000e4f2  jmp     short loc_18000E4F9
0x18000e4f4  mov     ecx, 2
0x18000e4f9  mov     edx, [rdx]
0x18000e4fb  mov     ebx, 1
0x18000e500  xor     eax, eax
0x18000e502  mov     r8d, ecx
0x18000e505  or      r8d, edx
0x18000e508  cmp     r8d, edx
0x18000e50b  mov     r9d, r8d
0x18000e50e  setz    al
0x18000e511  or      r9d, ebx
0x18000e514  cmp     r8d, edx
0x18000e517  mov     [r10+10h], eax
0x18000e51b  mov     eax, edx
0x18000e51d  cmovz   r9d, r8d
0x18000e521  lock cmpxchg [rsi], r9d
0x18000e526  jz      short loc_18000E52C
0x18000e528  mov     edx, eax
0x18000e52a  jmp     short loc_18000E500
0x18000e52c  test    bl, r9b
0x18000e52f  jz      short loc_18000E535
0x18000e531  test    bl, dl
0x18000e533  jz      short loc_18000E537
0x18000e535  xor     ebx, ebx
0x18000e537  mov     [r10], ebx
0x18000e53a  jmp     loc_18000E6C6
0x18000e53f  mov     ecx, [rdx]
0x18000e541  xor     r9d, r9d
0x18000e544  cmp     r11d, 5
0x18000e548  mov     ebx, 1
0x18000e54d  setz    r9b
0x18000e551  mov     eax, ecx
0x18000e553  mov     dword ptr [r10+4], 0
0x18000e55b  or      eax, ebx
0x18000e55d  mov     edx, eax
0x18000e55f  shr     edx, 16h
0x18000e562  and     edx, ebx
0x18000e564  cmp     edx, r9d
0x18000e567  jz      short loc_18000E5A9
0x18000e569  mov     r8d, eax
0x18000e56c  shr     r8d, 0Fh
0x18000e570  and     r8d, 7Fh
0x18000e574  jbe     short loc_18000E58E
0x18000e576  cmp     r11d, ebx
0x18000e579  mov     [r10+4], r8d
0x18000e57d  mov     edx, 5
0x18000e582  cmovnz  edx, ebx
0x18000e585  and     eax, 0FFC07FFFh
0x18000e58a  mov     [r10+8], edx
0x18000e58e  xor     r8d, r8d
0x18000e591  mov     edx, 400000h
0x18000e596  cmp     r11d, 5
0x18000e59a  cmovz   r8d, edx
0x18000e59e  mov     edx, eax
0x18000e5a0  btr     edx, 16h
0x18000e5a4  mov     eax, r8d
0x18000e5a7  or      eax, edx
0x18000e5a9  mov     edx, eax
0x18000e5ab  shr     edx, 0Fh
0x18000e5ae  and     edx, 7Fh
0x18000e5b1  lea     r8d, [rdx+1]
0x18000e5b5  cmp     r8d, 7Fh
0x18000e5b9  ja      short loc_18000E5C0
0x18000e5bb  cmp     r8d, edx
0x18000e5be  jnb     short loc_18000E5CB
0x18000e5c0  mov     r8d, ebx
0x18000e5c3  mov     [r10+8], r11d
0x18000e5c7  mov     [r10+4], edx
0x18000e5cb  shl     r8d, 0Fh
0x18000e5cf  xor     r8d, eax
0x18000e5d2  and     r8d, 3F8000h
0x18000e5d9  xor     r8d, eax
0x18000e5dc  mov     eax, ecx
0x18000e5de  lock cmpxchg [rsi], r8d
0x18000e5e3  jz      short loc_18000E5EC
0x18000e5e5  mov     ecx, eax
0x18000e5e7  jmp     loc_18000E551
0x18000e5ec  not     ecx
0x18000e5ee  and     ecx, ebx
0x18000e5f0  mov     [r10], ecx
0x18000e5f3  jmp     loc_18000E6BE
0x18000e5f8  mov     edx, [rdx]
0x18000e5fa  xor     ebp, ebp
0x18000e5fc  lea     ecx, [rbp+4]
0x18000e5ff  cmp     r11d, ecx
0x18000e602  lea     ebx, [rcx-3]
0x18000e605  setz    bpl
0x18000e609  mov     eax, edx
0x18000e60b  mov     dword ptr [r10+4], 0
0x18000e613  or      eax, ebx
0x18000e615  mov     r8d, eax
0x18000e618  shr     r8d, 0Eh
0x18000e61c  and     r8d, ebx
0x18000e61f  cmp     r8d, ebp
0x18000e622  jz      short loc_18000E66B
0x18000e624  mov     edi, eax
0x18000e626  shr     edi, 5
0x18000e629  and     edi, 1FFh
0x18000e62f  jbe     short loc_18000E64D
0x18000e631  mov     r8d, r11d
0x18000e634  mov     [r10+4], edi
0x18000e638  neg     r8d
0x18000e63b  sbb     r9d, r9d
0x18000e63e  not     r9d
0x18000e641  and     r9d, ecx
0x18000e644  mov     [r10+8], r9d
0x18000e648  and     eax, 0FFFFC01Fh
0x18000e64d  xor     r9d, r9d
0x18000e650  mov     r8d, 4000h
0x18000e656  cmp     r11d, ecx
0x18000e659  cmovz   r9d, r8d
0x18000e65d  mov     r8d, eax
0x18000e660  btr     r8d, 0Eh
0x18000e665  mov     eax, r9d
0x18000e668  or      eax, r8d
0x18000e66b  mov     r8d, eax
0x18000e66e  shr     r8d, 5
0x18000e672  and     r8d, 1FFh
0x18000e679  lea     r9d, [r8+1]
0x18000e67d  cmp     r9d, 1FFh
0x18000e684  ja      short loc_18000E68B
0x18000e686  cmp     r9d, r8d
0x18000e689  jnb     short loc_18000E696
0x18000e68b  mov     r9d, ebx
0x18000e68e  mov     [r10+8], r11d
0x18000e692  mov     [r10+4], r8d
0x18000e696  shl     r9d, 5
0x18000e69a  xor     r9d, eax
0x18000e69d  and     r9d, 3FE0h
0x18000e6a4  xor     r9d, eax
0x18000e6a7  mov     eax, edx
0x18000e6a9  lock cmpxchg [rsi], r9d
0x18000e6ae  jz      short loc_18000E6B7
0x18000e6b0  mov     edx, eax
0x18000e6b2  jmp     loc_18000E609
0x18000e6b7  not     edx
0x18000e6b9  and     edx, ebx
0x18000e6bb  mov     [r10], edx
0x18000e6be  mov     dword ptr [r10+10h], 0
0x18000e6c6  mov     rax, r10
0x18000e6c9  pop     rdi
0x18000e6ca  pop     rsi
0x18000e6cb  pop     rbp
0x18000e6cc  pop     rbx
0x18000e6cd  retn
```
