# CoTaskMemFree_0

- ea: `0x180005f44`
- end: `0x180005f4a`
- name: `CoTaskMemFree_0`
- size: `6`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014bc4`
- `0x1800163a8`
- `0x1800553b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005f44`

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
0x180005f44  jmp     cs:__imp_CoTaskMemFree
```
