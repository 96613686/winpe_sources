# DllCanUnloadNow

- ea: `0x180001050`
- end: `0x18000105e`
- name: `DllCanUnloadNow`
- size: `14`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180001057`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x180001050  lea     rcx, gPFactory
0x180001057  jmp     cs:__imp_NdrDllCanUnloadNow
```
