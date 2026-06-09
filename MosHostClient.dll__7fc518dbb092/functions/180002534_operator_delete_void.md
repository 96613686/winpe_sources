# operator delete(void *)

- ea: `0x180002534`
- end: `0x180002539`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `29`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002920`
- `0x1800029b4`
- `0x1800040f0`
- `0x180004150`
- `0x180004190`
- `0x180007a00`
- `0x180007a30`
- `0x180007fc0`
- `0x180008ebc`
- `0x180008fd8`
- `0x1800090c0`
- `0x18000914c`
- `0x180009234`
- `0x180009294`
- `0x180009304`
- `0x180009798`
- `0x18000c138`
- `0x18000c270`
- `0x18000cb14`
- `0x18000cb70`
- `0x18000cbe4`
- `0x18000cc3c`
- `0x18000cd98`
- `0x18000dfac`
- `0x18000e19c`
- `0x18000e2c0`
- `0x18000e5f8`
- `0x18000e908`
- `0x18000f6f4`

## callees

- `0x180002fa0`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180002534  jmp     free
```
