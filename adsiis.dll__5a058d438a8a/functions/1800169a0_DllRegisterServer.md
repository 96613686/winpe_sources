# DllRegisterServer

- ea: `0x1800169a0`
- end: `0x1800169ac`
- name: `DllRegisterServer`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001d4e0`

## string_xrefs

- `0x1800169a0`: `InstallComponent`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const unsigned __int16 *v0; // rcx

  return CallRegisterComponent(v0, "InstallComponent");
}

```

## disassembly

```asm
0x1800169a0  lea     rdx, aInstallcompone; "InstallComponent"
0x1800169a7  jmp     ?CallRegisterComponent@@YAJPEBGPEAD@Z; CallRegisterComponent(ushort const *,char *)
```
