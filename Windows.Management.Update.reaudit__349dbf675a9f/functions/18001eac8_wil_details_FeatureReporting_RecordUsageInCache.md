# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001eac8`
- end: `0x18001eda8`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d7cc`

## callees

- `0x18001eac8`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // ecx
  unsigned __int32 v9; // ett
  int v10; // edx
  signed __int32 v11; // eax
  int v12; // ebx
  char v13; // r9
  signed __int32 v14; // r8d
  signed __int32 v15; // ett
  signed __int32 v16; // eax
  BOOL v17; // edi
  unsigned int v18; // ecx
  char v19; // r9
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // edx
  signed __int32 v24; // ett
  signed __int32 v25; // eax
  BOOL v26; // r14d
  unsigned int v27; // ecx
  char v28; // di
  int v29; // r9d
  unsigned int v30; // r9d
  unsigned int v31; // r8d
  signed __int32 v32; // ett

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_47;
    case 1:
      goto LABEL_33;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_47:
      v25 = *a2;
      v26 = a3 == 4;
      do
      {
        *(_DWORD *)(a1 + 4) = 0;
        v27 = v25 | 1;
        v28 = v25;
        if ( (((v25 | 1u) >> 14) & 1) != v26 )
        {
          if ( ((v27 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v27 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v27 = v25 & 0xFFFFC01E | 1;
          }
          v29 = 0;
          if ( a3 == 4 )
            v29 = 0x4000;
          v27 = v27 & 0xFFFFBFFF | v29;
        }
        v30 = (v27 >> 5) & 0x1FF;
        v31 = v30 + 1;
        if ( v30 + 1 > 0x1FF || v31 < v30 )
        {
          LOWORD(v31) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v30;
        }
        v32 = v25;
        v25 = _InterlockedCompareExchange(
                a2,
                ((unsigned __int16)v27 ^ (unsigned __int16)(32 * v31)) & 0x3FE0 ^ v27,
                v25);
      }
      while ( v32 != v25 );
      *(_DWORD *)a1 = (v28 & 1) == 0;
      goto LABEL_59;
    case 5:
LABEL_33:
      v16 = *a2;
      v17 = a3 == 5;
      do
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        v19 = v16;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v20 = 5;
            if ( a3 != 1 )
              v20 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v20;
          }
          v21 = 0;
          if ( a3 == 5 )
            v21 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v21;
        }
        v22 = (v18 >> 15) & 0x7F;
        v23 = v22 + 1;
        if ( v22 + 1 > 0x7F || v23 < v22 )
        {
          v23 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v22;
        }
        v24 = v16;
        v16 = _InterlockedCompareExchange(a2, (v18 ^ (v23 << 15)) & 0x3F8000 ^ v18, v16);
      }
      while ( v24 != v16 );
      *(_DWORD *)a1 = (v19 & 1) == 0;
LABEL_59:
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
      *(_DWORD *)(a1 + 12) = 0;
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
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
  do
  {
    v13 = v11;
    *(_DWORD *)(a1 + 16) = (v11 | v10) == v11;
    v14 = v11 | v10 | 1;
    if ( (v11 | v10) == v11 )
      v14 = v11 | v10;
    v15 = v11;
    v11 = _InterlockedCompareExchange(a2, v14, v11);
  }
  while ( v15 != v11 );
  if ( (v14 & 1) == 0 || (v13 & 1) != 0 )
    v12 = 0;
  *(_DWORD *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x18001eac8  mov     rax, rsp
0x18001eacb  mov     [rax+8], rbx
0x18001eacf  mov     [rax+10h], rbp
0x18001ead3  mov     [rax+18h], rsi
0x18001ead7  mov     [rax+20h], rdi
0x18001eadb  push    r14
0x18001eadd  xor     eax, eax
0x18001eadf  xorps   xmm0, xmm0
0x18001eae2  mov     r10, rcx
0x18001eae5  mov     r11d, r8d
0x18001eae8  mov     rsi, rdx
0x18001eaeb  movups  xmmword ptr [rcx], xmm0
0x18001eaee  mov     [rcx+10h], rax
0x18001eaf2  mov     ecx, r8d
0x18001eaf5  test    r8d, r8d
0x18001eaf8  jz      loc_18001ECC6
0x18001eafe  sub     ecx, 1
0x18001eb01  jz      loc_18001EC15
0x18001eb07  sub     ecx, 1
0x18001eb0a  jz      loc_18001EBA0
0x18001eb10  sub     ecx, 1
0x18001eb13  jz      loc_18001EBA0
0x18001eb19  sub     ecx, 1
0x18001eb1c  jz      loc_18001ECC6
0x18001eb22  sub     ecx, 1
0x18001eb25  jz      loc_18001EC15
0x18001eb2b  sub     ecx, 1
0x18001eb2e  jz      short loc_18001EBA0
0x18001eb30  cmp     ecx, 1
0x18001eb33  jz      short loc_18001EBA0
0x18001eb35  add     r8d, 0FFFFFEC0h
0x18001eb3c  lea     ebx, [rax+1]
0x18001eb3f  cmp     r8d, 40h ; '@'
0x18001eb43  jge     short loc_18001EB8E
0x18001eb45  mov     eax, [rdx+4]
0x18001eb48  mov     r9d, r8d
0x18001eb4b  shl     r9d, 5
0x18001eb4f  lea     edx, [rbx+0Fh]
0x18001eb52  test    dl, al
0x18001eb54  jz      short loc_18001EB67
0x18001eb56  mov     ecx, eax
0x18001eb58  shr     ecx, 5
0x18001eb5b  and     ecx, 3Fh
0x18001eb5e  cmp     ecx, r8d
0x18001eb61  jnz     short loc_18001EB67
0x18001eb63  mov     ecx, ebx
0x18001eb65  jmp     short loc_18001EB69
0x18001eb67  xor     ecx, ecx
0x18001eb69  mov     [r10+10h], ecx
0x18001eb6d  mov     ecx, r9d
0x18001eb70  xor     ecx, eax
0x18001eb72  and     ecx, 7E0h
0x18001eb78  xor     ecx, eax
0x18001eb7a  or      ecx, edx
0x18001eb7c  lock cmpxchg [rsi+4], ecx
0x18001eb81  jnz     short loc_18001EB52
0x18001eb83  cmp     dword ptr [r10+10h], 0
0x18001eb88  jnz     loc_18001ED8D
0x18001eb8e  and     dword ptr [r10+0Ch], 0
0x18001eb93  mov     [r10+8], r11d
0x18001eb97  mov     [r10+4], ebx
0x18001eb9b  jmp     loc_18001ED8D
0x18001eba0  xor     edx, edx
0x18001eba2  sub     r11d, 2
0x18001eba6  jz      short loc_18001EBCE
0x18001eba8  sub     r11d, 1
0x18001ebac  jz      short loc_18001EBC7
0x18001ebae  sub     r11d, 3
0x18001ebb2  jz      short loc_18001EBC0
0x18001ebb4  cmp     r11d, 1
0x18001ebb8  jnz     short loc_18001EBD3
0x18001ebba  lea     edx, [r11+0Fh]
0x18001ebbe  jmp     short loc_18001EBD3
0x18001ebc0  mov     edx, 4
0x18001ebc5  jmp     short loc_18001EBD3
0x18001ebc7  mov     edx, 8
0x18001ebcc  jmp     short loc_18001EBD3
0x18001ebce  mov     edx, 2
0x18001ebd3  mov     eax, [rsi]
0x18001ebd5  mov     ebx, 1
0x18001ebda  xor     r8d, r8d
0x18001ebdd  mov     ecx, edx
0x18001ebdf  or      ecx, eax
0x18001ebe1  mov     r9d, eax
0x18001ebe4  cmp     ecx, eax
0x18001ebe6  setz    r8b
0x18001ebea  mov     [r10+10h], r8d
0x18001ebee  mov     r8d, ecx
0x18001ebf1  or      r8d, ebx
0x18001ebf4  cmp     ecx, eax
0x18001ebf6  cmovz   r8d, ecx
0x18001ebfa  lock cmpxchg [rsi], r8d
0x18001ebff  jnz     short loc_18001EBDA
0x18001ec01  test    bl, r8b
0x18001ec04  jz      short loc_18001EC0B
0x18001ec06  test    bl, r9b
0x18001ec09  jz      short loc_18001EC0D
0x18001ec0b  xor     ebx, ebx
0x18001ec0d  mov     [r10], ebx
0x18001ec10  jmp     loc_18001ED8D
0x18001ec15  mov     eax, [rdx]
0x18001ec17  xor     edi, edi
0x18001ec19  cmp     r11d, 5
0x18001ec1d  mov     ebx, 1
0x18001ec22  setz    dil
0x18001ec26  and     dword ptr [r10+4], 0
0x18001ec2b  mov     ecx, eax
0x18001ec2d  or      ecx, ebx
0x18001ec2f  mov     r9d, eax
0x18001ec32  mov     edx, ecx
0x18001ec34  shr     edx, 16h
0x18001ec37  and     edx, ebx
0x18001ec39  cmp     edx, edi
0x18001ec3b  jz      short loc_18001EC7E
0x18001ec3d  mov     r8d, ecx
0x18001ec40  shr     r8d, 0Fh
0x18001ec44  and     r8d, 7Fh
0x18001ec48  jbe     short loc_18001EC63
0x18001ec4a  cmp     r11d, ebx
0x18001ec4d  mov     [r10+4], r8d
0x18001ec51  mov     edx, 5
0x18001ec56  cmovnz  edx, ebx
0x18001ec59  and     ecx, 0FFC07FFFh
0x18001ec5f  mov     [r10+8], edx
0x18001ec63  xor     r8d, r8d
0x18001ec66  mov     edx, 400000h
0x18001ec6b  cmp     r11d, 5
0x18001ec6f  cmovz   r8d, edx
0x18001ec73  mov     edx, ecx
0x18001ec75  btr     edx, 16h
0x18001ec79  mov     ecx, r8d
0x18001ec7c  or      ecx, edx
0x18001ec7e  mov     r8d, ecx
0x18001ec81  shr     r8d, 0Fh
0x18001ec85  and     r8d, 7Fh
0x18001ec89  lea     edx, [r8+1]
0x18001ec8d  cmp     edx, 7Fh
0x18001ec90  ja      short loc_18001EC97
0x18001ec92  cmp     edx, r8d
0x18001ec95  jnb     short loc_18001ECA1
0x18001ec97  mov     edx, ebx
0x18001ec99  mov     [r10+8], r11d
0x18001ec9d  mov     [r10+4], r8d
0x18001eca1  shl     edx, 0Fh
0x18001eca4  xor     edx, ecx
0x18001eca6  and     edx, 3F8000h
0x18001ecac  xor     ecx, edx
0x18001ecae  lock cmpxchg [rsi], ecx
0x18001ecb2  jnz     loc_18001EC26
0x18001ecb8  not     r9d
0x18001ecbb  and     r9d, ebx
0x18001ecbe  mov     [r10], r9d
0x18001ecc1  jmp     loc_18001ED88
0x18001ecc6  mov     eax, [rdx]
0x18001ecc8  xor     r14d, r14d
0x18001eccb  lea     edx, [r14+4]
0x18001eccf  cmp     r11d, edx
0x18001ecd2  lea     ebx, [rdx-3]
0x18001ecd5  setz    r14b
0x18001ecd9  and     dword ptr [r10+4], 0
0x18001ecde  mov     ecx, eax
0x18001ece0  or      ecx, ebx
0x18001ece2  mov     edi, eax
0x18001ece4  mov     r8d, ecx
0x18001ece7  shr     r8d, 0Eh
0x18001eceb  and     r8d, ebx
0x18001ecee  cmp     r8d, r14d
0x18001ecf1  jz      short loc_18001ED3B
0x18001ecf3  mov     ebp, ecx
0x18001ecf5  shr     ebp, 5
0x18001ecf8  and     ebp, 1FFh
0x18001ecfe  jbe     short loc_18001ED1D
0x18001ed00  mov     r8d, r11d
0x18001ed03  mov     [r10+4], ebp
0x18001ed07  neg     r8d
0x18001ed0a  sbb     r9d, r9d
0x18001ed0d  not     r9d
0x18001ed10  and     r9d, edx
0x18001ed13  mov     [r10+8], r9d
0x18001ed17  and     ecx, 0FFFFC01Fh
0x18001ed1d  xor     r9d, r9d
0x18001ed20  mov     r8d, 4000h
0x18001ed26  cmp     r11d, edx
0x18001ed29  cmovz   r9d, r8d
0x18001ed2d  mov     r8d, ecx
0x18001ed30  btr     r8d, 0Eh
0x18001ed35  mov     ecx, r9d
0x18001ed38  or      ecx, r8d
0x18001ed3b  mov     r9d, ecx
0x18001ed3e  shr     r9d, 5
0x18001ed42  and     r9d, 1FFh
0x18001ed49  lea     r8d, [r9+1]
0x18001ed4d  cmp     r8d, 1FFh
0x18001ed54  ja      short loc_18001ED5B
0x18001ed56  cmp     r8d, r9d
0x18001ed59  jnb     short loc_18001ED66
0x18001ed5b  mov     r8d, ebx
0x18001ed5e  mov     [r10+8], r11d
0x18001ed62  mov     [r10+4], r9d
0x18001ed66  shl     r8d, 5
0x18001ed6a  xor     r8d, ecx
0x18001ed6d  and     r8d, 3FE0h
0x18001ed74  xor     ecx, r8d
0x18001ed77  lock cmpxchg [rsi], ecx
0x18001ed7b  jnz     loc_18001ECD9
0x18001ed81  not     edi
0x18001ed83  and     edi, ebx
0x18001ed85  mov     [r10], edi
0x18001ed88  and     dword ptr [r10+10h], 0
0x18001ed8d  mov     rbx, [rsp+8+arg_0]
0x18001ed92  mov     rax, r10
0x18001ed95  mov     rbp, [rsp+8+arg_8]
0x18001ed9a  mov     rsi, [rsp+8+arg_10]
0x18001ed9f  mov     rdi, [rsp+8+arg_18]
0x18001eda4  pop     r14
0x18001eda6  retn
```
