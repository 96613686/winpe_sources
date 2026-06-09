# DllUnregisterServer

- ea: `0x18000a560`
- end: `0x18000a633`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000a3d0`

## callees

- `0x180008bf4`
- `0x1800095d0`
- `0x18000a560`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a576`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a622`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a576`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a622`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000a569`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000a569`

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
    v4 = off_18001E140;
    v5 = off_18001E148;
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
        v5 = off_18001E148;
      }
      ++v4;
    }
  }
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{15C88C78-4CB3-49B5-97D4-01E60C8E6B9D}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x18000a560  push    rbx
0x18000a562  push    rbp
0x18000a563  push    rsi
0x18000a564  push    rdi
0x18000a565  sub     rsp, 48h
0x18000a569  call    cs:__imp_GetThreadLocale
0x18000a56f  mov     ebp, eax
0x18000a571  mov     ecx, 800h; Locale
0x18000a576  call    cs:__imp_SetThreadLocale
0x18000a57c  nop
0x18000a57d  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000a584  test    rax, rax
0x18000a587  jz      short loc_18000A594
0x18000a589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a58e  mov     ebx, eax
0x18000a590  test    eax, eax
0x18000a592  js      short loc_18000A5EC
0x18000a594  xor     ebx, ebx
0x18000a596  mov     rdi, cs:off_18001E140
0x18000a59d  mov     rax, cs:off_18001E148
0x18000a5a4  jmp     short loc_18000A5E7
0x18000a5a6  mov     rsi, [rdi]
0x18000a5a9  test    rsi, rsi
0x18000a5ac  jz      short loc_18000A5E3
0x18000a5ae  mov     rax, [rsi+38h]
0x18000a5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b7  xor     r8d, r8d; int
0x18000a5ba  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000a5bd  mov     rcx, [rsi]; rguid
0x18000a5c0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000a5c5  mov     ebx, eax
0x18000a5c7  test    eax, eax
0x18000a5c9  js      short loc_18000A5EC
0x18000a5cb  xor     ecx, ecx
0x18000a5cd  mov     rax, [rsi+8]
0x18000a5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5d6  mov     ebx, eax
0x18000a5d8  test    eax, eax
0x18000a5da  js      short loc_18000A5EC
0x18000a5dc  mov     rax, cs:off_18001E148
0x18000a5e3  add     rdi, 8
0x18000a5e7  cmp     rdi, rax
0x18000a5ea  jb      short loc_18000A5A6
0x18000a5ec  test    ebx, ebx
0x18000a5ee  js      short loc_18000A620
0x18000a5f0  lea     rax, aAppid; "APPID"
0x18000a5f7  mov     [rsp+68h+var_48], rax
0x18000a5fc  lea     rax, a15c88c784cb349; "{15C88C78-4CB3-49B5-97D4-01E60C8E6B9D}"
0x18000a603  mov     [rsp+68h+var_40], rax
0x18000a608  xorps   xmm0, xmm0
0x18000a60b  movdqu  [rsp+68h+var_38], xmm0
0x18000a611  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000a616  xor     r8d, r8d; int
0x18000a619  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000a61e  mov     ebx, eax
0x18000a620  mov     ecx, ebp; Locale
0x18000a622  call    cs:__imp_SetThreadLocale
0x18000a628  mov     eax, ebx
0x18000a62a  add     rsp, 48h
0x18000a62e  pop     rdi
0x18000a62f  pop     rsi
0x18000a630  pop     rbp
0x18000a631  pop     rbx
0x18000a632  retn
```
