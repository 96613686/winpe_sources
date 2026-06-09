# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18000ec28`
- end: `0x18000ecfd`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ed04`

## callees

- `0x18000ec28`

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
0x18000ec28  push    rbx
0x18000ec2a  push    rsi
0x18000ec2b  push    rdi
0x18000ec2c  mov     r8d, [rcx]
0x18000ec2f  lea     r10, [r9+8]
0x18000ec33  xor     edi, edi
0x18000ec35  mov     ebx, edx
0x18000ec37  cmp     edx, 4
0x18000ec3a  mov     rsi, rcx
0x18000ec3d  setz    dil
0x18000ec41  mov     eax, r8d
0x18000ec44  mov     dword ptr [r9+4], 0
0x18000ec4c  or      eax, 1
0x18000ec4f  mov     ecx, eax
0x18000ec51  shr     ecx, 0Eh
0x18000ec54  and     ecx, 1
0x18000ec57  cmp     ecx, edi
0x18000ec59  jz      short loc_18000EC9D
0x18000ec5b  mov     r11d, eax
0x18000ec5e  shr     r11d, 5
0x18000ec62  and     r11d, 1FFh
0x18000ec69  jbe     short loc_18000EC86
0x18000ec6b  mov     ecx, ebx
0x18000ec6d  mov     [r9+4], r11d
0x18000ec71  neg     ecx
0x18000ec73  lea     r10, [r9+8]
0x18000ec77  sbb     edx, edx
0x18000ec79  not     edx
0x18000ec7b  and     edx, 4
0x18000ec7e  mov     [r10], edx
0x18000ec81  and     eax, 0FFFFC01Fh
0x18000ec86  xor     edx, edx
0x18000ec88  mov     ecx, 4000h
0x18000ec8d  cmp     ebx, 4
0x18000ec90  cmovz   edx, ecx
0x18000ec93  mov     ecx, eax
0x18000ec95  btr     ecx, 0Eh
0x18000ec99  mov     eax, edx
0x18000ec9b  or      eax, ecx
0x18000ec9d  mov     ecx, eax
0x18000ec9f  shr     ecx, 5
0x18000eca2  and     ecx, 1FFh
0x18000eca8  lea     edx, [rcx+1]
0x18000ecab  cmp     edx, 1FFh
0x18000ecb1  ja      short loc_18000ECBD
0x18000ecb3  cmp     edx, ecx
0x18000ecb5  jb      short loc_18000ECBD
0x18000ecb7  lea     r10, [r9+8]
0x18000ecbb  jmp     short loc_18000ECC9
0x18000ecbd  mov     edx, 1
0x18000ecc2  mov     [r10], ebx
0x18000ecc5  mov     [r9+4], ecx
0x18000ecc9  shl     edx, 5
0x18000eccc  xor     edx, eax
0x18000ecce  and     edx, 3FE0h
0x18000ecd4  xor     edx, eax
0x18000ecd6  mov     eax, r8d
0x18000ecd9  lock cmpxchg [rsi], edx
0x18000ecdd  jz      short loc_18000ECE7
0x18000ecdf  mov     r8d, eax
0x18000ece2  jmp     loc_18000EC41
0x18000ece7  not     r8d
0x18000ecea  mov     dword ptr [r9+10h], 0
0x18000ecf2  and     r8d, 1
0x18000ecf6  mov     [r9], r8d
0x18000ecf9  pop     rdi
0x18000ecfa  pop     rsi
0x18000ecfb  pop     rbx
0x18000ecfc  retn
```
