# DllRegisterServer

- ea: `0x18008eb00`
- end: `0x18008eb6e`
- name: `DllRegisterServer`
- size: `110`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18008de38`
- `0x18008eb00`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18008eb5d`
- `RPCRT4!NdrDllRegisterProxy` at `0x18008eb5d`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18008eb17`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18008eb26`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18008eb17`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18008eb26`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18008eb0a`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18008eb0a`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebx
  HRESULT v1; // edi
  PCInterfaceStubVtblList v3; // rax
  const CLSID *piid; // r8

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<CVirtualAudioDeviceModule>::RegisterServer();
  SetThreadLocale(ThreadLocale);
  if ( v1 < 0 )
    return v1;
  v3 = *aProxyFileList->pStubVtblList;
  if ( v3 )
    piid = v3->header.piid;
  else
    piid = 0;
  return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x18008eb00  mov     [rsp+arg_0], rbx
0x18008eb05  push    rdi
0x18008eb06  sub     rsp, 20h
0x18008eb0a  call    cs:__imp_GetThreadLocale
0x18008eb10  mov     ecx, 800h; Locale
0x18008eb15  mov     ebx, eax
0x18008eb17  call    cs:__imp_SetThreadLocale
0x18008eb1d  call    ?RegisterServer@?$CAtlModuleT@VCVirtualAudioDeviceModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CVirtualAudioDeviceModule>::RegisterServer(int,_GUID const *)
0x18008eb22  mov     ecx, ebx; Locale
0x18008eb24  mov     edi, eax
0x18008eb26  call    cs:__imp_SetThreadLocale
0x18008eb2c  test    edi, edi
0x18008eb2e  jns     short loc_18008EB34
0x18008eb30  mov     eax, edi
0x18008eb32  jmp     short loc_18008EB63
0x18008eb34  mov     rax, cs:aProxyFileList
0x18008eb3b  mov     rcx, [rax+8]
0x18008eb3f  mov     rax, [rcx]
0x18008eb42  test    rax, rax
0x18008eb45  jz      short loc_18008EB4C
0x18008eb47  mov     r8, [rax]
0x18008eb4a  jmp     short loc_18008EB4F
0x18008eb4c  xor     r8d, r8d; pclsid
0x18008eb4f  mov     rcx, cs:hProxyDll; hDll
0x18008eb56  lea     rdx, aProxyFileList; pProxyFileList
0x18008eb5d  call    cs:__imp_NdrDllRegisterProxy
0x18008eb63  mov     rbx, [rsp+28h+arg_0]
0x18008eb68  add     rsp, 20h
0x18008eb6c  pop     rdi
0x18008eb6d  retn
```
