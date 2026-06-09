# memmove_s_0

- ea: `0x180001f1e`
- end: `0x180001f24`
- name: `memmove_s_0`
- size: `6`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001934`

## import_xrefs

- `msvcrt!memmove_s` at `0x180001f1e`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl memmove_s_0(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  return memmove_s(Destination, DestinationSize, Source, SourceSize);
}

```

## disassembly

```asm
0x180001f1e  jmp     cs:__imp_memmove_s
```
