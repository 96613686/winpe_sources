# DllRegisterServer

- ea: `0x18000d480`
- end: `0x18000d562`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000d3e0`

## callees

- `0x18000adb4`
- `0x18000c6b0`
- `0x18000d480`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000d489`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000d489`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000d496`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000d551`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000d496`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000d551`

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
  v9[1] = L"{945588ac-b364-4795-abc4-58cdf9009ed9}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v4 = off_18005F100;
    v5 = off_18005F108;
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
        v5 = off_18005F108;
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
0x18000d480  push    rbx
0x18000d482  push    rbp
0x18000d483  push    rsi
0x18000d484  push    rdi
0x18000d485  sub     rsp, 48h
0x18000d489  call    cs:__imp_GetThreadLocale
0x18000d48f  mov     ebp, eax
0x18000d491  mov     ecx, 800h; Locale
0x18000d496  call    cs:__imp_SetThreadLocale
0x18000d49c  lea     rax, aAppid; "APPID"
0x18000d4a3  mov     [rsp+68h+var_48], rax
0x18000d4a8  lea     rax, a945588acB36447; "{945588ac-b364-4795-abc4-58cdf9009ed9}"
0x18000d4af  mov     [rsp+68h+var_40], rax
0x18000d4b4  xorps   xmm0, xmm0
0x18000d4b7  movdqu  [rsp+68h+var_38], xmm0
0x18000d4bd  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000d4c2  mov     r8d, 1; int
0x18000d4c8  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000d4cd  mov     ebx, eax
0x18000d4cf  test    eax, eax
0x18000d4d1  js      short loc_18000D54F
0x18000d4d3  xor     ebx, ebx
0x18000d4d5  mov     rdi, cs:off_18005F100
0x18000d4dc  mov     rax, cs:off_18005F108
0x18000d4e3  jmp     short loc_18000D52C
0x18000d4e5  mov     rsi, [rdi]
0x18000d4e8  test    rsi, rsi
0x18000d4eb  jz      short loc_18000D528
0x18000d4ed  mov     ecx, 1
0x18000d4f2  mov     rax, [rsi+8]
0x18000d4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4fb  mov     ebx, eax
0x18000d4fd  test    eax, eax
0x18000d4ff  js      short loc_18000D531
0x18000d501  mov     rax, [rsi+38h]
0x18000d505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d50a  mov     r8d, 1; int
0x18000d510  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000d513  mov     rcx, [rsi]; rguid
0x18000d516  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000d51b  mov     ebx, eax
0x18000d51d  test    eax, eax
0x18000d51f  js      short loc_18000D531
0x18000d521  mov     rax, cs:off_18005F108
0x18000d528  add     rdi, 8
0x18000d52c  cmp     rdi, rax
0x18000d52f  jb      short loc_18000D4E5
0x18000d531  test    ebx, ebx
0x18000d533  js      short loc_18000D54F
0x18000d535  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18000d53c  test    rax, rax
0x18000d53f  jz      short loc_18000D54F
0x18000d541  mov     rcx, cs:hModule
0x18000d548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d54d  mov     ebx, eax
0x18000d54f  mov     ecx, ebp; Locale
0x18000d551  call    cs:__imp_SetThreadLocale
0x18000d557  mov     eax, ebx
0x18000d559  add     rsp, 48h
0x18000d55d  pop     rdi
0x18000d55e  pop     rsi
0x18000d55f  pop     rbp
0x18000d560  pop     rbx
0x18000d561  retn
```
