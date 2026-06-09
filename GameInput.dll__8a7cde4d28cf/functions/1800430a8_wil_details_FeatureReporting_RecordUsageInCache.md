# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800430a8`
- end: `0x18004337b`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800434b0`

## callees

- `0x1800430a8`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  int v7; // r8d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  signed __int32 v12; // edx
  int v13; // ebx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  BOOL v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  signed __int32 v23; // eax
  signed __int32 v24; // edx
  BOOL v25; // ebp
  unsigned int v26; // eax
  int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // r9d
  signed __int32 v30; // eax

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
      v24 = *a2;
      v25 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v26 = v24 | 1;
        if ( (((v24 | 1u) >> 14) & 1) != v25 )
        {
          if ( ((v26 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v26 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v26 = v24 & 0xFFFFC01E | 1;
          }
          v27 = 0;
          if ( a3 == 4 )
            v27 = 0x4000;
          v26 = v26 & 0xFFFFBFFF | v27;
        }
        v28 = (v26 >> 5) & 0x1FF;
        v29 = v28 + 1;
        if ( v28 + 1 > 0x1FF || v29 < v28 )
        {
          LOWORD(v29) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v28;
        }
        v30 = _InterlockedCompareExchange(
                a2,
                v26 ^ ((unsigned __int16)v26 ^ (unsigned __int16)(32 * v29)) & 0x3FE0,
                v24);
        if ( v24 == v30 )
          break;
        v24 = v30;
      }
      *(_DWORD *)a1 = (v24 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v16 = *a2;
      v17 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v19 = 5;
            if ( a3 != 1 )
              v19 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v19;
          }
          v20 = 0;
          if ( a3 == 5 )
            v20 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v20;
        }
        v21 = (v18 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v18 ^ (v18 ^ (v22 << 15)) & 0x3F8000, v16);
        if ( v16 == v23 )
          break;
        v16 = v23;
      }
      *(_DWORD *)a1 = (v16 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( v7 >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return a1;
  }
LABEL_17:
  v11 = 0;
  switch ( a3 )
  {
    case 2:
      v11 = 2;
      break;
    case 3:
      v11 = 8;
      break;
    case 6:
      v11 = 4;
      break;
    case 7:
      v11 = 16;
      break;
  }
  v12 = *a2;
  v13 = 1;
  while ( 1 )
  {
    v14 = v12 | v11 | 1;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    if ( (v12 | v11) == v12 )
      v14 = v12 | v11;
    v15 = _InterlockedCompareExchange(a2, v14, v12);
    if ( v12 == v15 )
      break;
    v12 = v15;
  }
  if ( (v14 & 1) == 0 || (v12 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x1800430a8  push    rbx
0x1800430aa  push    rbp
0x1800430ab  push    rsi
0x1800430ac  push    rdi
0x1800430ad  xor     eax, eax
0x1800430af  xorps   xmm0, xmm0
0x1800430b2  mov     r10, rcx
0x1800430b5  mov     edi, r9d
0x1800430b8  mov     r11d, r8d
0x1800430bb  mov     rsi, rdx
0x1800430be  movups  xmmword ptr [rcx], xmm0
0x1800430c1  mov     [rcx+10h], rax
0x1800430c5  mov     ecx, r8d
0x1800430c8  test    r8d, r8d
0x1800430cb  jz      loc_1800432A4
0x1800430d1  sub     ecx, 1
0x1800430d4  jz      loc_1800431EB
0x1800430da  sub     ecx, 1
0x1800430dd  jz      loc_180043172
0x1800430e3  sub     ecx, 1
0x1800430e6  jz      loc_180043172
0x1800430ec  sub     ecx, 1
0x1800430ef  jz      loc_1800432A4
0x1800430f5  sub     ecx, 1
0x1800430f8  jz      loc_1800431EB
0x1800430fe  sub     ecx, 1
0x180043101  jz      short loc_180043172
0x180043103  cmp     ecx, 1
0x180043106  jz      short loc_180043172
0x180043108  add     r8d, 0FFFFFEC0h
0x18004310f  lea     ebx, [rax+1]
0x180043112  cmp     r8d, 40h ; '@'
0x180043116  jge     short loc_180043161
0x180043118  mov     eax, [rdx+4]
0x18004311b  lea     ecx, [rbx+0Fh]
0x18004311e  mov     r9d, r8d
0x180043121  shl     r9d, 5
0x180043125  test    cl, al
0x180043127  jz      short loc_18004313A
0x180043129  mov     edx, eax
0x18004312b  shr     edx, 5
0x18004312e  and     edx, 3Fh
0x180043131  cmp     edx, r8d
0x180043134  jnz     short loc_18004313A
0x180043136  mov     edx, ebx
0x180043138  jmp     short loc_18004313C
0x18004313a  xor     edx, edx
0x18004313c  mov     [r10+10h], edx
0x180043140  mov     edx, r9d
0x180043143  xor     edx, eax
0x180043145  and     edx, 7E0h
0x18004314b  xor     edx, eax
0x18004314d  or      edx, ecx
0x18004314f  lock cmpxchg [rsi+4], edx
0x180043154  jnz     short loc_180043125
0x180043156  cmp     dword ptr [r10+10h], 0
0x18004315b  jnz     loc_180043372
0x180043161  mov     [r10+8], r11d
0x180043165  mov     [r10+4], ebx
0x180043169  mov     [r10+0Ch], edi
0x18004316d  jmp     loc_180043372
0x180043172  xor     ecx, ecx
0x180043174  sub     r11d, 2
0x180043178  jz      short loc_1800431A0
0x18004317a  sub     r11d, 1
0x18004317e  jz      short loc_180043199
0x180043180  sub     r11d, 3
0x180043184  jz      short loc_180043192
0x180043186  cmp     r11d, 1
0x18004318a  jnz     short loc_1800431A5
0x18004318c  lea     ecx, [r11+0Fh]
0x180043190  jmp     short loc_1800431A5
0x180043192  mov     ecx, 4
0x180043197  jmp     short loc_1800431A5
0x180043199  mov     ecx, 8
0x18004319e  jmp     short loc_1800431A5
0x1800431a0  mov     ecx, 2
0x1800431a5  mov     edx, [rdx]
0x1800431a7  mov     ebx, 1
0x1800431ac  xor     eax, eax
0x1800431ae  mov     r8d, ecx
0x1800431b1  or      r8d, edx
0x1800431b4  cmp     r8d, edx
0x1800431b7  mov     r9d, r8d
0x1800431ba  setz    al
0x1800431bd  or      r9d, ebx
0x1800431c0  cmp     r8d, edx
0x1800431c3  mov     [r10+10h], eax
0x1800431c7  mov     eax, edx
0x1800431c9  cmovz   r9d, r8d
0x1800431cd  lock cmpxchg [rsi], r9d
0x1800431d2  jz      short loc_1800431D8
0x1800431d4  mov     edx, eax
0x1800431d6  jmp     short loc_1800431AC
0x1800431d8  test    bl, r9b
0x1800431db  jz      short loc_1800431E1
0x1800431dd  test    bl, dl
0x1800431df  jz      short loc_1800431E3
0x1800431e1  xor     ebx, ebx
0x1800431e3  mov     [r10], ebx
0x1800431e6  jmp     loc_180043372
0x1800431eb  mov     ecx, [rdx]
0x1800431ed  xor     r9d, r9d
0x1800431f0  cmp     r11d, 5
0x1800431f4  mov     ebx, 1
0x1800431f9  setz    r9b
0x1800431fd  mov     eax, ecx
0x1800431ff  mov     dword ptr [r10+4], 0
0x180043207  or      eax, ebx
0x180043209  mov     edx, eax
0x18004320b  shr     edx, 16h
0x18004320e  and     edx, ebx
0x180043210  cmp     edx, r9d
0x180043213  jz      short loc_180043255
0x180043215  mov     r8d, eax
0x180043218  shr     r8d, 0Fh
0x18004321c  and     r8d, 7Fh
0x180043220  jbe     short loc_18004323A
0x180043222  cmp     r11d, ebx
0x180043225  mov     [r10+4], r8d
0x180043229  mov     edx, 5
0x18004322e  cmovnz  edx, ebx
0x180043231  and     eax, 0FFC07FFFh
0x180043236  mov     [r10+8], edx
0x18004323a  xor     r8d, r8d
0x18004323d  mov     edx, 400000h
0x180043242  cmp     r11d, 5
0x180043246  cmovz   r8d, edx
0x18004324a  mov     edx, eax
0x18004324c  btr     edx, 16h
0x180043250  mov     eax, r8d
0x180043253  or      eax, edx
0x180043255  mov     edx, eax
0x180043257  shr     edx, 0Fh
0x18004325a  and     edx, 7Fh
0x18004325d  lea     r8d, [rdx+1]
0x180043261  cmp     r8d, 7Fh
0x180043265  ja      short loc_18004326C
0x180043267  cmp     r8d, edx
0x18004326a  jnb     short loc_180043277
0x18004326c  mov     r8d, ebx
0x18004326f  mov     [r10+8], r11d
0x180043273  mov     [r10+4], edx
0x180043277  shl     r8d, 0Fh
0x18004327b  xor     r8d, eax
0x18004327e  and     r8d, 3F8000h
0x180043285  xor     r8d, eax
0x180043288  mov     eax, ecx
0x18004328a  lock cmpxchg [rsi], r8d
0x18004328f  jz      short loc_180043298
0x180043291  mov     ecx, eax
0x180043293  jmp     loc_1800431FD
0x180043298  not     ecx
0x18004329a  and     ecx, ebx
0x18004329c  mov     [r10], ecx
0x18004329f  jmp     loc_18004336A
0x1800432a4  mov     edx, [rdx]
0x1800432a6  xor     ebp, ebp
0x1800432a8  lea     ecx, [rbp+4]
0x1800432ab  cmp     r11d, ecx
0x1800432ae  lea     ebx, [rcx-3]
0x1800432b1  setz    bpl
0x1800432b5  mov     eax, edx
0x1800432b7  mov     dword ptr [r10+4], 0
0x1800432bf  or      eax, ebx
0x1800432c1  mov     r8d, eax
0x1800432c4  shr     r8d, 0Eh
0x1800432c8  and     r8d, ebx
0x1800432cb  cmp     r8d, ebp
0x1800432ce  jz      short loc_180043317
0x1800432d0  mov     edi, eax
0x1800432d2  shr     edi, 5
0x1800432d5  and     edi, 1FFh
0x1800432db  jbe     short loc_1800432F9
0x1800432dd  mov     r8d, r11d
0x1800432e0  mov     [r10+4], edi
0x1800432e4  neg     r8d
0x1800432e7  sbb     r9d, r9d
0x1800432ea  not     r9d
0x1800432ed  and     r9d, ecx
0x1800432f0  mov     [r10+8], r9d
0x1800432f4  and     eax, 0FFFFC01Fh
0x1800432f9  xor     r9d, r9d
0x1800432fc  mov     r8d, 4000h
0x180043302  cmp     r11d, ecx
0x180043305  cmovz   r9d, r8d
0x180043309  mov     r8d, eax
0x18004330c  btr     r8d, 0Eh
0x180043311  mov     eax, r9d
0x180043314  or      eax, r8d
0x180043317  mov     r8d, eax
0x18004331a  shr     r8d, 5
0x18004331e  and     r8d, 1FFh
0x180043325  lea     r9d, [r8+1]
0x180043329  cmp     r9d, 1FFh
0x180043330  ja      short loc_180043337
0x180043332  cmp     r9d, r8d
0x180043335  jnb     short loc_180043342
0x180043337  mov     r9d, ebx
0x18004333a  mov     [r10+8], r11d
0x18004333e  mov     [r10+4], r8d
0x180043342  shl     r9d, 5
0x180043346  xor     r9d, eax
0x180043349  and     r9d, 3FE0h
0x180043350  xor     r9d, eax
0x180043353  mov     eax, edx
0x180043355  lock cmpxchg [rsi], r9d
0x18004335a  jz      short loc_180043363
0x18004335c  mov     edx, eax
0x18004335e  jmp     loc_1800432B5
0x180043363  not     edx
0x180043365  and     edx, ebx
0x180043367  mov     [r10], edx
0x18004336a  mov     dword ptr [r10+10h], 0
0x180043372  mov     rax, r10
0x180043375  pop     rdi
0x180043376  pop     rsi
0x180043377  pop     rbp
0x180043378  pop     rbx
0x180043379  retn
```
