# _o_malloc_0

- ea: `0x180001d0a`
- end: `0x180001d10`
- name: `_o_malloc_0`
- size: `6`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180001d0a`

## pseudocode

```c
// attributes: thunk
void *__cdecl o_malloc_0(size_t Size)
{
  return malloc(Size);
}

```

## disassembly

```asm
0x180001d0a  jmp     cs:__imp_malloc
```
