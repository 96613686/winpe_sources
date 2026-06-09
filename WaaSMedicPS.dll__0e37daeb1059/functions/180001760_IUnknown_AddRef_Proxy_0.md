# IUnknown_AddRef_Proxy_0

- ea: `0x180001760`
- end: `0x180001766`
- name: `IUnknown_AddRef_Proxy_0`
- size: `6`
- prototype: `ULONG __stdcall(IUnknown *This)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!IUnknown_AddRef_Proxy` at `0x180001760`

## pseudocode

```c
// attributes: thunk
ULONG __stdcall IUnknown_AddRef_Proxy_0(IUnknown *This)
{
  return IUnknown_AddRef_Proxy(This);
}

```

## disassembly

```asm
0x180001760  jmp     cs:__imp_IUnknown_AddRef_Proxy
```
