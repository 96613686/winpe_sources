# DllRegisterServer

- ea: `0x180009cd0`
- end: `0x180009db2`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180009c30`

## callees

- `0x180008444`
- `0x180008f00`
- `0x180009cd0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009ce6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009da1`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009ce6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009da1`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009cd9`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009cd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  unsigned int v1; // edx
  ATL::CAtlModule *v2; // rcx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rdi
  __int64 *v5; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v6; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  _QWORD v9[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v10; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v9[0] = L"APPID";
  v9[1] = L"{04CE96FD-36B2-41ED-8A3E-A5606951F766}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v4 = off_180012100;
    v5 = off_180012108;
    while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        updated = (*((__int64 (__fastcall **)(__int64))v6 + 1))(1);
        if ( updated < 0 )
          break;
        v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v6 + 7))();
        updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 1);
        if ( updated < 0 )
          break;
        v5 = off_180012108;
      }
      ++v4;
    }
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hModule);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180009cd0  push    rbx
0x180009cd2  push    rbp
0x180009cd3  push    rsi
0x180009cd4  push    rdi
0x180009cd5  sub     rsp, 48h
0x180009cd9  call    cs:__imp_GetThreadLocale
0x180009cdf  mov     ebp, eax
0x180009ce1  mov     ecx, 800h; Locale
0x180009ce6  call    cs:__imp_SetThreadLocale
0x180009cec  lea     rax, aAppid; "APPID"
0x180009cf3  mov     [rsp+68h+var_48], rax
0x180009cf8  lea     rax, a04ce96fd36b241; "{04CE96FD-36B2-41ED-8A3E-A5606951F766}"
0x180009cff  mov     [rsp+68h+var_40], rax
0x180009d04  xorps   xmm0, xmm0
0x180009d07  movdqu  [rsp+68h+var_38], xmm0
0x180009d0d  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180009d12  mov     r8d, 1; int
0x180009d18  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180009d1d  mov     ebx, eax
0x180009d1f  test    eax, eax
0x180009d21  js      short loc_180009D9F
0x180009d23  xor     ebx, ebx
0x180009d25  mov     rdi, cs:off_180012100
0x180009d2c  mov     rax, cs:off_180012108
0x180009d33  jmp     short loc_180009D7C
0x180009d35  mov     rsi, [rdi]
0x180009d38  test    rsi, rsi
0x180009d3b  jz      short loc_180009D78
0x180009d3d  mov     ecx, 1
0x180009d42  mov     rax, [rsi+8]
0x180009d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d4b  mov     ebx, eax
0x180009d4d  test    eax, eax
0x180009d4f  js      short loc_180009D81
0x180009d51  mov     rax, [rsi+38h]
0x180009d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d5a  mov     r8d, 1; int
0x180009d60  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009d63  mov     rcx, [rsi]; rguid
0x180009d66  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009d6b  mov     ebx, eax
0x180009d6d  test    eax, eax
0x180009d6f  js      short loc_180009D81
0x180009d71  mov     rax, cs:off_180012108
0x180009d78  add     rdi, 8
0x180009d7c  cmp     rdi, rax
0x180009d7f  jb      short loc_180009D35
0x180009d81  test    ebx, ebx
0x180009d83  js      short loc_180009D9F
0x180009d85  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180009d8c  test    rax, rax
0x180009d8f  jz      short loc_180009D9F
0x180009d91  mov     rcx, cs:hModule
0x180009d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d9d  mov     ebx, eax
0x180009d9f  mov     ecx, ebp; Locale
0x180009da1  call    cs:__imp_SetThreadLocale
0x180009da7  mov     eax, ebx
0x180009da9  add     rsp, 48h
0x180009dad  pop     rdi
0x180009dae  pop     rsi
0x180009daf  pop     rbp
0x180009db0  pop     rbx
0x180009db1  retn
```
