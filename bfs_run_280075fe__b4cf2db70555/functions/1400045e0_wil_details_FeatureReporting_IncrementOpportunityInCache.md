# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1400045e0`
- end: `0x1400046aa`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000478c`

## callees

- `0x1400045e0`

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
0x1400045e0  push    rbx
0x1400045e2  push    rsi
0x1400045e3  push    rdi
0x1400045e4  mov     r8d, [rcx]
0x1400045e7  lea     r10, [r9+8]
0x1400045eb  xor     ebx, ebx
0x1400045ed  mov     r11d, edx
0x1400045f0  cmp     edx, 5
0x1400045f3  mov     rdi, rcx
0x1400045f6  mov     esi, 1
0x1400045fb  setz    bl
0x1400045fe  mov     eax, r8d
0x140004601  mov     dword ptr [r9+4], 0
0x140004609  or      eax, esi
0x14000460b  mov     ecx, eax
0x14000460d  shr     ecx, 16h
0x140004610  and     ecx, esi
0x140004612  cmp     ecx, ebx
0x140004614  jz      short loc_140004653
0x140004616  mov     edx, eax
0x140004618  shr     edx, 0Fh
0x14000461b  and     edx, 7Fh
0x14000461e  jbe     short loc_14000463B
0x140004620  cmp     r11d, esi
0x140004623  mov     [r9+4], edx
0x140004627  mov     ecx, 5
0x14000462c  lea     r10, [r9+8]
0x140004630  cmovnz  ecx, esi
0x140004633  and     eax, 0FFC07FFFh
0x140004638  mov     [r10], ecx
0x14000463b  xor     edx, edx
0x14000463d  mov     ecx, 400000h
0x140004642  cmp     r11d, 5
0x140004646  cmovz   edx, ecx
0x140004649  mov     ecx, eax
0x14000464b  btr     ecx, 16h
0x14000464f  mov     eax, edx
0x140004651  or      eax, ecx
0x140004653  mov     ecx, eax
0x140004655  shr     ecx, 0Fh
0x140004658  and     ecx, 7Fh
0x14000465b  lea     edx, [rcx+1]
0x14000465e  cmp     edx, 7Fh
0x140004661  ja      short loc_14000466D
0x140004663  cmp     edx, ecx
0x140004665  jb      short loc_14000466D
0x140004667  lea     r10, [r9+8]
0x14000466b  jmp     short loc_140004676
0x14000466d  mov     edx, esi
0x14000466f  mov     [r10], r11d
0x140004672  mov     [r9+4], ecx
0x140004676  shl     edx, 0Fh
0x140004679  xor     edx, eax
0x14000467b  and     edx, 3F8000h
0x140004681  xor     edx, eax
0x140004683  mov     eax, r8d
0x140004686  lock cmpxchg [rdi], edx
0x14000468a  jz      short loc_140004694
0x14000468c  mov     r8d, eax
0x14000468f  jmp     loc_1400045FE
0x140004694  not     r8d
0x140004697  mov     dword ptr [r9+10h], 0
0x14000469f  and     r8d, esi
0x1400046a2  mov     [r9], r8d
0x1400046a5  pop     rdi
0x1400046a6  pop     rsi
0x1400046a7  pop     rbx
0x1400046a8  retn
```
