# DllRegisterServer

- ea: `0x180002770`
- end: `0x180002776`
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
  return -2147024846;
}

```

## disassembly

```asm
0x180002770  mov     eax, 80070032h; DllRegisterServer
0x180002775  retn
```
