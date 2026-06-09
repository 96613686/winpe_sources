# __Platform_CoTaskMemAlloc

- ea: `0x1400039f2`
- end: `0x1400039f8`
- name: `__Platform_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000bf34`
- `0x140029a28`
- `0x140029ad8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400039f2`

## pseudocode

```c
// attributes: thunk
LPVOID __stdcall _Platform_CoTaskMemAlloc(SIZE_T cb)
{
  return CoTaskMemAlloc(cb);
}

```

## disassembly

```asm
0x1400039f2  jmp     cs:__imp_CoTaskMemAlloc
```
