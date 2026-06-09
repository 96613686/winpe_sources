# DllUnregisterServer

- ea: `0x1800050a0`
- end: `0x180005190`
- name: `DllUnregisterServer`
- size: `240`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004a74`
- `0x180004bac`
- `0x1800050a0`
- `0x180007010`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18000517f`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18000517f`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000514c`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000514c`
- `KERNEL32!SetThreadLocale` at `0x1800050b7`
- `KERNEL32!SetThreadLocale` at `0x180005115`
- `KERNEL32!SetThreadLocale` at `0x1800050b7`
- `KERNEL32!SetThreadLocale` at `0x180005115`
- `KERNEL32!GetThreadLocale` at `0x1800050aa`
- `KERNEL32!GetThreadLocale` at `0x1800050aa`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  int v1; // edx
  ATL::CAtlComModule *v2; // rcx
  const struct _GUID *v3; // r8
  HRESULT updated; // ebx
  ATL::CAtlModule *v5; // rcx
  HRESULT result; // eax
  PCInterfaceStubVtblList v7; // rax
  const CLSID *piid; // r8
  PCInterfaceStubVtblList v9; // rax
  const CLSID *v10; // r8
  _QWORD v11[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v12; // [rsp+30h] [rbp-18h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (updated = ATL::_pPerfUnRegFunc(), updated >= 0) )
  {
    updated = ATL::CAtlComModule::UnregisterServer(v2, v1, v3);
    if ( updated >= 0 )
    {
      v11[0] = L"APPID";
      v11[1] = L"{E8054D20-497D-4E16-BF41-6E69FCD381A5}";
      v12 = 0;
      updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v5, 0x65u, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v11);
    }
  }
  SetThreadLocale(ThreadLocale);
  if ( updated < 0 )
    return updated;
  v7 = *aProxyFileList->pStubVtblList;
  if ( v7 )
    piid = v7->header.piid;
  else
    piid = 0;
  result = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  if ( result >= 0 )
  {
    v9 = *aProxyFileList->pStubVtblList;
    if ( v9 )
      v10 = v9->header.piid;
    else
      v10 = 0;
    return NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800050a0  mov     [rsp+arg_0], rbx
0x1800050a5  push    rdi
0x1800050a6  sub     rsp, 40h
0x1800050aa  call    cs:__imp_GetThreadLocale
0x1800050b0  mov     ecx, 800h; Locale
0x1800050b5  mov     edi, eax
0x1800050b7  call    cs:__imp_SetThreadLocale
0x1800050bd  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x1800050c4  test    rax, rax
0x1800050c7  jz      short loc_1800050D4
0x1800050c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ce  mov     ebx, eax
0x1800050d0  test    eax, eax
0x1800050d2  js      short loc_180005113
0x1800050d4  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x1800050d9  mov     ebx, eax
0x1800050db  test    eax, eax
0x1800050dd  js      short loc_180005113
0x1800050df  xor     r8d, r8d; int
0x1800050e2  lea     rax, aAppid; "APPID"
0x1800050e9  mov     [rsp+48h+var_28], rax
0x1800050ee  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x1800050f3  lea     rax, aE8054d20497d4e; "{E8054D20-497D-4E16-BF41-6E69FCD381A5}"
0x1800050fa  xorps   xmm0, xmm0
0x1800050fd  mov     [rsp+48h+var_20], rax
0x180005102  lea     edx, [r8+65h]; unsigned int
0x180005106  movdqu  [rsp+48h+var_18], xmm0
0x18000510c  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180005111  mov     ebx, eax
0x180005113  mov     ecx, edi; Locale
0x180005115  call    cs:__imp_SetThreadLocale
0x18000511b  test    ebx, ebx
0x18000511d  jns     short loc_180005123
0x18000511f  mov     eax, ebx
0x180005121  jmp     short loc_180005185
0x180005123  mov     rax, cs:aProxyFileList
0x18000512a  mov     rcx, [rax+8]
0x18000512e  mov     rax, [rcx]
0x180005131  test    rax, rax
0x180005134  jz      short loc_18000513B
0x180005136  mov     r8, [rax]
0x180005139  jmp     short loc_18000513E
0x18000513b  xor     r8d, r8d; pclsid
0x18000513e  mov     rcx, cs:hProxyDll; hDll
0x180005145  lea     rdx, aProxyFileList; pProxyFileList
0x18000514c  call    cs:__imp_NdrDllRegisterProxy
0x180005152  test    eax, eax
0x180005154  js      short loc_180005185
0x180005156  mov     rax, cs:aProxyFileList
0x18000515d  mov     rcx, [rax+8]
0x180005161  mov     rax, [rcx]
0x180005164  test    rax, rax
0x180005167  jz      short loc_18000516E
0x180005169  mov     r8, [rax]
0x18000516c  jmp     short loc_180005171
0x18000516e  xor     r8d, r8d; pclsid
0x180005171  mov     rcx, cs:hProxyDll; hDll
0x180005178  lea     rdx, aProxyFileList; pProxyFileList
0x18000517f  call    cs:__imp_NdrDllUnregisterProxy
0x180005185  mov     rbx, [rsp+48h+arg_0]
0x18000518a  add     rsp, 40h
0x18000518e  pop     rdi
0x18000518f  retn
```
