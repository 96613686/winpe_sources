# CoTaskMemAlloc

- ea: `0x180027cda`
- end: `0x180027ce0`
- name: `CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008170`
- `0x180009ed0`
- `0x18000a3e0`
- `0x18000f2e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027cda`

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
0x180027cda  jmp     cs:__imp_CoTaskMemAlloc
```
