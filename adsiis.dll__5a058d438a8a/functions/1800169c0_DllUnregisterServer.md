# DllUnregisterServer

- ea: `0x1800169c0`
- end: `0x1800169cc`
- name: `DllUnregisterServer`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001d4e0`

## string_xrefs

- `0x1800169c0`: `RemoveComponent`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const unsigned __int16 *v0; // rcx

  return CallRegisterComponent(v0, "RemoveComponent");
}

```

## disassembly

```asm
0x1800169c0  lea     rdx, aRemovecomponen; "RemoveComponent"
0x1800169c7  jmp     ?CallRegisterComponent@@YAJPEBGPEAD@Z; CallRegisterComponent(ushort const *,char *)
```
