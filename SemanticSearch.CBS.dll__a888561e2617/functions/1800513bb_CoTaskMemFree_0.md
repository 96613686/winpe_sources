# CoTaskMemFree_0

- ea: `0x1800513bb`
- end: `0x1800513c1`
- name: `CoTaskMemFree_0`
- size: `6`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `16`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003260`
- `0x180007800`
- `0x180007870`
- `0x1800078a0`
- `0x180007970`
- `0x180017220`
- `0x180017ed0`
- `0x1800285c0`
- `0x1800455b0`
- `0x180045d00`
- `0x180046d70`
- `0x180047e90`
- `0x180048280`
- `0x180048340`
- `0x18004abf0`
- `0x18004b400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800513bb`

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
0x1800513bb  jmp     cs:__imp_CoTaskMemFree
```
