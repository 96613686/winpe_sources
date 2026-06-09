# memcpy_0

- ea: `0x18000d6fb`
- end: `0x18000d701`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800023c0`
- `0x180002f50`
- `0x18000806c`
- `0x18000821c`

## import_xrefs

- `ntdll!memcpy` at `0x18000d6fb`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy_0(void *a1, const void *Src, size_t Size)
{
  return memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18000d6fb  jmp     cs:__imp_memcpy
```
