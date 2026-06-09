# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000eb58`
- end: `0x18000ec21`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ed04`

## callees

- `0x18000eb58`

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
0x18000eb58  push    rbx
0x18000eb5a  push    rsi
0x18000eb5b  push    rdi
0x18000eb5c  mov     r8d, [rcx]
0x18000eb5f  lea     r10, [r9+8]
0x18000eb63  xor     ebx, ebx
0x18000eb65  mov     r11d, edx
0x18000eb68  cmp     edx, 5
0x18000eb6b  mov     rdi, rcx
0x18000eb6e  mov     esi, 1
0x18000eb73  setz    bl
0x18000eb76  mov     eax, r8d
0x18000eb79  mov     dword ptr [r9+4], 0
0x18000eb81  or      eax, esi
0x18000eb83  mov     ecx, eax
0x18000eb85  shr     ecx, 16h
0x18000eb88  and     ecx, esi
0x18000eb8a  cmp     ecx, ebx
0x18000eb8c  jz      short loc_18000EBCB
0x18000eb8e  mov     edx, eax
0x18000eb90  shr     edx, 0Fh
0x18000eb93  and     edx, 7Fh
0x18000eb96  jbe     short loc_18000EBB3
0x18000eb98  cmp     r11d, esi
0x18000eb9b  mov     [r9+4], edx
0x18000eb9f  mov     ecx, 5
0x18000eba4  lea     r10, [r9+8]
0x18000eba8  cmovnz  ecx, esi
0x18000ebab  and     eax, 0FFC07FFFh
0x18000ebb0  mov     [r10], ecx
0x18000ebb3  xor     edx, edx
0x18000ebb5  mov     ecx, 400000h
0x18000ebba  cmp     r11d, 5
0x18000ebbe  cmovz   edx, ecx
0x18000ebc1  mov     ecx, eax
0x18000ebc3  btr     ecx, 16h
0x18000ebc7  mov     eax, edx
0x18000ebc9  or      eax, ecx
0x18000ebcb  mov     ecx, eax
0x18000ebcd  shr     ecx, 0Fh
0x18000ebd0  and     ecx, 7Fh
0x18000ebd3  lea     edx, [rcx+1]
0x18000ebd6  cmp     edx, 7Fh
0x18000ebd9  ja      short loc_18000EBE5
0x18000ebdb  cmp     edx, ecx
0x18000ebdd  jb      short loc_18000EBE5
0x18000ebdf  lea     r10, [r9+8]
0x18000ebe3  jmp     short loc_18000EBEE
0x18000ebe5  mov     edx, esi
0x18000ebe7  mov     [r10], r11d
0x18000ebea  mov     [r9+4], ecx
0x18000ebee  shl     edx, 0Fh
0x18000ebf1  xor     edx, eax
0x18000ebf3  and     edx, 3F8000h
0x18000ebf9  xor     edx, eax
0x18000ebfb  mov     eax, r8d
0x18000ebfe  lock cmpxchg [rdi], edx
0x18000ec02  jz      short loc_18000EC0C
0x18000ec04  mov     r8d, eax
0x18000ec07  jmp     loc_18000EB76
0x18000ec0c  not     r8d
0x18000ec0f  mov     dword ptr [r9+10h], 0
0x18000ec17  and     r8d, esi
0x18000ec1a  mov     [r9], r8d
0x18000ec1d  pop     rdi
0x18000ec1e  pop     rsi
0x18000ec1f  pop     rbx
0x18000ec20  retn
```
