# DllUnregisterServer

- ea: `0x180009dc0`
- end: `0x180009e93`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180009c30`

## callees

- `0x180008444`
- `0x180008f00`
- `0x180009dc0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009dd6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009e82`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009dd6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180009e82`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009dc9`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009dc9`

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
    v4 = off_180012100;
    v5 = off_180012108;
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
        v5 = off_180012108;
      }
      ++v4;
    }
  }
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{04CE96FD-36B2-41ED-8A3E-A5606951F766}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180009dc0  push    rbx
0x180009dc2  push    rbp
0x180009dc3  push    rsi
0x180009dc4  push    rdi
0x180009dc5  sub     rsp, 48h
0x180009dc9  call    cs:__imp_GetThreadLocale
0x180009dcf  mov     ebp, eax
0x180009dd1  mov     ecx, 800h; Locale
0x180009dd6  call    cs:__imp_SetThreadLocale
0x180009ddc  nop
0x180009ddd  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180009de4  test    rax, rax
0x180009de7  jz      short loc_180009DF4
0x180009de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dee  mov     ebx, eax
0x180009df0  test    eax, eax
0x180009df2  js      short loc_180009E4C
0x180009df4  xor     ebx, ebx
0x180009df6  mov     rdi, cs:off_180012100
0x180009dfd  mov     rax, cs:off_180012108
0x180009e04  jmp     short loc_180009E47
0x180009e06  mov     rsi, [rdi]
0x180009e09  test    rsi, rsi
0x180009e0c  jz      short loc_180009E43
0x180009e0e  mov     rax, [rsi+38h]
0x180009e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e17  xor     r8d, r8d; int
0x180009e1a  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009e1d  mov     rcx, [rsi]; rguid
0x180009e20  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009e25  mov     ebx, eax
0x180009e27  test    eax, eax
0x180009e29  js      short loc_180009E4C
0x180009e2b  xor     ecx, ecx
0x180009e2d  mov     rax, [rsi+8]
0x180009e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e36  mov     ebx, eax
0x180009e38  test    eax, eax
0x180009e3a  js      short loc_180009E4C
0x180009e3c  mov     rax, cs:off_180012108
0x180009e43  add     rdi, 8
0x180009e47  cmp     rdi, rax
0x180009e4a  jb      short loc_180009E06
0x180009e4c  test    ebx, ebx
0x180009e4e  js      short loc_180009E80
0x180009e50  lea     rax, aAppid; "APPID"
0x180009e57  mov     [rsp+68h+var_48], rax
0x180009e5c  lea     rax, a04ce96fd36b241; "{04CE96FD-36B2-41ED-8A3E-A5606951F766}"
0x180009e63  mov     [rsp+68h+var_40], rax
0x180009e68  xorps   xmm0, xmm0
0x180009e6b  movdqu  [rsp+68h+var_38], xmm0
0x180009e71  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180009e76  xor     r8d, r8d; int
0x180009e79  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180009e7e  mov     ebx, eax
0x180009e80  mov     ecx, ebp; Locale
0x180009e82  call    cs:__imp_SetThreadLocale
0x180009e88  mov     eax, ebx
0x180009e8a  add     rsp, 48h
0x180009e8e  pop     rdi
0x180009e8f  pop     rsi
0x180009e90  pop     rbp
0x180009e91  pop     rbx
0x180009e92  retn
```
