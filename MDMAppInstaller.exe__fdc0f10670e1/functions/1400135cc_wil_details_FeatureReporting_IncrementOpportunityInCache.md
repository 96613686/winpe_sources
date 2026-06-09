# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1400135cc`
- end: `0x140013695`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013778`

## callees

- `0x1400135cc`

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
0x1400135cc  push    rbx
0x1400135ce  push    rsi
0x1400135cf  push    rdi
0x1400135d0  mov     r8d, [rcx]
0x1400135d3  lea     r10, [r9+8]
0x1400135d7  xor     ebx, ebx
0x1400135d9  mov     r11d, edx
0x1400135dc  cmp     edx, 5
0x1400135df  mov     rdi, rcx
0x1400135e2  mov     esi, 1
0x1400135e7  setz    bl
0x1400135ea  mov     eax, r8d
0x1400135ed  mov     dword ptr [r9+4], 0
0x1400135f5  or      eax, esi
0x1400135f7  mov     ecx, eax
0x1400135f9  shr     ecx, 16h
0x1400135fc  and     ecx, esi
0x1400135fe  cmp     ecx, ebx
0x140013600  jz      short loc_14001363F
0x140013602  mov     edx, eax
0x140013604  shr     edx, 0Fh
0x140013607  and     edx, 7Fh
0x14001360a  jbe     short loc_140013627
0x14001360c  cmp     r11d, esi
0x14001360f  mov     [r9+4], edx
0x140013613  mov     ecx, 5
0x140013618  lea     r10, [r9+8]
0x14001361c  cmovnz  ecx, esi
0x14001361f  and     eax, 0FFC07FFFh
0x140013624  mov     [r10], ecx
0x140013627  xor     edx, edx
0x140013629  mov     ecx, 400000h
0x14001362e  cmp     r11d, 5
0x140013632  cmovz   edx, ecx
0x140013635  mov     ecx, eax
0x140013637  btr     ecx, 16h
0x14001363b  mov     eax, edx
0x14001363d  or      eax, ecx
0x14001363f  mov     ecx, eax
0x140013641  shr     ecx, 0Fh
0x140013644  and     ecx, 7Fh
0x140013647  lea     edx, [rcx+1]
0x14001364a  cmp     edx, 7Fh
0x14001364d  ja      short loc_140013659
0x14001364f  cmp     edx, ecx
0x140013651  jb      short loc_140013659
0x140013653  lea     r10, [r9+8]
0x140013657  jmp     short loc_140013662
0x140013659  mov     edx, esi
0x14001365b  mov     [r10], r11d
0x14001365e  mov     [r9+4], ecx
0x140013662  shl     edx, 0Fh
0x140013665  xor     edx, eax
0x140013667  and     edx, 3F8000h
0x14001366d  xor     edx, eax
0x14001366f  mov     eax, r8d
0x140013672  lock cmpxchg [rdi], edx
0x140013676  jz      short loc_140013680
0x140013678  mov     r8d, eax
0x14001367b  jmp     loc_1400135EA
0x140013680  not     r8d
0x140013683  mov     dword ptr [r9+10h], 0
0x14001368b  and     r8d, esi
0x14001368e  mov     [r9], r8d
0x140013691  pop     rdi
0x140013692  pop     rsi
0x140013693  pop     rbx
0x140013694  retn
```
