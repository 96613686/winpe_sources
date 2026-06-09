# DllRegisterServer

- ea: `0x180009d60`
- end: `0x180009e42`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180009cc0`

## callees

- `0x1800084d4`
- `0x180008f90`
- `0x180009d60`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009d76`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009e31`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009d76`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009e31`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009d69`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009d69`

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
  v9[1] = L"{5A2E778A-2450-42A0-88E9-E9C04CA2BA62}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v4 = off_180015100;
    v5 = off_180015108;
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
        v5 = off_180015108;
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
0x180009d60  push    rbx
0x180009d62  push    rbp
0x180009d63  push    rsi
0x180009d64  push    rdi
0x180009d65  sub     rsp, 48h
0x180009d69  call    cs:__imp_GetThreadLocale
0x180009d6f  mov     ebp, eax
0x180009d71  mov     ecx, 800h; Locale
0x180009d76  call    cs:__imp_SetThreadLocale
0x180009d7c  lea     rax, aAppid; "APPID"
0x180009d83  mov     [rsp+68h+var_48], rax
0x180009d88  lea     rax, a5a2e778a245042; "{5A2E778A-2450-42A0-88E9-E9C04CA2BA62}"
0x180009d8f  mov     [rsp+68h+var_40], rax
0x180009d94  xorps   xmm0, xmm0
0x180009d97  movdqu  [rsp+68h+var_38], xmm0
0x180009d9d  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180009da2  mov     r8d, 1; int
0x180009da8  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180009dad  mov     ebx, eax
0x180009daf  test    eax, eax
0x180009db1  js      short loc_180009E2F
0x180009db3  xor     ebx, ebx
0x180009db5  mov     rdi, cs:off_180015100
0x180009dbc  mov     rax, cs:off_180015108
0x180009dc3  jmp     short loc_180009E0C
0x180009dc5  mov     rsi, [rdi]
0x180009dc8  test    rsi, rsi
0x180009dcb  jz      short loc_180009E08
0x180009dcd  mov     ecx, 1
0x180009dd2  mov     rax, [rsi+8]
0x180009dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ddb  mov     ebx, eax
0x180009ddd  test    eax, eax
0x180009ddf  js      short loc_180009E11
0x180009de1  mov     rax, [rsi+38h]
0x180009de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dea  mov     r8d, 1; int
0x180009df0  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009df3  mov     rcx, [rsi]; rguid
0x180009df6  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009dfb  mov     ebx, eax
0x180009dfd  test    eax, eax
0x180009dff  js      short loc_180009E11
0x180009e01  mov     rax, cs:off_180015108
0x180009e08  add     rdi, 8
0x180009e0c  cmp     rdi, rax
0x180009e0f  jb      short loc_180009DC5
0x180009e11  test    ebx, ebx
0x180009e13  js      short loc_180009E2F
0x180009e15  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180009e1c  test    rax, rax
0x180009e1f  jz      short loc_180009E2F
0x180009e21  mov     rcx, cs:hModule
0x180009e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e2d  mov     ebx, eax
0x180009e2f  mov     ecx, ebp; Locale
0x180009e31  call    cs:__imp_SetThreadLocale
0x180009e37  mov     eax, ebx
0x180009e39  add     rsp, 48h
0x180009e3d  pop     rdi
0x180009e3e  pop     rsi
0x180009e3f  pop     rbp
0x180009e40  pop     rbx
0x180009e41  retn
```
