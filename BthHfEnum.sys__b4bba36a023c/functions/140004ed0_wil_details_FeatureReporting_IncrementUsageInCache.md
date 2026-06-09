# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x140004ed0`
- end: `0x140004fa6`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004fac`

## callees

- `0x140004ed0`

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
0x140004ed0  push    rbx
0x140004ed2  push    rsi
0x140004ed3  push    rdi
0x140004ed4  mov     r8d, [rcx]
0x140004ed7  lea     r10, [r9+8]
0x140004edb  xor     edi, edi
0x140004edd  mov     ebx, edx
0x140004edf  cmp     edx, 4
0x140004ee2  mov     rsi, rcx
0x140004ee5  setz    dil
0x140004ee9  mov     eax, r8d
0x140004eec  mov     dword ptr [r9+4], 0
0x140004ef4  or      eax, 1
0x140004ef7  mov     ecx, eax
0x140004ef9  shr     ecx, 0Eh
0x140004efc  and     ecx, 1
0x140004eff  cmp     ecx, edi
0x140004f01  jz      short loc_140004F45
0x140004f03  mov     r11d, eax
0x140004f06  shr     r11d, 5
0x140004f0a  and     r11d, 1FFh
0x140004f11  jbe     short loc_140004F2E
0x140004f13  mov     ecx, ebx
0x140004f15  mov     [r9+4], r11d
0x140004f19  neg     ecx
0x140004f1b  lea     r10, [r9+8]
0x140004f1f  sbb     edx, edx
0x140004f21  not     edx
0x140004f23  and     edx, 4
0x140004f26  mov     [r10], edx
0x140004f29  and     eax, 0FFFFC01Fh
0x140004f2e  xor     edx, edx
0x140004f30  mov     ecx, 4000h
0x140004f35  cmp     ebx, 4
0x140004f38  cmovz   edx, ecx
0x140004f3b  mov     ecx, eax
0x140004f3d  btr     ecx, 0Eh
0x140004f41  mov     eax, edx
0x140004f43  or      eax, ecx
0x140004f45  mov     ecx, eax
0x140004f47  shr     ecx, 5
0x140004f4a  and     ecx, 1FFh
0x140004f50  lea     edx, [rcx+1]
0x140004f53  cmp     edx, 1FFh
0x140004f59  ja      short loc_140004F65
0x140004f5b  cmp     edx, ecx
0x140004f5d  jb      short loc_140004F65
0x140004f5f  lea     r10, [r9+8]
0x140004f63  jmp     short loc_140004F71
0x140004f65  mov     edx, 1
0x140004f6a  mov     [r10], ebx
0x140004f6d  mov     [r9+4], ecx
0x140004f71  shl     edx, 5
0x140004f74  xor     edx, eax
0x140004f76  and     edx, 3FE0h
0x140004f7c  xor     edx, eax
0x140004f7e  mov     eax, r8d
0x140004f81  lock cmpxchg [rsi], edx
0x140004f85  jz      short loc_140004F8F
0x140004f87  mov     r8d, eax
0x140004f8a  jmp     loc_140004EE9
0x140004f8f  not     r8d
0x140004f92  mov     dword ptr [r9+10h], 0
0x140004f9a  and     r8d, 1
0x140004f9e  mov     [r9], r8d
0x140004fa1  pop     rdi
0x140004fa2  pop     rsi
0x140004fa3  pop     rbx
0x140004fa4  retn
```
