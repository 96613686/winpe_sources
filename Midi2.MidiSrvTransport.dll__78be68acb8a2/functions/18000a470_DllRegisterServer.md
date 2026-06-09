# DllRegisterServer

- ea: `0x18000a470`
- end: `0x18000a552`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000a3d0`

## callees

- `0x180008bf4`
- `0x1800095d0`
- `0x18000a470`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a486`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a541`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a486`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a541`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000a479`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000a479`

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
  v9[1] = L"{15C88C78-4CB3-49B5-97D4-01E60C8E6B9D}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v4 = off_18001E140;
    v5 = off_18001E148;
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
        v5 = off_18001E148;
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
0x18000a470  push    rbx
0x18000a472  push    rbp
0x18000a473  push    rsi
0x18000a474  push    rdi
0x18000a475  sub     rsp, 48h
0x18000a479  call    cs:__imp_GetThreadLocale
0x18000a47f  mov     ebp, eax
0x18000a481  mov     ecx, 800h; Locale
0x18000a486  call    cs:__imp_SetThreadLocale
0x18000a48c  lea     rax, aAppid; "APPID"
0x18000a493  mov     [rsp+68h+var_48], rax
0x18000a498  lea     rax, a15c88c784cb349; "{15C88C78-4CB3-49B5-97D4-01E60C8E6B9D}"
0x18000a49f  mov     [rsp+68h+var_40], rax
0x18000a4a4  xorps   xmm0, xmm0
0x18000a4a7  movdqu  [rsp+68h+var_38], xmm0
0x18000a4ad  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000a4b2  mov     r8d, 1; int
0x18000a4b8  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000a4bd  mov     ebx, eax
0x18000a4bf  test    eax, eax
0x18000a4c1  js      short loc_18000A53F
0x18000a4c3  xor     ebx, ebx
0x18000a4c5  mov     rdi, cs:off_18001E140
0x18000a4cc  mov     rax, cs:off_18001E148
0x18000a4d3  jmp     short loc_18000A51C
0x18000a4d5  mov     rsi, [rdi]
0x18000a4d8  test    rsi, rsi
0x18000a4db  jz      short loc_18000A518
0x18000a4dd  mov     ecx, 1
0x18000a4e2  mov     rax, [rsi+8]
0x18000a4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4eb  mov     ebx, eax
0x18000a4ed  test    eax, eax
0x18000a4ef  js      short loc_18000A521
0x18000a4f1  mov     rax, [rsi+38h]
0x18000a4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4fa  mov     r8d, 1; int
0x18000a500  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000a503  mov     rcx, [rsi]; rguid
0x18000a506  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000a50b  mov     ebx, eax
0x18000a50d  test    eax, eax
0x18000a50f  js      short loc_18000A521
0x18000a511  mov     rax, cs:off_18001E148
0x18000a518  add     rdi, 8
0x18000a51c  cmp     rdi, rax
0x18000a51f  jb      short loc_18000A4D5
0x18000a521  test    ebx, ebx
0x18000a523  js      short loc_18000A53F
0x18000a525  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18000a52c  test    rax, rax
0x18000a52f  jz      short loc_18000A53F
0x18000a531  mov     rcx, cs:hModule
0x18000a538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a53d  mov     ebx, eax
0x18000a53f  mov     ecx, ebp; Locale
0x18000a541  call    cs:__imp_SetThreadLocale
0x18000a547  mov     eax, ebx
0x18000a549  add     rsp, 48h
0x18000a54d  pop     rdi
0x18000a54e  pop     rsi
0x18000a54f  pop     rbp
0x18000a550  pop     rbx
0x18000a551  retn
```
