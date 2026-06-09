# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x1800513c1`
- end: `0x1800513c7`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `25`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800037b0`
- `0x180005230`
- `0x18000d130`
- `0x18000d8b0`
- `0x180017220`
- `0x180019900`
- `0x18001c480`
- `0x18001d800`
- `0x180022580`
- `0x180022a40`
- `0x180022db0`
- `0x180023120`
- `0x180036660`
- `0x18003a380`
- `0x180040d10`
- `0x180044eb0`
- `0x180045ee0`
- `0x180046310`
- `0x180046f80`
- `0x180047350`
- `0x1800476c0`
- `0x1800486b0`
- `0x18004abf0`
- `0x18004aea0`
- `0x18004b400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800513c1`

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
0x1800513c1  jmp     cs:__imp_CoTaskMemAlloc
```
