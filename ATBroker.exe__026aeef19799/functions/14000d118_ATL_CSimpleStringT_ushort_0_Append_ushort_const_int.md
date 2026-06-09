# ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)

- ea: `0x14000d118`
- end: `0x14000d1b2`
- name: `?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d1b8`
- `0x14000d334`
- `0x14000d3a0`
- `0x14000ddb0`
- `0x14000e538`
- `0x14000ea38`
- `0x14000ee8c`
- `0x1400116c4`
- `0x140015830`

## callees

- `0x140004890`
- `0x140007560`
- `0x14000d118`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000d179`
- `msvcrt!memcpy_s` at `0x14000d179`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::Append(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rsi
  const void *v5; // rbp
  unsigned __int64 v7; // r14
  int v8; // ebx
  __int64 v9; // rax
  __int64 result; // rax

  v3 = a3;
  v4 = ((__int64)a2 - *a1) >> 1;
  v5 = a2;
  v7 = *(unsigned int *)(*a1 - 16);
  v8 = v7 + a3;
  if ( (((*(_DWORD *)(*a1 - 12) - (v7 + a3)) | (1 - *(_DWORD *)(*a1 - 8))) & 0x80000000) != 0LL )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v8);
  v9 = *a1;
  if ( v4 <= v7 )
    v5 = (const void *)(v9 + 2 * v4);
  memcpy_s((void *const)(v9 + 2 * v7), 2 * v3, v5, 2 * v3);
  if ( v8 < 0 || v8 > *(_DWORD *)(*a1 - 12) )
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16) = v8;
  result = 0;
  *(_WORD *)(*a1 + 2LL * v8) = 0;
  return result;
}

```

## disassembly

```asm
0x14000d118  push    rbx
0x14000d11a  push    rbp
0x14000d11b  push    rsi
0x14000d11c  push    rdi
0x14000d11d  push    r14
0x14000d11f  push    r15
0x14000d121  sub     rsp, 28h
0x14000d125  mov     rax, [rcx]
0x14000d128  mov     rsi, rdx
0x14000d12b  sub     rsi, rax
0x14000d12e  movsxd  r15, r8d
0x14000d131  mov     r9d, 1
0x14000d137  sar     rsi, 1
0x14000d13a  mov     rbp, rdx
0x14000d13d  mov     rdi, rcx
0x14000d140  mov     r14d, [rax-10h]
0x14000d144  sub     r9d, [rax-8]
0x14000d148  mov     eax, [rax-0Ch]
0x14000d14b  lea     ebx, [r14+r15]
0x14000d14f  sub     eax, ebx
0x14000d151  or      r9d, eax
0x14000d154  jge     short loc_14000D15D
0x14000d156  mov     edx, ebx
0x14000d158  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000d15d  mov     rax, [rdi]
0x14000d160  cmp     rsi, r14
0x14000d163  ja      short loc_14000D169
0x14000d165  lea     rbp, [rax+rsi*2]
0x14000d169  mov     rdx, r15
0x14000d16c  lea     rcx, [rax+r14*2]; Destination
0x14000d170  add     rdx, rdx; DestinationSize
0x14000d173  mov     r8, rbp; Source
0x14000d176  mov     r9, rdx; SourceSize
0x14000d179  call    cs:__imp_memcpy_s
0x14000d17f  test    ebx, ebx
0x14000d181  js      short loc_14000D1A7
0x14000d183  mov     rax, [rdi]
0x14000d186  cmp     ebx, [rax-0Ch]
0x14000d189  jg      short loc_14000D1A7
0x14000d18b  mov     [rax-10h], ebx
0x14000d18e  xor     eax, eax
0x14000d190  mov     rcx, [rdi]
0x14000d193  movsxd  rdx, ebx
0x14000d196  mov     [rcx+rdx*2], ax
0x14000d19a  add     rsp, 28h
0x14000d19e  pop     r15
0x14000d1a0  pop     r14
0x14000d1a2  pop     rdi
0x14000d1a3  pop     rsi
0x14000d1a4  pop     rbp
0x14000d1a5  pop     rbx
0x14000d1a6  retn
0x14000d1a7  mov     ecx, 80070057h; int
0x14000d1ac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
