# DllRegisterServer

- ea: `0x18000b220`
- end: `0x18000b23c`
- name: `DllRegisterServer`
- size: `28`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18000b235`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  return NdrDllRegisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &CLSID_PSFactoryBuffer);
}

```

## disassembly

```asm
0x18000b220  mov     rcx, cs:hProxyDll
0x18000b227  lea     r8, CLSID_PSFactoryBuffer
0x18000b22e  lea     rdx, aProxyFileList
0x18000b235  jmp     cs:__imp_NdrDllRegisterProxy
```
