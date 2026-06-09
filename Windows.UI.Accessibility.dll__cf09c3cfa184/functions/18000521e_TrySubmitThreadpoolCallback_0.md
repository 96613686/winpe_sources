# TrySubmitThreadpoolCallback_0

- ea: `0x18000521e`
- end: `0x180005224`
- name: `TrySubmitThreadpoolCallback_0`
- size: `6`
- prototype: `BOOL __stdcall(PTP_SIMPLE_CALLBACK pfns, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002494c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000521e`

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
0x18000521e  jmp     cs:__imp_TrySubmitThreadpoolCallback
```
