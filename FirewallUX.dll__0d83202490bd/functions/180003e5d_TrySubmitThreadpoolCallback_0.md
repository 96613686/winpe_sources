# TrySubmitThreadpoolCallback_0

- ea: `0x180003e5d`
- end: `0x180003e63`
- name: `TrySubmitThreadpoolCallback_0`
- size: `6`
- prototype: `BOOL __stdcall(PTP_SIMPLE_CALLBACK pfns, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001baf4`
- `0x180022fd0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180003e5d`

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
0x180003e5d  jmp     cs:__imp_TrySubmitThreadpoolCallback
```
