# TrySubmitThreadpoolCallback_0

- ea: `0x18001c741`
- end: `0x18001c747`
- name: `TrySubmitThreadpoolCallback_0`
- size: `6`
- prototype: `BOOL __stdcall(PTP_SIMPLE_CALLBACK pfns, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800128a0`

## import_xrefs

- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18001c741`

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
0x18001c741  jmp     cs:__imp_TrySubmitThreadpoolCallback
```
