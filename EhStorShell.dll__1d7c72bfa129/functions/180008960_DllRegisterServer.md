# DllRegisterServer

- ea: `0x180008960`
- end: `0x180008963`
- name: `DllRegisterServer`
- size: `3`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  return 0;
}

```

## disassembly

```asm
0x180008960  xor     eax, eax; DllRegisterServer
0x180008962  retn
```
