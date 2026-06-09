# memmove_0

- ea: `0x18002bb0d`
- end: `0x18002bb13`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x180007d00`
- `0x18000fb2c`
- `0x180010fd0`
- `0x18001ba64`
- `0x18001c2fc`
- `0x18001c334`
- `0x180028dac`
- `0x18002915c`
- `0x18002f14c`
- `0x18002f1ac`
- `0x180033a58`
- `0x180034a14`
- `0x180034af4`
- `0x180034bd4`
- `0x180034ee8`
- `0x18003caa8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18002bb0d`

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
0x18002bb0d  jmp     cs:__imp_memmove
```
