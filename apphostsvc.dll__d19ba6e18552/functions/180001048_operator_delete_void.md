# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001dc0`
- `0x180001f10`
- `0x180002348`
- `0x1800024ac`
- `0x180002780`
- `0x180002b4c`
- `0x180003e30`
- `0x1800056d0`
- `0x180006494`
- `0x180006e70`
- `0x180007878`
- `0x180007afc`
- `0x180007c5c`
- `0x180007f40`
- `0x180008430`
- `0x1800086b8`
- `0x18000885c`
- `0x180009090`
- `0x180009216`
- `0x180009228`
- `0x180009278`
- `0x1800092ae`

## callees

- `0x18000162c`

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
0x180001048  jmp     free_0
```
