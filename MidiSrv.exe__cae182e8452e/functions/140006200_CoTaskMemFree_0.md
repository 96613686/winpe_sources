# CoTaskMemFree_0

- ea: `0x140006200`
- end: `0x140006206`
- name: `CoTaskMemFree_0`
- size: `6`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `6`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x140028bac`
- `0x14002efd0`
- `0x14002f77c`
- `0x140030250`
- `0x1400318c8`
- `0x140051dfc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006200`

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
0x140006200  jmp     cs:__imp_CoTaskMemFree
```
