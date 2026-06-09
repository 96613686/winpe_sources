# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180018b8c`
- end: `0x180018c55`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000567c`

## callees

- `0x180018b8c`

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
0x180018b8c  push    rbx
0x180018b8e  push    rsi
0x180018b8f  push    rdi
0x180018b90  mov     r8d, [rcx]
0x180018b93  lea     r10, [r9+8]
0x180018b97  xor     ebx, ebx
0x180018b99  mov     r11d, edx
0x180018b9c  cmp     edx, 5
0x180018b9f  mov     rdi, rcx
0x180018ba2  mov     esi, 1
0x180018ba7  setz    bl
0x180018baa  mov     eax, r8d
0x180018bad  mov     dword ptr [r9+4], 0
0x180018bb5  or      eax, esi
0x180018bb7  mov     ecx, eax
0x180018bb9  shr     ecx, 16h
0x180018bbc  and     ecx, esi
0x180018bbe  cmp     ecx, ebx
0x180018bc0  jz      short loc_180018BFF
0x180018bc2  mov     edx, eax
0x180018bc4  shr     edx, 0Fh
0x180018bc7  and     edx, 7Fh
0x180018bca  jbe     short loc_180018BE7
0x180018bcc  cmp     r11d, esi
0x180018bcf  mov     [r9+4], edx
0x180018bd3  mov     ecx, 5
0x180018bd8  lea     r10, [r9+8]
0x180018bdc  cmovnz  ecx, esi
0x180018bdf  and     eax, 0FFC07FFFh
0x180018be4  mov     [r10], ecx
0x180018be7  xor     edx, edx
0x180018be9  mov     ecx, 400000h
0x180018bee  cmp     r11d, 5
0x180018bf2  cmovz   edx, ecx
0x180018bf5  mov     ecx, eax
0x180018bf7  btr     ecx, 16h
0x180018bfb  mov     eax, edx
0x180018bfd  or      eax, ecx
0x180018bff  mov     ecx, eax
0x180018c01  shr     ecx, 0Fh
0x180018c04  and     ecx, 7Fh
0x180018c07  lea     edx, [rcx+1]
0x180018c0a  cmp     edx, 7Fh
0x180018c0d  ja      short loc_180018C19
0x180018c0f  cmp     edx, ecx
0x180018c11  jb      short loc_180018C19
0x180018c13  lea     r10, [r9+8]
0x180018c17  jmp     short loc_180018C22
0x180018c19  mov     edx, esi
0x180018c1b  mov     [r10], r11d
0x180018c1e  mov     [r9+4], ecx
0x180018c22  shl     edx, 0Fh
0x180018c25  xor     edx, eax
0x180018c27  and     edx, 3F8000h
0x180018c2d  xor     edx, eax
0x180018c2f  mov     eax, r8d
0x180018c32  lock cmpxchg [rdi], edx
0x180018c36  jz      short loc_180018C40
0x180018c38  mov     r8d, eax
0x180018c3b  jmp     loc_180018BAA
0x180018c40  not     r8d
0x180018c43  mov     dword ptr [r9+10h], 0
0x180018c4b  and     r8d, esi
0x180018c4e  mov     [r9], r8d
0x180018c51  pop     rdi
0x180018c52  pop     rsi
0x180018c53  pop     rbx
0x180018c54  retn
```
