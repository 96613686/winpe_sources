# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1400019f8`
- end: `0x140001ace`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001ad4`

## callees

- `0x1400019f8`

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
0x1400019f8  push    rbx
0x1400019fa  push    rsi
0x1400019fb  push    rdi
0x1400019fc  mov     r8d, [rcx]
0x1400019ff  lea     r10, [r9+8]
0x140001a03  xor     edi, edi
0x140001a05  mov     ebx, edx
0x140001a07  cmp     edx, 4
0x140001a0a  mov     rsi, rcx
0x140001a0d  setz    dil
0x140001a11  mov     eax, r8d
0x140001a14  mov     dword ptr [r9+4], 0
0x140001a1c  or      eax, 1
0x140001a1f  mov     ecx, eax
0x140001a21  shr     ecx, 0Eh
0x140001a24  and     ecx, 1
0x140001a27  cmp     ecx, edi
0x140001a29  jz      short loc_140001A6D
0x140001a2b  mov     r11d, eax
0x140001a2e  shr     r11d, 5
0x140001a32  and     r11d, 1FFh
0x140001a39  jbe     short loc_140001A56
0x140001a3b  mov     ecx, ebx
0x140001a3d  mov     [r9+4], r11d
0x140001a41  neg     ecx
0x140001a43  lea     r10, [r9+8]
0x140001a47  sbb     edx, edx
0x140001a49  not     edx
0x140001a4b  and     edx, 4
0x140001a4e  mov     [r10], edx
0x140001a51  and     eax, 0FFFFC01Fh
0x140001a56  xor     edx, edx
0x140001a58  mov     ecx, 4000h
0x140001a5d  cmp     ebx, 4
0x140001a60  cmovz   edx, ecx
0x140001a63  mov     ecx, eax
0x140001a65  btr     ecx, 0Eh
0x140001a69  mov     eax, edx
0x140001a6b  or      eax, ecx
0x140001a6d  mov     ecx, eax
0x140001a6f  shr     ecx, 5
0x140001a72  and     ecx, 1FFh
0x140001a78  lea     edx, [rcx+1]
0x140001a7b  cmp     edx, 1FFh
0x140001a81  ja      short loc_140001A8D
0x140001a83  cmp     edx, ecx
0x140001a85  jb      short loc_140001A8D
0x140001a87  lea     r10, [r9+8]
0x140001a8b  jmp     short loc_140001A99
0x140001a8d  mov     edx, 1
0x140001a92  mov     [r10], ebx
0x140001a95  mov     [r9+4], ecx
0x140001a99  shl     edx, 5
0x140001a9c  xor     edx, eax
0x140001a9e  and     edx, 3FE0h
0x140001aa4  xor     edx, eax
0x140001aa6  mov     eax, r8d
0x140001aa9  lock cmpxchg [rsi], edx
0x140001aad  jz      short loc_140001AB7
0x140001aaf  mov     r8d, eax
0x140001ab2  jmp     loc_140001A11
0x140001ab7  not     r8d
0x140001aba  mov     dword ptr [r9+10h], 0
0x140001ac2  and     r8d, 1
0x140001ac6  mov     [r9], r8d
0x140001ac9  pop     rdi
0x140001aca  pop     rsi
0x140001acb  pop     rbx
0x140001acc  retn
```
