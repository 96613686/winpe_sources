# pMemFree

- ea: `0x18000eac0`
- end: `0x18000eaf5`
- name: `pMemFree`
- size: `53`
- prototype: `void __fastcall(LPVOID lpMem)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x18000400c`
- `0x180004344`
- `0x1800043d8`
- `0x180004e70`
- `0x180005d80`
- `0x1800069c0`
- `0x180007cd0`
- `0x180007d60`
- `0x1800087a0`
- `0x1800091a0`
- `0x1800098c0`
- `0x18000dc98`
- `0x18000e16c`
- `0x18000eafc`
- `0x18000ee14`
- `0x18000efb0`
- `0x180016304`
- `0x18001639c`
- `0x18001646c`
- `0x1800168c8`
- `0x180016a08`
- `0x180016d30`
- `0x180016f40`
- `0x180017280`
- `0x1800173a0`
- `0x1800177c8`

## callees

- `0x18000eac0`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000eaea`
- `KERNEL32!HeapFree` at `0x18000eaea`

## pseudocode

```c
void __fastcall pMemFree(LPVOID lpMem)
{
  if ( lpMem )
  {
    if ( pMemFreeUser )
      pMemFreeUser(lpMem);
    else
      HeapFree(hHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x18000eac0  sub     rsp, 28h
0x18000eac4  test    rcx, rcx
0x18000eac7  jz      short loc_18000EAF0
0x18000eac9  mov     rax, cs:?pMemFreeUser@@3P6AXPEAX@ZEA; void (*pMemFreeUser)(void *)
0x18000ead0  test    rax, rax
0x18000ead3  jz      short loc_18000EADE
0x18000ead5  add     rsp, 28h
0x18000ead9  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000eade  mov     r8, rcx; lpMem
0x18000eae1  xor     edx, edx; dwFlags
0x18000eae3  mov     rcx, cs:hHeap; hHeap
0x18000eaea  call    cs:__imp_HeapFree
0x18000eaf0  add     rsp, 28h
0x18000eaf4  retn
```
