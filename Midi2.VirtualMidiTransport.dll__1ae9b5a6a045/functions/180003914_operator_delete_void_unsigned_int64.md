# operator delete(void *,unsigned __int64)

- ea: `0x180003914`
- end: `0x180003919`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `56`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000534c`
- `0x180005680`
- `0x1800056f0`
- `0x180005760`
- `0x1800057a0`
- `0x1800057e0`
- `0x180005bf8`
- `0x1800066d0`
- `0x180006c20`
- `0x1800093e0`
- `0x18000ac6c`
- `0x18000ae00`
- `0x18000ae60`
- `0x18000aee0`
- `0x18000af40`
- `0x18000bf6c`
- `0x18000c070`
- `0x18000c0a0`
- `0x18000c0d0`
- `0x18000c110`
- `0x18000cbfc`
- `0x18000cde0`
- `0x18000ce74`
- `0x18000cf6c`
- `0x18000d4a0`
- `0x18000d4f0`
- `0x18000d57c`
- `0x18000d748`
- `0x18000d7cc`
- `0x180012a44`
- `0x180012d10`
- `0x180012e20`
- `0x1800141e0`
- `0x180014308`
- `0x1800143b0`
- `0x180014570`
- `0x180014a10`
- `0x180014a60`
- `0x180018268`
- `0x180018300`
- `0x1800183e0`
- `0x180018460`
- `0x180018b70`
- `0x180018c74`
- `0x180019558`
- `0x18001a744`
- `0x18001a9b4`
- `0x18001aac0`
- `0x18001ab00`
- `0x18001ab60`

## callees

- `0x1800038d4`

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
0x180003914  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
