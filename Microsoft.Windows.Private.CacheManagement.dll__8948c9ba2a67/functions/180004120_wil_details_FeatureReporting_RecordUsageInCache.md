# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180004120`
- end: `0x1800043e4`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `708`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b580`

## callees

- `0x180004120`

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
0x180004120  mov     [rsp+arg_0], rbx
0x180004125  mov     [rsp+arg_8], rbp
0x18000412a  mov     [rsp+arg_10], rsi
0x18000412f  mov     [rsp+arg_18], rdi
0x180004134  xor     eax, eax
0x180004136  movsxd  r11, r8d
0x180004139  xorps   xmm0, xmm0
0x18000413c  mov     rsi, rdx
0x18000413f  mov     r10, rcx
0x180004142  movups  xmmword ptr [rcx], xmm0
0x180004145  mov     [rcx+10h], rax
0x180004149  cmp     r11d, 7; switch 8 cases
0x18000414d  ja      def_180004165; jumptable 0000000180004165 default case
0x180004153  lea     rcx, cs:180000000h
0x18000415a  mov     r9d, ds:(jpt_180004165 - 180000000h)[rcx+r11*4]
0x180004162  add     r9, rcx
0x180004165  jmp     r9; switch jump
0x180004168  xor     ebx, ebx; jumptable 0000000180004165 cases 2,3,6,7
0x18000416a  mov     edx, ebx
0x18000416c  sub     r11d, 2
0x180004170  jz      short loc_180004199
0x180004172  sub     r11d, 1
0x180004176  jz      short loc_180004192
0x180004178  sub     r11d, 3
0x18000417c  jz      short loc_18000418B
0x18000417e  cmp     r11d, 1
0x180004182  jnz     short loc_18000419E
0x180004184  mov     edx, 10h
0x180004189  jmp     short loc_18000419E
0x18000418b  mov     edx, 4
0x180004190  jmp     short loc_18000419E
0x180004192  mov     edx, 8
0x180004197  jmp     short loc_18000419E
0x180004199  mov     edx, 2
0x18000419e  mov     ecx, [rsi]
0x1800041a0  mov     eax, ebx
0x1800041a2  mov     r8d, edx
0x1800041a5  or      r8d, ecx
0x1800041a8  cmp     r8d, ecx
0x1800041ab  mov     r9d, r8d
0x1800041ae  setz    al
0x1800041b1  or      r9d, 1
0x1800041b5  cmp     r8d, ecx
0x1800041b8  mov     [r10+10h], eax
0x1800041bc  mov     eax, ecx
0x1800041be  cmovz   r9d, r8d
0x1800041c2  lock cmpxchg [rsi], r9d
0x1800041c7  jz      short loc_1800041CD
0x1800041c9  mov     ecx, eax
0x1800041cb  jmp     short loc_1800041A0
0x1800041cd  test    r9b, 1
0x1800041d1  jz      short loc_1800041DD
0x1800041d3  mov     edi, 1
0x1800041d8  test    cl, 1
0x1800041db  jz      short loc_1800041DF
0x1800041dd  mov     edi, ebx
0x1800041df  mov     [r10], edi
0x1800041e2  jmp     loc_1800043AB
0x1800041e7  mov     ecx, [rdx]; jumptable 0000000180004165 cases 0,4
0x1800041e9  xor     ebx, ebx
0x1800041eb  cmp     r11d, 4
0x1800041ef  mov     ebp, ebx
0x1800041f1  mov     edx, 4
0x1800041f6  mov     edi, 1
0x1800041fb  setz    bpl
0x1800041ff  nop
0x180004200  mov     eax, ecx
0x180004202  mov     [r10+4], ebx
0x180004206  or      eax, edi
0x180004208  mov     r8d, eax
0x18000420b  shr     r8d, 0Eh
0x18000420f  and     r8d, edi
0x180004212  cmp     r8d, ebp
0x180004215  jz      short loc_18000424C
0x180004217  mov     r9d, eax
0x18000421a  shr     r9d, 5
0x18000421e  and     r9d, 1FFh
0x180004225  jbe     short loc_18000423E
0x180004227  test    r11d, r11d
0x18000422a  mov     [r10+4], r9d
0x18000422e  mov     r8d, ebx
0x180004231  cmovz   r8d, edx
0x180004235  and     eax, 0FFFFC01Fh
0x18000423a  mov     [r10+8], r8d
0x18000423e  mov     r8d, ebp
0x180004241  btr     eax, 0Eh
0x180004245  shl     r8d, 0Eh
0x180004249  or      eax, r8d
0x18000424c  mov     r9d, eax
0x18000424f  shr     r9d, 5
0x180004253  and     r9d, 1FFh
0x18000425a  lea     r8d, [r9+1]
0x18000425e  cmp     r8d, 1FFh
0x180004265  ja      short loc_18000426C
0x180004267  cmp     r8d, r9d
0x18000426a  jnb     short loc_180004277
0x18000426c  mov     r8d, edi
0x18000426f  mov     [r10+8], r11d
0x180004273  mov     [r10+4], r9d
0x180004277  shl     r8d, 5
0x18000427b  xor     r8d, eax
0x18000427e  and     r8d, 3FE0h
0x180004285  xor     r8d, eax
0x180004288  mov     eax, ecx
0x18000428a  lock cmpxchg [rsi], r8d
0x18000428f  jz      short loc_180004298
0x180004291  mov     ecx, eax
0x180004293  jmp     loc_180004200
0x180004298  not     ecx
0x18000429a  mov     [r10+10h], ebx
0x18000429e  and     ecx, edi
0x1800042a0  mov     [r10], ecx
0x1800042a3  jmp     loc_1800043AB
0x1800042a8  mov     ecx, [rdx]; jumptable 0000000180004165 cases 1,5
0x1800042aa  xor     ebx, ebx
0x1800042ac  cmp     r11d, 5
0x1800042b0  mov     r9d, ebx
0x1800042b3  mov     edi, 1
0x1800042b8  mov     ebp, 5
0x1800042bd  setz    r9b
0x1800042c1  mov     eax, ecx
0x1800042c3  mov     [r10+4], ebx
0x1800042c7  or      eax, edi
0x1800042c9  mov     edx, eax
0x1800042cb  shr     edx, 16h
0x1800042ce  and     edx, edi
0x1800042d0  cmp     edx, r9d
0x1800042d3  jz      short loc_180004309
0x1800042d5  mov     r8d, eax
0x1800042d8  shr     r8d, 0Fh
0x1800042dc  and     r8d, 7Fh
0x1800042e0  jbe     short loc_1800042F7
0x1800042e2  mov     edx, edi
0x1800042e4  mov     [r10+4], r8d
0x1800042e8  cmp     r11d, edx
0x1800042eb  cmovz   edx, ebp
0x1800042ee  and     eax, 0FFC07FFFh
0x1800042f3  mov     [r10+8], edx
0x1800042f7  mov     edx, eax
0x1800042f9  mov     r8d, r9d
0x1800042fc  shl     r8d, 16h
0x180004300  btr     edx, 16h
0x180004304  mov     eax, r8d
0x180004307  or      eax, edx
0x180004309  mov     r8d, eax
0x18000430c  shr     r8d, 0Fh
0x180004310  and     r8d, 7Fh
0x180004314  lea     edx, [r8+1]
0x180004318  cmp     edx, 7Fh
0x18000431b  ja      short loc_180004322
0x18000431d  cmp     edx, r8d
0x180004320  jnb     short loc_18000432C
0x180004322  mov     edx, edi
0x180004324  mov     [r10+8], r11d
0x180004328  mov     [r10+4], r8d
0x18000432c  shl     edx, 0Fh
0x18000432f  xor     edx, eax
0x180004331  and     edx, 3F8000h
0x180004337  xor     edx, eax
0x180004339  mov     eax, ecx
0x18000433b  lock cmpxchg [rsi], edx
0x18000433f  jz      loc_180004298
0x180004345  mov     ecx, eax
0x180004347  jmp     loc_1800042C1
0x18000434c  lea     edx, [r11-140h]; jumptable 0000000180004165 default case
0x180004353  xor     ebx, ebx
0x180004355  mov     edi, 1
0x18000435a  cmp     edx, 40h ; '@'
0x18000435d  jge     short loc_18000439F
0x18000435f  mov     eax, [rsi+4]
0x180004362  mov     r8d, edx
0x180004365  shl     r8d, 5
0x180004369  nop     dword ptr [rax+00000000h]
0x180004370  test    al, 10h
0x180004372  jz      short loc_180004382
0x180004374  mov     ecx, eax
0x180004376  shr     ecx, 5
0x180004379  and     ecx, 3Fh
0x18000437c  cmp     ecx, edx
0x18000437e  mov     ecx, edi
0x180004380  jz      short loc_180004384
0x180004382  mov     ecx, ebx
0x180004384  mov     [r10+10h], ecx
0x180004388  mov     ecx, r8d
0x18000438b  xor     ecx, eax
0x18000438d  and     ecx, 7E0h
0x180004393  xor     ecx, eax
0x180004395  or      ecx, 10h
0x180004398  lock cmpxchg [rsi+4], ecx
0x18000439d  jnz     short loc_180004370
0x18000439f  mov     [r10+8], r11d
0x1800043a3  mov     [r10+4], edi
0x1800043a7  mov     [r10+0Ch], ebx
0x1800043ab  mov     rbx, [rsp+arg_0]
0x1800043b0  mov     rax, r10
0x1800043b3  mov     rbp, [rsp+arg_8]
0x1800043b8  mov     rsi, [rsp+arg_10]
0x1800043bd  mov     rdi, [rsp+arg_18]
0x1800043c2  retn
```
