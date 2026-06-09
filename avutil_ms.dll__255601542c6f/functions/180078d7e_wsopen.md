# _wsopen

- ea: `0x180078d7e`
- end: `0x180078d84`
- name: `_wsopen`
- size: `6`
- prototype: `int(const wchar_t *FileName, int OpenFlag, int ShareFlag, ...)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18003a558`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!_wsopen` at `0x180078d7e`

## pseudocode

```c
// attributes: thunk
int wsopen(const wchar_t *FileName, int OpenFlag, int ShareFlag, ...)
{
  return _wsopen(FileName, OpenFlag, ShareFlag);
}

```

## disassembly

```asm
0x180078d7e  jmp     cs:__imp__wsopen
```
