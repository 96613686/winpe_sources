# memcpy_0

- ea: `0x180004acc`
- end: `0x180004ad2`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180001440`
- `0x180001520`
- `0x180001670`
- `0x1800017c0`
- `0x180002c80`
- `0x180002f10`
- `0x180003080`
- `0x180003470`
- `0x180003640`
- `0x1800037f0`
- `0x1800038a0`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x180004acc`

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
0x180004acc  jmp     cs:__imp_memcpy
```
