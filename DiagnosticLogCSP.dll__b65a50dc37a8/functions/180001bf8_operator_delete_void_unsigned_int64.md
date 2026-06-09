# operator delete(void *,unsigned __int64)

- ea: `0x180001bf8`
- end: `0x180001bfd`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `131`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002adc`
- `0x1800030f0`
- `0x180003270`
- `0x1800032b0`
- `0x1800041a0`
- `0x1800041e0`
- `0x180006d90`
- `0x180007580`
- `0x180008800`
- `0x180009330`
- `0x1800098d0`
- `0x18000a704`
- `0x18000a924`
- `0x18000aa10`
- `0x18000c0c4`
- `0x18000c120`
- `0x18000c1d0`
- `0x18000d8f8`
- `0x18000dfd8`
- `0x18000f478`
- `0x18001045c`
- `0x1800104b8`
- `0x1800106c8`
- `0x1800106ec`
- `0x18001075c`
- `0x1800107d0`
- `0x180010ed4`
- `0x180012afc`
- `0x180012fbc`
- `0x180014104`
- `0x1800141c0`
- `0x180015c1c`
- `0x180015de0`
- `0x180015e20`
- `0x180015e80`
- `0x180015ec0`
- `0x180017244`
- `0x180018d90`
- `0x18001d5b0`
- `0x18001de4c`
- `0x18001e074`
- `0x18001e324`
- `0x18001e380`
- `0x18001e41c`
- `0x18001e478`
- `0x18001e594`
- `0x18001e70c`
- `0x18001e810`
- `0x18001f32c`
- `0x18001fb30`

## callees

- `0x1800021e0`

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
0x180001bf8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
