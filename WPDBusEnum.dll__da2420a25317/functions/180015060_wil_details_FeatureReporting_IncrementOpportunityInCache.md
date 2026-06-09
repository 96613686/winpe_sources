# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180015060`
- end: `0x180015129`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001520c`

## callees

- `0x180015060`

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
0x180015060  push    rbx
0x180015062  push    rsi
0x180015063  push    rdi
0x180015064  mov     r8d, [rcx]
0x180015067  lea     r10, [r9+8]
0x18001506b  xor     ebx, ebx
0x18001506d  mov     r11d, edx
0x180015070  cmp     edx, 5
0x180015073  mov     rdi, rcx
0x180015076  mov     esi, 1
0x18001507b  setz    bl
0x18001507e  mov     eax, r8d
0x180015081  mov     dword ptr [r9+4], 0
0x180015089  or      eax, esi
0x18001508b  mov     ecx, eax
0x18001508d  shr     ecx, 16h
0x180015090  and     ecx, esi
0x180015092  cmp     ecx, ebx
0x180015094  jz      short loc_1800150D3
0x180015096  mov     edx, eax
0x180015098  shr     edx, 0Fh
0x18001509b  and     edx, 7Fh
0x18001509e  jbe     short loc_1800150BB
0x1800150a0  cmp     r11d, esi
0x1800150a3  mov     [r9+4], edx
0x1800150a7  mov     ecx, 5
0x1800150ac  lea     r10, [r9+8]
0x1800150b0  cmovnz  ecx, esi
0x1800150b3  and     eax, 0FFC07FFFh
0x1800150b8  mov     [r10], ecx
0x1800150bb  xor     edx, edx
0x1800150bd  mov     ecx, 400000h
0x1800150c2  cmp     r11d, 5
0x1800150c6  cmovz   edx, ecx
0x1800150c9  mov     ecx, eax
0x1800150cb  btr     ecx, 16h
0x1800150cf  mov     eax, edx
0x1800150d1  or      eax, ecx
0x1800150d3  mov     ecx, eax
0x1800150d5  shr     ecx, 0Fh
0x1800150d8  and     ecx, 7Fh
0x1800150db  lea     edx, [rcx+1]
0x1800150de  cmp     edx, 7Fh
0x1800150e1  ja      short loc_1800150ED
0x1800150e3  cmp     edx, ecx
0x1800150e5  jb      short loc_1800150ED
0x1800150e7  lea     r10, [r9+8]
0x1800150eb  jmp     short loc_1800150F6
0x1800150ed  mov     edx, esi
0x1800150ef  mov     [r10], r11d
0x1800150f2  mov     [r9+4], ecx
0x1800150f6  shl     edx, 0Fh
0x1800150f9  xor     edx, eax
0x1800150fb  and     edx, 3F8000h
0x180015101  xor     edx, eax
0x180015103  mov     eax, r8d
0x180015106  lock cmpxchg [rdi], edx
0x18001510a  jz      short loc_180015114
0x18001510c  mov     r8d, eax
0x18001510f  jmp     loc_18001507E
0x180015114  not     r8d
0x180015117  mov     dword ptr [r9+10h], 0
0x18001511f  and     r8d, esi
0x180015122  mov     [r9], r8d
0x180015125  pop     rdi
0x180015126  pop     rsi
0x180015127  pop     rbx
0x180015128  retn
```
