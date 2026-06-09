# DllUnregisterServer

- ea: `0x18000d570`
- end: `0x18000d643`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000d3e0`

## callees

- `0x18000adb4`
- `0x18000c6b0`
- `0x18000d570`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000d579`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000d579`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000d586`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000d632`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000d586`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000d632`

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
    v4 = off_18005F100;
    v5 = off_18005F108;
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
        v5 = off_18005F108;
      }
      ++v4;
    }
  }
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{945588ac-b364-4795-abc4-58cdf9009ed9}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x18000d570  push    rbx
0x18000d572  push    rbp
0x18000d573  push    rsi
0x18000d574  push    rdi
0x18000d575  sub     rsp, 48h
0x18000d579  call    cs:__imp_GetThreadLocale
0x18000d57f  mov     ebp, eax
0x18000d581  mov     ecx, 800h; Locale
0x18000d586  call    cs:__imp_SetThreadLocale
0x18000d58c  nop
0x18000d58d  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000d594  test    rax, rax
0x18000d597  jz      short loc_18000D5A4
0x18000d599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d59e  mov     ebx, eax
0x18000d5a0  test    eax, eax
0x18000d5a2  js      short loc_18000D5FC
0x18000d5a4  xor     ebx, ebx
0x18000d5a6  mov     rdi, cs:off_18005F100
0x18000d5ad  mov     rax, cs:off_18005F108
0x18000d5b4  jmp     short loc_18000D5F7
0x18000d5b6  mov     rsi, [rdi]
0x18000d5b9  test    rsi, rsi
0x18000d5bc  jz      short loc_18000D5F3
0x18000d5be  mov     rax, [rsi+38h]
0x18000d5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5c7  xor     r8d, r8d; int
0x18000d5ca  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000d5cd  mov     rcx, [rsi]; rguid
0x18000d5d0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000d5d5  mov     ebx, eax
0x18000d5d7  test    eax, eax
0x18000d5d9  js      short loc_18000D5FC
0x18000d5db  xor     ecx, ecx
0x18000d5dd  mov     rax, [rsi+8]
0x18000d5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5e6  mov     ebx, eax
0x18000d5e8  test    eax, eax
0x18000d5ea  js      short loc_18000D5FC
0x18000d5ec  mov     rax, cs:off_18005F108
0x18000d5f3  add     rdi, 8
0x18000d5f7  cmp     rdi, rax
0x18000d5fa  jb      short loc_18000D5B6
0x18000d5fc  test    ebx, ebx
0x18000d5fe  js      short loc_18000D630
0x18000d600  lea     rax, aAppid; "APPID"
0x18000d607  mov     [rsp+68h+var_48], rax
0x18000d60c  lea     rax, a945588acB36447; "{945588ac-b364-4795-abc4-58cdf9009ed9}"
0x18000d613  mov     [rsp+68h+var_40], rax
0x18000d618  xorps   xmm0, xmm0
0x18000d61b  movdqu  [rsp+68h+var_38], xmm0
0x18000d621  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000d626  xor     r8d, r8d; int
0x18000d629  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000d62e  mov     ebx, eax
0x18000d630  mov     ecx, ebp; Locale
0x18000d632  call    cs:__imp_SetThreadLocale
0x18000d638  mov     eax, ebx
0x18000d63a  add     rsp, 48h
0x18000d63e  pop     rdi
0x18000d63f  pop     rsi
0x18000d640  pop     rbp
0x18000d641  pop     rbx
0x18000d642  retn
```
