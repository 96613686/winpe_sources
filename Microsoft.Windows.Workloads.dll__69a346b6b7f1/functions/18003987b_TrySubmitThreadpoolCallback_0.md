# TrySubmitThreadpoolCallback_0

- ea: `0x18003987b`
- end: `0x180039881`
- name: `TrySubmitThreadpoolCallback_0`
- size: `6`
- prototype: `BOOL __stdcall(PTP_SIMPLE_CALLBACK pfns, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a290`
- `0x18001c360`

## import_xrefs

- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18003987b`

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
0x18003987b  jmp     cs:__imp_TrySubmitThreadpoolCallback
```
