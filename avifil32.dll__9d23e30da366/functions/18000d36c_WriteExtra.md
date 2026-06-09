# WriteExtra

- ea: `0x18000d36c`
- end: `0x18000d472`
- name: `WriteExtra`
- size: `262`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061d0`
- `0x18000c8c0`
- `0x18000c970`

## callees

- `0x18000d36c`
- `0x180017365`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000d3e7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000d3e7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000d3cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000d3cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000d407`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000d407`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d3c3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d3d5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d3c3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d3d5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000d3fe`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000d3fe`

## pseudocode

```c
__int64 __fastcall WriteExtra(__int64 a1, int a2, const void *a3, int a4)
{
  __int64 v8; // rdi
  LPCVOID v9; // rcx
  unsigned __int64 v10; // rax
  SIZE_T v11; // rsi
  HGLOBAL v12; // rax
  HGLOBAL v13; // rax
  HGLOBAL v14; // rax
  char *v15; // rax
  char *v16; // rsi
  int v18; // eax

  if ( a4 < 0 || *(int *)(a1 + 8) < 0 )
    return 2147762280LL;
  v8 = (unsigned int)(a4 + 8);
  if ( (unsigned int)v8 < a4 )
    return 2147942934LL;
  v9 = *(LPCVOID *)a1;
  if ( v9 )
  {
    v10 = *(int *)(a1 + 8);
    v11 = v10 + v8;
    if ( v10 + v8 >= v10 )
    {
      v12 = GlobalHandle(v9);
      GlobalUnlock(v12);
      v13 = GlobalHandle(*(LPCVOID *)a1);
      v14 = GlobalReAlloc(v13, v11, 0x2002u);
      goto LABEL_8;
    }
    return 2147942934LL;
  }
  *(_DWORD *)(a1 + 8) = 0;
  v14 = GlobalAlloc(0x2002u, (unsigned int)v8);
LABEL_8:
  v15 = (char *)GlobalLock(v14);
  v16 = v15;
  if ( !v15 )
    return 2147762279LL;
  *(_DWORD *)&v15[*(int *)(a1 + 8)] = a2;
  *(_DWORD *)&v15[*(int *)(a1 + 8) + 4] = a4;
  memmove_0(&v15[*(int *)(a1 + 8) + 8], a3, v8 - 8);
  *(_QWORD *)a1 = v16;
  v18 = v8 + 1;
  if ( (v8 & 1) == 0 )
    v18 = v8;
  *(_DWORD *)(a1 + 8) += v18;
  return 0;
}

```

## disassembly

```asm
0x18000d36c  push    rbx
0x18000d36e  push    rbp
0x18000d36f  push    rsi
0x18000d370  push    rdi
0x18000d371  push    r12
0x18000d373  push    r14
0x18000d375  push    r15
0x18000d377  sub     rsp, 20h
0x18000d37b  mov     ebp, r9d
0x18000d37e  mov     r15, r8
0x18000d381  mov     r12d, edx
0x18000d384  mov     rbx, rcx
0x18000d387  test    r9d, r9d
0x18000d38a  js      loc_18000D45E
0x18000d390  cmp     dword ptr [rcx+8], 0
0x18000d394  jl      loc_18000D45E
0x18000d39a  lea     edi, [r9+8]
0x18000d39e  cmp     edi, r9d
0x18000d3a1  jb      loc_18000D457
0x18000d3a7  mov     rcx, [rcx]; pMem
0x18000d3aa  mov     r14d, edi
0x18000d3ad  test    rcx, rcx
0x18000d3b0  jz      short loc_18000D3EF
0x18000d3b2  movsxd  rax, dword ptr [rbx+8]
0x18000d3b6  lea     rsi, [rax+rdi]
0x18000d3ba  cmp     rsi, rax
0x18000d3bd  jb      loc_18000D457
0x18000d3c3  call    cs:__imp_GlobalHandle
0x18000d3c9  mov     rcx, rax; hMem
0x18000d3cc  call    cs:__imp_GlobalUnlock
0x18000d3d2  mov     rcx, [rbx]; pMem
0x18000d3d5  call    cs:__imp_GlobalHandle
0x18000d3db  mov     r8d, 2002h; uFlags
0x18000d3e1  mov     rdx, rsi; dwBytes
0x18000d3e4  mov     rcx, rax; hMem
0x18000d3e7  call    cs:__imp_GlobalReAlloc
0x18000d3ed  jmp     short loc_18000D404
0x18000d3ef  mov     rdx, r14; dwBytes
0x18000d3f2  mov     dword ptr [rbx+8], 0
0x18000d3f9  mov     ecx, 2002h; uFlags
0x18000d3fe  call    cs:__imp_GlobalAlloc
0x18000d404  mov     rcx, rax; hMem
0x18000d407  call    cs:__imp_GlobalLock
0x18000d40d  mov     rsi, rax
0x18000d410  test    rax, rax
0x18000d413  jnz     short loc_18000D41C
0x18000d415  mov     eax, 80044067h
0x18000d41a  jmp     short loc_18000D463
0x18000d41c  movsxd  rax, dword ptr [rbx+8]
0x18000d420  lea     r8, [rdi-8]; Size
0x18000d424  mov     rdx, r15; Src
0x18000d427  mov     [rax+rsi], r12d
0x18000d42b  movsxd  rax, dword ptr [rbx+8]
0x18000d42f  mov     [rax+rsi+4], ebp
0x18000d433  movsxd  rcx, dword ptr [rbx+8]
0x18000d437  add     rcx, 8
0x18000d43b  add     rcx, rsi; void *
0x18000d43e  call    memmove_0
0x18000d443  test    dil, 1
0x18000d447  mov     [rbx], rsi
0x18000d44a  lea     eax, [rdi+1]
0x18000d44d  cmovz   eax, edi
0x18000d450  add     [rbx+8], eax
0x18000d453  xor     eax, eax
0x18000d455  jmp     short loc_18000D463
0x18000d457  mov     eax, 80070216h
0x18000d45c  jmp     short loc_18000D463
0x18000d45e  mov     eax, 80044068h
0x18000d463  add     rsp, 20h
0x18000d467  pop     r15
0x18000d469  pop     r14
0x18000d46b  pop     r12
0x18000d46d  pop     rdi
0x18000d46e  pop     rsi
0x18000d46f  pop     rbp
0x18000d470  pop     rbx
0x18000d471  retn
```
