# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1800078d8`
- end: `0x1800079a1`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007a84`

## callees

- `0x1800078d8`

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
0x1800078d8  push    rbx
0x1800078da  push    rsi
0x1800078db  push    rdi
0x1800078dc  mov     r8d, [rcx]
0x1800078df  lea     r10, [r9+8]
0x1800078e3  xor     ebx, ebx
0x1800078e5  mov     r11d, edx
0x1800078e8  cmp     edx, 5
0x1800078eb  mov     rdi, rcx
0x1800078ee  mov     esi, 1
0x1800078f3  setz    bl
0x1800078f6  mov     eax, r8d
0x1800078f9  mov     dword ptr [r9+4], 0
0x180007901  or      eax, esi
0x180007903  mov     ecx, eax
0x180007905  shr     ecx, 16h
0x180007908  and     ecx, esi
0x18000790a  cmp     ecx, ebx
0x18000790c  jz      short loc_18000794B
0x18000790e  mov     edx, eax
0x180007910  shr     edx, 0Fh
0x180007913  and     edx, 7Fh
0x180007916  jbe     short loc_180007933
0x180007918  cmp     r11d, esi
0x18000791b  mov     [r9+4], edx
0x18000791f  mov     ecx, 5
0x180007924  lea     r10, [r9+8]
0x180007928  cmovnz  ecx, esi
0x18000792b  and     eax, 0FFC07FFFh
0x180007930  mov     [r10], ecx
0x180007933  xor     edx, edx
0x180007935  mov     ecx, 400000h
0x18000793a  cmp     r11d, 5
0x18000793e  cmovz   edx, ecx
0x180007941  mov     ecx, eax
0x180007943  btr     ecx, 16h
0x180007947  mov     eax, edx
0x180007949  or      eax, ecx
0x18000794b  mov     ecx, eax
0x18000794d  shr     ecx, 0Fh
0x180007950  and     ecx, 7Fh
0x180007953  lea     edx, [rcx+1]
0x180007956  cmp     edx, 7Fh
0x180007959  ja      short loc_180007965
0x18000795b  cmp     edx, ecx
0x18000795d  jb      short loc_180007965
0x18000795f  lea     r10, [r9+8]
0x180007963  jmp     short loc_18000796E
0x180007965  mov     edx, esi
0x180007967  mov     [r10], r11d
0x18000796a  mov     [r9+4], ecx
0x18000796e  shl     edx, 0Fh
0x180007971  xor     edx, eax
0x180007973  and     edx, 3F8000h
0x180007979  xor     edx, eax
0x18000797b  mov     eax, r8d
0x18000797e  lock cmpxchg [rdi], edx
0x180007982  jz      short loc_18000798C
0x180007984  mov     r8d, eax
0x180007987  jmp     loc_1800078F6
0x18000798c  not     r8d
0x18000798f  mov     dword ptr [r9+10h], 0
0x180007997  and     r8d, esi
0x18000799a  mov     [r9], r8d
0x18000799d  pop     rdi
0x18000799e  pop     rsi
0x18000799f  pop     rbx
0x1800079a0  retn
```
