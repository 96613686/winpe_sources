# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x1800089e8`
- end: `0x180008abd`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800085d4`
- `0x180008760`

## callees

- `0x1800089e8`

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
0x1800089e8  push    rbx
0x1800089ea  push    rsi
0x1800089eb  push    rdi
0x1800089ec  mov     r8d, [rcx]
0x1800089ef  lea     r10, [r9+8]
0x1800089f3  xor     edi, edi
0x1800089f5  mov     ebx, edx
0x1800089f7  cmp     edx, 4
0x1800089fa  mov     rsi, rcx
0x1800089fd  setz    dil
0x180008a01  mov     eax, r8d
0x180008a04  mov     dword ptr [r9+4], 0
0x180008a0c  or      eax, 1
0x180008a0f  mov     ecx, eax
0x180008a11  shr     ecx, 0Eh
0x180008a14  and     ecx, 1
0x180008a17  cmp     ecx, edi
0x180008a19  jz      short loc_180008A5D
0x180008a1b  mov     r11d, eax
0x180008a1e  shr     r11d, 5
0x180008a22  and     r11d, 1FFh
0x180008a29  jbe     short loc_180008A46
0x180008a2b  mov     ecx, ebx
0x180008a2d  mov     [r9+4], r11d
0x180008a31  neg     ecx
0x180008a33  lea     r10, [r9+8]
0x180008a37  sbb     edx, edx
0x180008a39  not     edx
0x180008a3b  and     edx, 4
0x180008a3e  mov     [r10], edx
0x180008a41  and     eax, 0FFFFC01Fh
0x180008a46  xor     edx, edx
0x180008a48  mov     ecx, 4000h
0x180008a4d  cmp     ebx, 4
0x180008a50  cmovz   edx, ecx
0x180008a53  mov     ecx, eax
0x180008a55  btr     ecx, 0Eh
0x180008a59  mov     eax, edx
0x180008a5b  or      eax, ecx
0x180008a5d  mov     ecx, eax
0x180008a5f  shr     ecx, 5
0x180008a62  and     ecx, 1FFh
0x180008a68  lea     edx, [rcx+1]
0x180008a6b  cmp     edx, 1FFh
0x180008a71  ja      short loc_180008A7D
0x180008a73  cmp     edx, ecx
0x180008a75  jb      short loc_180008A7D
0x180008a77  lea     r10, [r9+8]
0x180008a7b  jmp     short loc_180008A89
0x180008a7d  mov     edx, 1
0x180008a82  mov     [r10], ebx
0x180008a85  mov     [r9+4], ecx
0x180008a89  shl     edx, 5
0x180008a8c  xor     edx, eax
0x180008a8e  and     edx, 3FE0h
0x180008a94  xor     edx, eax
0x180008a96  mov     eax, r8d
0x180008a99  lock cmpxchg [rsi], edx
0x180008a9d  jz      short loc_180008AA7
0x180008a9f  mov     r8d, eax
0x180008aa2  jmp     loc_180008A01
0x180008aa7  not     r8d
0x180008aaa  mov     dword ptr [r9+10h], 0
0x180008ab2  and     r8d, 1
0x180008ab6  mov     [r9], r8d
0x180008ab9  pop     rdi
0x180008aba  pop     rsi
0x180008abb  pop     rbx
0x180008abc  retn
```
