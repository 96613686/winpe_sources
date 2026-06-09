# operator delete(void *,std::nothrow_t const &)

- ea: `0x18000d2c4`
- end: `0x18000d2c9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `35`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005fc0`
- `0x1800069b0`
- `0x1800071c0`
- `0x180007248`
- `0x18000760c`
- `0x18000a6a0`
- `0x18000bdec`
- `0x18000c17c`
- `0x18000e550`
- `0x18000e590`
- `0x180010bc0`
- `0x180010bf0`
- `0x180011ca0`
- `0x180011cd0`
- `0x180011d10`
- `0x180011d50`
- `0x180017920`
- `0x180017950`
- `0x180018490`
- `0x1800184d0`
- `0x180019ba4`
- `0x18001d7b4`
- `0x18001d8b0`
- `0x18001d8e0`
- `0x18001d920`
- `0x18001d960`
- `0x18001d990`
- `0x18001d9d0`
- `0x18001da10`
- `0x1800230d8`
- `0x180025210`
- `0x180025814`
- `0x180025a53`
- `0x18002632b`
- `0x1800263b5`

## callees

- `0x18000d778`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18000d2c4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
