# TrySubmitThreadpoolCallback_0

- ea: `0x1800020d9`
- end: `0x1800020df`
- name: `TrySubmitThreadpoolCallback_0`
- size: `6`
- prototype: `BOOL __stdcall(PTP_SIMPLE_CALLBACK pfns, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180009144`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800020d9`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall TrySubmitThreadpoolCallback_0(PTP_SIMPLE_CALLBACK pfns, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)
{
  return TrySubmitThreadpoolCallback(pfns, pv, pcbe);
}

```

## disassembly

```asm
0x1800020d9  jmp     cs:__imp_TrySubmitThreadpoolCallback
```
