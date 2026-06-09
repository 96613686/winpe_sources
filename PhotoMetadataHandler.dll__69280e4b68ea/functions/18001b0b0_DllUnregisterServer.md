# DllUnregisterServer

- ea: `0x18001b0b0`
- end: `0x18001b108`
- name: `DllUnregisterServer`
- size: `88`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800190b4`
- `0x18001a940`
- `0x18001b0b0`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18001b0e6`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18001b0e6`

## string_xrefs

- `0x18001b0f6`: `UnregDll`

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
0x18001b0b0  sub     rsp, 28h
0x18001b0b4  call    ?UnregisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::UnregisterServer(int,_GUID const *)
0x18001b0b9  test    eax, eax
0x18001b0bb  js      short loc_18001B102
0x18001b0bd  mov     rax, cs:aProxyFileList
0x18001b0c4  mov     rcx, [rax+8]
0x18001b0c8  mov     rax, [rcx]
0x18001b0cb  test    rax, rax
0x18001b0ce  jz      short loc_18001B0D5
0x18001b0d0  mov     r8, [rax]
0x18001b0d3  jmp     short loc_18001B0D8
0x18001b0d5  xor     r8d, r8d; pclsid
0x18001b0d8  mov     rcx, cs:hProxyDll; hDll
0x18001b0df  lea     rdx, aProxyFileList; pProxyFileList
0x18001b0e6  call    cs:__imp_NdrDllUnregisterProxy
0x18001b0ed  nop     dword ptr [rax+rax+00h]
0x18001b0f2  test    eax, eax
0x18001b0f4  js      short loc_18001B102
0x18001b0f6  lea     rdx, aUnregdll; "UnregDll"
0x18001b0fd  call    ?CallRegInstall@@YAJPEAUHINSTANCE__@@PEBD@Z; CallRegInstall(HINSTANCE__ *,char const *)
0x18001b102  add     rsp, 28h
0x18001b106  retn
```
