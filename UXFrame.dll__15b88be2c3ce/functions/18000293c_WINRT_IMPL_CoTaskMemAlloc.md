# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x18000293c`
- end: `0x180002942`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e164`
- `0x1800310a4`
- `0x180031140`
- `0x180035180`
- `0x180045908`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000293c`

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
0x18000293c  jmp     cs:__imp_CoTaskMemAlloc
```
