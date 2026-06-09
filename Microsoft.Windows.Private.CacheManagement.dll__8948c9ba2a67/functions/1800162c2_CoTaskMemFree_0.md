# CoTaskMemFree_0

- ea: `0x1800162c2`
- end: `0x1800162c8`
- name: `CoTaskMemFree_0`
- size: `6`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006750`
- `0x1800099a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800162c2`

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
0x1800162c2  jmp     cs:__imp_CoTaskMemFree
```
