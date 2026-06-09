# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1400124e0`
- end: `0x1400127ba`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400110ac`

## callees

- `0x1400124e0`

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
0x1400124e0  push    rbx
0x1400124e2  push    rbp
0x1400124e3  push    rsi
0x1400124e4  push    rdi
0x1400124e5  xor     eax, eax
0x1400124e7  xorps   xmm0, xmm0
0x1400124ea  mov     r11d, r8d
0x1400124ed  mov     rsi, rdx
0x1400124f0  mov     r10, rcx
0x1400124f3  mov     r9d, r8d
0x1400124f6  movups  xmmword ptr [rcx], xmm0
0x1400124f9  mov     [rcx+10h], rax
0x1400124fd  test    r8d, r8d
0x140012500  jz      loc_1400126E4
0x140012506  sub     r9d, 1
0x14001250a  jz      loc_14001262B
0x140012510  sub     r9d, 1
0x140012514  jz      loc_1400125B2
0x14001251a  sub     r9d, 1
0x14001251e  jz      loc_1400125B2
0x140012524  sub     r9d, 1
0x140012528  jz      loc_1400126E4
0x14001252e  sub     r9d, 1
0x140012532  jz      loc_14001262B
0x140012538  sub     r9d, 1
0x14001253c  jz      short loc_1400125B2
0x14001253e  cmp     r9d, 1
0x140012542  jz      short loc_1400125B2
0x140012544  add     r8d, 0FFFFFEC0h
0x14001254b  lea     ebx, [rax+1]
0x14001254e  cmp     r8d, 40h ; '@'
0x140012552  jge     short loc_14001259D
0x140012554  mov     eax, [rdx+4]
0x140012557  lea     ecx, [rbx+0Fh]
0x14001255a  mov     r9d, r8d
0x14001255d  shl     r9d, 5
0x140012561  test    cl, al
0x140012563  jz      short loc_140012576
0x140012565  mov     edx, eax
0x140012567  shr     edx, 5
0x14001256a  and     edx, 3Fh
0x14001256d  cmp     edx, r8d
0x140012570  jnz     short loc_140012576
0x140012572  mov     edx, ebx
0x140012574  jmp     short loc_140012578
0x140012576  xor     edx, edx
0x140012578  mov     [r10+10h], edx
0x14001257c  mov     edx, r9d
0x14001257f  xor     edx, eax
0x140012581  and     edx, 7E0h
0x140012587  xor     edx, eax
0x140012589  or      edx, ecx
0x14001258b  lock cmpxchg [rsi+4], edx
0x140012590  jnz     short loc_140012561
0x140012592  cmp     dword ptr [r10+10h], 0
0x140012597  jnz     loc_1400127B2
0x14001259d  mov     [r10+8], r11d
0x1400125a1  mov     [r10+4], ebx
0x1400125a5  mov     dword ptr [r10+0Ch], 0
0x1400125ad  jmp     loc_1400127B2
0x1400125b2  xor     ecx, ecx
0x1400125b4  sub     r11d, 2
0x1400125b8  jz      short loc_1400125E0
0x1400125ba  sub     r11d, 1
0x1400125be  jz      short loc_1400125D9
0x1400125c0  sub     r11d, 3
0x1400125c4  jz      short loc_1400125D2
0x1400125c6  cmp     r11d, 1
0x1400125ca  jnz     short loc_1400125E5
0x1400125cc  lea     ecx, [r11+0Fh]
0x1400125d0  jmp     short loc_1400125E5
0x1400125d2  mov     ecx, 4
0x1400125d7  jmp     short loc_1400125E5
0x1400125d9  mov     ecx, 8
0x1400125de  jmp     short loc_1400125E5
0x1400125e0  mov     ecx, 2
0x1400125e5  mov     edx, [rdx]
0x1400125e7  mov     ebx, 1
0x1400125ec  xor     eax, eax
0x1400125ee  mov     r8d, ecx
0x1400125f1  or      r8d, edx
0x1400125f4  cmp     r8d, edx
0x1400125f7  mov     r9d, r8d
0x1400125fa  setz    al
0x1400125fd  or      r9d, ebx
0x140012600  cmp     r8d, edx
0x140012603  mov     [r10+10h], eax
0x140012607  mov     eax, edx
0x140012609  cmovz   r9d, r8d
0x14001260d  lock cmpxchg [rsi], r9d
0x140012612  jz      short loc_140012618
0x140012614  mov     edx, eax
0x140012616  jmp     short loc_1400125EC
0x140012618  test    bl, r9b
0x14001261b  jz      short loc_140012621
0x14001261d  test    bl, dl
0x14001261f  jz      short loc_140012623
0x140012621  xor     ebx, ebx
0x140012623  mov     [r10], ebx
0x140012626  jmp     loc_1400127B2
0x14001262b  mov     ecx, [rdx]
0x14001262d  xor     r9d, r9d
0x140012630  cmp     r11d, 5
0x140012634  mov     ebx, 1
0x140012639  setz    r9b
0x14001263d  mov     eax, ecx
0x14001263f  mov     dword ptr [r10+4], 0
0x140012647  or      eax, ebx
0x140012649  mov     edx, eax
0x14001264b  shr     edx, 16h
0x14001264e  and     edx, ebx
0x140012650  cmp     edx, r9d
0x140012653  jz      short loc_140012695
0x140012655  mov     r8d, eax
0x140012658  shr     r8d, 0Fh
0x14001265c  and     r8d, 7Fh
0x140012660  jbe     short loc_14001267A
0x140012662  cmp     r11d, ebx
0x140012665  mov     [r10+4], r8d
0x140012669  mov     edx, 5
0x14001266e  cmovnz  edx, ebx
0x140012671  and     eax, 0FFC07FFFh
0x140012676  mov     [r10+8], edx
0x14001267a  xor     r8d, r8d
0x14001267d  mov     edx, 400000h
0x140012682  cmp     r11d, 5
0x140012686  cmovz   r8d, edx
0x14001268a  mov     edx, eax
0x14001268c  btr     edx, 16h
0x140012690  mov     eax, r8d
0x140012693  or      eax, edx
0x140012695  mov     edx, eax
0x140012697  shr     edx, 0Fh
0x14001269a  and     edx, 7Fh
0x14001269d  lea     r8d, [rdx+1]
0x1400126a1  cmp     r8d, 7Fh
0x1400126a5  ja      short loc_1400126AC
0x1400126a7  cmp     r8d, edx
0x1400126aa  jnb     short loc_1400126B7
0x1400126ac  mov     r8d, ebx
0x1400126af  mov     [r10+8], r11d
0x1400126b3  mov     [r10+4], edx
0x1400126b7  shl     r8d, 0Fh
0x1400126bb  xor     r8d, eax
0x1400126be  and     r8d, 3F8000h
0x1400126c5  xor     r8d, eax
0x1400126c8  mov     eax, ecx
0x1400126ca  lock cmpxchg [rsi], r8d
0x1400126cf  jz      short loc_1400126D8
0x1400126d1  mov     ecx, eax
0x1400126d3  jmp     loc_14001263D
0x1400126d8  not     ecx
0x1400126da  and     ecx, ebx
0x1400126dc  mov     [r10], ecx
0x1400126df  jmp     loc_1400127AA
0x1400126e4  mov     edx, [rdx]
0x1400126e6  xor     ebp, ebp
0x1400126e8  lea     ecx, [rbp+4]
0x1400126eb  cmp     r11d, ecx
0x1400126ee  lea     ebx, [rcx-3]
0x1400126f1  setz    bpl
0x1400126f5  mov     eax, edx
0x1400126f7  mov     dword ptr [r10+4], 0
0x1400126ff  or      eax, ebx
0x140012701  mov     r8d, eax
0x140012704  shr     r8d, 0Eh
0x140012708  and     r8d, ebx
0x14001270b  cmp     r8d, ebp
0x14001270e  jz      short loc_140012757
0x140012710  mov     edi, eax
0x140012712  shr     edi, 5
0x140012715  and     edi, 1FFh
0x14001271b  jbe     short loc_140012739
0x14001271d  mov     r8d, r11d
0x140012720  mov     [r10+4], edi
0x140012724  neg     r8d
0x140012727  sbb     r9d, r9d
0x14001272a  not     r9d
0x14001272d  and     r9d, ecx
0x140012730  mov     [r10+8], r9d
0x140012734  and     eax, 0FFFFC01Fh
0x140012739  xor     r9d, r9d
0x14001273c  mov     r8d, 4000h
0x140012742  cmp     r11d, ecx
0x140012745  cmovz   r9d, r8d
0x140012749  mov     r8d, eax
0x14001274c  btr     r8d, 0Eh
0x140012751  mov     eax, r9d
0x140012754  or      eax, r8d
0x140012757  mov     r8d, eax
0x14001275a  shr     r8d, 5
0x14001275e  and     r8d, 1FFh
0x140012765  lea     r9d, [r8+1]
0x140012769  cmp     r9d, 1FFh
0x140012770  ja      short loc_140012777
0x140012772  cmp     r9d, r8d
0x140012775  jnb     short loc_140012782
0x140012777  mov     r9d, ebx
0x14001277a  mov     [r10+8], r11d
0x14001277e  mov     [r10+4], r8d
0x140012782  shl     r9d, 5
0x140012786  xor     r9d, eax
0x140012789  and     r9d, 3FE0h
0x140012790  xor     r9d, eax
0x140012793  mov     eax, edx
0x140012795  lock cmpxchg [rsi], r9d
0x14001279a  jz      short loc_1400127A3
0x14001279c  mov     edx, eax
0x14001279e  jmp     loc_1400126F5
0x1400127a3  not     edx
0x1400127a5  and     edx, ebx
0x1400127a7  mov     [r10], edx
0x1400127aa  mov     dword ptr [r10+10h], 0
0x1400127b2  mov     rax, r10
0x1400127b5  pop     rdi
0x1400127b6  pop     rsi
0x1400127b7  pop     rbp
0x1400127b8  pop     rbx
0x1400127b9  retn
```
