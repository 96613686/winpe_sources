# operator delete(void *,unsigned __int64)

- ea: `0x180002ce0`
- end: `0x180002ce5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006720`
- `0x180006790`
- `0x180007510`
- `0x180007614`
- `0x1800076cc`
- `0x180007714`
- `0x180007aa0`
- `0x180007ad0`
- `0x180007b10`
- `0x180007c88`
- `0x180007f18`
- `0x18000d5b0`
- `0x18000dc0c`
- `0x18000dd84`
- `0x18000eb3c`
- `0x18000f814`
- `0x18000fef4`
- `0x18000ff2c`
- `0x1800106a8`

## callees

- `0x18000315c`

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
0x180002ce0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
