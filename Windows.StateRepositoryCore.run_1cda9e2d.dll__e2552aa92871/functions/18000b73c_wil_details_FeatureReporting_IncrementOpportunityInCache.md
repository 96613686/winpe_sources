# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000b73c`
- end: `0x18000b805`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b8e8`

## callees

- `0x18000b73c`

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
0x18000b73c  push    rbx
0x18000b73e  push    rsi
0x18000b73f  push    rdi
0x18000b740  mov     r8d, [rcx]
0x18000b743  lea     r10, [r9+8]
0x18000b747  xor     ebx, ebx
0x18000b749  mov     r11d, edx
0x18000b74c  cmp     edx, 5
0x18000b74f  mov     rdi, rcx
0x18000b752  mov     esi, 1
0x18000b757  setz    bl
0x18000b75a  mov     eax, r8d
0x18000b75d  mov     dword ptr [r9+4], 0
0x18000b765  or      eax, esi
0x18000b767  mov     ecx, eax
0x18000b769  shr     ecx, 16h
0x18000b76c  and     ecx, esi
0x18000b76e  cmp     ecx, ebx
0x18000b770  jz      short loc_18000B7AF
0x18000b772  mov     edx, eax
0x18000b774  shr     edx, 0Fh
0x18000b777  and     edx, 7Fh
0x18000b77a  jbe     short loc_18000B797
0x18000b77c  cmp     r11d, esi
0x18000b77f  mov     [r9+4], edx
0x18000b783  mov     ecx, 5
0x18000b788  lea     r10, [r9+8]
0x18000b78c  cmovnz  ecx, esi
0x18000b78f  and     eax, 0FFC07FFFh
0x18000b794  mov     [r10], ecx
0x18000b797  xor     edx, edx
0x18000b799  mov     ecx, 400000h
0x18000b79e  cmp     r11d, 5
0x18000b7a2  cmovz   edx, ecx
0x18000b7a5  mov     ecx, eax
0x18000b7a7  btr     ecx, 16h
0x18000b7ab  mov     eax, edx
0x18000b7ad  or      eax, ecx
0x18000b7af  mov     ecx, eax
0x18000b7b1  shr     ecx, 0Fh
0x18000b7b4  and     ecx, 7Fh
0x18000b7b7  lea     edx, [rcx+1]
0x18000b7ba  cmp     edx, 7Fh
0x18000b7bd  ja      short loc_18000B7C9
0x18000b7bf  cmp     edx, ecx
0x18000b7c1  jb      short loc_18000B7C9
0x18000b7c3  lea     r10, [r9+8]
0x18000b7c7  jmp     short loc_18000B7D2
0x18000b7c9  mov     edx, esi
0x18000b7cb  mov     [r10], r11d
0x18000b7ce  mov     [r9+4], ecx
0x18000b7d2  shl     edx, 0Fh
0x18000b7d5  xor     edx, eax
0x18000b7d7  and     edx, 3F8000h
0x18000b7dd  xor     edx, eax
0x18000b7df  mov     eax, r8d
0x18000b7e2  lock cmpxchg [rdi], edx
0x18000b7e6  jz      short loc_18000B7F0
0x18000b7e8  mov     r8d, eax
0x18000b7eb  jmp     loc_18000B75A
0x18000b7f0  not     r8d
0x18000b7f3  mov     dword ptr [r9+10h], 0
0x18000b7fb  and     r8d, esi
0x18000b7fe  mov     [r9], r8d
0x18000b801  pop     rdi
0x18000b802  pop     rsi
0x18000b803  pop     rbx
0x18000b804  retn
```
