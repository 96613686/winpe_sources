# malloc

- ea: `0x18002cb60`
- end: `0x18002cb66`
- name: `malloc`
- size: `6`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c150`
- `0x180010cf8`
- `0x180010ea8`
- `0x1800152b1`
- `0x180018371`
- `0x18001c46a`
- `0x18001d52c`
- `0x180020c00`
- `0x1800227f0`
- `0x180024260`
- `0x1800251d0`
- `0x180025750`
- `0x180026630`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002cb60`

## pseudocode

```c
// attributes: thunk
void *__cdecl malloc(size_t Size)
{
  return __imp_malloc(Size);
}

```

## disassembly

```asm
0x18002cb60  jmp     cs:__imp_malloc
```
