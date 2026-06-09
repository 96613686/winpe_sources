# operator delete(void *,unsigned __int64)

- ea: `0x180007380`
- end: `0x180007385`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `48`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000875c`
- `0x180009300`
- `0x180009340`
- `0x18000cae0`
- `0x18000cb20`
- `0x18000ed9c`
- `0x18000edd0`
- `0x1800153c4`
- `0x1800153f4`
- `0x180015424`
- `0x180015480`
- `0x1800154c0`
- `0x1800154f4`
- `0x180015530`
- `0x18001cc10`
- `0x18001cc90`
- `0x1800205f0`
- `0x180023ac0`
- `0x180023af4`
- `0x180023b30`
- `0x18002a640`
- `0x18002a67c`
- `0x18002a6c0`
- `0x18002a6fc`
- `0x18002a738`
- `0x18002d2d0`
- `0x18002e7f0`
- `0x18002e824`
- `0x18002f870`
- `0x180032c50`
- `0x180036ad0`
- `0x180036b10`
- `0x18003bc46`
- `0x18003bc80`
- `0x18003bf17`
- `0x18003c39f`
- `0x18003c477`
- `0x18003c4d4`
- `0x18003c6a1`
- `0x18003c802`
- `0x18003c85f`
- `0x18003c8ce`
- `0x18003c904`
- `0x18003d442`
- `0x18003d51e`
- `0x18003d637`
- `0x18003db9d`
- `0x18003dead`

## callees

- `0x180007374`

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
0x180007380  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
