# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x14000d678`
- end: `0x14000d741`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d824`

## callees

- `0x14000d678`

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
0x14000d678  push    rbx
0x14000d67a  push    rsi
0x14000d67b  push    rdi
0x14000d67c  mov     r8d, [rcx]
0x14000d67f  lea     r10, [r9+8]
0x14000d683  xor     ebx, ebx
0x14000d685  mov     r11d, edx
0x14000d688  cmp     edx, 5
0x14000d68b  mov     rdi, rcx
0x14000d68e  mov     esi, 1
0x14000d693  setz    bl
0x14000d696  mov     eax, r8d
0x14000d699  mov     dword ptr [r9+4], 0
0x14000d6a1  or      eax, esi
0x14000d6a3  mov     ecx, eax
0x14000d6a5  shr     ecx, 16h
0x14000d6a8  and     ecx, esi
0x14000d6aa  cmp     ecx, ebx
0x14000d6ac  jz      short loc_14000D6EB
0x14000d6ae  mov     edx, eax
0x14000d6b0  shr     edx, 0Fh
0x14000d6b3  and     edx, 7Fh
0x14000d6b6  jbe     short loc_14000D6D3
0x14000d6b8  cmp     r11d, esi
0x14000d6bb  mov     [r9+4], edx
0x14000d6bf  mov     ecx, 5
0x14000d6c4  lea     r10, [r9+8]
0x14000d6c8  cmovnz  ecx, esi
0x14000d6cb  and     eax, 0FFC07FFFh
0x14000d6d0  mov     [r10], ecx
0x14000d6d3  xor     edx, edx
0x14000d6d5  mov     ecx, 400000h
0x14000d6da  cmp     r11d, 5
0x14000d6de  cmovz   edx, ecx
0x14000d6e1  mov     ecx, eax
0x14000d6e3  btr     ecx, 16h
0x14000d6e7  mov     eax, edx
0x14000d6e9  or      eax, ecx
0x14000d6eb  mov     ecx, eax
0x14000d6ed  shr     ecx, 0Fh
0x14000d6f0  and     ecx, 7Fh
0x14000d6f3  lea     edx, [rcx+1]
0x14000d6f6  cmp     edx, 7Fh
0x14000d6f9  ja      short loc_14000D705
0x14000d6fb  cmp     edx, ecx
0x14000d6fd  jb      short loc_14000D705
0x14000d6ff  lea     r10, [r9+8]
0x14000d703  jmp     short loc_14000D70E
0x14000d705  mov     edx, esi
0x14000d707  mov     [r10], r11d
0x14000d70a  mov     [r9+4], ecx
0x14000d70e  shl     edx, 0Fh
0x14000d711  xor     edx, eax
0x14000d713  and     edx, 3F8000h
0x14000d719  xor     edx, eax
0x14000d71b  mov     eax, r8d
0x14000d71e  lock cmpxchg [rdi], edx
0x14000d722  jz      short loc_14000D72C
0x14000d724  mov     r8d, eax
0x14000d727  jmp     loc_14000D696
0x14000d72c  not     r8d
0x14000d72f  mov     dword ptr [r9+10h], 0
0x14000d737  and     r8d, esi
0x14000d73a  mov     [r9], r8d
0x14000d73d  pop     rdi
0x14000d73e  pop     rsi
0x14000d73f  pop     rbx
0x14000d740  retn
```
