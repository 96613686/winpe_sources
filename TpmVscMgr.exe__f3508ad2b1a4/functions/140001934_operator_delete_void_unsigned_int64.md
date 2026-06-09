# operator delete(void *,unsigned __int64)

- ea: `0x140001934`
- end: `0x140001939`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `43`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400031d0`
- `0x140003210`
- `0x14000641c`
- `0x140006af4`
- `0x140006c84`
- `0x140006f18`
- `0x140008028`
- `0x14000804c`
- `0x140008070`
- `0x1400080e0`
- `0x140008278`
- `0x140008308`
- `0x140008380`
- `0x140008530`
- `0x14000859c`
- `0x140008688`
- `0x140008784`
- `0x140009654`
- `0x1400096ac`
- `0x140009710`
- `0x140009760`
- `0x140009dd8`
- `0x140009e94`
- `0x14000a388`
- `0x14000a75c`
- `0x14000a8a0`
- `0x14000a92c`
- `0x14000b08c`
- `0x14000b16c`
- `0x14000b248`
- `0x14000b5b4`
- `0x14000b8e0`
- `0x14000d5a8`
- `0x14000dab8`
- `0x14000db60`
- `0x14000dcf8`
- `0x14000e510`
- `0x14000e62c`
- `0x14000e870`
- `0x14000e9f8`
- `0x14000ef04`
- `0x14000f54c`
- `0x1400110b8`

## callees

- `0x140002240`

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
0x140001934  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
