# CoTaskMemFree

- ea: `0x180005f5c`
- end: `0x180005f62`
- name: `CoTaskMemFree`
- size: `6`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001420c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f5c`

## pseudocode

```c
// attributes: thunk
void __stdcall CoTaskMemFree(LPVOID pv)
{
  __imp_CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x180005f5c  jmp     cs:__imp_CoTaskMemFree
```
