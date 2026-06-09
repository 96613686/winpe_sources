# DllRegisterServer

- ea: `0x18001a390`
- end: `0x18001a42d`
- name: `DllRegisterServer`
- size: `157`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001833c`
- `0x180018680`
- `0x180019490`
- `0x18001a390`
- `0x180028010`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18001a411`
- `RPCRT4!NdrDllRegisterProxy` at `0x18001a411`

## string_xrefs

- `0x18001a41b`: `RegDll`

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

  v0 = qword_180098F98;
  if ( qword_180098F98 )
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
0x18001a390  push    rbx
0x18001a392  sub     rsp, 20h
0x18001a396  mov     rbx, cs:qword_180098F98
0x18001a39d  test    rbx, rbx
0x18001a3a0  jz      short loc_18001A3DE
0x18001a3a2  jmp     short loc_18001A3D8
0x18001a3a4  mov     ecx, 1
0x18001a3a9  mov     rax, [rbx+8]
0x18001a3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3b2  test    eax, eax
0x18001a3b4  js      short loc_18001A3E4
0x18001a3b6  mov     rax, [rbx+38h]
0x18001a3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3bf  mov     r8d, 1; int
0x18001a3c5  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18001a3c8  mov     rcx, [rbx]; rguid
0x18001a3cb  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18001a3d0  test    eax, eax
0x18001a3d2  js      short loc_18001A3E4
0x18001a3d4  add     rbx, 48h ; 'H'
0x18001a3d8  cmp     qword ptr [rbx], 0
0x18001a3dc  jnz     short loc_18001A3A4
0x18001a3de  call    ?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)
0x18001a3e3  nop
0x18001a3e4  test    eax, eax
0x18001a3e6  js      short loc_18001A427
0x18001a3e8  mov     rax, cs:aProxyFileList
0x18001a3ef  mov     rcx, [rax+8]
0x18001a3f3  mov     rax, [rcx]
0x18001a3f6  test    rax, rax
0x18001a3f9  jz      short loc_18001A400
0x18001a3fb  mov     r8, [rax]
0x18001a3fe  jmp     short loc_18001A403
0x18001a400  xor     r8d, r8d; pclsid
0x18001a403  lea     rdx, aProxyFileList; pProxyFileList
0x18001a40a  mov     rcx, cs:hProxyDll; hDll
0x18001a411  call    cs:__imp_NdrDllRegisterProxy
0x18001a417  test    eax, eax
0x18001a419  js      short loc_18001A427
0x18001a41b  lea     rdx, aRegdll; "RegDll"
0x18001a422  call    ?CallRegInstall@@YAJPEAUHINSTANCE__@@PEBD@Z; CallRegInstall(HINSTANCE__ *,char const *)
0x18001a427  add     rsp, 20h
0x18001a42b  pop     rbx
0x18001a42c  retn
```
