# operator delete(void *)

- ea: `0x1800019b0`
- end: `0x1800019b5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `21`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800019bc`
- `0x180005410`
- `0x180005470`
- `0x1800054d0`
- `0x180005510`
- `0x180005550`
- `0x1800055d0`
- `0x180005650`
- `0x180005690`
- `0x180006ca0`
- `0x180008680`
- `0x1800087c8`
- `0x180009ac0`
- `0x18000bf70`
- `0x18000c33c`
- `0x18000f748`
- `0x18000f858`
- `0x18000f95c`
- `0x18000fce0`
- `0x18000ff38`
- `0x180010830`

## callees

- `0x180001fb9`

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
0x1800019b0  jmp     free_0
```
