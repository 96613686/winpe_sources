# memset

- ea: `0x1400089fa`
- end: `0x140008a00`
- name: `memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140005028`
- `0x140005214`
- `0x140005b00`
- `0x140006668`
- `0x140006b54`
- `0x140008538`
- `0x140008684`

## import_xrefs

- `VCRUNTIME140!memset` at `0x1400089fa`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  return __imp_memset(a1, Val, Size);
}

```

## disassembly

```asm
0x1400089fa  jmp     cs:__imp_memset
```
