# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180012510`
- end: `0x1800127ea`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dda0`

## callees

- `0x180012510`

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
0x180012510  push    rbx
0x180012512  push    rbp
0x180012513  push    rsi
0x180012514  push    rdi
0x180012515  xor     eax, eax
0x180012517  xorps   xmm0, xmm0
0x18001251a  mov     r11d, r8d
0x18001251d  mov     rsi, rdx
0x180012520  mov     r10, rcx
0x180012523  mov     r9d, r8d
0x180012526  movups  xmmword ptr [rcx], xmm0
0x180012529  mov     [rcx+10h], rax
0x18001252d  test    r8d, r8d
0x180012530  jz      loc_180012714
0x180012536  sub     r9d, 1
0x18001253a  jz      loc_18001265B
0x180012540  sub     r9d, 1
0x180012544  jz      loc_1800125E2
0x18001254a  sub     r9d, 1
0x18001254e  jz      loc_1800125E2
0x180012554  sub     r9d, 1
0x180012558  jz      loc_180012714
0x18001255e  sub     r9d, 1
0x180012562  jz      loc_18001265B
0x180012568  sub     r9d, 1
0x18001256c  jz      short loc_1800125E2
0x18001256e  cmp     r9d, 1
0x180012572  jz      short loc_1800125E2
0x180012574  add     r8d, 0FFFFFEC0h
0x18001257b  lea     ebx, [rax+1]
0x18001257e  cmp     r8d, 40h ; '@'
0x180012582  jge     short loc_1800125CD
0x180012584  mov     eax, [rdx+4]
0x180012587  lea     ecx, [rbx+0Fh]
0x18001258a  mov     r9d, r8d
0x18001258d  shl     r9d, 5
0x180012591  test    cl, al
0x180012593  jz      short loc_1800125A6
0x180012595  mov     edx, eax
0x180012597  shr     edx, 5
0x18001259a  and     edx, 3Fh
0x18001259d  cmp     edx, r8d
0x1800125a0  jnz     short loc_1800125A6
0x1800125a2  mov     edx, ebx
0x1800125a4  jmp     short loc_1800125A8
0x1800125a6  xor     edx, edx
0x1800125a8  mov     [r10+10h], edx
0x1800125ac  mov     edx, r9d
0x1800125af  xor     edx, eax
0x1800125b1  and     edx, 7E0h
0x1800125b7  xor     edx, eax
0x1800125b9  or      edx, ecx
0x1800125bb  lock cmpxchg [rsi+4], edx
0x1800125c0  jnz     short loc_180012591
0x1800125c2  cmp     dword ptr [r10+10h], 0
0x1800125c7  jnz     loc_1800127E2
0x1800125cd  mov     [r10+8], r11d
0x1800125d1  mov     [r10+4], ebx
0x1800125d5  mov     dword ptr [r10+0Ch], 0
0x1800125dd  jmp     loc_1800127E2
0x1800125e2  xor     ecx, ecx
0x1800125e4  sub     r11d, 2
0x1800125e8  jz      short loc_180012610
0x1800125ea  sub     r11d, 1
0x1800125ee  jz      short loc_180012609
0x1800125f0  sub     r11d, 3
0x1800125f4  jz      short loc_180012602
0x1800125f6  cmp     r11d, 1
0x1800125fa  jnz     short loc_180012615
0x1800125fc  lea     ecx, [r11+0Fh]
0x180012600  jmp     short loc_180012615
0x180012602  mov     ecx, 4
0x180012607  jmp     short loc_180012615
0x180012609  mov     ecx, 8
0x18001260e  jmp     short loc_180012615
0x180012610  mov     ecx, 2
0x180012615  mov     edx, [rdx]
0x180012617  mov     ebx, 1
0x18001261c  xor     eax, eax
0x18001261e  mov     r8d, ecx
0x180012621  or      r8d, edx
0x180012624  cmp     r8d, edx
0x180012627  mov     r9d, r8d
0x18001262a  setz    al
0x18001262d  or      r9d, ebx
0x180012630  cmp     r8d, edx
0x180012633  mov     [r10+10h], eax
0x180012637  mov     eax, edx
0x180012639  cmovz   r9d, r8d
0x18001263d  lock cmpxchg [rsi], r9d
0x180012642  jz      short loc_180012648
0x180012644  mov     edx, eax
0x180012646  jmp     short loc_18001261C
0x180012648  test    bl, r9b
0x18001264b  jz      short loc_180012651
0x18001264d  test    bl, dl
0x18001264f  jz      short loc_180012653
0x180012651  xor     ebx, ebx
0x180012653  mov     [r10], ebx
0x180012656  jmp     loc_1800127E2
0x18001265b  mov     ecx, [rdx]
0x18001265d  xor     r9d, r9d
0x180012660  cmp     r11d, 5
0x180012664  mov     ebx, 1
0x180012669  setz    r9b
0x18001266d  mov     eax, ecx
0x18001266f  mov     dword ptr [r10+4], 0
0x180012677  or      eax, ebx
0x180012679  mov     edx, eax
0x18001267b  shr     edx, 16h
0x18001267e  and     edx, ebx
0x180012680  cmp     edx, r9d
0x180012683  jz      short loc_1800126C5
0x180012685  mov     r8d, eax
0x180012688  shr     r8d, 0Fh
0x18001268c  and     r8d, 7Fh
0x180012690  jbe     short loc_1800126AA
0x180012692  cmp     r11d, ebx
0x180012695  mov     [r10+4], r8d
0x180012699  mov     edx, 5
0x18001269e  cmovnz  edx, ebx
0x1800126a1  and     eax, 0FFC07FFFh
0x1800126a6  mov     [r10+8], edx
0x1800126aa  xor     r8d, r8d
0x1800126ad  mov     edx, 400000h
0x1800126b2  cmp     r11d, 5
0x1800126b6  cmovz   r8d, edx
0x1800126ba  mov     edx, eax
0x1800126bc  btr     edx, 16h
0x1800126c0  mov     eax, r8d
0x1800126c3  or      eax, edx
0x1800126c5  mov     edx, eax
0x1800126c7  shr     edx, 0Fh
0x1800126ca  and     edx, 7Fh
0x1800126cd  lea     r8d, [rdx+1]
0x1800126d1  cmp     r8d, 7Fh
0x1800126d5  ja      short loc_1800126DC
0x1800126d7  cmp     r8d, edx
0x1800126da  jnb     short loc_1800126E7
0x1800126dc  mov     r8d, ebx
0x1800126df  mov     [r10+8], r11d
0x1800126e3  mov     [r10+4], edx
0x1800126e7  shl     r8d, 0Fh
0x1800126eb  xor     r8d, eax
0x1800126ee  and     r8d, 3F8000h
0x1800126f5  xor     r8d, eax
0x1800126f8  mov     eax, ecx
0x1800126fa  lock cmpxchg [rsi], r8d
0x1800126ff  jz      short loc_180012708
0x180012701  mov     ecx, eax
0x180012703  jmp     loc_18001266D
0x180012708  not     ecx
0x18001270a  and     ecx, ebx
0x18001270c  mov     [r10], ecx
0x18001270f  jmp     loc_1800127DA
0x180012714  mov     edx, [rdx]
0x180012716  xor     ebp, ebp
0x180012718  lea     ecx, [rbp+4]
0x18001271b  cmp     r11d, ecx
0x18001271e  lea     ebx, [rcx-3]
0x180012721  setz    bpl
0x180012725  mov     eax, edx
0x180012727  mov     dword ptr [r10+4], 0
0x18001272f  or      eax, ebx
0x180012731  mov     r8d, eax
0x180012734  shr     r8d, 0Eh
0x180012738  and     r8d, ebx
0x18001273b  cmp     r8d, ebp
0x18001273e  jz      short loc_180012787
0x180012740  mov     edi, eax
0x180012742  shr     edi, 5
0x180012745  and     edi, 1FFh
0x18001274b  jbe     short loc_180012769
0x18001274d  mov     r8d, r11d
0x180012750  mov     [r10+4], edi
0x180012754  neg     r8d
0x180012757  sbb     r9d, r9d
0x18001275a  not     r9d
0x18001275d  and     r9d, ecx
0x180012760  mov     [r10+8], r9d
0x180012764  and     eax, 0FFFFC01Fh
0x180012769  xor     r9d, r9d
0x18001276c  mov     r8d, 4000h
0x180012772  cmp     r11d, ecx
0x180012775  cmovz   r9d, r8d
0x180012779  mov     r8d, eax
0x18001277c  btr     r8d, 0Eh
0x180012781  mov     eax, r9d
0x180012784  or      eax, r8d
0x180012787  mov     r8d, eax
0x18001278a  shr     r8d, 5
0x18001278e  and     r8d, 1FFh
0x180012795  lea     r9d, [r8+1]
0x180012799  cmp     r9d, 1FFh
0x1800127a0  ja      short loc_1800127A7
0x1800127a2  cmp     r9d, r8d
0x1800127a5  jnb     short loc_1800127B2
0x1800127a7  mov     r9d, ebx
0x1800127aa  mov     [r10+8], r11d
0x1800127ae  mov     [r10+4], r8d
0x1800127b2  shl     r9d, 5
0x1800127b6  xor     r9d, eax
0x1800127b9  and     r9d, 3FE0h
0x1800127c0  xor     r9d, eax
0x1800127c3  mov     eax, edx
0x1800127c5  lock cmpxchg [rsi], r9d
0x1800127ca  jz      short loc_1800127D3
0x1800127cc  mov     edx, eax
0x1800127ce  jmp     loc_180012725
0x1800127d3  not     edx
0x1800127d5  and     edx, ebx
0x1800127d7  mov     [r10], edx
0x1800127da  mov     dword ptr [r10+10h], 0
0x1800127e2  mov     rax, r10
0x1800127e5  pop     rdi
0x1800127e6  pop     rsi
0x1800127e7  pop     rbp
0x1800127e8  pop     rbx
0x1800127e9  retn
```
