# CoTaskMemAlloc_0

- ea: `0x18000574c`
- end: `0x180005752`
- name: `CoTaskMemAlloc_0`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012250`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000574c`

## pseudocode

```c
// attributes: thunk
LPVOID __stdcall CoTaskMemAlloc_0(SIZE_T cb)
{
  return CoTaskMemAlloc(cb);
}

```

## disassembly

```asm
0x18000574c  jmp     cs:__imp_CoTaskMemAlloc
```
