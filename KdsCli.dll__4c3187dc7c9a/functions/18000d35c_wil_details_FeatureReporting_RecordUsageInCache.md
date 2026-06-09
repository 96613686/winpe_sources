# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000d35c`
- end: `0x18000d636`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cb6c`

## callees

- `0x18000d35c`

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
0x18000d35c  push    rbx
0x18000d35e  push    rbp
0x18000d35f  push    rsi
0x18000d360  push    rdi
0x18000d361  xor     eax, eax
0x18000d363  xorps   xmm0, xmm0
0x18000d366  mov     r11d, r8d
0x18000d369  mov     rsi, rdx
0x18000d36c  mov     r10, rcx
0x18000d36f  mov     r9d, r8d
0x18000d372  movups  xmmword ptr [rcx], xmm0
0x18000d375  mov     [rcx+10h], rax
0x18000d379  test    r8d, r8d
0x18000d37c  jz      loc_18000D560
0x18000d382  sub     r9d, 1
0x18000d386  jz      loc_18000D4A7
0x18000d38c  sub     r9d, 1
0x18000d390  jz      loc_18000D42E
0x18000d396  sub     r9d, 1
0x18000d39a  jz      loc_18000D42E
0x18000d3a0  sub     r9d, 1
0x18000d3a4  jz      loc_18000D560
0x18000d3aa  sub     r9d, 1
0x18000d3ae  jz      loc_18000D4A7
0x18000d3b4  sub     r9d, 1
0x18000d3b8  jz      short loc_18000D42E
0x18000d3ba  cmp     r9d, 1
0x18000d3be  jz      short loc_18000D42E
0x18000d3c0  add     r8d, 0FFFFFEC0h
0x18000d3c7  lea     ebx, [rax+1]
0x18000d3ca  cmp     r8d, 40h ; '@'
0x18000d3ce  jge     short loc_18000D419
0x18000d3d0  mov     eax, [rdx+4]
0x18000d3d3  lea     ecx, [rbx+0Fh]
0x18000d3d6  mov     r9d, r8d
0x18000d3d9  shl     r9d, 5
0x18000d3dd  test    cl, al
0x18000d3df  jz      short loc_18000D3F2
0x18000d3e1  mov     edx, eax
0x18000d3e3  shr     edx, 5
0x18000d3e6  and     edx, 3Fh
0x18000d3e9  cmp     edx, r8d
0x18000d3ec  jnz     short loc_18000D3F2
0x18000d3ee  mov     edx, ebx
0x18000d3f0  jmp     short loc_18000D3F4
0x18000d3f2  xor     edx, edx
0x18000d3f4  mov     [r10+10h], edx
0x18000d3f8  mov     edx, r9d
0x18000d3fb  xor     edx, eax
0x18000d3fd  and     edx, 7E0h
0x18000d403  xor     edx, eax
0x18000d405  or      edx, ecx
0x18000d407  lock cmpxchg [rsi+4], edx
0x18000d40c  jnz     short loc_18000D3DD
0x18000d40e  cmp     dword ptr [r10+10h], 0
0x18000d413  jnz     loc_18000D62E
0x18000d419  mov     [r10+8], r11d
0x18000d41d  mov     [r10+4], ebx
0x18000d421  mov     dword ptr [r10+0Ch], 0
0x18000d429  jmp     loc_18000D62E
0x18000d42e  xor     ecx, ecx
0x18000d430  sub     r11d, 2
0x18000d434  jz      short loc_18000D45C
0x18000d436  sub     r11d, 1
0x18000d43a  jz      short loc_18000D455
0x18000d43c  sub     r11d, 3
0x18000d440  jz      short loc_18000D44E
0x18000d442  cmp     r11d, 1
0x18000d446  jnz     short loc_18000D461
0x18000d448  lea     ecx, [r11+0Fh]
0x18000d44c  jmp     short loc_18000D461
0x18000d44e  mov     ecx, 4
0x18000d453  jmp     short loc_18000D461
0x18000d455  mov     ecx, 8
0x18000d45a  jmp     short loc_18000D461
0x18000d45c  mov     ecx, 2
0x18000d461  mov     edx, [rdx]
0x18000d463  mov     ebx, 1
0x18000d468  xor     eax, eax
0x18000d46a  mov     r8d, ecx
0x18000d46d  or      r8d, edx
0x18000d470  cmp     r8d, edx
0x18000d473  mov     r9d, r8d
0x18000d476  setz    al
0x18000d479  or      r9d, ebx
0x18000d47c  cmp     r8d, edx
0x18000d47f  mov     [r10+10h], eax
0x18000d483  mov     eax, edx
0x18000d485  cmovz   r9d, r8d
0x18000d489  lock cmpxchg [rsi], r9d
0x18000d48e  jz      short loc_18000D494
0x18000d490  mov     edx, eax
0x18000d492  jmp     short loc_18000D468
0x18000d494  test    bl, r9b
0x18000d497  jz      short loc_18000D49D
0x18000d499  test    bl, dl
0x18000d49b  jz      short loc_18000D49F
0x18000d49d  xor     ebx, ebx
0x18000d49f  mov     [r10], ebx
0x18000d4a2  jmp     loc_18000D62E
0x18000d4a7  mov     ecx, [rdx]
0x18000d4a9  xor     r9d, r9d
0x18000d4ac  cmp     r11d, 5
0x18000d4b0  mov     ebx, 1
0x18000d4b5  setz    r9b
0x18000d4b9  mov     eax, ecx
0x18000d4bb  mov     dword ptr [r10+4], 0
0x18000d4c3  or      eax, ebx
0x18000d4c5  mov     edx, eax
0x18000d4c7  shr     edx, 16h
0x18000d4ca  and     edx, ebx
0x18000d4cc  cmp     edx, r9d
0x18000d4cf  jz      short loc_18000D511
0x18000d4d1  mov     r8d, eax
0x18000d4d4  shr     r8d, 0Fh
0x18000d4d8  and     r8d, 7Fh
0x18000d4dc  jbe     short loc_18000D4F6
0x18000d4de  cmp     r11d, ebx
0x18000d4e1  mov     [r10+4], r8d
0x18000d4e5  mov     edx, 5
0x18000d4ea  cmovnz  edx, ebx
0x18000d4ed  and     eax, 0FFC07FFFh
0x18000d4f2  mov     [r10+8], edx
0x18000d4f6  xor     r8d, r8d
0x18000d4f9  mov     edx, 400000h
0x18000d4fe  cmp     r11d, 5
0x18000d502  cmovz   r8d, edx
0x18000d506  mov     edx, eax
0x18000d508  btr     edx, 16h
0x18000d50c  mov     eax, r8d
0x18000d50f  or      eax, edx
0x18000d511  mov     edx, eax
0x18000d513  shr     edx, 0Fh
0x18000d516  and     edx, 7Fh
0x18000d519  lea     r8d, [rdx+1]
0x18000d51d  cmp     r8d, 7Fh
0x18000d521  ja      short loc_18000D528
0x18000d523  cmp     r8d, edx
0x18000d526  jnb     short loc_18000D533
0x18000d528  mov     r8d, ebx
0x18000d52b  mov     [r10+8], r11d
0x18000d52f  mov     [r10+4], edx
0x18000d533  shl     r8d, 0Fh
0x18000d537  xor     r8d, eax
0x18000d53a  and     r8d, 3F8000h
0x18000d541  xor     r8d, eax
0x18000d544  mov     eax, ecx
0x18000d546  lock cmpxchg [rsi], r8d
0x18000d54b  jz      short loc_18000D554
0x18000d54d  mov     ecx, eax
0x18000d54f  jmp     loc_18000D4B9
0x18000d554  not     ecx
0x18000d556  and     ecx, ebx
0x18000d558  mov     [r10], ecx
0x18000d55b  jmp     loc_18000D626
0x18000d560  mov     edx, [rdx]
0x18000d562  xor     ebp, ebp
0x18000d564  lea     ecx, [rbp+4]
0x18000d567  cmp     r11d, ecx
0x18000d56a  lea     ebx, [rcx-3]
0x18000d56d  setz    bpl
0x18000d571  mov     eax, edx
0x18000d573  mov     dword ptr [r10+4], 0
0x18000d57b  or      eax, ebx
0x18000d57d  mov     r8d, eax
0x18000d580  shr     r8d, 0Eh
0x18000d584  and     r8d, ebx
0x18000d587  cmp     r8d, ebp
0x18000d58a  jz      short loc_18000D5D3
0x18000d58c  mov     edi, eax
0x18000d58e  shr     edi, 5
0x18000d591  and     edi, 1FFh
0x18000d597  jbe     short loc_18000D5B5
0x18000d599  mov     r8d, r11d
0x18000d59c  mov     [r10+4], edi
0x18000d5a0  neg     r8d
0x18000d5a3  sbb     r9d, r9d
0x18000d5a6  not     r9d
0x18000d5a9  and     r9d, ecx
0x18000d5ac  mov     [r10+8], r9d
0x18000d5b0  and     eax, 0FFFFC01Fh
0x18000d5b5  xor     r9d, r9d
0x18000d5b8  mov     r8d, 4000h
0x18000d5be  cmp     r11d, ecx
0x18000d5c1  cmovz   r9d, r8d
0x18000d5c5  mov     r8d, eax
0x18000d5c8  btr     r8d, 0Eh
0x18000d5cd  mov     eax, r9d
0x18000d5d0  or      eax, r8d
0x18000d5d3  mov     r8d, eax
0x18000d5d6  shr     r8d, 5
0x18000d5da  and     r8d, 1FFh
0x18000d5e1  lea     r9d, [r8+1]
0x18000d5e5  cmp     r9d, 1FFh
0x18000d5ec  ja      short loc_18000D5F3
0x18000d5ee  cmp     r9d, r8d
0x18000d5f1  jnb     short loc_18000D5FE
0x18000d5f3  mov     r9d, ebx
0x18000d5f6  mov     [r10+8], r11d
0x18000d5fa  mov     [r10+4], r8d
0x18000d5fe  shl     r9d, 5
0x18000d602  xor     r9d, eax
0x18000d605  and     r9d, 3FE0h
0x18000d60c  xor     r9d, eax
0x18000d60f  mov     eax, edx
0x18000d611  lock cmpxchg [rsi], r9d
0x18000d616  jz      short loc_18000D61F
0x18000d618  mov     edx, eax
0x18000d61a  jmp     loc_18000D571
0x18000d61f  not     edx
0x18000d621  and     edx, ebx
0x18000d623  mov     [r10], edx
0x18000d626  mov     dword ptr [r10+10h], 0
0x18000d62e  mov     rax, r10
0x18000d631  pop     rdi
0x18000d632  pop     rsi
0x18000d633  pop     rbp
0x18000d634  pop     rbx
0x18000d635  retn
```
