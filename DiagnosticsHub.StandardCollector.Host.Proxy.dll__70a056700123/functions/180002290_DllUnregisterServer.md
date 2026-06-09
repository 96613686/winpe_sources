# DllUnregisterServer

- ea: `0x180002290`
- end: `0x180002312`
- name: `DllUnregisterServer`
- size: `130`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002290`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180002307`
- `RPCRT4!NdrDllUnregisterProxy` at `0x180002307`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  if ( *aProxyFileList->pStubVtblList )
    return NdrDllUnregisterProxy(
             hProxyDll,
             (const ProxyFileInfo **)&aProxyFileList,
             **(const CLSID ***)aProxyFileList->pStubVtblList);
  else
    return NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, 0);
}

```

## disassembly

```asm
0x180002290  sub     rsp, 38h
0x180002294  mov     eax, 8
0x180002299  imul    rax, 0
0x18000229d  lea     rcx, aProxyFileList
0x1800022a4  mov     rax, [rcx+rax]
0x1800022a8  mov     ecx, 8
0x1800022ad  imul    rcx, 0
0x1800022b1  mov     rax, [rax+8]
0x1800022b5  cmp     qword ptr [rcx+rax], 0
0x1800022ba  jz      short loc_1800022EB
0x1800022bc  mov     eax, 8
0x1800022c1  imul    rax, 0
0x1800022c5  lea     rcx, aProxyFileList
0x1800022cc  mov     rax, [rcx+rax]
0x1800022d0  mov     ecx, 8
0x1800022d5  imul    rcx, 0
0x1800022d9  mov     rax, [rax+8]
0x1800022dd  mov     rax, [rax+rcx]
0x1800022e1  mov     rax, [rax]
0x1800022e4  mov     [rsp+38h+pclsid], rax
0x1800022e9  jmp     short loc_1800022F4
0x1800022eb  mov     [rsp+38h+pclsid], 0
0x1800022f4  mov     r8, [rsp+38h+pclsid]; pclsid
0x1800022f9  lea     rdx, aProxyFileList; pProxyFileList
0x180002300  mov     rcx, cs:hProxyDll; hDll
0x180002307  call    cs:__imp_NdrDllUnregisterProxy
0x18000230d  add     rsp, 38h
0x180002311  retn
```
