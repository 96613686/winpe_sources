# memmove

- ea: `0x14005b85c`
- end: `0x14005b862`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `33`
- callee_count: `0`
- tags: ``

## callers

- `0x140004248`
- `0x140006dcc`
- `0x140008110`
- `0x1400083f0`
- `0x140009314`
- `0x14000d4f0`
- `0x14000d580`
- `0x14001e810`
- `0x14002021c`
- `0x140026ea0`
- `0x14002802c`
- `0x14002d59c`
- `0x14002feec`
- `0x1400305cc`
- `0x140034070`
- `0x140034dc0`
- `0x1400353d0`
- `0x1400362dc`
- `0x1400364dc`
- `0x1400378e0`
- `0x140037f2c`
- `0x14003827c`
- `0x14003adc8`
- `0x140044c60`
- `0x140046700`
- `0x140046c00`
- `0x140047860`
- `0x140048f28`
- `0x14004c8e8`
- `0x14004d5fc`
- `0x14004db60`
- `0x14004e860`
- `0x14004f8e0`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x14005b85c`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x14005b85c  jmp     cs:__imp_memmove
```
