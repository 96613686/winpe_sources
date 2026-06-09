# DllRegisterServer

- ea: `0x18001b000`
- end: `0x18001b0a4`
- name: `DllRegisterServer`
- size: `164`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180018d78`
- `0x1800190b4`
- `0x18001a040`
- `0x18001b000`
- `0x180029010`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18001b081`
- `RPCRT4!NdrDllRegisterProxy` at `0x18001b081`

## string_xrefs

- `0x18001b091`: `RegDll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v2; // rax
  PCInterfaceStubVtblList v3; // rax
  const CLSID *piid; // r8
  HINSTANCE v5; // rcx

  v0 = qword_18009A088;
  if ( qword_18009A088 )
  {
    while ( *(_QWORD *)v0 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v0 + 8))(1);
      if ( result < 0 )
        goto LABEL_8;
      v2 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v2, 1);
      if ( result < 0 )
        goto LABEL_8;
      v0 += 72;
    }
  }
  result = ATL::CAtlModuleT<ATL::CComModule>::RegisterServer();
LABEL_8:
  if ( result >= 0 )
  {
    v3 = *aProxyFileList->pStubVtblList;
    if ( v3 )
      piid = v3->header.piid;
    else
      piid = 0;
    result = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
    if ( result >= 0 )
      return CallRegInstall(v5, "RegDll");
  }
  return result;
}

```

## disassembly

```asm
0x18001b000  push    rbx
0x18001b002  sub     rsp, 20h
0x18001b006  mov     rbx, cs:qword_18009A088
0x18001b00d  test    rbx, rbx
0x18001b010  jz      short loc_18001B04E
0x18001b012  jmp     short loc_18001B048
0x18001b014  mov     ecx, 1
0x18001b019  mov     rax, [rbx+8]
0x18001b01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b022  test    eax, eax
0x18001b024  js      short loc_18001B054
0x18001b026  mov     rax, [rbx+38h]
0x18001b02a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b02f  mov     r8d, 1; int
0x18001b035  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18001b038  mov     rcx, [rbx]; rguid
0x18001b03b  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18001b040  test    eax, eax
0x18001b042  js      short loc_18001B054
0x18001b044  add     rbx, 48h ; 'H'
0x18001b048  cmp     qword ptr [rbx], 0
0x18001b04c  jnz     short loc_18001B014
0x18001b04e  call    ?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)
0x18001b053  nop
0x18001b054  test    eax, eax
0x18001b056  js      short loc_18001B09D
0x18001b058  mov     rax, cs:aProxyFileList
0x18001b05f  mov     rcx, [rax+8]
0x18001b063  mov     rax, [rcx]
0x18001b066  test    rax, rax
0x18001b069  jz      short loc_18001B070
0x18001b06b  mov     r8, [rax]
0x18001b06e  jmp     short loc_18001B073
0x18001b070  xor     r8d, r8d; pclsid
0x18001b073  lea     rdx, aProxyFileList; pProxyFileList
0x18001b07a  mov     rcx, cs:hProxyDll; hDll
0x18001b081  call    cs:__imp_NdrDllRegisterProxy
0x18001b088  nop     dword ptr [rax+rax+00h]
0x18001b08d  test    eax, eax
0x18001b08f  js      short loc_18001B09D
0x18001b091  lea     rdx, aRegdll; "RegDll"
0x18001b098  call    ?CallRegInstall@@YAJPEAUHINSTANCE__@@PEBD@Z; CallRegInstall(HINSTANCE__ *,char const *)
0x18001b09d  add     rsp, 20h
0x18001b0a1  pop     rbx
0x18001b0a2  retn
```
