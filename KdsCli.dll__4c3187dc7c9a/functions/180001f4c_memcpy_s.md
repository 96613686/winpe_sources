# memcpy_s

- ea: `0x180001f4c`
- end: `0x180001f52`
- name: `memcpy_s`
- size: `6`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c740`
- `0x18000cd04`
- `0x18000d284`
- `0x180012e3c`
- `0x1800138b8`
- `0x180014418`
- `0x1800145a8`
- `0x180014c04`
- `0x180015728`
- `0x180015bf8`
- `0x1800164dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_memcpy_s` at `0x180001f4c`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl memcpy_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  return __imp_memcpy_s(Destination, DestinationSize, Source, SourceSize);
}

```

## disassembly

```asm
0x180001f4c  jmp     cs:__imp_memcpy_s
```
