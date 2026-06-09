# PrxDllUnregisterServer

- ea: `0x180006b20`
- end: `0x180006b50`
- name: `PrxDllUnregisterServer`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001f9b0`
- `0x1800211b4`

## callees

- `0x180006b20`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180006b49`

## pseudocode

```c
HRESULT PrxDllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  return NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x180006b20  mov     rax, cs:aProxyFileList
0x180006b27  mov     rcx, [rax+8]
0x180006b2b  mov     rax, [rcx]
0x180006b2e  test    rax, rax
0x180006b31  jz      short loc_180006B38
0x180006b33  mov     r8, [rax]
0x180006b36  jmp     short loc_180006B3B
0x180006b38  xor     r8d, r8d
0x180006b3b  mov     rcx, cs:hProxyDll
0x180006b42  lea     rdx, aProxyFileList
0x180006b49  jmp     cs:__imp_NdrDllUnregisterProxy
```
