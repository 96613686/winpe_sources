# DllUnregisterServer

- ea: `0x18001a440`
- end: `0x18001a491`
- name: `DllUnregisterServer`
- size: `81`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180018680`
- `0x180019d44`
- `0x18001a440`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18001a476`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18001a476`

## string_xrefs

- `0x18001a480`: `UnregDll`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  int v0; // edx
  ATL::CComModule *v1; // rcx
  const struct _GUID *v2; // r8
  HRESULT result; // eax
  PCInterfaceStubVtblList v4; // rax
  const CLSID *piid; // r8
  HINSTANCE v6; // rcx

  result = ATL::CComModule::UnregisterServer(v1, v0, v2);
  if ( result >= 0 )
  {
    v4 = *aProxyFileList->pStubVtblList;
    if ( v4 )
      piid = v4->header.piid;
    else
      piid = 0;
    result = NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
    if ( result >= 0 )
      return CallRegInstall(v6, "UnregDll");
  }
  return result;
}

```

## disassembly

```asm
0x18001a440  sub     rsp, 28h
0x18001a444  call    ?UnregisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::UnregisterServer(int,_GUID const *)
0x18001a449  test    eax, eax
0x18001a44b  js      short loc_18001A48C
0x18001a44d  mov     rax, cs:aProxyFileList
0x18001a454  mov     rcx, [rax+8]
0x18001a458  mov     rax, [rcx]
0x18001a45b  test    rax, rax
0x18001a45e  jz      short loc_18001A465
0x18001a460  mov     r8, [rax]
0x18001a463  jmp     short loc_18001A468
0x18001a465  xor     r8d, r8d; pclsid
0x18001a468  mov     rcx, cs:hProxyDll; hDll
0x18001a46f  lea     rdx, aProxyFileList; pProxyFileList
0x18001a476  call    cs:__imp_NdrDllUnregisterProxy
0x18001a47c  test    eax, eax
0x18001a47e  js      short loc_18001A48C
0x18001a480  lea     rdx, aUnregdll; "UnregDll"
0x18001a487  call    ?CallRegInstall@@YAJPEAUHINSTANCE__@@PEBD@Z; CallRegInstall(HINSTANCE__ *,char const *)
0x18001a48c  add     rsp, 28h
0x18001a490  retn
```
