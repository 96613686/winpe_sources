# BuildPath

- ea: `0x180017fdc`
- end: `0x180017fe9`
- name: `BuildPath`
- size: `13`
- prototype: `LPWSTR __fastcall(WCHAR *, __int64, const WCHAR *, const WCHAR *)`
- caller_count: `5`
- callee_count: `0`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800151d8`
- `0x180015d34`
- `0x180016094`
- `0x180016ad0`
- `0x180016c0c`

## import_xrefs

- `SHLWAPI!PathCombineW` at `0x180017fe2`

## pseudocode

```c
LPWSTR __fastcall BuildPath(WCHAR *a1, __int64 a2, const WCHAR *a3, const WCHAR *a4)
{
  return PathCombineW(a1, a3, a4);
}

```

## disassembly

```asm
0x180017fdc  mov     rdx, r8
0x180017fdf  mov     r8, r9
0x180017fe2  jmp     cs:__imp_PathCombineW
```
