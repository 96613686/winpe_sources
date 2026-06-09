# DllRegisterServer

- ea: `0x18000af40`
- end: `0x18000b022`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000aea0`

## callees

- `0x1800096b4`
- `0x18000a170`
- `0x18000af40`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000af49`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000af49`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000af56`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b011`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000af56`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b011`

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
  v9[1] = L"{1b2e6e7f-e780-4406-92e0-14f4b8b04552}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v4 = off_18001B100;
    v5 = off_18001B108;
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
        v5 = off_18001B108;
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
0x18000af40  push    rbx
0x18000af42  push    rbp
0x18000af43  push    rsi
0x18000af44  push    rdi
0x18000af45  sub     rsp, 48h
0x18000af49  call    cs:__imp_GetThreadLocale
0x18000af4f  mov     ebp, eax
0x18000af51  mov     ecx, 800h; Locale
0x18000af56  call    cs:__imp_SetThreadLocale
0x18000af5c  lea     rax, aAppid; "APPID"
0x18000af63  mov     [rsp+68h+var_48], rax
0x18000af68  lea     rax, a1b2e6e7fE78044; "{1b2e6e7f-e780-4406-92e0-14f4b8b04552}"
0x18000af6f  mov     [rsp+68h+var_40], rax
0x18000af74  xorps   xmm0, xmm0
0x18000af77  movdqu  [rsp+68h+var_38], xmm0
0x18000af7d  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000af82  mov     r8d, 1; int
0x18000af88  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000af8d  mov     ebx, eax
0x18000af8f  test    eax, eax
0x18000af91  js      short loc_18000B00F
0x18000af93  xor     ebx, ebx
0x18000af95  mov     rdi, cs:off_18001B100
0x18000af9c  mov     rax, cs:off_18001B108
0x18000afa3  jmp     short loc_18000AFEC
0x18000afa5  mov     rsi, [rdi]
0x18000afa8  test    rsi, rsi
0x18000afab  jz      short loc_18000AFE8
0x18000afad  mov     ecx, 1
0x18000afb2  mov     rax, [rsi+8]
0x18000afb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afbb  mov     ebx, eax
0x18000afbd  test    eax, eax
0x18000afbf  js      short loc_18000AFF1
0x18000afc1  mov     rax, [rsi+38h]
0x18000afc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afca  mov     r8d, 1; int
0x18000afd0  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000afd3  mov     rcx, [rsi]; rguid
0x18000afd6  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000afdb  mov     ebx, eax
0x18000afdd  test    eax, eax
0x18000afdf  js      short loc_18000AFF1
0x18000afe1  mov     rax, cs:off_18001B108
0x18000afe8  add     rdi, 8
0x18000afec  cmp     rdi, rax
0x18000afef  jb      short loc_18000AFA5
0x18000aff1  test    ebx, ebx
0x18000aff3  js      short loc_18000B00F
0x18000aff5  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18000affc  test    rax, rax
0x18000afff  jz      short loc_18000B00F
0x18000b001  mov     rcx, cs:hModule
0x18000b008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b00d  mov     ebx, eax
0x18000b00f  mov     ecx, ebp; Locale
0x18000b011  call    cs:__imp_SetThreadLocale
0x18000b017  mov     eax, ebx
0x18000b019  add     rsp, 48h
0x18000b01d  pop     rdi
0x18000b01e  pop     rsi
0x18000b01f  pop     rbp
0x18000b020  pop     rbx
0x18000b021  retn
```
