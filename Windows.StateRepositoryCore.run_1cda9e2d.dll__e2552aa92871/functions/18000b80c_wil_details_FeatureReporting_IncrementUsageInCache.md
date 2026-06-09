# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18000b80c`
- end: `0x18000b8e1`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b8e8`

## callees

- `0x18000b80c`

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
0x18000b80c  push    rbx
0x18000b80e  push    rsi
0x18000b80f  push    rdi
0x18000b810  mov     r8d, [rcx]
0x18000b813  lea     r10, [r9+8]
0x18000b817  xor     edi, edi
0x18000b819  mov     ebx, edx
0x18000b81b  cmp     edx, 4
0x18000b81e  mov     rsi, rcx
0x18000b821  setz    dil
0x18000b825  mov     eax, r8d
0x18000b828  mov     dword ptr [r9+4], 0
0x18000b830  or      eax, 1
0x18000b833  mov     ecx, eax
0x18000b835  shr     ecx, 0Eh
0x18000b838  and     ecx, 1
0x18000b83b  cmp     ecx, edi
0x18000b83d  jz      short loc_18000B881
0x18000b83f  mov     r11d, eax
0x18000b842  shr     r11d, 5
0x18000b846  and     r11d, 1FFh
0x18000b84d  jbe     short loc_18000B86A
0x18000b84f  mov     ecx, ebx
0x18000b851  mov     [r9+4], r11d
0x18000b855  neg     ecx
0x18000b857  lea     r10, [r9+8]
0x18000b85b  sbb     edx, edx
0x18000b85d  not     edx
0x18000b85f  and     edx, 4
0x18000b862  mov     [r10], edx
0x18000b865  and     eax, 0FFFFC01Fh
0x18000b86a  xor     edx, edx
0x18000b86c  mov     ecx, 4000h
0x18000b871  cmp     ebx, 4
0x18000b874  cmovz   edx, ecx
0x18000b877  mov     ecx, eax
0x18000b879  btr     ecx, 0Eh
0x18000b87d  mov     eax, edx
0x18000b87f  or      eax, ecx
0x18000b881  mov     ecx, eax
0x18000b883  shr     ecx, 5
0x18000b886  and     ecx, 1FFh
0x18000b88c  lea     edx, [rcx+1]
0x18000b88f  cmp     edx, 1FFh
0x18000b895  ja      short loc_18000B8A1
0x18000b897  cmp     edx, ecx
0x18000b899  jb      short loc_18000B8A1
0x18000b89b  lea     r10, [r9+8]
0x18000b89f  jmp     short loc_18000B8AD
0x18000b8a1  mov     edx, 1
0x18000b8a6  mov     [r10], ebx
0x18000b8a9  mov     [r9+4], ecx
0x18000b8ad  shl     edx, 5
0x18000b8b0  xor     edx, eax
0x18000b8b2  and     edx, 3FE0h
0x18000b8b8  xor     edx, eax
0x18000b8ba  mov     eax, r8d
0x18000b8bd  lock cmpxchg [rsi], edx
0x18000b8c1  jz      short loc_18000B8CB
0x18000b8c3  mov     r8d, eax
0x18000b8c6  jmp     loc_18000B825
0x18000b8cb  not     r8d
0x18000b8ce  mov     dword ptr [r9+10h], 0
0x18000b8d6  and     r8d, 1
0x18000b8da  mov     [r9], r8d
0x18000b8dd  pop     rdi
0x18000b8de  pop     rsi
0x18000b8df  pop     rbx
0x18000b8e0  retn
```
