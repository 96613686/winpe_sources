# SHGetKnownFolderPath

- ea: `0x1400440c6`
- end: `0x1400440cc`
- name: `SHGetKnownFolderPath`
- size: `6`
- prototype: `HRESULT __stdcall(const KNOWNFOLDERID *const rfid, DWORD dwFlags, HANDLE hToken, PWSTR *ppszPath)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14002eb38`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x1400440c6`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall SHGetKnownFolderPath(const KNOWNFOLDERID *const rfid, DWORD dwFlags, HANDLE hToken, PWSTR *ppszPath)
{
  return __imp_SHGetKnownFolderPath(rfid, dwFlags, hToken, ppszPath);
}

```

## disassembly

```asm
0x1400440c6  jmp     cs:__imp_SHGetKnownFolderPath
```
