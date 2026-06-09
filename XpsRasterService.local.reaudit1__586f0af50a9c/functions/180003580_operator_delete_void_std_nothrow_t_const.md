# operator delete(void *,std::nothrow_t const &)

- ea: `0x180003580`
- end: `0x180003585`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `117`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004180`
- `0x1800043f0`
- `0x180004440`
- `0x1800046b0`
- `0x180004940`
- `0x180004b20`
- `0x180004da0`
- `0x180004f80`
- `0x180005110`
- `0x1800055a0`
- `0x1800056f0`
- `0x180005970`
- `0x180005b80`
- `0x180005eb0`
- `0x180006140`
- `0x180006660`
- `0x180006940`
- `0x180006de0`
- `0x180007150`
- `0x180007720`
- `0x1800077f0`
- `0x180007ed0`
- `0x18000acd0`
- `0x18000ad40`
- `0x18000add0`
- `0x18000aee0`
- `0x18000afb0`
- `0x18000b210`
- `0x18000ba20`
- `0x18000e5f0`
- `0x18000e630`
- `0x1800132e0`
- `0x180014700`
- `0x180014870`
- `0x1800149f0`
- `0x180014a60`
- `0x180015630`
- `0x180016120`
- `0x1800161e0`
- `0x1800162a0`
- `0x180016ce0`
- `0x180017290`
- `0x180017840`
- `0x180017aa0`
- `0x180017b60`
- `0x1800413d0`
- `0x180044b50`
- `0x18004a120`
- `0x18004ff70`
- `0x18004ffb0`

## callees

- `0x180003574`

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
0x180003580  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
