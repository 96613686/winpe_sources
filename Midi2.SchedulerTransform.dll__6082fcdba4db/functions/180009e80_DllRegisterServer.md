# DllRegisterServer

- ea: `0x180009e80`
- end: `0x180009f62`
- name: `DllRegisterServer`
- size: `226`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180009de0`

## callees

- `0x1800085f4`
- `0x1800090b0`
- `0x180009e80`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009e96`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009f51`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009e96`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009f51`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009e89`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009e89`

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
  v9[1] = L"{2ac669ca-18ca-4e7d-951e-b6cc511c96fc}";
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
0x180009e80  push    rbx
0x180009e82  push    rbp
0x180009e83  push    rsi
0x180009e84  push    rdi
0x180009e85  sub     rsp, 48h
0x180009e89  call    cs:__imp_GetThreadLocale
0x180009e8f  mov     ebp, eax
0x180009e91  mov     ecx, 800h; Locale
0x180009e96  call    cs:__imp_SetThreadLocale
0x180009e9c  lea     rax, aAppid; "APPID"
0x180009ea3  mov     [rsp+68h+var_48], rax
0x180009ea8  lea     rax, a2ac669ca18ca4e; "{2ac669ca-18ca-4e7d-951e-b6cc511c96fc}"
0x180009eaf  mov     [rsp+68h+var_40], rax
0x180009eb4  xorps   xmm0, xmm0
0x180009eb7  movdqu  [rsp+68h+var_38], xmm0
0x180009ebd  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180009ec2  mov     r8d, 1; int
0x180009ec8  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180009ecd  mov     ebx, eax
0x180009ecf  test    eax, eax
0x180009ed1  js      short loc_180009F4F
0x180009ed3  xor     ebx, ebx
0x180009ed5  mov     rdi, cs:off_180015100
0x180009edc  mov     rax, cs:off_180015108
0x180009ee3  jmp     short loc_180009F2C
0x180009ee5  mov     rsi, [rdi]
0x180009ee8  test    rsi, rsi
0x180009eeb  jz      short loc_180009F28
0x180009eed  mov     ecx, 1
0x180009ef2  mov     rax, [rsi+8]
0x180009ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009efb  mov     ebx, eax
0x180009efd  test    eax, eax
0x180009eff  js      short loc_180009F31
0x180009f01  mov     rax, [rsi+38h]
0x180009f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f0a  mov     r8d, 1; int
0x180009f10  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009f13  mov     rcx, [rsi]; rguid
0x180009f16  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009f1b  mov     ebx, eax
0x180009f1d  test    eax, eax
0x180009f1f  js      short loc_180009F31
0x180009f21  mov     rax, cs:off_180015108
0x180009f28  add     rdi, 8
0x180009f2c  cmp     rdi, rax
0x180009f2f  jb      short loc_180009EE5
0x180009f31  test    ebx, ebx
0x180009f33  js      short loc_180009F4F
0x180009f35  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180009f3c  test    rax, rax
0x180009f3f  jz      short loc_180009F4F
0x180009f41  mov     rcx, cs:hModule
0x180009f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f4d  mov     ebx, eax
0x180009f4f  mov     ecx, ebp; Locale
0x180009f51  call    cs:__imp_SetThreadLocale
0x180009f57  mov     eax, ebx
0x180009f59  add     rsp, 48h
0x180009f5d  pop     rdi
0x180009f5e  pop     rsi
0x180009f5f  pop     rbp
0x180009f60  pop     rbx
0x180009f61  retn
```
