# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000f2c0`
- end: `0x18000f584`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `708`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d9a0`
- `0x18000fb10`
- `0x180019d50`
- `0x180019f30`
- `0x18001a0e0`
- `0x180029ac0`
- `0x180029c70`

## callees

- `0x18000f2c0`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // edx
  signed __int32 i; // ecx
  signed __int32 v8; // r9d
  signed __int32 v9; // eax
  int v10; // edi
  signed __int32 v11; // ecx
  int v12; // ebp
  unsigned int v13; // eax
  int v14; // r8d
  unsigned int v15; // r9d
  unsigned int v16; // r8d
  signed __int32 v17; // eax
  int v18; // r9d
  unsigned int v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  unsigned int v22; // edx
  signed __int32 v23; // eax
  int v24; // edx
  unsigned __int32 v25; // eax
  int v26; // ecx
  unsigned __int32 v27; // ett

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
    case 4:
      v11 = *a2;
      v12 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v13 = v11 | 1;
        if ( (((v11 | 1u) >> 14) & 1) != v12 )
        {
          if ( ((v13 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v13 >> 5) & 0x1FF;
            v14 = 0;
            if ( !a3 )
              v14 = 4;
            v13 = v11 & 0xFFFFC01E | 1;
            *(_DWORD *)(a1 + 8) = v14;
          }
          v13 = (v12 << 14) | v13 & 0xFFFFBFFF;
        }
        v15 = (v13 >> 5) & 0x1FF;
        v16 = v15 + 1;
        if ( v15 + 1 > 0x1FF || v16 < v15 )
        {
          LOWORD(v16) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v15;
        }
        v17 = _InterlockedCompareExchange(
                a2,
                v13 ^ ((unsigned __int16)v13 ^ (unsigned __int16)(32 * v16)) & 0x3FE0,
                v11);
        if ( v11 == v17 )
          break;
        v11 = v17;
      }
      goto LABEL_31;
    case 1:
    case 5:
      v11 = *a2;
      v18 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v19 = v11 | 1;
        if ( (((v11 | 1u) >> 22) & 1) != v18 )
        {
          if ( ((v19 >> 15) & 0x7F) != 0 )
          {
            v20 = 1;
            *(_DWORD *)(a1 + 4) = (v19 >> 15) & 0x7F;
            if ( a3 == 1 )
              v20 = 5;
            v19 = v11 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v20;
          }
          v19 = v19 & 0xFFBFFFFF | (v18 << 22);
        }
        v21 = (v19 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v19 ^ (v19 ^ (v22 << 15)) & 0x3F8000, v11);
        if ( v11 == v23 )
          break;
        v11 = v23;
      }
LABEL_31:
      *(_DWORD *)(a1 + 16) = 0;
      *(_DWORD *)a1 = (v11 & 1) == 0;
      break;
    case 2:
    case 3:
    case 6:
    case 7:
      v6 = 0;
      switch ( a3 )
      {
        case 2:
          v6 = 2;
          break;
        case 3:
          v6 = 8;
          break;
        case 6:
          v6 = 4;
          break;
        case 7:
          v6 = 16;
          break;
      }
      for ( i = *a2; ; i = v9 )
      {
        v8 = i | v6 | 1;
        *(_DWORD *)(a1 + 16) = (i | v6) == i;
        if ( (i | v6) == i )
          v8 = i | v6;
        v9 = _InterlockedCompareExchange(a2, v8, i);
        if ( i == v9 )
          break;
      }
      if ( (v8 & 1) == 0 || (v10 = 1, (i & 1) != 0) )
        v10 = 0;
      *(_DWORD *)a1 = v10;
      break;
    default:
      v24 = a3 - 320;
      if ( a3 - 320 < 64 )
      {
        v25 = *((_DWORD *)a2 + 1);
        do
        {
          if ( (v25 & 0x10) == 0 || (v26 = 1, ((v25 >> 5) & 0x3F) != v24) )
            v26 = 0;
          *(_DWORD *)(a1 + 16) = v26;
          v27 = v25;
          v25 = _InterlockedCompareExchange(
                  a2 + 1,
                  v25 ^ ((unsigned __int16)v25 ^ (unsigned __int16)(32 * v24)) & 0x7E0 | 0x10,
                  v25);
        }
        while ( v27 != v25 );
      }
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
      break;
  }
  return a1;
}

```

## disassembly

