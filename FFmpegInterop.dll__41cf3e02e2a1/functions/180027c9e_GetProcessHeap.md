# GetProcessHeap

- ea: `0x180027c9e`
- end: `0x180027ca4`
- name: `GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x1800042c8`
- `0x180004420`
- `0x180004580`
- `0x1800080d4`
- `0x18000a9f0`
- `0x18000b12c`
- `0x18001180c`
- `0x18001eb40`
- `0x18001ec14`
- `0x18001fb00`
- `0x180020558`
- `0x180020a28`
- `0x180020c20`
- `0x18002dee0`
- `0x18002dfcf`
- `0x18002e0be`
- `0x1800303f6`
- `0x1800307eb`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027c9e`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall GetProcessHeap()
{
  return __imp_GetProcessHeap();
}

```

## disassembly

```asm
0x180027c9e  jmp     cs:__imp_GetProcessHeap
```
