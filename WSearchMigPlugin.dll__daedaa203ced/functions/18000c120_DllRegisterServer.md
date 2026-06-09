# DllRegisterServer

- ea: `0x18000c120`
- end: `0x18000c1ea`
- name: `DllRegisterServer`
- size: `202`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000ad54`
- `0x18000b224`
- `0x18000c120`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000c13f`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000c1d9`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000c13f`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000c1d9`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000c132`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000c132`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  const wchar_t *v1; // rdx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rdi
  __int64 *i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rsi
  __int64 v5; // rcx
  HRESULT v6; // ebx
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v2 = off_180025520;
  for ( i = off_180025528; v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v2 )
  {
    v4 = *v2;
    if ( *v2 )
    {
      v6 = (*((__int64 (__fastcall **)(__int64))v4 + 1))(1);
      if ( v6 < 0 )
        goto LABEL_8;
      v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (__fastcall **)(__int64))v4 + 7))(v5);
      v6 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v7, 1);
      if ( v6 < 0 )
        goto LABEL_8;
      i = off_180025528;
    }
  }
  v6 = ATL::AtlRegisterTypeLib(off_180025518, v1);
LABEL_8:
  if ( v6 >= 0 && ATL::_pPerfRegFunc )
    v6 = ATL::_pPerfRegFunc(hModule);
  SetThreadLocale(ThreadLocale);
  return v6;
}

```

## disassembly

```asm
0x18000c120  push    rbx
0x18000c122  push    rbp
0x18000c123  push    rsi
0x18000c124  push    rdi
0x18000c125  sub     rsp, 38h
0x18000c129  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000c132  call    cs:__imp_GetThreadLocale
0x18000c138  mov     ebp, eax
0x18000c13a  mov     ecx, 800h; Locale
0x18000c13f  call    cs:__imp_SetThreadLocale
0x18000c145  nop
0x18000c146  xor     ebx, ebx
0x18000c148  mov     rdi, cs:off_180025520
0x18000c14f  mov     rcx, cs:off_180025528
0x18000c156  cmp     rdi, rcx
0x18000c159  jnb     short loc_18000C1AB
0x18000c15b  mov     rsi, [rdi]
0x18000c15e  test    rsi, rsi
0x18000c161  jz      short loc_18000C19E
0x18000c163  mov     ecx, 1
0x18000c168  mov     rax, [rsi+8]
0x18000c16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c171  mov     ebx, eax
0x18000c173  test    eax, eax
0x18000c175  js      short loc_18000C1B9
0x18000c177  mov     rax, [rsi+38h]
0x18000c17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c180  mov     r8d, 1; int
0x18000c186  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000c189  mov     rcx, [rsi]; rguid
0x18000c18c  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000c191  mov     ebx, eax
0x18000c193  test    eax, eax
0x18000c195  js      short loc_18000C1B9
0x18000c197  mov     rcx, cs:off_180025528
0x18000c19e  add     rdi, 8
0x18000c1a2  cmp     rdi, rcx
0x18000c1a5  jb      short loc_18000C15B
0x18000c1a7  test    ebx, ebx
0x18000c1a9  js      short loc_18000C1D7
0x18000c1ab  mov     rcx, cs:off_180025518; HINSTANCE
0x18000c1b2  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEB_W@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,wchar_t const *)
0x18000c1b7  mov     ebx, eax
0x18000c1b9  test    ebx, ebx
0x18000c1bb  js      short loc_18000C1D7
0x18000c1bd  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x18000c1c4  test    rax, rax
0x18000c1c7  jz      short loc_18000C1D7
0x18000c1c9  mov     rcx, cs:hModule
0x18000c1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1d5  mov     ebx, eax
0x18000c1d7  mov     ecx, ebp; Locale
0x18000c1d9  call    cs:__imp_SetThreadLocale
0x18000c1df  mov     eax, ebx
0x18000c1e1  add     rsp, 38h
0x18000c1e5  pop     rdi
0x18000c1e6  pop     rsi
0x18000c1e7  pop     rbp
0x18000c1e8  pop     rbx
0x18000c1e9  retn
```
