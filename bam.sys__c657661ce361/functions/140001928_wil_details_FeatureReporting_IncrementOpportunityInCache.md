# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x140001928`
- end: `0x1400019f2`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001ad4`

## callees

- `0x140001928`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementOpportunityInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  int *v5; // r10
  BOOL v8; // ebx
  unsigned int v9; // eax
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 5;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 22) & 1) != v8 )
    {
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        a4[1] = (v9 >> 15) & 0x7F;
        v10 = 5;
        v5 = a4 + 2;
        if ( a2 != 1 )
          v10 = 1;
        v9 = v4 & 0xFFC07FFE | 1;
        *v5 = v10;
      }
      v11 = 0;
      if ( a2 == 5 )
        v11 = 0x400000;
      v9 = v9 & 0xFFBFFFFF | v11;
    }
    v12 = (v9 >> 15) & 0x7F;
    v13 = v12 + 1;
    if ( v12 + 1 > 0x7F || v13 < v12 )
    {
      v13 = 1;
      *v5 = a2;
      a4[1] = v12;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(a1, v9 ^ (v9 ^ (v13 << 15)) & 0x3F8000, v4);
    if ( v4 == (_DWORD)result )
      break;
    v4 = result;
  }
  a4[4] = 0;
  *a4 = (v4 & 1) == 0;
  return result;
}

```

## disassembly

```asm
0x140001928  push    rbx
0x14000192a  push    rsi
0x14000192b  push    rdi
0x14000192c  mov     r8d, [rcx]
0x14000192f  lea     r10, [r9+8]
0x140001933  xor     ebx, ebx
0x140001935  mov     r11d, edx
0x140001938  cmp     edx, 5
0x14000193b  mov     rdi, rcx
0x14000193e  mov     esi, 1
0x140001943  setz    bl
0x140001946  mov     eax, r8d
0x140001949  mov     dword ptr [r9+4], 0
0x140001951  or      eax, esi
0x140001953  mov     ecx, eax
0x140001955  shr     ecx, 16h
0x140001958  and     ecx, esi
0x14000195a  cmp     ecx, ebx
0x14000195c  jz      short loc_14000199B
0x14000195e  mov     edx, eax
0x140001960  shr     edx, 0Fh
0x140001963  and     edx, 7Fh
0x140001966  jbe     short loc_140001983
0x140001968  cmp     r11d, esi
0x14000196b  mov     [r9+4], edx
0x14000196f  mov     ecx, 5
0x140001974  lea     r10, [r9+8]
0x140001978  cmovnz  ecx, esi
0x14000197b  and     eax, 0FFC07FFFh
0x140001980  mov     [r10], ecx
0x140001983  xor     edx, edx
0x140001985  mov     ecx, 400000h
0x14000198a  cmp     r11d, 5
0x14000198e  cmovz   edx, ecx
0x140001991  mov     ecx, eax
0x140001993  btr     ecx, 16h
0x140001997  mov     eax, edx
0x140001999  or      eax, ecx
0x14000199b  mov     ecx, eax
0x14000199d  shr     ecx, 0Fh
0x1400019a0  and     ecx, 7Fh
0x1400019a3  lea     edx, [rcx+1]
0x1400019a6  cmp     edx, 7Fh
0x1400019a9  ja      short loc_1400019B5
0x1400019ab  cmp     edx, ecx
0x1400019ad  jb      short loc_1400019B5
0x1400019af  lea     r10, [r9+8]
0x1400019b3  jmp     short loc_1400019BE
0x1400019b5  mov     edx, esi
0x1400019b7  mov     [r10], r11d
0x1400019ba  mov     [r9+4], ecx
0x1400019be  shl     edx, 0Fh
0x1400019c1  xor     edx, eax
0x1400019c3  and     edx, 3F8000h
0x1400019c9  xor     edx, eax
0x1400019cb  mov     eax, r8d
0x1400019ce  lock cmpxchg [rdi], edx
0x1400019d2  jz      short loc_1400019DC
0x1400019d4  mov     r8d, eax
0x1400019d7  jmp     loc_140001946
0x1400019dc  not     r8d
0x1400019df  mov     dword ptr [r9+10h], 0
0x1400019e7  and     r8d, esi
0x1400019ea  mov     [r9], r8d
0x1400019ed  pop     rdi
0x1400019ee  pop     rsi
0x1400019ef  pop     rbx
0x1400019f0  retn
```
