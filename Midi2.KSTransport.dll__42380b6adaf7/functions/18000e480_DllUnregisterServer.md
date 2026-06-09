# DllUnregisterServer

- ea: `0x18000e480`
- end: `0x18000e553`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000e2f0`

## callees

- `0x18000b684`
- `0x18000d4f0`
- `0x18000e480`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000e489`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000e489`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000e496`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000e542`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000e496`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000e542`

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
    v4 = off_180071140;
    v5 = off_180071148;
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
        v5 = off_180071148;
      }
      ++v4;
    }
  }
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{05244d43-856c-4948-82de-eae678ab9f6f}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x18000e480  push    rbx
0x18000e482  push    rbp
0x18000e483  push    rsi
0x18000e484  push    rdi
0x18000e485  sub     rsp, 48h
0x18000e489  call    cs:__imp_GetThreadLocale
0x18000e48f  mov     ebp, eax
0x18000e491  mov     ecx, 800h; Locale
0x18000e496  call    cs:__imp_SetThreadLocale
0x18000e49c  nop
0x18000e49d  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000e4a4  test    rax, rax
0x18000e4a7  jz      short loc_18000E4B4
0x18000e4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ae  mov     ebx, eax
0x18000e4b0  test    eax, eax
0x18000e4b2  js      short loc_18000E50C
0x18000e4b4  xor     ebx, ebx
0x18000e4b6  mov     rdi, cs:off_180071140
0x18000e4bd  mov     rax, cs:off_180071148
0x18000e4c4  jmp     short loc_18000E507
0x18000e4c6  mov     rsi, [rdi]
0x18000e4c9  test    rsi, rsi
0x18000e4cc  jz      short loc_18000E503
0x18000e4ce  mov     rax, [rsi+38h]
0x18000e4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4d7  xor     r8d, r8d; int
0x18000e4da  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000e4dd  mov     rcx, [rsi]; rguid
0x18000e4e0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000e4e5  mov     ebx, eax
0x18000e4e7  test    eax, eax
0x18000e4e9  js      short loc_18000E50C
0x18000e4eb  xor     ecx, ecx
0x18000e4ed  mov     rax, [rsi+8]
0x18000e4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4f6  mov     ebx, eax
0x18000e4f8  test    eax, eax
0x18000e4fa  js      short loc_18000E50C
0x18000e4fc  mov     rax, cs:off_180071148
0x18000e503  add     rdi, 8
0x18000e507  cmp     rdi, rax
0x18000e50a  jb      short loc_18000E4C6
0x18000e50c  test    ebx, ebx
0x18000e50e  js      short loc_18000E540
0x18000e510  lea     rax, aAppid; "APPID"
0x18000e517  mov     [rsp+68h+var_48], rax
0x18000e51c  lea     rax, a05244d43856c49; "{05244d43-856c-4948-82de-eae678ab9f6f}"
0x18000e523  mov     [rsp+68h+var_40], rax
0x18000e528  xorps   xmm0, xmm0
0x18000e52b  movdqu  [rsp+68h+var_38], xmm0
0x18000e531  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000e536  xor     r8d, r8d; int
0x18000e539  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000e53e  mov     ebx, eax
0x18000e540  mov     ecx, ebp; Locale
0x18000e542  call    cs:__imp_SetThreadLocale
0x18000e548  mov     eax, ebx
0x18000e54a  add     rsp, 48h
0x18000e54e  pop     rdi
0x18000e54f  pop     rsi
0x18000e550  pop     rbp
0x18000e551  pop     rbx
0x18000e552  retn
```
