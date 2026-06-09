# ATL::CAtlDllModuleT<Windows::Globalization::Spelling::CSpellCheckModule>::DllUnregisterServer(int)

- ea: `0x18006bb20`
- end: `0x18006bbcd`
- name: `?DllUnregisterServer@?$CAtlDllModuleT@VCSpellCheckModule@Spelling@Globalization@Windows@@@ATL@@QEAAJH@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18006c8c0`

## callees

- `0x18006b53c`
- `0x18006bb20`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18006bb3c`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18006bbb5`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18006bb3c`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18006bbb5`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18006bb2f`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18006bb2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ATL::CAtlDllModuleT<Windows::Globalization::Spelling::CSpellCheckModule>::DllUnregisterServer()
{
  LCID ThreadLocale; // esi
  int v1; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v3; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax
  unsigned int v6; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (v1 = ATL::_pPerfUnRegFunc(), v1 >= 0) )
  {
    v1 = 0;
    v2 = off_1801209E0;
    v3 = off_1801209E8;
    while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
    {
      v4 = *v2;
      if ( *v2 )
      {
        v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v4 + 7))();
        v1 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 0);
        if ( v1 < 0 )
          break;
        v1 = (*((__int64 (__fastcall **)(_QWORD))v4 + 1))(0);
        if ( v1 < 0 )
          break;
        v3 = off_1801209E8;
      }
      ++v2;
    }
  }
  v6 = 0;
  if ( v1 < 0 )
    v6 = v1;
  SetThreadLocale(ThreadLocale);
  return v6;
}

```

## disassembly

```asm
0x18006bb20  mov     [rsp+arg_0], rbx
0x18006bb25  mov     [rsp+arg_8], rsi
0x18006bb2a  push    rdi
0x18006bb2b  sub     rsp, 20h
0x18006bb2f  call    cs:__imp_GetThreadLocale
0x18006bb35  mov     esi, eax
0x18006bb37  mov     ecx, 800h; Locale
0x18006bb3c  call    cs:__imp_SetThreadLocale
0x18006bb42  nop
0x18006bb43  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18006bb4a  test    rax, rax
0x18006bb4d  jz      short loc_18006BB58
0x18006bb4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb54  test    eax, eax
0x18006bb56  js      short loc_18006BBAC
0x18006bb58  xor     eax, eax
0x18006bb5a  mov     rbx, cs:off_1801209E0
0x18006bb61  mov     rcx, cs:off_1801209E8
0x18006bb68  jmp     short loc_18006BBA7
0x18006bb6a  mov     rdi, [rbx]
0x18006bb6d  test    rdi, rdi
0x18006bb70  jz      short loc_18006BBA3
0x18006bb72  mov     rax, [rdi+38h]
0x18006bb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb7b  xor     r8d, r8d; int
0x18006bb7e  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18006bb81  mov     rcx, [rdi]; rguid
0x18006bb84  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18006bb89  test    eax, eax
0x18006bb8b  js      short loc_18006BBAC
0x18006bb8d  xor     ecx, ecx
0x18006bb8f  mov     rax, [rdi+8]
0x18006bb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb98  test    eax, eax
0x18006bb9a  js      short loc_18006BBAC
0x18006bb9c  mov     rcx, cs:off_1801209E8
0x18006bba3  add     rbx, 8
0x18006bba7  cmp     rbx, rcx
0x18006bbaa  jb      short loc_18006BB6A
0x18006bbac  xor     ebx, ebx
0x18006bbae  test    eax, eax
0x18006bbb0  cmovs   ebx, eax
0x18006bbb3  mov     ecx, esi; Locale
0x18006bbb5  call    cs:__imp_SetThreadLocale
0x18006bbbb  mov     eax, ebx
0x18006bbbd  mov     rbx, [rsp+28h+arg_0]
0x18006bbc2  mov     rsi, [rsp+28h+arg_8]
0x18006bbc7  add     rsp, 20h
0x18006bbcb  pop     rdi
0x18006bbcc  retn
```
