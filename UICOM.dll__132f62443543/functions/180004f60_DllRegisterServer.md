# DllRegisterServer

- ea: `0x180004f60`
- end: `0x180005093`
- name: `DllRegisterServer`
- size: `307`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002ebc`
- `0x180003378`
- `0x180004bac`
- `0x180004f60`
- `0x180007010`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180005084`
- `RPCRT4!NdrDllRegisterProxy` at `0x180005084`
- `KERNEL32!SetThreadLocale` at `0x180004f76`
- `KERNEL32!SetThreadLocale` at `0x18000504d`
- `KERNEL32!SetThreadLocale` at `0x180004f76`
- `KERNEL32!SetThreadLocale` at `0x18000504d`
- `KERNEL32!GetThreadLocale` at `0x180004f69`
- `KERNEL32!GetThreadLocale` at `0x180004f69`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  ATL::CAtlModule *v1; // rcx
  const unsigned __int16 *v2; // rdx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rdi
  __int64 *v5; // rax
  __int64 v6; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  PCInterfaceStubVtblList v9; // rax
  const CLSID *piid; // r8
  _QWORD v11[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v12; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v11[0] = L"APPID";
  v11[1] = L"{E8054D20-497D-4E16-BF41-6E69FCD381A5}";
  v12 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v1, 0x65u, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v11);
  if ( updated >= 0 )
  {
    v4 = off_18000B0B0;
    v5 = (__int64 *)off_18000B0B8;
    if ( off_18000B0B0 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_18000B0B8 )
    {
      do
      {
        v6 = *(_QWORD *)v4;
        if ( *(_QWORD *)v4 )
        {
          updated = (*(__int64 (__fastcall **)(__int64))(v6 + 8))(1);
          if ( updated < 0 )
            goto LABEL_9;
          v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v6 + 56))();
          updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 1);
          if ( updated < 0 )
            goto LABEL_9;
          v5 = (__int64 *)off_18000B0B8;
        }
        v4 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v4 + 8);
      }
      while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v5 );
    }
    updated = ATL::AtlRegisterTypeLib(off_18000B0A8, v2);
LABEL_9:
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hInstance);
  }
  SetThreadLocale(ThreadLocale);
  if ( updated < 0 )
    return updated;
  v9 = *aProxyFileList->pStubVtblList;
  if ( v9 )
    piid = v9->header.piid;
  else
    piid = 0;
  return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x180004f60  push    rbx
0x180004f62  push    rbp
0x180004f63  push    rsi
0x180004f64  push    rdi
0x180004f65  sub     rsp, 48h
0x180004f69  call    cs:__imp_GetThreadLocale
0x180004f6f  mov     ecx, 800h; Locale
0x180004f74  mov     ebp, eax
0x180004f76  call    cs:__imp_SetThreadLocale
0x180004f7c  mov     edx, 65h ; 'e'; unsigned int
0x180004f81  lea     rax, aAppid; "APPID"
0x180004f88  mov     [rsp+68h+var_48], rax
0x180004f8d  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180004f92  lea     rax, aE8054d20497d4e; "{E8054D20-497D-4E16-BF41-6E69FCD381A5}"
0x180004f99  xorps   xmm0, xmm0
0x180004f9c  mov     [rsp+68h+var_40], rax
0x180004fa1  lea     r8d, [rdx-64h]; int
0x180004fa5  movdqu  [rsp+68h+var_38], xmm0
0x180004fab  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180004fb0  mov     ebx, eax
0x180004fb2  test    eax, eax
0x180004fb4  js      loc_18000504B
0x180004fba  mov     rdi, cs:off_18000B0B0
0x180004fc1  xor     ebx, ebx
0x180004fc3  mov     rax, cs:off_18000B0B8
0x180004fca  cmp     rdi, rax
0x180004fcd  jnb     short loc_18000501F
0x180004fcf  mov     rsi, [rdi]
0x180004fd2  test    rsi, rsi
0x180004fd5  jz      short loc_180005012
0x180004fd7  mov     rax, [rsi+8]
0x180004fdb  mov     ecx, 1
0x180004fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe5  mov     ebx, eax
0x180004fe7  test    eax, eax
0x180004fe9  js      short loc_18000502D
0x180004feb  mov     rax, [rsi+38h]
0x180004fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff4  mov     rcx, [rsi]; rguid
0x180004ff7  mov     r8d, 1; int
0x180004ffd  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180005000  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180005005  mov     ebx, eax
0x180005007  test    eax, eax
0x180005009  js      short loc_18000502D
0x18000500b  mov     rax, cs:off_18000B0B8
0x180005012  add     rdi, 8
0x180005016  cmp     rdi, rax
0x180005019  jb      short loc_180004FCF
0x18000501b  test    ebx, ebx
0x18000501d  js      short loc_18000504B
0x18000501f  mov     rcx, cs:off_18000B0A8; HINSTANCE
0x180005026  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x18000502b  mov     ebx, eax
0x18000502d  test    ebx, ebx
0x18000502f  js      short loc_18000504B
0x180005031  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180005038  test    rax, rax
0x18000503b  jz      short loc_18000504B
0x18000503d  mov     rcx, cs:hInstance
0x180005044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005049  mov     ebx, eax
0x18000504b  mov     ecx, ebp; Locale
0x18000504d  call    cs:__imp_SetThreadLocale
0x180005053  test    ebx, ebx
0x180005055  jns     short loc_18000505B
0x180005057  mov     eax, ebx
0x180005059  jmp     short loc_18000508A
0x18000505b  mov     rax, cs:aProxyFileList
0x180005062  mov     rcx, [rax+8]
0x180005066  mov     rax, [rcx]
0x180005069  test    rax, rax
0x18000506c  jz      short loc_180005073
0x18000506e  mov     r8, [rax]
0x180005071  jmp     short loc_180005076
0x180005073  xor     r8d, r8d; pclsid
0x180005076  mov     rcx, cs:hProxyDll; hDll
0x18000507d  lea     rdx, aProxyFileList; pProxyFileList
0x180005084  call    cs:__imp_NdrDllRegisterProxy
0x18000508a  add     rsp, 48h
0x18000508e  pop     rdi
0x18000508f  pop     rsi
0x180005090  pop     rbp
0x180005091  pop     rbx
0x180005092  retn
```
