# DisableThreadLibraryCalls_0

- ea: `0x180002312`
- end: `0x180002318`
- name: `DisableThreadLibraryCalls_0`
- size: `6`
- prototype: `BOOL __stdcall(HMODULE hLibModule)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x180002312`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall DisableThreadLibraryCalls_0(HMODULE hLibModule)
{
  return DisableThreadLibraryCalls(hLibModule);
}

```

## disassembly

```asm
0x180002312  jmp     cs:__imp_DisableThreadLibraryCalls
```
