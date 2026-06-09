# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x140010c98`
- end: `0x140010d6e`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140010d74`

## callees

- `0x140010c98`

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
0x140010c98  push    rbx
0x140010c9a  push    rsi
0x140010c9b  push    rdi
0x140010c9c  mov     r8d, [rcx]
0x140010c9f  lea     r10, [r9+8]
0x140010ca3  xor     edi, edi
0x140010ca5  mov     ebx, edx
0x140010ca7  cmp     edx, 4
0x140010caa  mov     rsi, rcx
0x140010cad  setz    dil
0x140010cb1  mov     eax, r8d
0x140010cb4  mov     dword ptr [r9+4], 0
0x140010cbc  or      eax, 1
0x140010cbf  mov     ecx, eax
0x140010cc1  shr     ecx, 0Eh
0x140010cc4  and     ecx, 1
0x140010cc7  cmp     ecx, edi
0x140010cc9  jz      short loc_140010D0D
0x140010ccb  mov     r11d, eax
0x140010cce  shr     r11d, 5
0x140010cd2  and     r11d, 1FFh
0x140010cd9  jbe     short loc_140010CF6
0x140010cdb  mov     ecx, ebx
0x140010cdd  mov     [r9+4], r11d
0x140010ce1  neg     ecx
0x140010ce3  lea     r10, [r9+8]
0x140010ce7  sbb     edx, edx
0x140010ce9  not     edx
0x140010ceb  and     edx, 4
0x140010cee  mov     [r10], edx
0x140010cf1  and     eax, 0FFFFC01Fh
0x140010cf6  xor     edx, edx
0x140010cf8  mov     ecx, 4000h
0x140010cfd  cmp     ebx, 4
0x140010d00  cmovz   edx, ecx
0x140010d03  mov     ecx, eax
0x140010d05  btr     ecx, 0Eh
0x140010d09  mov     eax, edx
0x140010d0b  or      eax, ecx
0x140010d0d  mov     ecx, eax
0x140010d0f  shr     ecx, 5
0x140010d12  and     ecx, 1FFh
0x140010d18  lea     edx, [rcx+1]
0x140010d1b  cmp     edx, 1FFh
0x140010d21  ja      short loc_140010D2D
0x140010d23  cmp     edx, ecx
0x140010d25  jb      short loc_140010D2D
0x140010d27  lea     r10, [r9+8]
0x140010d2b  jmp     short loc_140010D39
0x140010d2d  mov     edx, 1
0x140010d32  mov     [r10], ebx
0x140010d35  mov     [r9+4], ecx
0x140010d39  shl     edx, 5
0x140010d3c  xor     edx, eax
0x140010d3e  and     edx, 3FE0h
0x140010d44  xor     edx, eax
0x140010d46  mov     eax, r8d
0x140010d49  lock cmpxchg [rsi], edx
0x140010d4d  jz      short loc_140010D57
0x140010d4f  mov     r8d, eax
0x140010d52  jmp     loc_140010CB1
0x140010d57  not     r8d
0x140010d5a  mov     dword ptr [r9+10h], 0
0x140010d62  and     r8d, 1
0x140010d66  mov     [r9], r8d
0x140010d69  pop     rdi
0x140010d6a  pop     rsi
0x140010d6b  pop     rbx
0x140010d6c  retn
```
