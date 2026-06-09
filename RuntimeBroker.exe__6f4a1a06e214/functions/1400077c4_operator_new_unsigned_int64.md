# operator new(unsigned __int64)

- ea: `0x1400077c4`
- end: `0x1400077cb`
- name: `??2@YAPEAX_K@Z`
- size: `7`
- prototype: `LPVOID __stdcall(SIZE_T cb)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008ca4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400077c4`

## pseudocode

```c
// attributes: thunk
LPVOID __stdcall operator new(SIZE_T cb)
{
  return CoTaskMemAlloc(cb);
}

```

## disassembly

```asm
0x1400077c4  jmp     cs:__imp_CoTaskMemAlloc
```
