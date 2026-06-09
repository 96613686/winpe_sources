# DllRegisterServer

- ea: `0x18000e390`
- end: `0x18000e472`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000e2f0`

## callees

- `0x18000b684`
- `0x18000d4f0`
- `0x18000e390`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000e399`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000e399`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000e3a6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000e461`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000e3a6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000e461`

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
  v9[1] = L"{05244d43-856c-4948-82de-eae678ab9f6f}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v4 = off_180071140;
    v5 = off_180071148;
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
        v5 = off_180071148;
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
0x18000e390  push    rbx
0x18000e392  push    rbp
0x18000e393  push    rsi
0x18000e394  push    rdi
0x18000e395  sub     rsp, 48h
0x18000e399  call    cs:__imp_GetThreadLocale
0x18000e39f  mov     ebp, eax
0x18000e3a1  mov     ecx, 800h; Locale
0x18000e3a6  call    cs:__imp_SetThreadLocale
0x18000e3ac  lea     rax, aAppid; "APPID"
0x18000e3b3  mov     [rsp+68h+var_48], rax
0x18000e3b8  lea     rax, a05244d43856c49; "{05244d43-856c-4948-82de-eae678ab9f6f}"
0x18000e3bf  mov     [rsp+68h+var_40], rax
0x18000e3c4  xorps   xmm0, xmm0
0x18000e3c7  movdqu  [rsp+68h+var_38], xmm0
0x18000e3cd  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000e3d2  mov     r8d, 1; int
0x18000e3d8  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000e3dd  mov     ebx, eax
0x18000e3df  test    eax, eax
0x18000e3e1  js      short loc_18000E45F
0x18000e3e3  xor     ebx, ebx
0x18000e3e5  mov     rdi, cs:off_180071140
0x18000e3ec  mov     rax, cs:off_180071148
0x18000e3f3  jmp     short loc_18000E43C
0x18000e3f5  mov     rsi, [rdi]
0x18000e3f8  test    rsi, rsi
0x18000e3fb  jz      short loc_18000E438
0x18000e3fd  mov     ecx, 1
0x18000e402  mov     rax, [rsi+8]
0x18000e406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e40b  mov     ebx, eax
0x18000e40d  test    eax, eax
0x18000e40f  js      short loc_18000E441
0x18000e411  mov     rax, [rsi+38h]
0x18000e415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e41a  mov     r8d, 1; int
0x18000e420  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000e423  mov     rcx, [rsi]; rguid
0x18000e426  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000e42b  mov     ebx, eax
0x18000e42d  test    eax, eax
0x18000e42f  js      short loc_18000E441
0x18000e431  mov     rax, cs:off_180071148
0x18000e438  add     rdi, 8
0x18000e43c  cmp     rdi, rax
0x18000e43f  jb      short loc_18000E3F5
0x18000e441  test    ebx, ebx
0x18000e443  js      short loc_18000E45F
0x18000e445  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18000e44c  test    rax, rax
0x18000e44f  jz      short loc_18000E45F
0x18000e451  mov     rcx, cs:hModule
0x18000e458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e45d  mov     ebx, eax
0x18000e45f  mov     ecx, ebp; Locale
0x18000e461  call    cs:__imp_SetThreadLocale
0x18000e467  mov     eax, ebx
0x18000e469  add     rsp, 48h
0x18000e46d  pop     rdi
0x18000e46e  pop     rsi
0x18000e46f  pop     rbp
0x18000e470  pop     rbx
0x18000e471  retn
```
