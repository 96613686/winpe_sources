# IsolationAwarePrivatezlybNQyVOeNelJ

- ea: `0x1800081f0`
- end: `0x1800081f7`
- name: `IsolationAwarePrivatezlybNQyVOeNelJ`
- size: `7`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180008200`
- `0x180009c18`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800081f0`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall IsolationAwarePrivatezlybNQyVOeNelJ(LPCWSTR lpLibFileName)
{
  return LoadLibraryW(lpLibFileName);
}

```

## disassembly

```asm
0x1800081f0  jmp     cs:__imp_LoadLibraryW
```
