# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x140004e00`
- end: `0x140004eca`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004fac`

## callees

- `0x140004e00`

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
0x140004e00  push    rbx
0x140004e02  push    rsi
0x140004e03  push    rdi
0x140004e04  mov     r8d, [rcx]
0x140004e07  lea     r10, [r9+8]
0x140004e0b  xor     ebx, ebx
0x140004e0d  mov     r11d, edx
0x140004e10  cmp     edx, 5
0x140004e13  mov     rdi, rcx
0x140004e16  mov     esi, 1
0x140004e1b  setz    bl
0x140004e1e  mov     eax, r8d
0x140004e21  mov     dword ptr [r9+4], 0
0x140004e29  or      eax, esi
0x140004e2b  mov     ecx, eax
0x140004e2d  shr     ecx, 16h
0x140004e30  and     ecx, esi
0x140004e32  cmp     ecx, ebx
0x140004e34  jz      short loc_140004E73
0x140004e36  mov     edx, eax
0x140004e38  shr     edx, 0Fh
0x140004e3b  and     edx, 7Fh
0x140004e3e  jbe     short loc_140004E5B
0x140004e40  cmp     r11d, esi
0x140004e43  mov     [r9+4], edx
0x140004e47  mov     ecx, 5
0x140004e4c  lea     r10, [r9+8]
0x140004e50  cmovnz  ecx, esi
0x140004e53  and     eax, 0FFC07FFFh
0x140004e58  mov     [r10], ecx
0x140004e5b  xor     edx, edx
0x140004e5d  mov     ecx, 400000h
0x140004e62  cmp     r11d, 5
0x140004e66  cmovz   edx, ecx
0x140004e69  mov     ecx, eax
0x140004e6b  btr     ecx, 16h
0x140004e6f  mov     eax, edx
0x140004e71  or      eax, ecx
0x140004e73  mov     ecx, eax
0x140004e75  shr     ecx, 0Fh
0x140004e78  and     ecx, 7Fh
0x140004e7b  lea     edx, [rcx+1]
0x140004e7e  cmp     edx, 7Fh
0x140004e81  ja      short loc_140004E8D
0x140004e83  cmp     edx, ecx
0x140004e85  jb      short loc_140004E8D
0x140004e87  lea     r10, [r9+8]
0x140004e8b  jmp     short loc_140004E96
0x140004e8d  mov     edx, esi
0x140004e8f  mov     [r10], r11d
0x140004e92  mov     [r9+4], ecx
0x140004e96  shl     edx, 0Fh
0x140004e99  xor     edx, eax
0x140004e9b  and     edx, 3F8000h
0x140004ea1  xor     edx, eax
0x140004ea3  mov     eax, r8d
0x140004ea6  lock cmpxchg [rdi], edx
0x140004eaa  jz      short loc_140004EB4
0x140004eac  mov     r8d, eax
0x140004eaf  jmp     loc_140004E1E
0x140004eb4  not     r8d
0x140004eb7  mov     dword ptr [r9+10h], 0
0x140004ebf  and     r8d, esi
0x140004ec2  mov     [r9], r8d
0x140004ec5  pop     rdi
0x140004ec6  pop     rsi
0x140004ec7  pop     rbx
0x140004ec8  retn
```
