# operator delete(void *,unsigned __int64)

- ea: `0x180002054`
- end: `0x180002059`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `82`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003190`
- `0x1800031d0`
- `0x1800054a4`
- `0x18000559c`
- `0x18000591c`
- `0x180005b60`
- `0x180005b90`
- `0x180005bd0`
- `0x180005c10`
- `0x1800074ec`
- `0x180007840`
- `0x1800078ec`
- `0x180007ab0`
- `0x180007af0`
- `0x180009860`
- `0x180009c2c`
- `0x180009c88`
- `0x180009d00`
- `0x180009d60`
- `0x18000a0e8`
- `0x18000b184`
- `0x18000b2f4`
- `0x18000cfc8`
- `0x18000d06c`
- `0x18000d090`
- `0x18000d140`
- `0x18000d250`
- `0x18000d2d0`
- `0x18000d360`
- `0x18000d3a0`
- `0x18000d3e0`
- `0x18000da44`
- `0x18000dbd0`
- `0x18000e350`
- `0x18000e450`
- `0x18000ee58`
- `0x18000fc10`
- `0x18000fce8`
- `0x18000fd1c`
- `0x18000fed0`
- `0x18000fef4`
- `0x18000ff40`
- `0x180010450`
- `0x1800104c0`
- `0x180010530`
- `0x180010580`
- `0x1800105c0`
- `0x180010600`
- `0x180010640`
- `0x180010680`

## callees

- `0x1800020f4`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002054  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