```asm
0x18000f2c0  mov     [rsp+arg_0], rbx
0x18000f2c5  mov     [rsp+arg_8], rbp
0x18000f2ca  mov     [rsp+arg_10], rsi
0x18000f2cf  mov     [rsp+arg_18], rdi
0x18000f2d4  xor     eax, eax
0x18000f2d6  movsxd  r11, r8d
0x18000f2d9  xorps   xmm0, xmm0
0x18000f2dc  mov     rsi, rdx
0x18000f2df  mov     r10, rcx
0x18000f2e2  movups  xmmword ptr [rcx], xmm0
0x18000f2e5  mov     [rcx+10h], rax
0x18000f2e9  cmp     r11d, 7; switch 8 cases
0x18000f2ed  ja      def_18000F305; jumptable 000000018000F305 default case
0x18000f2f3  lea     rcx, cs:180000000h
0x18000f2fa  mov     r9d, ds:(jpt_18000F305 - 180000000h)[rcx+r11*4]
0x18000f302  add     r9, rcx
0x18000f305  jmp     r9; switch jump
0x18000f308  xor     ebx, ebx; jumptable 000000018000F305 cases 2,3,6,7
0x18000f30a  mov     edx, ebx
0x18000f30c  sub     r11d, 2
0x18000f310  jz      short loc_18000F339
0x18000f312  sub     r11d, 1
0x18000f316  jz      short loc_18000F332
0x18000f318  sub     r11d, 3
0x18000f31c  jz      short loc_18000F32B
0x18000f31e  cmp     r11d, 1
0x18000f322  jnz     short loc_18000F33E
0x18000f324  mov     edx, 10h
0x18000f329  jmp     short loc_18000F33E
0x18000f32b  mov     edx, 4
0x18000f330  jmp     short loc_18000F33E
0x18000f332  mov     edx, 8
0x18000f337  jmp     short loc_18000F33E
0x18000f339  mov     edx, 2
0x18000f33e  mov     ecx, [rsi]
0x18000f340  mov     eax, ebx
0x18000f342  mov     r8d, edx
0x18000f345  or      r8d, ecx
0x18000f348  cmp     r8d, ecx
0x18000f34b  mov     r9d, r8d
0x18000f34e  setz    al
0x18000f351  or      r9d, 1
0x18000f355  cmp     r8d, ecx
0x18000f358  mov     [r10+10h], eax
0x18000f35c  mov     eax, ecx
0x18000f35e  cmovz   r9d, r8d
0x18000f362  lock cmpxchg [rsi], r9d
0x18000f367  jz      short loc_18000F36D
0x18000f369  mov     ecx, eax
0x18000f36b  jmp     short loc_18000F340
0x18000f36d  test    r9b, 1
0x18000f371  jz      short loc_18000F37D
0x18000f373  mov     edi, 1
0x18000f378  test    cl, 1
0x18000f37b  jz      short loc_18000F37F
0x18000f37d  mov     edi, ebx
0x18000f37f  mov     [r10], edi
0x18000f382  jmp     loc_18000F54B
0x18000f387  mov     ecx, [rdx]; jumptable 000000018000F305 cases 0,4
0x18000f389  xor     ebx, ebx
0x18000f38b  cmp     r11d, 4
0x18000f38f  mov     ebp, ebx
0x18000f391  mov     edx, 4
0x18000f396  mov     edi, 1
0x18000f39b  setz    bpl
0x18000f39f  nop
0x18000f3a0  mov     eax, ecx
0x18000f3a2  mov     [r10+4], ebx
0x18000f3a6  or      eax, edi
0x18000f3a8  mov     r8d, eax
0x18000f3ab  shr     r8d, 0Eh
0x18000f3af  and     r8d, edi
0x18000f3b2  cmp     r8d, ebp
0x18000f3b5  jz      short loc_18000F3EC
0x18000f3b7  mov     r9d, eax
0x18000f3ba  shr     r9d, 5
0x18000f3be  and     r9d, 1FFh
0x18000f3c5  jbe     short loc_18000F3DE
0x18000f3c7  test    r11d, r11d
0x18000f3ca  mov     [r10+4], r9d
0x18000f3ce  mov     r8d, ebx
0x18000f3d1  cmovz   r8d, edx
0x18000f3d5  and     eax, 0FFFFC01Fh
0x18000f3da  mov     [r10+8], r8d
0x18000f3de  mov     r8d, ebp
0x18000f3e1  btr     eax, 0Eh
0x18000f3e5  shl     r8d, 0Eh
0x18000f3e9  or      eax, r8d
0x18000f3ec  mov     r9d, eax
0x18000f3ef  shr     r9d, 5
0x18000f3f3  and     r9d, 1FFh
0x18000f3fa  lea     r8d, [r9+1]
0x18000f3fe  cmp     r8d, 1FFh
0x18000f405  ja      short loc_18000F40C
0x18000f407  cmp     r8d, r9d
0x18000f40a  jnb     short loc_18000F417
0x18000f40c  mov     r8d, edi
0x18000f40f  mov     [r10+8], r11d
0x18000f413  mov     [r10+4], r9d
0x18000f417  shl     r8d, 5
0x18000f41b  xor     r8d, eax
0x18000f41e  and     r8d, 3FE0h
0x18000f425  xor     r8d, eax
0x18000f428  mov     eax, ecx
0x18000f42a  lock cmpxchg [rsi], r8d
0x18000f42f  jz      short loc_18000F438
0x18000f431  mov     ecx, eax
0x18000f433  jmp     loc_18000F3A0
0x18000f438  not     ecx
0x18000f43a  mov     [r10+10h], ebx
0x18000f43e  and     ecx, edi
0x18000f440  mov     [r10], ecx
0x18000f443  jmp     loc_18000F54B
0x18000f448  mov     ecx, [rdx]; jumptable 000000018000F305 cases 1,5
0x18000f44a  xor     ebx, ebx
0x18000f44c  cmp     r11d, 5
0x18000f450  mov     r9d, ebx
0x18000f453  mov     edi, 1
0x18000f458  mov     ebp, 5
0x18000f45d  setz    r9b
0x18000f461  mov     eax, ecx
0x18000f463  mov     [r10+4], ebx
0x18000f467  or      eax, edi
0x18000f469  mov     edx, eax
0x18000f46b  shr     edx, 16h
0x18000f46e  and     edx, edi
0x18000f470  cmp     edx, r9d
0x18000f473  jz      short loc_18000F4A9
0x18000f475  mov     r8d, eax
0x18000f478  shr     r8d, 0Fh
0x18000f47c  and     r8d, 7Fh
0x18000f480  jbe     short loc_18000F497
0x18000f482  mov     edx, edi
0x18000f484  mov     [r10+4], r8d
0x18000f488  cmp     r11d, edx
0x18000f48b  cmovz   edx, ebp
0x18000f48e  and     eax, 0FFC07FFFh
0x18000f493  mov     [r10+8], edx
0x18000f497  mov     edx, eax
0x18000f499  mov     r8d, r9d
0x18000f49c  shl     r8d, 16h
0x18000f4a0  btr     edx, 16h
0x18000f4a4  mov     eax, r8d
0x18000f4a7  or      eax, edx
0x18000f4a9  mov     r8d, eax
0x18000f4ac  shr     r8d, 0Fh
0x18000f4b0  and     r8d, 7Fh
0x18000f4b4  lea     edx, [r8+1]
0x18000f4b8  cmp     edx, 7Fh
0x18000f4bb  ja      short loc_18000F4C2
0x18000f4bd  cmp     edx, r8d
0x18000f4c0  jnb     short loc_18000F4CC
0x18000f4c2  mov     edx, edi
0x18000f4c4  mov     [r10+8], r11d
0x18000f4c8  mov     [r10+4], r8d
0x18000f4cc  shl     edx, 0Fh
0x18000f4cf  xor     edx, eax
0x18000f4d1  and     edx, 3F8000h
0x18000f4d7  xor     edx, eax
0x18000f4d9  mov     eax, ecx
0x18000f4db  lock cmpxchg [rsi], edx
0x18000f4df  jz      loc_18000F438
0x18000f4e5  mov     ecx, eax
0x18000f4e7  jmp     loc_18000F461
0x18000f4ec  lea     edx, [r11-140h]; jumptable 000000018000F305 default case
0x18000f4f3  xor     ebx, ebx
0x18000f4f5  mov     edi, 1
0x18000f4fa  cmp     edx, 40h ; '@'
0x18000f4fd  jge     short loc_18000F53F
0x18000f4ff  mov     eax, [rsi+4]
0x18000f502  mov     r8d, edx
0x18000f505  shl     r8d, 5
0x18000f509  nop     dword ptr [rax+00000000h]
0x18000f510  test    al, 10h
0x18000f512  jz      short loc_18000F522
0x18000f514  mov     ecx, eax
0x18000f516  shr     ecx, 5
0x18000f519  and     ecx, 3Fh
0x18000f51c  cmp     ecx, edx
0x18000f51e  mov     ecx, edi
0x18000f520  jz      short loc_18000F524
0x18000f522  mov     ecx, ebx
0x18000f524  mov     [r10+10h], ecx
0x18000f528  mov     ecx, r8d
0x18000f52b  xor     ecx, eax
0x18000f52d  and     ecx, 7E0h
0x18000f533  xor     ecx, eax
0x18000f535  or      ecx, 10h
0x18000f538  lock cmpxchg [rsi+4], ecx
0x18000f53d  jnz     short loc_18000F510
0x18000f53f  mov     [r10+8], r11d
0x18000f543  mov     [r10+4], edi
0x18000f547  mov     [r10+0Ch], ebx
0x18000f54b  mov     rbx, [rsp+arg_0]
0x18000f550  mov     rax, r10
0x18000f553  mov     rbp, [rsp+arg_8]
0x18000f558  mov     rsi, [rsp+arg_10]
0x18000f55d  mov     rdi, [rsp+arg_18]
0x18000f562  retn
```
