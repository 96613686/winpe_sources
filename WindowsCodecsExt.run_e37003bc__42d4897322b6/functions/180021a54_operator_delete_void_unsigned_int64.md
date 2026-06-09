# operator delete(void *,unsigned __int64)

- ea: `0x180021a54`
- end: `0x180021a59`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `43`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008870`
- `0x180008e50`
- `0x180009760`
- `0x18000b42c`
- `0x18000b4d8`
- `0x18000b514`
- `0x18000fe70`
- `0x180010260`
- `0x180011230`
- `0x1800114a0`
- `0x1800124f0`
- `0x180012cd0`
- `0x1800183f8`
- `0x180018fa0`
- `0x180022880`
- `0x180022dd0`
- `0x180023430`
- `0x180023fd0`
- `0x180024010`
- `0x180024050`
- `0x180024dd0`
- `0x18002ae80`
- `0x18002b100`
- `0x18002b500`
- `0x18002b540`
- `0x18002bdf0`
- `0x18002c4c0`
- `0x18002c9c0`
- `0x18002ca00`
- `0x18002ca40`
- `0x18002d9d0`
- `0x18002dd30`
- `0x18002dd70`
- `0x18002ddb0`
- `0x18002ddf0`
- `0x18002de30`
- `0x18002eb70`
- `0x18002ebb0`
- `0x18002ee80`
- `0x18002eec0`
- `0x18002fa90`
- `0x18002fcd0`
- `0x180030f00`

## callees

- `0x180021628`

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
0x180021a54  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
