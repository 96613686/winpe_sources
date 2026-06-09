# CoTaskMemFree_0

- ea: `0x18022aeae`
- end: `0x18022aeb4`
- name: `CoTaskMemFree_0`
- size: `6`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `15`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037be0`
- `0x180046760`
- `0x180055e40`
- `0x180058700`
- `0x180058d30`
- `0x180059490`
- `0x18005d210`
- `0x18005fd00`
- `0x18005fdd0`
- `0x180060080`
- `0x18006a6a0`
- `0x18006a710`
- `0x18006a7e0`
- `0x18006c5d0`
- `0x1800706d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18022aeae`

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
0x18022aeae  jmp     cs:__imp_CoTaskMemFree
```
