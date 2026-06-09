# _wmakepath_s_0

- ea: `0x140014b10`
- end: `0x140014b16`
- name: `_wmakepath_s_0`
- size: `6`
- prototype: `errno_t __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Drive, const wchar_t *Dir, const wchar_t *Filename, const wchar_t *Ext)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400134ac`

## import_xrefs

- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x140014b10`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl wmakepath_s_0(
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Drive,
        const wchar_t *Dir,
        const wchar_t *Filename,
        const wchar_t *Ext)
{
  return _wmakepath_s(Buffer, BufferCount, Drive, Dir, Filename, Ext);
}

```

## disassembly

```asm
0x140014b10  jmp     cs:__imp__wmakepath_s
```
