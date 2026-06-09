# DllUnregisterServer

- ea: `0x180018dc0`
- end: `0x180018dc7`
- name: `DllUnregisterServer`
- size: `7`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180025658`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  return AMovieDllRegisterServer2(0);
}

```

## disassembly

```asm
0x180018dc0  xor     ecx, ecx
0x180018dc2  jmp     AMovieDllRegisterServer2
```
