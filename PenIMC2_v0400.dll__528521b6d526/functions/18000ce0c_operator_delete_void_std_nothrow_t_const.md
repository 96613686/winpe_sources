# operator delete(void *,std::nothrow_t const &)

- ea: `0x18000ce0c`
- end: `0x18000ce11`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `46`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001390`
- `0x180001e00`
- `0x180002140`
- `0x1800021b0`
- `0x180002264`
- `0x1800022d4`
- `0x180002300`
- `0x180002fa0`
- `0x180002ffc`
- `0x180003370`
- `0x180003480`
- `0x18000358c`
- `0x1800035a8`
- `0x1800057c0`
- `0x180006210`
- `0x1800066dc`
- `0x180006b10`
- `0x1800071ec`
- `0x180007558`
- `0x18000953c`
- `0x18000a030`
- `0x18000a954`
- `0x18000aa8c`
- `0x18000ada8`
- `0x18000b098`
- `0x18000b39c`
- `0x18000b8bc`
- `0x18000bf50`
- `0x18000bf8c`
- `0x18000c110`
- `0x18000c800`
- `0x18000c860`
- `0x18000cbb8`
- `0x18000cde0`
- `0x18000dea0`
- `0x18000e51a`
- `0x18000e5ab`
- `0x18000ec5e`
- `0x18000ec7b`
- `0x18000ec98`
- `0x18000ecb8`
- `0x18000edb0`
- `0x18000edff`
- `0x18000eedc`
- `0x18000ef41`
- `0x18000ef7a`

## callees

- `0x18000cdd0`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18000ce0c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
