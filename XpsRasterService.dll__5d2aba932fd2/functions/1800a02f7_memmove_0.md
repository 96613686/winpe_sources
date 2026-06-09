# memmove_0

- ea: `0x1800a02f7`
- end: `0x1800a02fd`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180003fd0`
- `0x180004440`
- `0x180005510`
- `0x1800055a0`
- `0x180014770`
- `0x180014a60`
- `0x180015630`
- `0x1800a924c`
- `0x1800a9398`
- `0x1800a97d0`
- `0x1800b1a04`
- `0x1800b5b00`
- `0x1800b5b64`
- `0x1800b74f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800a02f7`

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
0x1800a02f7  jmp     cs:__imp_memmove
```
