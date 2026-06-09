# DllUnregisterServer

- ea: `0x18000be90`
- end: `0x18000bf63`
- name: `DllUnregisterServer`
- size: `211`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000bd00`

## callees

- `0x18000a514`
- `0x18000afd0`
- `0x18000be90`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000be99`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000be99`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000bea6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000bf52`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000bea6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000bf52`

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
    v4 = off_18002D100;
    v5 = off_18002D108;
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
        v5 = off_18002D108;
      }
      ++v4;
    }
  }
  if ( updated >= 0 )
  {
    v9[0] = L"APPID";
    v9[1] = L"{42af54fc-9aba-4fe8-8ea2-d32d2a333a0c}";
    v10 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x18000be90  push    rbx
0x18000be92  push    rbp
0x18000be93  push    rsi
0x18000be94  push    rdi
0x18000be95  sub     rsp, 48h
0x18000be99  call    cs:__imp_GetThreadLocale
0x18000be9f  mov     ebp, eax
0x18000bea1  mov     ecx, 800h; Locale
0x18000bea6  call    cs:__imp_SetThreadLocale
0x18000beac  nop
0x18000bead  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000beb4  test    rax, rax
0x18000beb7  jz      short loc_18000BEC4
0x18000beb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bebe  mov     ebx, eax
0x18000bec0  test    eax, eax
0x18000bec2  js      short loc_18000BF1C
0x18000bec4  xor     ebx, ebx
0x18000bec6  mov     rdi, cs:off_18002D100
0x18000becd  mov     rax, cs:off_18002D108
0x18000bed4  jmp     short loc_18000BF17
0x18000bed6  mov     rsi, [rdi]
0x18000bed9  test    rsi, rsi
0x18000bedc  jz      short loc_18000BF13
0x18000bede  mov     rax, [rsi+38h]
0x18000bee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee7  xor     r8d, r8d; int
0x18000beea  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000beed  mov     rcx, [rsi]; rguid
0x18000bef0  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000bef5  mov     ebx, eax
0x18000bef7  test    eax, eax
0x18000bef9  js      short loc_18000BF1C
0x18000befb  xor     ecx, ecx
0x18000befd  mov     rax, [rsi+8]
0x18000bf01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf06  mov     ebx, eax
0x18000bf08  test    eax, eax
0x18000bf0a  js      short loc_18000BF1C
0x18000bf0c  mov     rax, cs:off_18002D108
0x18000bf13  add     rdi, 8
0x18000bf17  cmp     rdi, rax
0x18000bf1a  jb      short loc_18000BED6
0x18000bf1c  test    ebx, ebx
0x18000bf1e  js      short loc_18000BF50
0x18000bf20  lea     rax, aAppid; "APPID"
0x18000bf27  mov     [rsp+68h+var_48], rax
0x18000bf2c  lea     rax, a42af54fc9aba4f; "{42af54fc-9aba-4fe8-8ea2-d32d2a333a0c}"
0x18000bf33  mov     [rsp+68h+var_40], rax
0x18000bf38  xorps   xmm0, xmm0
0x18000bf3b  movdqu  [rsp+68h+var_38], xmm0
0x18000bf41  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18000bf46  xor     r8d, r8d; int
0x18000bf49  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000bf4e  mov     ebx, eax
0x18000bf50  mov     ecx, ebp; Locale
0x18000bf52  call    cs:__imp_SetThreadLocale
0x18000bf58  mov     eax, ebx
0x18000bf5a  add     rsp, 48h
0x18000bf5e  pop     rdi
0x18000bf5f  pop     rsi
0x18000bf60  pop     rbp
0x18000bf61  pop     rbx
0x18000bf62  retn
```
