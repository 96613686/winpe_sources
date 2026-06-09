# DllRegisterServer

- ea: `0x180012050`
- end: `0x180012132`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180011fb0`

## callees

- `0x18000c204`
- `0x1800111b0`
- `0x180012050`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180012066`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180012121`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180012066`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180012121`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180012059`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180012059`

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
  v9[1] = L"{74174a03-30ce-4a50-a440-bc969cb4d475}";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    updated = 0;
    v4 = off_180096140;
    v5 = off_180096148;
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
        v5 = off_180096148;
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
0x180012050  push    rbx
0x180012052  push    rbp
0x180012053  push    rsi
0x180012054  push    rdi
0x180012055  sub     rsp, 48h
0x180012059  call    cs:__imp_GetThreadLocale
0x18001205f  mov     ebp, eax
0x180012061  mov     ecx, 800h; Locale
0x180012066  call    cs:__imp_SetThreadLocale
0x18001206c  lea     rax, aAppid; "APPID"
0x180012073  mov     [rsp+68h+var_48], rax
0x180012078  lea     rax, a74174a0330ce4a; "{74174a03-30ce-4a50-a440-bc969cb4d475}"
0x18001207f  mov     [rsp+68h+var_40], rax
0x180012084  xorps   xmm0, xmm0
0x180012087  movdqu  [rsp+68h+var_38], xmm0
0x18001208d  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180012092  mov     r8d, 1; int
0x180012098  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18001209d  mov     ebx, eax
0x18001209f  test    eax, eax
0x1800120a1  js      short loc_18001211F
0x1800120a3  xor     ebx, ebx
0x1800120a5  mov     rdi, cs:off_180096140
0x1800120ac  mov     rax, cs:off_180096148
0x1800120b3  jmp     short loc_1800120FC
0x1800120b5  mov     rsi, [rdi]
0x1800120b8  test    rsi, rsi
0x1800120bb  jz      short loc_1800120F8
0x1800120bd  mov     ecx, 1
0x1800120c2  mov     rax, [rsi+8]
0x1800120c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120cb  mov     ebx, eax
0x1800120cd  test    eax, eax
0x1800120cf  js      short loc_180012101
0x1800120d1  mov     rax, [rsi+38h]
0x1800120d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120da  mov     r8d, 1; int
0x1800120e0  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800120e3  mov     rcx, [rsi]; rguid
0x1800120e6  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800120eb  mov     ebx, eax
0x1800120ed  test    eax, eax
0x1800120ef  js      short loc_180012101
0x1800120f1  mov     rax, cs:off_180096148
0x1800120f8  add     rdi, 8
0x1800120fc  cmp     rdi, rax
0x1800120ff  jb      short loc_1800120B5
0x180012101  test    ebx, ebx
0x180012103  js      short loc_18001211F
0x180012105  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18001210c  test    rax, rax
0x18001210f  jz      short loc_18001211F
0x180012111  mov     rcx, cs:hModule
0x180012118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001211d  mov     ebx, eax
0x18001211f  mov     ecx, ebp; Locale
0x180012121  call    cs:__imp_SetThreadLocale
0x180012127  mov     eax, ebx
0x180012129  add     rsp, 48h
0x18001212d  pop     rdi
0x18001212e  pop     rsi
0x18001212f  pop     rbp
0x180012130  pop     rbx
0x180012131  retn
```
