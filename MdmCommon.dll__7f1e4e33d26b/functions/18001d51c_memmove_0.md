# memmove_0

- ea: `0x18001d51c`
- end: `0x18001d522`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030c0`
- `0x1800040c0`
- `0x180005070`
- `0x180005e50`
- `0x1800062a4`
- `0x18000c38c`
- `0x18000e97c`
- `0x18000ef34`
- `0x180010b0c`
- `0x180010f90`
- `0x180011cf4`
- `0x1800124fc`
- `0x1800142c8`
- `0x180014e2c`
- `0x180015bf0`
- `0x180019e74`
- `0x18001a8d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18001d51c`

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
0x18001d51c  jmp     cs:__imp_memmove
```
