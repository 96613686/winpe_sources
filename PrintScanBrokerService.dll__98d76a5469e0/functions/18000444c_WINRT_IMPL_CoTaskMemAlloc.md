# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x18000444c`
- end: `0x180004452`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `9`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a630`
- `0x18000c0b0`
- `0x180013068`
- `0x1800130ec`
- `0x180013170`
- `0x1800131f4`
- `0x180013278`
- `0x180013334`
- `0x18001d228`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000444c`

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
0x18000444c  jmp     cs:__imp_CoTaskMemAlloc
```
