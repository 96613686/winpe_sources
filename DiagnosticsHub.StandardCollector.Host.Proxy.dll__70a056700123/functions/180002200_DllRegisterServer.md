# DllRegisterServer

- ea: `0x180002200`
- end: `0x180002282`
- name: `DllRegisterServer`
- size: `130`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002200`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180002277`
- `RPCRT4!NdrDllRegisterProxy` at `0x180002277`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  if ( *aProxyFileList->pStubVtblList )
    return NdrDllRegisterProxy(
             hProxyDll,
             (const ProxyFileInfo **)&aProxyFileList,
             **(const CLSID ***)aProxyFileList->pStubVtblList);
  else
    return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, 0);
}

```

## disassembly

```asm
0x180002200  sub     rsp, 38h
0x180002204  mov     eax, 8
0x180002209  imul    rax, 0
0x18000220d  lea     rcx, aProxyFileList
0x180002214  mov     rax, [rcx+rax]
0x180002218  mov     ecx, 8
0x18000221d  imul    rcx, 0
0x180002221  mov     rax, [rax+8]
0x180002225  cmp     qword ptr [rcx+rax], 0
0x18000222a  jz      short loc_18000225B
0x18000222c  mov     eax, 8
0x180002231  imul    rax, 0
0x180002235  lea     rcx, aProxyFileList
0x18000223c  mov     rax, [rcx+rax]
0x180002240  mov     ecx, 8
0x180002245  imul    rcx, 0
0x180002249  mov     rax, [rax+8]
0x18000224d  mov     rax, [rax+rcx]
0x180002251  mov     rax, [rax]
0x180002254  mov     [rsp+38h+pclsid], rax
0x180002259  jmp     short loc_180002264
0x18000225b  mov     [rsp+38h+pclsid], 0
0x180002264  mov     r8, [rsp+38h+pclsid]; pclsid
0x180002269  lea     rdx, aProxyFileList; pProxyFileList
0x180002270  mov     rcx, cs:hProxyDll; hDll
0x180002277  call    cs:__imp_NdrDllRegisterProxy
0x18000227d  add     rsp, 38h
0x180002281  retn
```
