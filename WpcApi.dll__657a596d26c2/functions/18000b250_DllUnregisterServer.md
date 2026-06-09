# DllUnregisterServer

- ea: `0x18000b250`
- end: `0x18000b26c`
- name: `DllUnregisterServer`
- size: `28`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18000b265`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  return NdrDllUnregisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &CLSID_PSFactoryBuffer);
}

```

## disassembly

```asm
0x18000b250  mov     rcx, cs:hProxyDll
0x18000b257  lea     r8, CLSID_PSFactoryBuffer
0x18000b25e  lea     rdx, aProxyFileList
0x18000b265  jmp     cs:__imp_NdrDllUnregisterProxy
```
