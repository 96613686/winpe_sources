# wil_details_FeatureReporting_IncrementUsageInCache

- ea: `0x18000b9fc`
- end: `0x18000bad1`
- name: `wil_details_FeatureReporting_IncrementUsageInCache`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bad8`

## callees

- `0x18000b9fc`

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
0x18000b9fc  push    rbx
0x18000b9fe  push    rsi
0x18000b9ff  push    rdi
0x18000ba00  mov     r8d, [rcx]
0x18000ba03  lea     r10, [r9+8]
0x18000ba07  xor     edi, edi
0x18000ba09  mov     ebx, edx
0x18000ba0b  cmp     edx, 4
0x18000ba0e  mov     rsi, rcx
0x18000ba11  setz    dil
0x18000ba15  mov     eax, r8d
0x18000ba18  mov     dword ptr [r9+4], 0
0x18000ba20  or      eax, 1
0x18000ba23  mov     ecx, eax
0x18000ba25  shr     ecx, 0Eh
0x18000ba28  and     ecx, 1
0x18000ba2b  cmp     ecx, edi
0x18000ba2d  jz      short loc_18000BA71
0x18000ba2f  mov     r11d, eax
0x18000ba32  shr     r11d, 5
0x18000ba36  and     r11d, 1FFh
0x18000ba3d  jbe     short loc_18000BA5A
0x18000ba3f  mov     ecx, ebx
0x18000ba41  mov     [r9+4], r11d
0x18000ba45  neg     ecx
0x18000ba47  lea     r10, [r9+8]
0x18000ba4b  sbb     edx, edx
0x18000ba4d  not     edx
0x18000ba4f  and     edx, 4
0x18000ba52  mov     [r10], edx
0x18000ba55  and     eax, 0FFFFC01Fh
0x18000ba5a  xor     edx, edx
0x18000ba5c  mov     ecx, 4000h
0x18000ba61  cmp     ebx, 4
0x18000ba64  cmovz   edx, ecx
0x18000ba67  mov     ecx, eax
0x18000ba69  btr     ecx, 0Eh
0x18000ba6d  mov     eax, edx
0x18000ba6f  or      eax, ecx
0x18000ba71  mov     ecx, eax
0x18000ba73  shr     ecx, 5
0x18000ba76  and     ecx, 1FFh
0x18000ba7c  lea     edx, [rcx+1]
0x18000ba7f  cmp     edx, 1FFh
0x18000ba85  ja      short loc_18000BA91
0x18000ba87  cmp     edx, ecx
0x18000ba89  jb      short loc_18000BA91
0x18000ba8b  lea     r10, [r9+8]
0x18000ba8f  jmp     short loc_18000BA9D
0x18000ba91  mov     edx, 1
0x18000ba96  mov     [r10], ebx
0x18000ba99  mov     [r9+4], ecx
0x18000ba9d  shl     edx, 5
0x18000baa0  xor     edx, eax
0x18000baa2  and     edx, 3FE0h
0x18000baa8  xor     edx, eax
0x18000baaa  mov     eax, r8d
0x18000baad  lock cmpxchg [rsi], edx
0x18000bab1  jz      short loc_18000BABB
0x18000bab3  mov     r8d, eax
0x18000bab6  jmp     loc_18000BA15
0x18000babb  not     r8d
0x18000babe  mov     dword ptr [r9+10h], 0
0x18000bac6  and     r8d, 1
0x18000baca  mov     [r9], r8d
0x18000bacd  pop     rdi
0x18000bace  pop     rsi
0x18000bacf  pop     rbx
0x18000bad0  retn
```
