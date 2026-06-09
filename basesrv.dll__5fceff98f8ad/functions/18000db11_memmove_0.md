# memmove_0

- ea: `0x18000db11`
- end: `0x18000db17`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x1800094cc`
- `0x18000a424`
- `0x18000abe0`
- `0x18000b500`
- `0x18000c2d0`

## import_xrefs

- `ntdll!memmove` at `0x18000db11`

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
0x18000db11  jmp     cs:__imp_memmove
```
