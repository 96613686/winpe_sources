# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800029b4`
- end: `0x1800029b9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008ff4`
- `0x180009050`
- `0x1800090c0`
- `0x18000914c`
- `0x18000bbc4`
- `0x18000bd90`
- `0x18000bdb0`
- `0x18000c138`
- `0x18000cb14`
- `0x18000cb70`
- `0x18000cc3c`
- `0x18000dfac`
- `0x18000e19c`
- `0x1800113dd`

## callees

- `0x180002534`

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
0x1800029b4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
