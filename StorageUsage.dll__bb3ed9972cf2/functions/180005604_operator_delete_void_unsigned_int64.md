# operator delete(void *,unsigned __int64)

- ea: `0x180005604`
- end: `0x180005609`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `14`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000eb18`
- `0x180010ac0`
- `0x180010af0`
- `0x180010b30`
- `0x180010b60`
- `0x180010bb0`
- `0x180010bf0`
- `0x180010c30`
- `0x180010c70`
- `0x180010cb0`
- `0x1800210e4`
- `0x18002425c`
- `0x1800268f0`
- `0x18002bb49`

## callees

- `0x1800055f8`

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
0x180005604  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
