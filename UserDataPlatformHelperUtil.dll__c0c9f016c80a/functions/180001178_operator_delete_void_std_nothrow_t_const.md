# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001178`
- end: `0x18000117d`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002744`
- `0x180002860`
- `0x1800028c0`
- `0x180002cb0`
- `0x180002d98`
- `0x1800031bc`
- `0x1800032b0`
- `0x1800035f8`
- `0x180003890`
- `0x18000504c`
- `0x180005df8`
- `0x1800061e0`
- `0x180007344`
- `0x180008dc0`

## callees

- `0x180001160`

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
0x180001178  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
