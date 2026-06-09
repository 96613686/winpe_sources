# GetProcessHeap

- ea: `0x180017b91`
- end: `0x180017b97`
- name: `GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a04c`
- `0x18000a28c`
- `0x18000f15c`
- `0x18000f3c0`
- `0x18001e287`
- `0x18001e376`
- `0x18001e465`
- `0x18001e9ef`
- `0x18001ede4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017b91`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall GetProcessHeap()
{
  return __imp_GetProcessHeap();
}

```

## disassembly

```asm
0x180017b91  jmp     cs:__imp_GetProcessHeap
```
