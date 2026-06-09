# std::_Wrap_alloc<std::allocator<uchar>>::deallocate(uchar *,unsigned __int64)

- ea: `0x18000a64c`
- end: `0x18000a656`
- name: `?deallocate@?$_Wrap_alloc@V?$allocator@E@std@@@std@@QEAAXPEAE_K@Z`
- size: `10`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180011a18`
- `0x180011b3d`
- `0x180011b63`
- `0x180011c97`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a64f`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(__int64 a1, void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x18000a64c  mov     rcx, rdx
0x18000a64f  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
