# DllRegisterServer

- ea: `0x180003c30`
- end: `0x180003c3c`
- name: `DllRegisterServer`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043f8`

## string_xrefs

- `0x180003c30`: `DllRegisterServer`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rcx

  return UndockedModuleForwarder::InvokeExportMethod<long,>(v0);
}

```

## disassembly

```asm
0x180003c30  lea     rdx, aDllregisterser_0; "DllRegisterServer"
0x180003c37  jmp     ??$InvokeExportMethod@J$$V@UndockedModuleForwarder@@QEAAJPEBD@Z; UndockedModuleForwarder::InvokeExportMethod<long,>(char const *)
```
