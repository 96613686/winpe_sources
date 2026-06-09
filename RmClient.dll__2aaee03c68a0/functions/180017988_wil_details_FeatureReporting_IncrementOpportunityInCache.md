# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x180017988`
- end: `0x180017a51`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800085d4`
- `0x180008760`

## callees

- `0x180017988`

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
0x180017988  push    rbx
0x18001798a  push    rsi
0x18001798b  push    rdi
0x18001798c  mov     r8d, [rcx]
0x18001798f  lea     r10, [r9+8]
0x180017993  xor     ebx, ebx
0x180017995  mov     r11d, edx
0x180017998  cmp     edx, 5
0x18001799b  mov     rdi, rcx
0x18001799e  mov     esi, 1
0x1800179a3  setz    bl
0x1800179a6  mov     eax, r8d
0x1800179a9  mov     dword ptr [r9+4], 0
0x1800179b1  or      eax, esi
0x1800179b3  mov     ecx, eax
0x1800179b5  shr     ecx, 16h
0x1800179b8  and     ecx, esi
0x1800179ba  cmp     ecx, ebx
0x1800179bc  jz      short loc_1800179FB
0x1800179be  mov     edx, eax
0x1800179c0  shr     edx, 0Fh
0x1800179c3  and     edx, 7Fh
0x1800179c6  jbe     short loc_1800179E3
0x1800179c8  cmp     r11d, esi
0x1800179cb  mov     [r9+4], edx
0x1800179cf  mov     ecx, 5
0x1800179d4  lea     r10, [r9+8]
0x1800179d8  cmovnz  ecx, esi
0x1800179db  and     eax, 0FFC07FFFh
0x1800179e0  mov     [r10], ecx
0x1800179e3  xor     edx, edx
0x1800179e5  mov     ecx, 400000h
0x1800179ea  cmp     r11d, 5
0x1800179ee  cmovz   edx, ecx
0x1800179f1  mov     ecx, eax
0x1800179f3  btr     ecx, 16h
0x1800179f7  mov     eax, edx
0x1800179f9  or      eax, ecx
0x1800179fb  mov     ecx, eax
0x1800179fd  shr     ecx, 0Fh
0x180017a00  and     ecx, 7Fh
0x180017a03  lea     edx, [rcx+1]
0x180017a06  cmp     edx, 7Fh
0x180017a09  ja      short loc_180017A15
0x180017a0b  cmp     edx, ecx
0x180017a0d  jb      short loc_180017A15
0x180017a0f  lea     r10, [r9+8]
0x180017a13  jmp     short loc_180017A1E
0x180017a15  mov     edx, esi
0x180017a17  mov     [r10], r11d
0x180017a1a  mov     [r9+4], ecx
0x180017a1e  shl     edx, 0Fh
0x180017a21  xor     edx, eax
0x180017a23  and     edx, 3F8000h
0x180017a29  xor     edx, eax
0x180017a2b  mov     eax, r8d
0x180017a2e  lock cmpxchg [rdi], edx
0x180017a32  jz      short loc_180017A3C
0x180017a34  mov     r8d, eax
0x180017a37  jmp     loc_1800179A6
0x180017a3c  not     r8d
0x180017a3f  mov     dword ptr [r9+10h], 0
0x180017a47  and     r8d, esi
0x180017a4a  mov     [r9], r8d
0x180017a4d  pop     rdi
0x180017a4e  pop     rsi
0x180017a4f  pop     rbx
0x180017a50  retn
```
