# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x14000d748`
- end: `0x14000d81d`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d824`

## callees

- `0x14000d748`

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
0x14000d748  push    rbx
0x14000d74a  push    rsi
0x14000d74b  push    rdi
0x14000d74c  mov     r8d, [rcx]
0x14000d74f  lea     r10, [r9+8]
0x14000d753  xor     edi, edi
0x14000d755  mov     ebx, edx
0x14000d757  cmp     edx, 4
0x14000d75a  mov     rsi, rcx
0x14000d75d  setz    dil
0x14000d761  mov     eax, r8d
0x14000d764  mov     dword ptr [r9+4], 0
0x14000d76c  or      eax, 1
0x14000d76f  mov     ecx, eax
0x14000d771  shr     ecx, 0Eh
0x14000d774  and     ecx, 1
0x14000d777  cmp     ecx, edi
0x14000d779  jz      short loc_14000D7BD
0x14000d77b  mov     r11d, eax
0x14000d77e  shr     r11d, 5
0x14000d782  and     r11d, 1FFh
0x14000d789  jbe     short loc_14000D7A6
0x14000d78b  mov     ecx, ebx
0x14000d78d  mov     [r9+4], r11d
0x14000d791  neg     ecx
0x14000d793  lea     r10, [r9+8]
0x14000d797  sbb     edx, edx
0x14000d799  not     edx
0x14000d79b  and     edx, 4
0x14000d79e  mov     [r10], edx
0x14000d7a1  and     eax, 0FFFFC01Fh
0x14000d7a6  xor     edx, edx
0x14000d7a8  mov     ecx, 4000h
0x14000d7ad  cmp     ebx, 4
0x14000d7b0  cmovz   edx, ecx
0x14000d7b3  mov     ecx, eax
0x14000d7b5  btr     ecx, 0Eh
0x14000d7b9  mov     eax, edx
0x14000d7bb  or      eax, ecx
0x14000d7bd  mov     ecx, eax
0x14000d7bf  shr     ecx, 5
0x14000d7c2  and     ecx, 1FFh
0x14000d7c8  lea     edx, [rcx+1]
0x14000d7cb  cmp     edx, 1FFh
0x14000d7d1  ja      short loc_14000D7DD
0x14000d7d3  cmp     edx, ecx
0x14000d7d5  jb      short loc_14000D7DD
0x14000d7d7  lea     r10, [r9+8]
0x14000d7db  jmp     short loc_14000D7E9
0x14000d7dd  mov     edx, 1
0x14000d7e2  mov     [r10], ebx
0x14000d7e5  mov     [r9+4], ecx
0x14000d7e9  shl     edx, 5
0x14000d7ec  xor     edx, eax
0x14000d7ee  and     edx, 3FE0h
0x14000d7f4  xor     edx, eax
0x14000d7f6  mov     eax, r8d
0x14000d7f9  lock cmpxchg [rsi], edx
0x14000d7fd  jz      short loc_14000D807
0x14000d7ff  mov     r8d, eax
0x14000d802  jmp     loc_14000D761
0x14000d807  not     r8d
0x14000d80a  mov     dword ptr [r9+10h], 0
0x14000d812  and     r8d, 1
0x14000d816  mov     [r9], r8d
0x14000d819  pop     rdi
0x14000d81a  pop     rsi
0x14000d81b  pop     rbx
0x14000d81c  retn
```
