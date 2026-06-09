# memmove_0

- ea: `0x1800034fe`
- end: `0x180003504`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `37`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a0e4`
- `0x18000df00`
- `0x18000df90`
- `0x180011704`
- `0x180015470`
- `0x18001c188`
- `0x18001faa0`
- `0x18001fea8`
- `0x180021c5c`
- `0x180025d44`
- `0x180026268`
- `0x1800279cc`
- `0x18002a5f4`
- `0x18002a6ac`
- `0x18002c484`
- `0x18002c900`
- `0x18002d764`
- `0x18002fe0c`
- `0x18002ffc0`
- `0x180030354`
- `0x18003b124`
- `0x1800420cc`
- `0x180042da8`
- `0x180043138`
- `0x18004acc0`
- `0x18004bd04`
- `0x18004bf70`
- `0x18004de9c`
- `0x18004dff4`
- `0x18004e224`
- `0x18004e2f0`
- `0x18004f890`
- `0x1800594f0`
- `0x18005f540`
- `0x180060808`
- `0x18009b4ec`
- `0x1800bc63c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800034fe`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x1800034fe  jmp     cs:__imp_memmove
```
