# operator delete(void *)

- ea: `0x180001300`
- end: `0x180001305`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `42`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001880`
- `0x180002760`
- `0x180002bf0`
- `0x180002ea0`
- `0x180003250`
- `0x18000341c`
- `0x180004fb0`
- `0x180005560`
- `0x1800056a0`
- `0x180006210`
- `0x180006300`
- `0x180006ca0`
- `0x180006e80`
- `0x1800073b4`
- `0x180007d7c`
- `0x180008890`
- `0x1800089b0`
- `0x180008aa0`
- `0x18000a088`
- `0x18000a288`
- `0x18000ccb0`
- `0x180010364`
- `0x180010d00`
- `0x180010d40`
- `0x18001135c`
- `0x18001161c`
- `0x1800118e0`
- `0x180012d89`
- `0x180012e0c`
- `0x180012e8f`
- `0x180012f2e`
- `0x18001307e`
- `0x1800130a2`
- `0x1800130b4`
- `0x1800130c6`
- `0x18001349a`
- `0x180013554`
- `0x1800139f5`
- `0x180013a73`
- `0x180013b24`
- `0x180014017`
- `0x1800143d7`

## callees

- `0x1800018e1`

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
0x180001300  jmp     free_0
```
