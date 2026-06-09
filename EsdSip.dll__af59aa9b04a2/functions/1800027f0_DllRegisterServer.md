# DllRegisterServer

- ea: `0x1800027f0`
- end: `0x1800027fc`
- name: `DllRegisterServer`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800028d0`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  return RegisterServer(&GUID_ESDSIP);
}

```

## disassembly

```asm
0x1800027f0  lea     rcx, GUID_ESDSIP
0x1800027f7  jmp     RegisterServer
```
