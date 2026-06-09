# wil_details_FeatureReporting_IncrementOpportunityInCache

- ea: `0x1800122f0`
- end: `0x1800123ba`
- name: `wil_details_FeatureReporting_IncrementOpportunityInCache`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001249c`

## callees

- `0x1800122f0`

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
0x1800122f0  push    rbx
0x1800122f2  push    rsi
0x1800122f3  push    rdi
0x1800122f4  mov     r8d, [rcx]
0x1800122f7  lea     r10, [r9+8]
0x1800122fb  xor     ebx, ebx
0x1800122fd  mov     r11d, edx
0x180012300  cmp     edx, 5
0x180012303  mov     rdi, rcx
0x180012306  mov     esi, 1
0x18001230b  setz    bl
0x18001230e  mov     eax, r8d
0x180012311  mov     dword ptr [r9+4], 0
0x180012319  or      eax, esi
0x18001231b  mov     ecx, eax
0x18001231d  shr     ecx, 16h
0x180012320  and     ecx, esi
0x180012322  cmp     ecx, ebx
0x180012324  jz      short loc_180012363
0x180012326  mov     edx, eax
0x180012328  shr     edx, 0Fh
0x18001232b  and     edx, 7Fh
0x18001232e  jbe     short loc_18001234B
0x180012330  cmp     r11d, esi
0x180012333  mov     [r9+4], edx
0x180012337  mov     ecx, 5
0x18001233c  lea     r10, [r9+8]
0x180012340  cmovnz  ecx, esi
0x180012343  and     eax, 0FFC07FFFh
0x180012348  mov     [r10], ecx
0x18001234b  xor     edx, edx
0x18001234d  mov     ecx, 400000h
0x180012352  cmp     r11d, 5
0x180012356  cmovz   edx, ecx
0x180012359  mov     ecx, eax
0x18001235b  btr     ecx, 16h
0x18001235f  mov     eax, edx
0x180012361  or      eax, ecx
0x180012363  mov     ecx, eax
0x180012365  shr     ecx, 0Fh
0x180012368  and     ecx, 7Fh
0x18001236b  lea     edx, [rcx+1]
0x18001236e  cmp     edx, 7Fh
0x180012371  ja      short loc_18001237D
0x180012373  cmp     edx, ecx
0x180012375  jb      short loc_18001237D
0x180012377  lea     r10, [r9+8]
0x18001237b  jmp     short loc_180012386
0x18001237d  mov     edx, esi
0x18001237f  mov     [r10], r11d
0x180012382  mov     [r9+4], ecx
0x180012386  shl     edx, 0Fh
0x180012389  xor     edx, eax
0x18001238b  and     edx, 3F8000h
0x180012391  xor     edx, eax
0x180012393  mov     eax, r8d
0x180012396  lock cmpxchg [rdi], edx
0x18001239a  jz      short loc_1800123A4
0x18001239c  mov     r8d, eax
0x18001239f  jmp     loc_18001230E
0x1800123a4  not     r8d
0x1800123a7  mov     dword ptr [r9+10h], 0
0x1800123af  and     r8d, esi
0x1800123b2  mov     [r9], r8d
0x1800123b5  pop     rdi
0x1800123b6  pop     rsi
0x1800123b7  pop     rbx
0x1800123b8  retn
```
