# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000a3a4`
- end: `0x18000a67e`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009d60`

## callees

- `0x18000a3a4`

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
0x18000a3a4  push    rbx
0x18000a3a6  push    rbp
0x18000a3a7  push    rsi
0x18000a3a8  push    rdi
0x18000a3a9  xor     eax, eax
0x18000a3ab  xorps   xmm0, xmm0
0x18000a3ae  mov     r11d, r8d
0x18000a3b1  mov     rsi, rdx
0x18000a3b4  mov     r10, rcx
0x18000a3b7  mov     r9d, r8d
0x18000a3ba  movups  xmmword ptr [rcx], xmm0
0x18000a3bd  mov     [rcx+10h], rax
0x18000a3c1  test    r8d, r8d
0x18000a3c4  jz      loc_18000A5A8
0x18000a3ca  sub     r9d, 1
0x18000a3ce  jz      loc_18000A4EF
0x18000a3d4  sub     r9d, 1
0x18000a3d8  jz      loc_18000A476
0x18000a3de  sub     r9d, 1
0x18000a3e2  jz      loc_18000A476
0x18000a3e8  sub     r9d, 1
0x18000a3ec  jz      loc_18000A5A8
0x18000a3f2  sub     r9d, 1
0x18000a3f6  jz      loc_18000A4EF
0x18000a3fc  sub     r9d, 1
0x18000a400  jz      short loc_18000A476
0x18000a402  cmp     r9d, 1
0x18000a406  jz      short loc_18000A476
0x18000a408  add     r8d, 0FFFFFEC0h
0x18000a40f  lea     ebx, [rax+1]
0x18000a412  cmp     r8d, 40h ; '@'
0x18000a416  jge     short loc_18000A461
0x18000a418  mov     eax, [rdx+4]
0x18000a41b  lea     ecx, [rbx+0Fh]
0x18000a41e  mov     r9d, r8d
0x18000a421  shl     r9d, 5
0x18000a425  test    cl, al
0x18000a427  jz      short loc_18000A43A
0x18000a429  mov     edx, eax
0x18000a42b  shr     edx, 5
0x18000a42e  and     edx, 3Fh
0x18000a431  cmp     edx, r8d
0x18000a434  jnz     short loc_18000A43A
0x18000a436  mov     edx, ebx
0x18000a438  jmp     short loc_18000A43C
0x18000a43a  xor     edx, edx
0x18000a43c  mov     [r10+10h], edx
0x18000a440  mov     edx, r9d
0x18000a443  xor     edx, eax
0x18000a445  and     edx, 7E0h
0x18000a44b  xor     edx, eax
0x18000a44d  or      edx, ecx
0x18000a44f  lock cmpxchg [rsi+4], edx
0x18000a454  jnz     short loc_18000A425
0x18000a456  cmp     dword ptr [r10+10h], 0
0x18000a45b  jnz     loc_18000A676
0x18000a461  mov     [r10+8], r11d
0x18000a465  mov     [r10+4], ebx
0x18000a469  mov     dword ptr [r10+0Ch], 0
0x18000a471  jmp     loc_18000A676
0x18000a476  xor     ecx, ecx
0x18000a478  sub     r11d, 2
0x18000a47c  jz      short loc_18000A4A4
0x18000a47e  sub     r11d, 1
0x18000a482  jz      short loc_18000A49D
0x18000a484  sub     r11d, 3
0x18000a488  jz      short loc_18000A496
0x18000a48a  cmp     r11d, 1
0x18000a48e  jnz     short loc_18000A4A9
0x18000a490  lea     ecx, [r11+0Fh]
0x18000a494  jmp     short loc_18000A4A9
0x18000a496  mov     ecx, 4
0x18000a49b  jmp     short loc_18000A4A9
0x18000a49d  mov     ecx, 8
0x18000a4a2  jmp     short loc_18000A4A9
0x18000a4a4  mov     ecx, 2
0x18000a4a9  mov     edx, [rdx]
0x18000a4ab  mov     ebx, 1
0x18000a4b0  xor     eax, eax
0x18000a4b2  mov     r8d, ecx
0x18000a4b5  or      r8d, edx
0x18000a4b8  cmp     r8d, edx
0x18000a4bb  mov     r9d, r8d
0x18000a4be  setz    al
0x18000a4c1  or      r9d, ebx
0x18000a4c4  cmp     r8d, edx
0x18000a4c7  mov     [r10+10h], eax
0x18000a4cb  mov     eax, edx
0x18000a4cd  cmovz   r9d, r8d
0x18000a4d1  lock cmpxchg [rsi], r9d
0x18000a4d6  jz      short loc_18000A4DC
0x18000a4d8  mov     edx, eax
0x18000a4da  jmp     short loc_18000A4B0
0x18000a4dc  test    bl, r9b
0x18000a4df  jz      short loc_18000A4E5
0x18000a4e1  test    bl, dl
0x18000a4e3  jz      short loc_18000A4E7
0x18000a4e5  xor     ebx, ebx
0x18000a4e7  mov     [r10], ebx
0x18000a4ea  jmp     loc_18000A676
0x18000a4ef  mov     ecx, [rdx]
0x18000a4f1  xor     r9d, r9d
0x18000a4f4  cmp     r11d, 5
0x18000a4f8  mov     ebx, 1
0x18000a4fd  setz    r9b
0x18000a501  mov     eax, ecx
0x18000a503  mov     dword ptr [r10+4], 0
0x18000a50b  or      eax, ebx
0x18000a50d  mov     edx, eax
0x18000a50f  shr     edx, 16h
0x18000a512  and     edx, ebx
0x18000a514  cmp     edx, r9d
0x18000a517  jz      short loc_18000A559
0x18000a519  mov     r8d, eax
0x18000a51c  shr     r8d, 0Fh
0x18000a520  and     r8d, 7Fh
0x18000a524  jbe     short loc_18000A53E
0x18000a526  cmp     r11d, ebx
0x18000a529  mov     [r10+4], r8d
0x18000a52d  mov     edx, 5
0x18000a532  cmovnz  edx, ebx
0x18000a535  and     eax, 0FFC07FFFh
0x18000a53a  mov     [r10+8], edx
0x18000a53e  xor     r8d, r8d
0x18000a541  mov     edx, 400000h
0x18000a546  cmp     r11d, 5
0x18000a54a  cmovz   r8d, edx
0x18000a54e  mov     edx, eax
0x18000a550  btr     edx, 16h
0x18000a554  mov     eax, r8d
0x18000a557  or      eax, edx
0x18000a559  mov     edx, eax
0x18000a55b  shr     edx, 0Fh
0x18000a55e  and     edx, 7Fh
0x18000a561  lea     r8d, [rdx+1]
0x18000a565  cmp     r8d, 7Fh
0x18000a569  ja      short loc_18000A570
0x18000a56b  cmp     r8d, edx
0x18000a56e  jnb     short loc_18000A57B
0x18000a570  mov     r8d, ebx
0x18000a573  mov     [r10+8], r11d
0x18000a577  mov     [r10+4], edx
0x18000a57b  shl     r8d, 0Fh
0x18000a57f  xor     r8d, eax
0x18000a582  and     r8d, 3F8000h
0x18000a589  xor     r8d, eax
0x18000a58c  mov     eax, ecx
0x18000a58e  lock cmpxchg [rsi], r8d
0x18000a593  jz      short loc_18000A59C
0x18000a595  mov     ecx, eax
0x18000a597  jmp     loc_18000A501
0x18000a59c  not     ecx
0x18000a59e  and     ecx, ebx
0x18000a5a0  mov     [r10], ecx
0x18000a5a3  jmp     loc_18000A66E
0x18000a5a8  mov     edx, [rdx]
0x18000a5aa  xor     ebp, ebp
0x18000a5ac  lea     ecx, [rbp+4]
0x18000a5af  cmp     r11d, ecx
0x18000a5b2  lea     ebx, [rcx-3]
0x18000a5b5  setz    bpl
0x18000a5b9  mov     eax, edx
0x18000a5bb  mov     dword ptr [r10+4], 0
0x18000a5c3  or      eax, ebx
0x18000a5c5  mov     r8d, eax
0x18000a5c8  shr     r8d, 0Eh
0x18000a5cc  and     r8d, ebx
0x18000a5cf  cmp     r8d, ebp
0x18000a5d2  jz      short loc_18000A61B
0x18000a5d4  mov     edi, eax
0x18000a5d6  shr     edi, 5
0x18000a5d9  and     edi, 1FFh
0x18000a5df  jbe     short loc_18000A5FD
0x18000a5e1  mov     r8d, r11d
0x18000a5e4  mov     [r10+4], edi
0x18000a5e8  neg     r8d
0x18000a5eb  sbb     r9d, r9d
0x18000a5ee  not     r9d
0x18000a5f1  and     r9d, ecx
0x18000a5f4  mov     [r10+8], r9d
0x18000a5f8  and     eax, 0FFFFC01Fh
0x18000a5fd  xor     r9d, r9d
0x18000a600  mov     r8d, 4000h
0x18000a606  cmp     r11d, ecx
0x18000a609  cmovz   r9d, r8d
0x18000a60d  mov     r8d, eax
0x18000a610  btr     r8d, 0Eh
0x18000a615  mov     eax, r9d
0x18000a618  or      eax, r8d
0x18000a61b  mov     r8d, eax
0x18000a61e  shr     r8d, 5
0x18000a622  and     r8d, 1FFh
0x18000a629  lea     r9d, [r8+1]
0x18000a62d  cmp     r9d, 1FFh
0x18000a634  ja      short loc_18000A63B
0x18000a636  cmp     r9d, r8d
0x18000a639  jnb     short loc_18000A646
0x18000a63b  mov     r9d, ebx
0x18000a63e  mov     [r10+8], r11d
0x18000a642  mov     [r10+4], r8d
0x18000a646  shl     r9d, 5
0x18000a64a  xor     r9d, eax
0x18000a64d  and     r9d, 3FE0h
0x18000a654  xor     r9d, eax
0x18000a657  mov     eax, edx
0x18000a659  lock cmpxchg [rsi], r9d
0x18000a65e  jz      short loc_18000A667
0x18000a660  mov     edx, eax
0x18000a662  jmp     loc_18000A5B9
0x18000a667  not     edx
0x18000a669  and     edx, ebx
0x18000a66b  mov     [r10], edx
0x18000a66e  mov     dword ptr [r10+10h], 0
0x18000a676  mov     rax, r10
0x18000a679  pop     rdi
0x18000a67a  pop     rsi
0x18000a67b  pop     rbp
0x18000a67c  pop     rbx
0x18000a67d  retn
```
