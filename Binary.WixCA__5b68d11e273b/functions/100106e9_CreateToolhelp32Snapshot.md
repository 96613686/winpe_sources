# CreateToolhelp32Snapshot

- ea: `0x100106e9`
- end: `0x100106ef`
- name: `CreateToolhelp32Snapshot`
- size: `6`
- prototype: `HANDLE __stdcall(DWORD dwFlags, DWORD th32ProcessID)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1000b2d8`

## import_xrefs

- `KERNEL32!CreateToolhelp32Snapshot` at `0x100106e9`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall CreateToolhelp32Snapshot(DWORD dwFlags, DWORD th32ProcessID)
{
  return __imp_CreateToolhelp32Snapshot(dwFlags, th32ProcessID);
}

```

## disassembly

```asm
0x100106e9  jmp     ds:__imp_CreateToolhelp32Snapshot
```
