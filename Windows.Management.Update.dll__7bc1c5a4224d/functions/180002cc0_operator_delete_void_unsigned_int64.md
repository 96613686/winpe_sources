# operator delete(void *,unsigned __int64)

- ea: `0x180002cc0`
- end: `0x180002cc5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `96`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003590`
- `0x180003730`
- `0x1800039c0`
- `0x180003aa0`
- `0x180003c30`
- `0x180003df0`
- `0x180003f60`
- `0x1800040f0`
- `0x180004260`
- `0x180004a40`
- `0x180004ce0`
- `0x180004f00`
- `0x180005420`
- `0x180005470`
- `0x1800054b0`
- `0x1800054f0`
- `0x180005540`
- `0x180005590`
- `0x1800056c0`
- `0x1800057a0`
- `0x1800067e0`
- `0x180006b10`
- `0x180007c70`
- `0x180007fa0`
- `0x1800080e0`
- `0x18000a030`
- `0x18000a070`
- `0x18000a0b0`
- `0x18000a110`
- `0x18000a150`
- `0x18000a1b0`
- `0x1800117a4`
- `0x180011c20`
- `0x180011c70`
- `0x180011cb0`
- `0x180011d00`
- `0x180011d40`
- `0x180011d80`
- `0x180011e00`
- `0x180011e40`
- `0x180011eb0`
- `0x180011ef0`
- `0x180011f30`
- `0x180011f80`
- `0x180011fc0`
- `0x180012000`
- `0x180012050`
- `0x1800148fc`
- `0x180014a00`
- `0x180014a80`

## callees

- `0x180003290`

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
0x180002cc0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
