# CoTaskMemFree_0

- ea: `0x180005314`
- end: `0x18000531a`
- name: `CoTaskMemFree_0`
- size: `6`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003622c`
- `0x1800376c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005314`

## pseudocode

```c
// attributes: thunk
void __stdcall CoTaskMemFree_0(LPVOID pv)
{
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x180005314  jmp     cs:__imp_CoTaskMemFree
```
