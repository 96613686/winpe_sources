# AdmDllCanUnloadNow

- ea: `0x180001c10`
- end: `0x180001c1e`
- name: `AdmDllCanUnloadNow`
- size: `14`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180001c17`

## pseudocode

```c
HRESULT __stdcall AdmDllCanUnloadNow()
{
  return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x180001c10  lea     rcx, gPFactory
0x180001c17  jmp     cs:__imp_NdrDllCanUnloadNow
```
