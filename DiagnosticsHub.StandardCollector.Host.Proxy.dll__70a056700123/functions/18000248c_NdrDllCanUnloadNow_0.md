# NdrDllCanUnloadNow_0

- ea: `0x18000248c`
- end: `0x180002492`
- name: `NdrDllCanUnloadNow_0`
- size: `6`
- prototype: `HRESULT __stdcall(CStdPSFactoryBuffer *pPSFactoryBuffer)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000248c`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall NdrDllCanUnloadNow_0(CStdPSFactoryBuffer *pPSFactoryBuffer)
{
  return NdrDllCanUnloadNow(pPSFactoryBuffer);
}

```

## disassembly

```asm
0x18000248c  jmp     cs:__imp_NdrDllCanUnloadNow
```
