# operator delete(void *)

- ea: `0x1400076bc`
- end: `0x1400076c3`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140008f38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400076bc`

## pseudocode

```c
// attributes: thunk
void __stdcall operator delete(LPVOID pv)
{
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x1400076bc  jmp     cs:__imp_CoTaskMemFree
```
