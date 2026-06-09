# DllCanUnloadNow

- ea: `0x180001790`
- end: `0x18000179e`
- name: `DllCanUnloadNow`
- size: `14`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180001797`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x180001790  lea     rcx, gPFactory
0x180001797  jmp     cs:__imp_NdrDllCanUnloadNow
```
