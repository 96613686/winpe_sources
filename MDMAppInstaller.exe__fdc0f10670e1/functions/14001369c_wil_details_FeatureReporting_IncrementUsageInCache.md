# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x14001369c`
- end: `0x140013771`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013778`

## callees

- `0x14001369c`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_IncrementUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  signed __int32 v4; // r8d
  _DWORD *v5; // r10
  BOOL v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // edx
  __int64 result; // rax

  v4 = *a1;
  v5 = a4 + 2;
  v8 = a2 == 4;
  while ( 1 )
  {
    a4[1] = 0;
    v9 = v4 | 1;
    if ( (((v4 | 1u) >> 14) & 1) != v8 )
    {
      if ( ((v9 >> 5) & 0x1FF) != 0 )
      {
        a4[1] = (v9 >> 5) & 0x1FF;
        v5 = a4 + 2;
        a4[2] = a2 == 0 ? 4 : 0;
        v9 = v4 & 0xFFFFC01E | 1;
      }
      v10 = 0;
      if ( a2 == 4 )
        v10 = 0x4000;
      v9 = v9 & 0xFFFFBFFF | v10;
    }
    v11 = (v9 >> 5) & 0x1FF;
    v12 = v11 + 1;
    if ( v11 + 1 > 0x1FF || v12 < v11 )
    {
      LOWORD(v12) = 1;
      *v5 = a2;
      a4[1] = v11;
    }
    else
    {
      v5 = a4 + 2;
    }
    result = (unsigned int)_InterlockedCompareExchange(
                             a1,
                             v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)(32 * v12)) & 0x3FE0,
                             v4);
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
0x14001369c  push    rbx
0x14001369e  push    rsi
0x14001369f  push    rdi
0x1400136a0  mov     r8d, [rcx]
0x1400136a3  lea     r10, [r9+8]
0x1400136a7  xor     edi, edi
0x1400136a9  mov     ebx, edx
0x1400136ab  cmp     edx, 4
0x1400136ae  mov     rsi, rcx
0x1400136b1  setz    dil
0x1400136b5  mov     eax, r8d
0x1400136b8  mov     dword ptr [r9+4], 0
0x1400136c0  or      eax, 1
0x1400136c3  mov     ecx, eax
0x1400136c5  shr     ecx, 0Eh
0x1400136c8  and     ecx, 1
0x1400136cb  cmp     ecx, edi
0x1400136cd  jz      short loc_140013711
0x1400136cf  mov     r11d, eax
0x1400136d2  shr     r11d, 5
0x1400136d6  and     r11d, 1FFh
0x1400136dd  jbe     short loc_1400136FA
0x1400136df  mov     ecx, ebx
0x1400136e1  mov     [r9+4], r11d
0x1400136e5  neg     ecx
0x1400136e7  lea     r10, [r9+8]
0x1400136eb  sbb     edx, edx
0x1400136ed  not     edx
0x1400136ef  and     edx, 4
0x1400136f2  mov     [r10], edx
0x1400136f5  and     eax, 0FFFFC01Fh
0x1400136fa  xor     edx, edx
0x1400136fc  mov     ecx, 4000h
0x140013701  cmp     ebx, 4
0x140013704  cmovz   edx, ecx
0x140013707  mov     ecx, eax
0x140013709  btr     ecx, 0Eh
0x14001370d  mov     eax, edx
0x14001370f  or      eax, ecx
0x140013711  mov     ecx, eax
0x140013713  shr     ecx, 5
0x140013716  and     ecx, 1FFh
0x14001371c  lea     edx, [rcx+1]
0x14001371f  cmp     edx, 1FFh
0x140013725  ja      short loc_140013731
0x140013727  cmp     edx, ecx
0x140013729  jb      short loc_140013731
0x14001372b  lea     r10, [r9+8]
0x14001372f  jmp     short loc_14001373D
0x140013731  mov     edx, 1
0x140013736  mov     [r10], ebx
0x140013739  mov     [r9+4], ecx
0x14001373d  shl     edx, 5
0x140013740  xor     edx, eax
0x140013742  and     edx, 3FE0h
0x140013748  xor     edx, eax
0x14001374a  mov     eax, r8d
0x14001374d  lock cmpxchg [rsi], edx
0x140013751  jz      short loc_14001375B
0x140013753  mov     r8d, eax
0x140013756  jmp     loc_1400136B5
0x14001375b  not     r8d
0x14001375e  mov     dword ptr [r9+10h], 0
0x140013766  and     r8d, 1
0x14001376a  mov     [r9], r8d
0x14001376d  pop     rdi
0x14001376e  pop     rsi
0x14001376f  pop     rbx
0x140013770  retn
```
