# SMALL_STRU::Copy(ushort const *)

- ea: `0x180002cf0`
- end: `0x180002d8b`
- name: `?Copy@SMALL_STRU@@QEAAJPEBG@Z`
- size: `155`
- prototype: `int(SMALL_STRU *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800032f0`
- `0x180004744`

## callees

- `0x180002cf0`
- `0x180008c13`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002d5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002d5b`

## pseudocode

```c
__int64 __fastcall SMALL_STRU::Copy(unsigned __int16 **this, unsigned __int16 *a2)
{
  unsigned __int16 *v5; // rdi
  __int64 v6; // rax
  SIZE_T v7; // rbp
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  unsigned __int16 *v10; // rax

  if ( !a2 )
    return 2147942487LL;
  v5 = *this;
  if ( a2 != *this )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = 2 * v6 + 2;
    if ( v5 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      *this = 0;
    }
    v9 = GetProcessHeap();
    v10 = (unsigned __int16 *)HeapAlloc(v9, 8u, v7);
    *this = v10;
    if ( !v10 )
      return 2147942408LL;
    memcpy_0(v10, a2, v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180002cf0  push    rbx
0x180002cf2  push    rbp
0x180002cf3  push    rsi
0x180002cf4  push    rdi
0x180002cf5  push    r14
0x180002cf7  sub     rsp, 20h
0x180002cfb  xor     r14d, r14d
0x180002cfe  mov     rbx, rdx
0x180002d01  mov     rsi, rcx
0x180002d04  test    rdx, rdx
0x180002d07  jnz     short loc_180002D10
0x180002d09  mov     eax, 80070057h
0x180002d0e  jmp     short loc_180002D80
0x180002d10  mov     rdi, [rcx]
0x180002d13  cmp     rbx, rdi
0x180002d16  jz      short loc_180002D7E
0x180002d18  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002d1c  inc     rax
0x180002d1f  cmp     [rdx+rax*2], r14w
0x180002d24  jnz     short loc_180002D1C
0x180002d26  lea     rbp, ds:2[rax*2]
0x180002d2e  test    rdi, rdi
0x180002d31  jz      short loc_180002D4A
0x180002d33  call    cs:__imp_GetProcessHeap
0x180002d39  mov     r8, rdi; lpMem
0x180002d3c  xor     edx, edx; dwFlags
0x180002d3e  mov     rcx, rax; hHeap
0x180002d41  call    cs:__imp_HeapFree
0x180002d47  mov     [rsi], r14
0x180002d4a  call    cs:__imp_GetProcessHeap
0x180002d50  mov     r8, rbp; dwBytes
0x180002d53  mov     edx, 8; dwFlags
0x180002d58  mov     rcx, rax; hHeap
0x180002d5b  call    cs:__imp_HeapAlloc
0x180002d61  mov     [rsi], rax
0x180002d64  test    rax, rax
0x180002d67  jnz     short loc_180002D70
0x180002d69  mov     eax, 80070008h
0x180002d6e  jmp     short loc_180002D80
0x180002d70  mov     r8, rbp; Size
0x180002d73  mov     rdx, rbx; Src
0x180002d76  mov     rcx, rax; void *
0x180002d79  call    memcpy_0
0x180002d7e  xor     eax, eax
0x180002d80  add     rsp, 20h
0x180002d84  pop     r14
0x180002d86  pop     rdi
0x180002d87  pop     rsi
0x180002d88  pop     rbp
0x180002d89  pop     rbx
0x180002d8a  retn
```
