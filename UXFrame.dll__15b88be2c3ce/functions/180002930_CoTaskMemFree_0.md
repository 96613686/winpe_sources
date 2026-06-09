# CoTaskMemFree_0

- ea: `0x180002930`
- end: `0x180002936`
- name: `CoTaskMemFree_0`
- size: `6`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `7`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f988`
- `0x180030b60`
- `0x180030be0`
- `0x1800325ac`
- `0x180035790`
- `0x180035810`
- `0x18004ef18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002930`

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
0x180002930  jmp     cs:__imp_CoTaskMemFree
```
