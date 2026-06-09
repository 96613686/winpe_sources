# IUnknown_Release_Proxy_0

- ea: `0x1800017f0`
- end: `0x1800017f6`
- name: `IUnknown_Release_Proxy_0`
- size: `6`
- prototype: `ULONG __stdcall(IUnknown *This)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!IUnknown_Release_Proxy` at `0x1800017f0`

## pseudocode

```c
// attributes: thunk
ULONG __stdcall IUnknown_Release_Proxy_0(IUnknown *This)
{
  return IUnknown_Release_Proxy(This);
}

```

## disassembly

```asm
0x1800017f0  jmp     cs:__imp_IUnknown_Release_Proxy
```
