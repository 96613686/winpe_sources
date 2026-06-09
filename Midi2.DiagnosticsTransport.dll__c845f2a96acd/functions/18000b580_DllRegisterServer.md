# DllRegisterServer

- ea: `0x18000b580`
- end: `0x18000b662`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000b4e0`

## callees

- `0x180009cf4`
- `0x18000a7b0`
- `0x18000b580`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b596`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b651`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b596`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b651`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000b589`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000b589`

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
  v9[1] = L"{578daa61-200b-4622-8cb1-6d8a6fa93c17}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v4 = off_18001A100;
    v5 = off_18001A108;
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
        v5 = off_18001A108;
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
0x18000b580  push    rbx
0x18000b582  push    rbp
0x18000b583  push    rsi
0x18000b584  push    rdi
0x18000b585  sub     rsp, 48h
0x18000b589  call    cs:__imp_GetThreadLocale
0x18000b58f  mov     ebp, eax
0x18000b591  mov     ecx, 800h; Locale
0x18000b596  call    cs:__imp_SetThreadLocale
0x18000b59c  lea     rax, aAppid; "APPID"
0x18000b5a3  mov     [rsp+68h+var_48], rax
0x18000b5a8  lea     rax, a578daa61200b46; "{578daa61-200b-4622-8cb1-6d8a6fa93c17}"
0x18000b5af  mov     [rsp+68h+var_40], rax
0x18000b5b4  xorps   xmm0, xmm0
0x18000b5b7  movdqu  [rsp+68h+var_38], xmm0
0x18000b5bd  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000b5c2  mov     r8d, 1; int
0x18000b5c8  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000b5cd  mov     ebx, eax
0x18000b5cf  test    eax, eax
0x18000b5d1  js      short loc_18000B64F
0x18000b5d3  xor     ebx, ebx
0x18000b5d5  mov     rdi, cs:off_18001A100
0x18000b5dc  mov     rax, cs:off_18001A108
0x18000b5e3  jmp     short loc_18000B62C
0x18000b5e5  mov     rsi, [rdi]
0x18000b5e8  test    rsi, rsi
0x18000b5eb  jz      short loc_18000B628
0x18000b5ed  mov     ecx, 1
0x18000b5f2  mov     rax, [rsi+8]
0x18000b5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5fb  mov     ebx, eax
0x18000b5fd  test    eax, eax
0x18000b5ff  js      short loc_18000B631
0x18000b601  mov     rax, [rsi+38h]
0x18000b605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b60a  mov     r8d, 1; int
0x18000b610  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000b613  mov     rcx, [rsi]; rguid
0x18000b616  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000b61b  mov     ebx, eax
0x18000b61d  test    eax, eax
0x18000b61f  js      short loc_18000B631
0x18000b621  mov     rax, cs:off_18001A108
0x18000b628  add     rdi, 8
0x18000b62c  cmp     rdi, rax
0x18000b62f  jb      short loc_18000B5E5
0x18000b631  test    ebx, ebx
0x18000b633  js      short loc_18000B64F
0x18000b635  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18000b63c  test    rax, rax
0x18000b63f  jz      short loc_18000B64F
0x18000b641  mov     rcx, cs:hModule
0x18000b648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b64d  mov     ebx, eax
0x18000b64f  mov     ecx, ebp; Locale
0x18000b651  call    cs:__imp_SetThreadLocale
0x18000b657  mov     eax, ebx
0x18000b659  add     rsp, 48h
0x18000b65d  pop     rdi
0x18000b65e  pop     rsi
0x18000b65f  pop     rbp
0x18000b660  pop     rbx
0x18000b661  retn
```
