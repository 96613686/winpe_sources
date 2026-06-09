# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1800123c0`
- end: `0x180012496`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001249c`

## callees

- `0x1800123c0`

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
0x1800123c0  push    rbx
0x1800123c2  push    rsi
0x1800123c3  push    rdi
0x1800123c4  mov     r8d, [rcx]
0x1800123c7  lea     r10, [r9+8]
0x1800123cb  xor     edi, edi
0x1800123cd  mov     ebx, edx
0x1800123cf  cmp     edx, 4
0x1800123d2  mov     rsi, rcx
0x1800123d5  setz    dil
0x1800123d9  mov     eax, r8d
0x1800123dc  mov     dword ptr [r9+4], 0
0x1800123e4  or      eax, 1
0x1800123e7  mov     ecx, eax
0x1800123e9  shr     ecx, 0Eh
0x1800123ec  and     ecx, 1
0x1800123ef  cmp     ecx, edi
0x1800123f1  jz      short loc_180012435
0x1800123f3  mov     r11d, eax
0x1800123f6  shr     r11d, 5
0x1800123fa  and     r11d, 1FFh
0x180012401  jbe     short loc_18001241E
0x180012403  mov     ecx, ebx
0x180012405  mov     [r9+4], r11d
0x180012409  neg     ecx
0x18001240b  lea     r10, [r9+8]
0x18001240f  sbb     edx, edx
0x180012411  not     edx
0x180012413  and     edx, 4
0x180012416  mov     [r10], edx
0x180012419  and     eax, 0FFFFC01Fh
0x18001241e  xor     edx, edx
0x180012420  mov     ecx, 4000h
0x180012425  cmp     ebx, 4
0x180012428  cmovz   edx, ecx
0x18001242b  mov     ecx, eax
0x18001242d  btr     ecx, 0Eh
0x180012431  mov     eax, edx
0x180012433  or      eax, ecx
0x180012435  mov     ecx, eax
0x180012437  shr     ecx, 5
0x18001243a  and     ecx, 1FFh
0x180012440  lea     edx, [rcx+1]
0x180012443  cmp     edx, 1FFh
0x180012449  ja      short loc_180012455
0x18001244b  cmp     edx, ecx
0x18001244d  jb      short loc_180012455
0x18001244f  lea     r10, [r9+8]
0x180012453  jmp     short loc_180012461
0x180012455  mov     edx, 1
0x18001245a  mov     [r10], ebx
0x18001245d  mov     [r9+4], ecx
0x180012461  shl     edx, 5
0x180012464  xor     edx, eax
0x180012466  and     edx, 3FE0h
0x18001246c  xor     edx, eax
0x18001246e  mov     eax, r8d
0x180012471  lock cmpxchg [rsi], edx
0x180012475  jz      short loc_18001247F
0x180012477  mov     r8d, eax
0x18001247a  jmp     loc_1800123D9
0x18001247f  not     r8d
0x180012482  mov     dword ptr [r9+10h], 0
0x18001248a  and     r8d, 1
0x18001248e  mov     [r9], r8d
0x180012491  pop     rdi
0x180012492  pop     rsi
0x180012493  pop     rbx
0x180012494  retn
```
