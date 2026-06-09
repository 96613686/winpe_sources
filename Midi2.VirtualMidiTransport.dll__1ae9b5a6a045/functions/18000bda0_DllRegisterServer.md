# DllRegisterServer

- ea: `0x18000bda0`
- end: `0x18000be82`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000bd00`

## callees

- `0x18000a514`
- `0x18000afd0`
- `0x18000bda0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000bda9`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000bda9`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000bdb6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000be71`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000bdb6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000be71`

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
  v9[1] = L"{42af54fc-9aba-4fe8-8ea2-d32d2a333a0c}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v4 = off_18002D100;
    v5 = off_18002D108;
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
        v5 = off_18002D108;
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
0x18000bda0  push    rbx
0x18000bda2  push    rbp
0x18000bda3  push    rsi
0x18000bda4  push    rdi
0x18000bda5  sub     rsp, 48h
0x18000bda9  call    cs:__imp_GetThreadLocale
0x18000bdaf  mov     ebp, eax
0x18000bdb1  mov     ecx, 800h; Locale
0x18000bdb6  call    cs:__imp_SetThreadLocale
0x18000bdbc  lea     rax, aAppid; "APPID"
0x18000bdc3  mov     [rsp+68h+var_48], rax
0x18000bdc8  lea     rax, a42af54fc9aba4f; "{42af54fc-9aba-4fe8-8ea2-d32d2a333a0c}"
0x18000bdcf  mov     [rsp+68h+var_40], rax
0x18000bdd4  xorps   xmm0, xmm0
0x18000bdd7  movdqu  [rsp+68h+var_38], xmm0
0x18000bddd  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000bde2  mov     r8d, 1; int
0x18000bde8  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000bded  mov     ebx, eax
0x18000bdef  test    eax, eax
0x18000bdf1  js      short loc_18000BE6F
0x18000bdf3  xor     ebx, ebx
0x18000bdf5  mov     rdi, cs:off_18002D100
0x18000bdfc  mov     rax, cs:off_18002D108
0x18000be03  jmp     short loc_18000BE4C
0x18000be05  mov     rsi, [rdi]
0x18000be08  test    rsi, rsi
0x18000be0b  jz      short loc_18000BE48
0x18000be0d  mov     ecx, 1
0x18000be12  mov     rax, [rsi+8]
0x18000be16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be1b  mov     ebx, eax
0x18000be1d  test    eax, eax
0x18000be1f  js      short loc_18000BE51
0x18000be21  mov     rax, [rsi+38h]
0x18000be25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be2a  mov     r8d, 1; int
0x18000be30  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000be33  mov     rcx, [rsi]; rguid
0x18000be36  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000be3b  mov     ebx, eax
0x18000be3d  test    eax, eax
0x18000be3f  js      short loc_18000BE51
0x18000be41  mov     rax, cs:off_18002D108
0x18000be48  add     rdi, 8
0x18000be4c  cmp     rdi, rax
0x18000be4f  jb      short loc_18000BE05
0x18000be51  test    ebx, ebx
0x18000be53  js      short loc_18000BE6F
0x18000be55  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18000be5c  test    rax, rax
0x18000be5f  jz      short loc_18000BE6F
0x18000be61  mov     rcx, cs:hModule
0x18000be68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be6d  mov     ebx, eax
0x18000be6f  mov     ecx, ebp; Locale
0x18000be71  call    cs:__imp_SetThreadLocale
0x18000be77  mov     eax, ebx
0x18000be79  add     rsp, 48h
0x18000be7d  pop     rdi
0x18000be7e  pop     rsi
0x18000be7f  pop     rbp
0x18000be80  pop     rbx
0x18000be81  retn
```
