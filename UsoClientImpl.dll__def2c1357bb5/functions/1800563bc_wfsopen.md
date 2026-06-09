# _wfsopen

- ea: `0x1800563bc`
- end: `0x1800563c2`
- name: `_wfsopen`
- size: `6`
- prototype: `FILE *__cdecl(const wchar_t *FileName, const wchar_t *Mode, int ShFlag)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180052ab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x1800563bc`

## pseudocode

```c
// attributes: thunk
FILE *__cdecl wfsopen(const wchar_t *FileName, const wchar_t *Mode, int ShFlag)
{
  return _wfsopen(FileName, Mode, ShFlag);
}

```

## disassembly

```asm
0x1800563bc  jmp     cs:__imp__wfsopen
```
