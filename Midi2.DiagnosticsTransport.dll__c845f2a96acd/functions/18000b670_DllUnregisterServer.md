# DllUnregisterServer

- ea: `0x18000b670`
- end: `0x18000b743`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000b4e0`

## callees

- `0x180009cf4`
- `0x18000a7b0`
- `0x18000b670`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b686`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b732`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b686`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b732`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000b679`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000b679`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllUnregisterServer()
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
  if ( !ATL::_pPerfUnRegFunc || (updated = ATL::_pPerfUnRegFunc(), updated >= 0) )
  {
    updated = 0;
    v4 = off_18001A100;
    v5 = off_18001A108;
    while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v6 + 7))();
        updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 0);
        if ( updated < 0 )
          break;
        updated = (*((__int64 (__fastcall **)(_QWORD))v6 + 1))(0);
        if ( updated < 0 )
          break;
        v5 = off_18001A108;
      }
      ++v4;
    }
  }
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{578daa61-200b-4622-8cb1-6d8a6fa93c17}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x18000b670  push    rbx
0x18000b672  push    rbp
0x18000b673  push    rsi
0x18000b674  push    rdi
0x18000b675  sub     rsp, 48h
0x18000b679  call    cs:__imp_GetThreadLocale
0x18000b67f  mov     ebp, eax
0x18000b681  mov     ecx, 800h; Locale
0x18000b686  call    cs:__imp_SetThreadLocale
0x18000b68c  nop
0x18000b68d  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000b694  test    rax, rax
0x18000b697  jz      short loc_18000B6A4
0x18000b699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b69e  mov     ebx, eax
0x18000b6a0  test    eax, eax
0x18000b6a2  js      short loc_18000B6FC
0x18000b6a4  xor     ebx, ebx
0x18000b6a6  mov     rdi, cs:off_18001A100
0x18000b6ad  mov     rax, cs:off_18001A108
0x18000b6b4  jmp     short loc_18000B6F7
0x18000b6b6  mov     rsi, [rdi]
0x18000b6b9  test    rsi, rsi
0x18000b6bc  jz      short loc_18000B6F3
0x18000b6be  mov     rax, [rsi+38h]
0x18000b6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c7  xor     r8d, r8d; int
0x18000b6ca  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000b6cd  mov     rcx, [rsi]; rguid
0x18000b6d0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000b6d5  mov     ebx, eax
0x18000b6d7  test    eax, eax
0x18000b6d9  js      short loc_18000B6FC
0x18000b6db  xor     ecx, ecx
0x18000b6dd  mov     rax, [rsi+8]
0x18000b6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6e6  mov     ebx, eax
0x18000b6e8  test    eax, eax
0x18000b6ea  js      short loc_18000B6FC
0x18000b6ec  mov     rax, cs:off_18001A108
0x18000b6f3  add     rdi, 8
0x18000b6f7  cmp     rdi, rax
0x18000b6fa  jb      short loc_18000B6B6
0x18000b6fc  test    ebx, ebx
0x18000b6fe  js      short loc_18000B730
0x18000b700  lea     rax, aAppid; "APPID"
0x18000b707  mov     [rsp+68h+var_48], rax
0x18000b70c  lea     rax, a578daa61200b46; "{578daa61-200b-4622-8cb1-6d8a6fa93c17}"
0x18000b713  mov     [rsp+68h+var_40], rax
0x18000b718  xorps   xmm0, xmm0
0x18000b71b  movdqu  [rsp+68h+var_38], xmm0
0x18000b721  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000b726  xor     r8d, r8d; int
0x18000b729  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000b72e  mov     ebx, eax
0x18000b730  mov     ecx, ebp; Locale
0x18000b732  call    cs:__imp_SetThreadLocale
0x18000b738  mov     eax, ebx
0x18000b73a  add     rsp, 48h
0x18000b73e  pop     rdi
0x18000b73f  pop     rsi
0x18000b740  pop     rbp
0x18000b741  pop     rbx
0x18000b742  retn
```
