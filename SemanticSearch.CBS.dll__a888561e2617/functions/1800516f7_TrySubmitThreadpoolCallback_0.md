# TrySubmitThreadpoolCallback_0

- ea: `0x1800516f7`
- end: `0x1800516fd`
- name: `TrySubmitThreadpoolCallback_0`
- size: `6`
- prototype: `BOOL __stdcall(PTP_SIMPLE_CALLBACK pfns, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180014840`
- `0x18002fd20`

## import_xrefs

- `KERNEL32!TrySubmitThreadpoolCallback` at `0x1800516f7`

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
0x1800516f7  jmp     cs:__imp_TrySubmitThreadpoolCallback
```
