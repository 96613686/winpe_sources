# MsiViewFetch

- ea: `0x10020f92`
- end: `0x10020f98`
- name: `MsiViewFetch`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hView, MSIHANDLE *phRecord)`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000e2ae`
- `0x1000e2ff`

## import_xrefs

- `msi!__imp_MsiViewFetch` at `0x10020f92`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiViewFetch(MSIHANDLE hView, MSIHANDLE *phRecord)
{
  return __imp_MsiViewFetch(hView, phRecord);
}

```

## disassembly

```asm
0x10020f92  jmp     ds:__imp_MsiViewFetch
```
