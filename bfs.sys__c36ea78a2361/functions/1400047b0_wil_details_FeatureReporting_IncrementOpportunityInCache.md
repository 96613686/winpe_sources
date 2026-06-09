# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1400047b0`
- end: `0x14000487a`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000495c`

## callees

- `0x1400047b0`

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
0x1400047b0  push    rbx
0x1400047b2  push    rsi
0x1400047b3  push    rdi
0x1400047b4  mov     r8d, [rcx]
0x1400047b7  lea     r10, [r9+8]
0x1400047bb  xor     ebx, ebx
0x1400047bd  mov     r11d, edx
0x1400047c0  cmp     edx, 5
0x1400047c3  mov     rdi, rcx
0x1400047c6  mov     esi, 1
0x1400047cb  setz    bl
0x1400047ce  mov     eax, r8d
0x1400047d1  mov     dword ptr [r9+4], 0
0x1400047d9  or      eax, esi
0x1400047db  mov     ecx, eax
0x1400047dd  shr     ecx, 16h
0x1400047e0  and     ecx, esi
0x1400047e2  cmp     ecx, ebx
0x1400047e4  jz      short loc_140004823
0x1400047e6  mov     edx, eax
0x1400047e8  shr     edx, 0Fh
0x1400047eb  and     edx, 7Fh
0x1400047ee  jbe     short loc_14000480B
0x1400047f0  cmp     r11d, esi
0x1400047f3  mov     [r9+4], edx
0x1400047f7  mov     ecx, 5
0x1400047fc  lea     r10, [r9+8]
0x140004800  cmovnz  ecx, esi
0x140004803  and     eax, 0FFC07FFFh
0x140004808  mov     [r10], ecx
0x14000480b  xor     edx, edx
0x14000480d  mov     ecx, 400000h
0x140004812  cmp     r11d, 5
0x140004816  cmovz   edx, ecx
0x140004819  mov     ecx, eax
0x14000481b  btr     ecx, 16h
0x14000481f  mov     eax, edx
0x140004821  or      eax, ecx
0x140004823  mov     ecx, eax
0x140004825  shr     ecx, 0Fh
0x140004828  and     ecx, 7Fh
0x14000482b  lea     edx, [rcx+1]
0x14000482e  cmp     edx, 7Fh
0x140004831  ja      short loc_14000483D
0x140004833  cmp     edx, ecx
0x140004835  jb      short loc_14000483D
0x140004837  lea     r10, [r9+8]
0x14000483b  jmp     short loc_140004846
0x14000483d  mov     edx, esi
0x14000483f  mov     [r10], r11d
0x140004842  mov     [r9+4], ecx
0x140004846  shl     edx, 0Fh
0x140004849  xor     edx, eax
0x14000484b  and     edx, 3F8000h
0x140004851  xor     edx, eax
0x140004853  mov     eax, r8d
0x140004856  lock cmpxchg [rdi], edx
0x14000485a  jz      short loc_140004864
0x14000485c  mov     r8d, eax
0x14000485f  jmp     loc_1400047CE
0x140004864  not     r8d
0x140004867  mov     dword ptr [r9+10h], 0
0x14000486f  and     r8d, esi
0x140004872  mov     [r9], r8d
0x140004875  pop     rdi
0x140004876  pop     rsi
0x140004877  pop     rbx
0x140004878  retn
```
