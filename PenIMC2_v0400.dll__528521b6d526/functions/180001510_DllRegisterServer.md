# DllRegisterServer

- ea: `0x180001510`
- end: `0x180001649`
- name: `DllRegisterServer`
- size: `313`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180001510`
- `0x1800023d0`
- `0x180002610`
- `0x1800057c0`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180001524`
- `KERNEL32!GetThreadLocale` at `0x180001524`
- `KERNEL32!SetThreadLocale` at `0x180001531`
- `KERNEL32!SetThreadLocale` at `0x18000160b`
- `KERNEL32!SetThreadLocale` at `0x180001531`
- `KERNEL32!SetThreadLocale` at `0x18000160b`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000162e`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000162e`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  ATL::CAtlModule *v1; // rcx
  const unsigned __int16 *v2; // rdx
  HRESULT updated; // ebx
  GUID **v4; // rdi
  __int64 *v5; // rax
  GUID *v6; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  _QWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v10; // [rsp+30h] [rbp-18h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v9[0] = L"APPID";
  v9[1] = L"{953E4863-7AD1-4DAE-B2BD-108F1D57967B}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResource(v1, 0x65u, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    v4 = off_180018210;
    v5 = (__int64 *)off_180018218;
    if ( off_180018210 < (GUID **)off_180018218 )
    {
      do
      {
        v6 = *v4;
        if ( *v4 )
        {
          updated = (*(__int64 (__fastcall **)(__int64))v6->Data4)(1);
          if ( updated < 0 )
            goto LABEL_9;
          v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))&v6[3].Data1)();
          updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)&v6->Data1, v7, 1);
          if ( updated < 0 )
            goto LABEL_9;
          v5 = (__int64 *)off_180018218;
        }
        ++v4;
      }
      while ( v4 < (GUID **)v5 );
    }
    updated = ATL::AtlRegisterTypeLib(off_180018208, v2);
LABEL_9:
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hModule);
  }
  SetThreadLocale(ThreadLocale);
  if ( updated >= 0 )
    return NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &IID_IPimcContext2);
  else
    return updated;
}

```

## disassembly

```asm
0x180001510  mov     [rsp+arg_0], rbx
0x180001515  mov     [rsp+arg_8], rbp
0x18000151a  mov     [rsp+arg_10], rsi
0x18000151f  push    rdi
0x180001520  sub     rsp, 40h
0x180001524  call    cs:__imp_GetThreadLocale
0x18000152a  mov     ecx, 800h; Locale
0x18000152f  mov     ebp, eax
0x180001531  call    cs:__imp_SetThreadLocale
0x180001537  mov     edx, 65h ; 'e'; unsigned int
0x18000153c  lea     rax, aAppid; "APPID"
0x180001543  mov     [rsp+48h+var_28], rax
0x180001548  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000154d  lea     rax, a953e48637ad14d; "{953E4863-7AD1-4DAE-B2BD-108F1D57967B}"
0x180001554  xorps   xmm0, xmm0
0x180001557  mov     [rsp+48h+var_20], rax
0x18000155c  lea     r8d, [rdx-64h]; int
0x180001560  movdqu  [rsp+48h+var_18], xmm0
0x180001566  call    ?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResource(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000156b  mov     ebx, eax
0x18000156d  test    eax, eax
0x18000156f  js      loc_180001609
0x180001575  mov     rdi, cs:off_180018210
0x18000157c  xor     ebx, ebx
0x18000157e  mov     rax, cs:off_180018218
0x180001585  cmp     rdi, rax
0x180001588  jnb     short loc_1800015DC
0x18000158a  mov     rsi, [rdi]
0x18000158d  test    rsi, rsi
0x180001590  jz      short loc_1800015CF
0x180001592  mov     rax, [rsi+8]
0x180001596  mov     ecx, 1
0x18000159b  call    cs:__guard_dispatch_icall_fptr
0x1800015a1  mov     ebx, eax
0x1800015a3  test    eax, eax
0x1800015a5  js      short loc_1800015EA
0x1800015a7  mov     rax, [rsi+30h]
0x1800015ab  call    cs:__guard_dispatch_icall_fptr
0x1800015b1  mov     rcx, [rsi]; rguid
0x1800015b4  mov     r8d, 1; int
0x1800015ba  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800015bd  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800015c2  mov     ebx, eax
0x1800015c4  test    eax, eax
0x1800015c6  js      short loc_1800015EA
0x1800015c8  mov     rax, cs:off_180018218
0x1800015cf  add     rdi, 8
0x1800015d3  cmp     rdi, rax
0x1800015d6  jb      short loc_18000158A
0x1800015d8  test    ebx, ebx
0x1800015da  js      short loc_180001609
0x1800015dc  mov     rcx, cs:off_180018208; HINSTANCE
0x1800015e3  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x1800015e8  mov     ebx, eax
0x1800015ea  test    ebx, ebx
0x1800015ec  js      short loc_180001609
0x1800015ee  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x1800015f5  test    rax, rax
0x1800015f8  jz      short loc_180001609
0x1800015fa  mov     rcx, cs:hModule
0x180001601  call    cs:__guard_dispatch_icall_fptr
0x180001607  mov     ebx, eax
0x180001609  mov     ecx, ebp; Locale
0x18000160b  call    cs:__imp_SetThreadLocale
0x180001611  test    ebx, ebx
0x180001613  jns     short loc_180001619
0x180001615  mov     eax, ebx
0x180001617  jmp     short loc_180001634
0x180001619  mov     rcx, cs:hProxyDll; hDll
0x180001620  lea     r8, IID_IPimcContext2; pclsid
0x180001627  lea     rdx, aProxyFileList; pProxyFileList
0x18000162e  call    cs:__imp_NdrDllRegisterProxy
0x180001634  mov     rbx, [rsp+48h+arg_0]
0x180001639  mov     rbp, [rsp+48h+arg_8]
0x18000163e  mov     rsi, [rsp+48h+arg_10]
0x180001643  add     rsp, 40h
0x180001647  pop     rdi
0x180001648  retn
```
