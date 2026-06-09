# DllRegisterServer

- ea: `0x180002640`
- end: `0x180002646`
- name: `DllRegisterServer`
- size: `6`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  return -2147467263;
}

```

## disassembly

```asm
0x180002640  mov     eax, 80004001h; DllRegisterServer
0x180002645  retn
```
