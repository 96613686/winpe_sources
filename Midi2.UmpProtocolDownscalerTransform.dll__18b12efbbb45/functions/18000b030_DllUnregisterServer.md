# DllUnregisterServer

- ea: `0x18000b030`
- end: `0x18000b103`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000aea0`

## callees

- `0x1800096b4`
- `0x18000a170`
- `0x18000b030`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000b039`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000b039`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b046`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b0f2`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b046`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000b0f2`

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
    v4 = off_18001B100;
    v5 = off_18001B108;
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
        v5 = off_18001B108;
      }
      ++v4;
    }
  }
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{1b2e6e7f-e780-4406-92e0-14f4b8b04552}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x18000b030  push    rbx
0x18000b032  push    rbp
0x18000b033  push    rsi
0x18000b034  push    rdi
0x18000b035  sub     rsp, 48h
0x18000b039  call    cs:__imp_GetThreadLocale
0x18000b03f  mov     ebp, eax
0x18000b041  mov     ecx, 800h; Locale
0x18000b046  call    cs:__imp_SetThreadLocale
0x18000b04c  nop
0x18000b04d  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000b054  test    rax, rax
0x18000b057  jz      short loc_18000B064
0x18000b059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b05e  mov     ebx, eax
0x18000b060  test    eax, eax
0x18000b062  js      short loc_18000B0BC
0x18000b064  xor     ebx, ebx
0x18000b066  mov     rdi, cs:off_18001B100
0x18000b06d  mov     rax, cs:off_18001B108
0x18000b074  jmp     short loc_18000B0B7
0x18000b076  mov     rsi, [rdi]
0x18000b079  test    rsi, rsi
0x18000b07c  jz      short loc_18000B0B3
0x18000b07e  mov     rax, [rsi+38h]
0x18000b082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b087  xor     r8d, r8d; int
0x18000b08a  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000b08d  mov     rcx, [rsi]; rguid
0x18000b090  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000b095  mov     ebx, eax
0x18000b097  test    eax, eax
0x18000b099  js      short loc_18000B0BC
0x18000b09b  xor     ecx, ecx
0x18000b09d  mov     rax, [rsi+8]
0x18000b0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0a6  mov     ebx, eax
0x18000b0a8  test    eax, eax
0x18000b0aa  js      short loc_18000B0BC
0x18000b0ac  mov     rax, cs:off_18001B108
0x18000b0b3  add     rdi, 8
0x18000b0b7  cmp     rdi, rax
0x18000b0ba  jb      short loc_18000B076
0x18000b0bc  test    ebx, ebx
0x18000b0be  js      short loc_18000B0F0
0x18000b0c0  lea     rax, aAppid; "APPID"
0x18000b0c7  mov     [rsp+68h+var_48], rax
0x18000b0cc  lea     rax, a1b2e6e7fE78044; "{1b2e6e7f-e780-4406-92e0-14f4b8b04552}"
0x18000b0d3  mov     [rsp+68h+var_40], rax
0x18000b0d8  xorps   xmm0, xmm0
0x18000b0db  movdqu  [rsp+68h+var_38], xmm0
0x18000b0e1  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000b0e6  xor     r8d, r8d; int
0x18000b0e9  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000b0ee  mov     ebx, eax
0x18000b0f0  mov     ecx, ebp; Locale
0x18000b0f2  call    cs:__imp_SetThreadLocale
0x18000b0f8  mov     eax, ebx
0x18000b0fa  add     rsp, 48h
0x18000b0fe  pop     rdi
0x18000b0ff  pop     rsi
0x18000b100  pop     rbp
0x18000b101  pop     rbx
0x18000b102  retn
```
