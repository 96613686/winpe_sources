# DllUnregisterServer

- ea: `0x180009e50`
- end: `0x180009f23`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180009cc0`

## callees

- `0x1800084d4`
- `0x180008f90`
- `0x180009e50`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009e66`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009f12`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009e66`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009f12`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009e59`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009e59`

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
    v9[1] = L"{5A2E778A-2450-42A0-88E9-E9C04CA2BA62}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180009e50  push    rbx
0x180009e52  push    rbp
0x180009e53  push    rsi
0x180009e54  push    rdi
0x180009e55  sub     rsp, 48h
0x180009e59  call    cs:__imp_GetThreadLocale
0x180009e5f  mov     ebp, eax
0x180009e61  mov     ecx, 800h; Locale
0x180009e66  call    cs:__imp_SetThreadLocale
0x180009e6c  nop
0x180009e6d  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180009e74  test    rax, rax
0x180009e77  jz      short loc_180009E84
0x180009e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e7e  mov     ebx, eax
0x180009e80  test    eax, eax
0x180009e82  js      short loc_180009EDC
0x180009e84  xor     ebx, ebx
0x180009e86  mov     rdi, cs:off_180015100
0x180009e8d  mov     rax, cs:off_180015108
0x180009e94  jmp     short loc_180009ED7
0x180009e96  mov     rsi, [rdi]
0x180009e99  test    rsi, rsi
0x180009e9c  jz      short loc_180009ED3
0x180009e9e  mov     rax, [rsi+38h]
0x180009ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ea7  xor     r8d, r8d; int
0x180009eaa  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009ead  mov     rcx, [rsi]; rguid
0x180009eb0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009eb5  mov     ebx, eax
0x180009eb7  test    eax, eax
0x180009eb9  js      short loc_180009EDC
0x180009ebb  xor     ecx, ecx
0x180009ebd  mov     rax, [rsi+8]
0x180009ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ec6  mov     ebx, eax
0x180009ec8  test    eax, eax
0x180009eca  js      short loc_180009EDC
0x180009ecc  mov     rax, cs:off_180015108
0x180009ed3  add     rdi, 8
0x180009ed7  cmp     rdi, rax
0x180009eda  jb      short loc_180009E96
0x180009edc  test    ebx, ebx
0x180009ede  js      short loc_180009F10
0x180009ee0  lea     rax, aAppid; "APPID"
0x180009ee7  mov     [rsp+68h+var_48], rax
0x180009eec  lea     rax, a5a2e778a245042; "{5A2E778A-2450-42A0-88E9-E9C04CA2BA62}"
0x180009ef3  mov     [rsp+68h+var_40], rax
0x180009ef8  xorps   xmm0, xmm0
0x180009efb  movdqu  [rsp+68h+var_38], xmm0
0x180009f01  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180009f06  xor     r8d, r8d; int
0x180009f09  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180009f0e  mov     ebx, eax
0x180009f10  mov     ecx, ebp; Locale
0x180009f12  call    cs:__imp_SetThreadLocale
0x180009f18  mov     eax, ebx
0x180009f1a  add     rsp, 48h
0x180009f1e  pop     rdi
0x180009f1f  pop     rsi
0x180009f20  pop     rbp
0x180009f21  pop     rbx
0x180009f22  retn
```
