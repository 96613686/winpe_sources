# memmove_0

- ea: `0x1400121ec`
- end: `0x1400121f2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a728`
- `0x14000da08`
- `0x14000df7c`
- `0x14000e348`
- `0x14000f8f0`
- `0x1400100bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1400121ec`

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
0x1400121ec  jmp     cs:__imp_memmove
```
