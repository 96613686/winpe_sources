# operator delete(void *,unsigned __int64)

- ea: `0x1800033f4`
- end: `0x1800033f9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004cb8`
- `0x180004ff0`
- `0x180005060`
- `0x1800050d0`
- `0x180005110`
- `0x180005150`
- `0x180005568`
- `0x180006040`
- `0x180006590`
- `0x180008d10`
- `0x18000a44c`
- `0x18000a5e0`
- `0x18000a640`
- `0x18000a6c0`
- `0x18000a720`
- `0x18000b7fc`
- `0x18000b870`
- `0x18000b8a0`
- `0x18000b8d0`
- `0x18000b930`
- `0x18000b990`
- `0x18000b9c0`
- `0x18000c5cc`
- `0x18000c944`
- `0x18000d0b4`
- `0x18001148c`
- `0x1800115c4`

## callees

- `0x1800033b4`

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
0x1800033f4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
