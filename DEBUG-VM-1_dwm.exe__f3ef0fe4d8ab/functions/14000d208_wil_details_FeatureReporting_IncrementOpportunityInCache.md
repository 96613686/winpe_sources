# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x14000d208`
- end: `0x14000d2d1`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d3b4`

## callees

- `0x14000d208`

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
0x14000d208  push    rbx
0x14000d20a  push    rsi
0x14000d20b  push    rdi
0x14000d20c  mov     r8d, [rcx]
0x14000d20f  lea     r10, [r9+8]
0x14000d213  xor     ebx, ebx
0x14000d215  mov     r11d, edx
0x14000d218  cmp     edx, 5
0x14000d21b  mov     rdi, rcx
0x14000d21e  mov     esi, 1
0x14000d223  setz    bl
0x14000d226  mov     eax, r8d
0x14000d229  mov     dword ptr [r9+4], 0
0x14000d231  or      eax, esi
0x14000d233  mov     ecx, eax
0x14000d235  shr     ecx, 16h
0x14000d238  and     ecx, esi
0x14000d23a  cmp     ecx, ebx
0x14000d23c  jz      short loc_14000D27B
0x14000d23e  mov     edx, eax
0x14000d240  shr     edx, 0Fh
0x14000d243  and     edx, 7Fh
0x14000d246  jbe     short loc_14000D263
0x14000d248  cmp     r11d, esi
0x14000d24b  mov     [r9+4], edx
0x14000d24f  mov     ecx, 5
0x14000d254  lea     r10, [r9+8]
0x14000d258  cmovnz  ecx, esi
0x14000d25b  and     eax, 0FFC07FFFh
0x14000d260  mov     [r10], ecx
0x14000d263  xor     edx, edx
0x14000d265  mov     ecx, 400000h
0x14000d26a  cmp     r11d, 5
0x14000d26e  cmovz   edx, ecx
0x14000d271  mov     ecx, eax
0x14000d273  btr     ecx, 16h
0x14000d277  mov     eax, edx
0x14000d279  or      eax, ecx
0x14000d27b  mov     ecx, eax
0x14000d27d  shr     ecx, 0Fh
0x14000d280  and     ecx, 7Fh
0x14000d283  lea     edx, [rcx+1]
0x14000d286  cmp     edx, 7Fh
0x14000d289  ja      short loc_14000D295
0x14000d28b  cmp     edx, ecx
0x14000d28d  jb      short loc_14000D295
0x14000d28f  lea     r10, [r9+8]
0x14000d293  jmp     short loc_14000D29E
0x14000d295  mov     edx, esi
0x14000d297  mov     [r10], r11d
0x14000d29a  mov     [r9+4], ecx
0x14000d29e  shl     edx, 0Fh
0x14000d2a1  xor     edx, eax
0x14000d2a3  and     edx, 3F8000h
0x14000d2a9  xor     edx, eax
0x14000d2ab  mov     eax, r8d
0x14000d2ae  lock cmpxchg [rdi], edx
0x14000d2b2  jz      short loc_14000D2BC
0x14000d2b4  mov     r8d, eax
0x14000d2b7  jmp     loc_14000D226
0x14000d2bc  not     r8d
0x14000d2bf  mov     dword ptr [r9+10h], 0
0x14000d2c7  and     r8d, esi
0x14000d2ca  mov     [r9], r8d
0x14000d2cd  pop     rdi
0x14000d2ce  pop     rsi
0x14000d2cf  pop     rbx
0x14000d2d0  retn
```
