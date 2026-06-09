# operator delete(void *)

- ea: `0x18001c370`
- end: `0x18001c375`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `34`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005b2c`
- `0x180006004`
- `0x1800063c0`
- `0x180007910`
- `0x180009150`
- `0x180009190`
- `0x180009da0`
- `0x18000a310`
- `0x18000dca0`
- `0x180010dc4`
- `0x180012190`
- `0x180017b44`
- `0x18001cc70`
- `0x180023168`
- `0x180024300`
- `0x180024330`
- `0x18002438c`
- `0x1800243c0`
- `0x180024400`
- `0x180029600`
- `0x180029e74`
- `0x18002bc10`
- `0x18002c810`
- `0x18002d4f0`
- `0x18002ed70`
- `0x1800319e4`
- `0x180031d10`
- `0x180033760`
- `0x1800339d0`
- `0x180033bf0`
- `0x180033f00`
- `0x180034452`
- `0x180035b87`
- `0x180035d58`

## callees

- `0x18001ccbe`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x18001c370  jmp     free_0
```
