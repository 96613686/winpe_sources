# operator delete(void *)

- ea: `0x180001064`
- end: `0x180001069`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `15`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001b50`
- `0x180001b80`
- `0x180001be0`
- `0x180001cc0`
- `0x180001e00`
- `0x180003200`
- `0x18000445c`
- `0x180004650`
- `0x180004b1c`
- `0x180004c44`
- `0x180005a64`
- `0x180005e2c`
- `0x180005f10`
- `0x180005fc8`
- `0x180006078`

## callees

- `0x180001536`

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
0x180001064  jmp     free_0
```
