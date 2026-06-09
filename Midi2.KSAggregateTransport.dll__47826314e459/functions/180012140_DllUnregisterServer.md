# DllUnregisterServer

- ea: `0x180012140`
- end: `0x180012213`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180011fb0`

## callees

- `0x18000c204`
- `0x1800111b0`
- `0x180012140`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180012156`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180012202`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180012156`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180012202`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180012149`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180012149`

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
    v4 = off_180096140;
    v5 = off_180096148;
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
        v5 = off_180096148;
      }
      ++v4;
    }
  }
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{74174a03-30ce-4a50-a440-bc969cb4d475}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180012140  push    rbx
0x180012142  push    rbp
0x180012143  push    rsi
0x180012144  push    rdi
0x180012145  sub     rsp, 48h
0x180012149  call    cs:__imp_GetThreadLocale
0x18001214f  mov     ebp, eax
0x180012151  mov     ecx, 800h; Locale
0x180012156  call    cs:__imp_SetThreadLocale
0x18001215c  nop
0x18001215d  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180012164  test    rax, rax
0x180012167  jz      short loc_180012174
0x180012169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001216e  mov     ebx, eax
0x180012170  test    eax, eax
0x180012172  js      short loc_1800121CC
0x180012174  xor     ebx, ebx
0x180012176  mov     rdi, cs:off_180096140
0x18001217d  mov     rax, cs:off_180096148
0x180012184  jmp     short loc_1800121C7
0x180012186  mov     rsi, [rdi]
0x180012189  test    rsi, rsi
0x18001218c  jz      short loc_1800121C3
0x18001218e  mov     rax, [rsi+38h]
0x180012192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012197  xor     r8d, r8d; int
0x18001219a  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18001219d  mov     rcx, [rsi]; rguid
0x1800121a0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800121a5  mov     ebx, eax
0x1800121a7  test    eax, eax
0x1800121a9  js      short loc_1800121CC
0x1800121ab  xor     ecx, ecx
0x1800121ad  mov     rax, [rsi+8]
0x1800121b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121b6  mov     ebx, eax
0x1800121b8  test    eax, eax
0x1800121ba  js      short loc_1800121CC
0x1800121bc  mov     rax, cs:off_180096148
0x1800121c3  add     rdi, 8
0x1800121c7  cmp     rdi, rax
0x1800121ca  jb      short loc_180012186
0x1800121cc  test    ebx, ebx
0x1800121ce  js      short loc_180012200
0x1800121d0  lea     rax, aAppid; "APPID"
0x1800121d7  mov     [rsp+68h+var_48], rax
0x1800121dc  lea     rax, a74174a0330ce4a; "{74174a03-30ce-4a50-a440-bc969cb4d475}"
0x1800121e3  mov     [rsp+68h+var_40], rax
0x1800121e8  xorps   xmm0, xmm0
0x1800121eb  movdqu  [rsp+68h+var_38], xmm0
0x1800121f1  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x1800121f6  xor     r8d, r8d; int
0x1800121f9  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x1800121fe  mov     ebx, eax
0x180012200  mov     ecx, ebp; Locale
0x180012202  call    cs:__imp_SetThreadLocale
0x180012208  mov     eax, ebx
0x18001220a  add     rsp, 48h
0x18001220e  pop     rdi
0x18001220f  pop     rsi
0x180012210  pop     rbp
0x180012211  pop     rbx
0x180012212  retn
```
