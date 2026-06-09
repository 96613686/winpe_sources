# WINRT_IMPL_CoTaskMemAlloc

- ea: `0x18022ae90`
- end: `0x18022ae96`
- name: `WINRT_IMPL_CoTaskMemAlloc`
- size: `6`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `23`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003010`
- `0x1800102d0`
- `0x18001ff00`
- `0x180020750`
- `0x180020f40`
- `0x180021350`
- `0x180021770`
- `0x180021ca0`
- `0x180022920`
- `0x18002e5d0`
- `0x180037be0`
- `0x18004cd20`
- `0x180055e40`
- `0x180058700`
- `0x180058d30`
- `0x18005bc40`
- `0x18005c1c0`
- `0x18005d8f0`
- `0x18005dc40`
- `0x18005e760`
- `0x18006bf80`
- `0x18006c110`
- `0x1800706d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18022ae90`

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
0x18022ae90  jmp     cs:__imp_CoTaskMemAlloc
```
