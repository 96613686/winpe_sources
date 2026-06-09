# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x1800398a5`
- end: `0x1800398ab`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `4`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000c5b0`
- `0x18000d0c0`
- `0x1800183c0`
- `0x18002c440`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800398a5`

## pseudocode

```c
// attributes: thunk
LPVOID __stdcall WINRT_IMPL_CoTaskMemAlloc(SIZE_T cb)
{
  return CoTaskMemAlloc(cb);
}

```

## disassembly

```asm
0x1800398a5  jmp     cs:__imp_CoTaskMemAlloc
```
