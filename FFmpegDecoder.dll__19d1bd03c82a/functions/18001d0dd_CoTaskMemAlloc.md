# CoTaskMemAlloc

- ea: `0x18001d0dd`
- end: `0x18001d0e3`
- name: `CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800094c0`
- `0x180009d8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d0dd`

## pseudocode

```c
// attributes: thunk
LPVOID __stdcall CoTaskMemAlloc(SIZE_T cb)
{
  return __imp_CoTaskMemAlloc(cb);
}

```

## disassembly

```asm
0x18001d0dd  jmp     cs:__imp_CoTaskMemAlloc
```
