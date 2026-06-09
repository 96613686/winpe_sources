# operator delete(void *)

- ea: `0x180001124`
- end: `0x180001129`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ce0`
- `0x180001f30`
- `0x1800020f0`
- `0x180002170`
- `0x180002240`
- `0x1800022e0`
- `0x1800025f0`
- `0x180002850`
- `0x180002a3c`
- `0x180002c40`
- `0x180002e90`
- `0x180003090`
- `0x18000313c`
- `0x180003298`
- `0x18000333c`
- `0x18000340c`
- `0x180003538`
- `0x1800039d4`
- `0x180003f60`
- `0x1800043d0`
- `0x180004468`
- `0x1800050f0`
- `0x180007e44`
- `0x180007f80`

## callees

- `0x180001642`

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
0x180001124  jmp     free_0
```
