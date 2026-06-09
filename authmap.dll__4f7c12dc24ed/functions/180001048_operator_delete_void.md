# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001a10`
- `0x180001bf0`
- `0x180001c20`
- `0x180001c50`
- `0x180001cb0`
- `0x1800033e0`
- `0x180003470`
- `0x180003520`
- `0x18000357c`
- `0x180003f3c`
- `0x1800041f0`
- `0x180004ec0`

## callees

- `0x180001526`

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
