# std::allocator<uint>::deallocate(uint *,unsigned __int64)

- ea: `0x18000eb84`
- end: `0x18000eb8c`
- name: `?deallocate@?$allocator@I@std@@QEAAXPEAI_K@Z`
- size: `8`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002826a`
- `0x18002828a`
- `0x1800282df`
- `0x18002833b`
- `0x180028441`
- `0x180028461`
- `0x180028481`
- `0x1800284bd`
- `0x1800284dd`
- `0x180028658`
- `0x1800287f4`
- `0x180028bf7`
- `0x180028c51`
- `0x180028c71`
- `0x180028fe1`
- `0x180029065`
- `0x180029085`
- `0x1800290a5`
- `0x1800290c5`
- `0x18002919f`
- `0x1800291bf`
- `0x180029247`
- `0x180029484`
- `0x180029744`
- `0x1800297f0`
- `0x18002982c`

## callees

- `0x1800268f4`

## pseudocode

```c
void __fastcall std::allocator<unsigned int>::deallocate(__int64 a1, void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x18000eb84  mov     rcx, rdx; Block
0x18000eb87  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
