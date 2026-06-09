# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x180004724`
- end: `0x18000472a`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800152f0`
- `0x180015380`
- `0x180015410`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004724`

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
0x180004724  jmp     cs:__imp_CoTaskMemAlloc
```
