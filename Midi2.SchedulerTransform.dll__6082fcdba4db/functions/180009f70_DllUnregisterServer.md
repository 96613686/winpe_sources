# DllUnregisterServer

- ea: `0x180009f70`
- end: `0x18000a043`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180009de0`

## callees

- `0x1800085f4`
- `0x1800090b0`
- `0x180009f70`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009f86`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a032`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009f86`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000a032`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009f79`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009f79`

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
    v4 = off_180015100;
    v5 = off_180015108;
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
        v5 = off_180015108;
      }
      ++v4;
    }
  }
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{2ac669ca-18ca-4e7d-951e-b6cc511c96fc}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180009f70  push    rbx
0x180009f72  push    rbp
0x180009f73  push    rsi
0x180009f74  push    rdi
0x180009f75  sub     rsp, 48h
0x180009f79  call    cs:__imp_GetThreadLocale
0x180009f7f  mov     ebp, eax
0x180009f81  mov     ecx, 800h; Locale
0x180009f86  call    cs:__imp_SetThreadLocale
0x180009f8c  nop
0x180009f8d  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180009f94  test    rax, rax
0x180009f97  jz      short loc_180009FA4
0x180009f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f9e  mov     ebx, eax
0x180009fa0  test    eax, eax
0x180009fa2  js      short loc_180009FFC
0x180009fa4  xor     ebx, ebx
0x180009fa6  mov     rdi, cs:off_180015100
0x180009fad  mov     rax, cs:off_180015108
0x180009fb4  jmp     short loc_180009FF7
0x180009fb6  mov     rsi, [rdi]
0x180009fb9  test    rsi, rsi
0x180009fbc  jz      short loc_180009FF3
0x180009fbe  mov     rax, [rsi+38h]
0x180009fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc7  xor     r8d, r8d; int
0x180009fca  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009fcd  mov     rcx, [rsi]; rguid
0x180009fd0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009fd5  mov     ebx, eax
0x180009fd7  test    eax, eax
0x180009fd9  js      short loc_180009FFC
0x180009fdb  xor     ecx, ecx
0x180009fdd  mov     rax, [rsi+8]
0x180009fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe6  mov     ebx, eax
0x180009fe8  test    eax, eax
0x180009fea  js      short loc_180009FFC
0x180009fec  mov     rax, cs:off_180015108
0x180009ff3  add     rdi, 8
0x180009ff7  cmp     rdi, rax
0x180009ffa  jb      short loc_180009FB6
0x180009ffc  test    ebx, ebx
0x180009ffe  js      short loc_18000A030
0x18000a000  lea     rax, aAppid; "APPID"
0x18000a007  mov     [rsp+68h+var_48], rax
0x18000a00c  lea     rax, a2ac669ca18ca4e; "{2ac669ca-18ca-4e7d-951e-b6cc511c96fc}"
0x18000a013  mov     [rsp+68h+var_40], rax
0x18000a018  xorps   xmm0, xmm0
0x18000a01b  movdqu  [rsp+68h+var_38], xmm0
0x18000a021  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000a026  xor     r8d, r8d; int
0x18000a029  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000a02e  mov     ebx, eax
0x18000a030  mov     ecx, ebp; Locale
0x18000a032  call    cs:__imp_SetThreadLocale
0x18000a038  mov     eax, ebx
0x18000a03a  add     rsp, 48h
0x18000a03e  pop     rdi
0x18000a03f  pop     rsi
0x18000a040  pop     rbp
0x18000a041  pop     rbx
0x18000a042  retn
```
