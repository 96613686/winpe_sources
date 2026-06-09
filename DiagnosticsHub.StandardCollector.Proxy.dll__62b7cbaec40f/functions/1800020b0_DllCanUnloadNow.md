# DllCanUnloadNow

- ea: `0x1800020b0`
- end: `0x1800020c6`
- name: `DllCanUnloadNow`
- size: `22`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800020bb`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800020bb`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x1800020b0  sub     rsp, 28h
0x1800020b4  lea     rcx, gPFactory; pPSFactoryBuffer
0x1800020bb  call    cs:__imp_NdrDllCanUnloadNow
0x1800020c1  add     rsp, 28h
0x1800020c5  retn
```
