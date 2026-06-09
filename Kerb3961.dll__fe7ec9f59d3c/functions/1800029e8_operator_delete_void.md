# operator delete(void *)

- ea: `0x1800029e8`
- end: `0x180002a37`
- name: `??3@YAXPEAX@Z`
- size: `79`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001d64`
- `0x180002740`
- `0x180002800`

## callees

- `0x1800029e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a1d`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180002a03`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180002a03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002a2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002a2b`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  HANDLE ProcessHeap; // rax
  SIZE_T v3; // rax
  _BYTE *i; // rcx
  HANDLE v5; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    v3 = HeapSize(ProcessHeap, 0, lpMem);
    for ( i = lpMem; v3; --v3 )
      *i++ = 0;
    v5 = GetProcessHeap();
    HeapFree(v5, 0, lpMem);
  }
}

```

## disassembly

```asm
0x1800029e8  test    rcx, rcx
0x1800029eb  jz      short locret_180002A36
0x1800029ed  push    rbx
0x1800029ee  sub     rsp, 20h
0x1800029f2  mov     rbx, rcx
0x1800029f5  call    cs:__imp_GetProcessHeap
0x1800029fb  mov     r8, rbx; lpMem
0x1800029fe  xor     edx, edx; dwFlags
0x180002a00  mov     rcx, rax; hHeap
0x180002a03  call    cs:__imp_HeapSize
0x180002a09  mov     rcx, rbx
0x180002a0c  test    rax, rax
0x180002a0f  jz      short loc_180002A1D
0x180002a11  mov     byte ptr [rcx], 0
0x180002a14  inc     rcx
0x180002a17  sub     rax, 1
0x180002a1b  jnz     short loc_180002A11
0x180002a1d  call    cs:__imp_GetProcessHeap
0x180002a23  mov     r8, rbx; lpMem
0x180002a26  xor     edx, edx; dwFlags
0x180002a28  mov     rcx, rax; hHeap
0x180002a2b  call    cs:__imp_HeapFree
0x180002a31  add     rsp, 20h
0x180002a35  pop     rbx
0x180002a36  retn
```
