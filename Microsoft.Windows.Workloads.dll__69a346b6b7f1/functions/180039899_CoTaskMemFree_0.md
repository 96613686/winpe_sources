# CoTaskMemFree_0

- ea: `0x180039899`
- end: `0x18003989f`
- name: `CoTaskMemFree_0`
- size: `6`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180008c60`
- `0x18000ade0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180039899`

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
0x180039899  jmp     cs:__imp_CoTaskMemFree
```
