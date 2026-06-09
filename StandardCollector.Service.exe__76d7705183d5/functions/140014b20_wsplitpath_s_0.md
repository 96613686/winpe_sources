# _wsplitpath_s_0

- ea: `0x140014b20`
- end: `0x140014b26`
- name: `_wsplitpath_s_0`
- size: `6`
- prototype: `errno_t __cdecl(const wchar_t *FullPath, wchar_t *Drive, size_t DriveCount, wchar_t *Dir, size_t DirCount, wchar_t *Filename, size_t FilenameCount, wchar_t *Ext, size_t ExtCount)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400134ac`

## import_xrefs

- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x140014b20`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl wsplitpath_s_0(
        const wchar_t *FullPath,
        wchar_t *Drive,
        size_t DriveCount,
        wchar_t *Dir,
        size_t DirCount,
        wchar_t *Filename,
        size_t FilenameCount,
        wchar_t *Ext,
        size_t ExtCount)
{
  return _wsplitpath_s(FullPath, Drive, DriveCount, Dir, DirCount, Filename, FilenameCount, Ext, ExtCount);
}

```

## disassembly

```asm
0x140014b20  jmp     cs:__imp__wsplitpath_s
```
