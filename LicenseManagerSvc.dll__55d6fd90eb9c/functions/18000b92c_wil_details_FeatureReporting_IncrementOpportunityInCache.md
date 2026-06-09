# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x18000b92c`
- end: `0x18000b9f5`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bad8`

## callees

- `0x18000b92c`

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
0x18000b92c  push    rbx
0x18000b92e  push    rsi
0x18000b92f  push    rdi
0x18000b930  mov     r8d, [rcx]
0x18000b933  lea     r10, [r9+8]
0x18000b937  xor     ebx, ebx
0x18000b939  mov     r11d, edx
0x18000b93c  cmp     edx, 5
0x18000b93f  mov     rdi, rcx
0x18000b942  mov     esi, 1
0x18000b947  setz    bl
0x18000b94a  mov     eax, r8d
0x18000b94d  mov     dword ptr [r9+4], 0
0x18000b955  or      eax, esi
0x18000b957  mov     ecx, eax
0x18000b959  shr     ecx, 16h
0x18000b95c  and     ecx, esi
0x18000b95e  cmp     ecx, ebx
0x18000b960  jz      short loc_18000B99F
0x18000b962  mov     edx, eax
0x18000b964  shr     edx, 0Fh
0x18000b967  and     edx, 7Fh
0x18000b96a  jbe     short loc_18000B987
0x18000b96c  cmp     r11d, esi
0x18000b96f  mov     [r9+4], edx
0x18000b973  mov     ecx, 5
0x18000b978  lea     r10, [r9+8]
0x18000b97c  cmovnz  ecx, esi
0x18000b97f  and     eax, 0FFC07FFFh
0x18000b984  mov     [r10], ecx
0x18000b987  xor     edx, edx
0x18000b989  mov     ecx, 400000h
0x18000b98e  cmp     r11d, 5
0x18000b992  cmovz   edx, ecx
0x18000b995  mov     ecx, eax
0x18000b997  btr     ecx, 16h
0x18000b99b  mov     eax, edx
0x18000b99d  or      eax, ecx
0x18000b99f  mov     ecx, eax
0x18000b9a1  shr     ecx, 0Fh
0x18000b9a4  and     ecx, 7Fh
0x18000b9a7  lea     edx, [rcx+1]
0x18000b9aa  cmp     edx, 7Fh
0x18000b9ad  ja      short loc_18000B9B9
0x18000b9af  cmp     edx, ecx
0x18000b9b1  jb      short loc_18000B9B9
0x18000b9b3  lea     r10, [r9+8]
0x18000b9b7  jmp     short loc_18000B9C2
0x18000b9b9  mov     edx, esi
0x18000b9bb  mov     [r10], r11d
0x18000b9be  mov     [r9+4], ecx
0x18000b9c2  shl     edx, 0Fh
0x18000b9c5  xor     edx, eax
0x18000b9c7  and     edx, 3F8000h
0x18000b9cd  xor     edx, eax
0x18000b9cf  mov     eax, r8d
0x18000b9d2  lock cmpxchg [rdi], edx
0x18000b9d6  jz      short loc_18000B9E0
0x18000b9d8  mov     r8d, eax
0x18000b9db  jmp     loc_18000B94A
0x18000b9e0  not     r8d
0x18000b9e3  mov     dword ptr [r9+10h], 0
0x18000b9eb  and     r8d, esi
0x18000b9ee  mov     [r9], r8d
0x18000b9f1  pop     rdi
0x18000b9f2  pop     rsi
0x18000b9f3  pop     rbx
0x18000b9f4  retn
```
