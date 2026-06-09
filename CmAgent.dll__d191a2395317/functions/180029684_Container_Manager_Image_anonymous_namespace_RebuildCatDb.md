# Container::Manager::Image::_anonymous_namespace_::RebuildCatDb

- ea: `0x180029684`
- end: `0x180029922`
- name: `Container::Manager::Image::_anonymous_namespace_::RebuildCatDb`
- size: `670`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180026b2c`

## callees

- `0x180002534`
- `0x1800045e4`
- `0x180007b2c`
- `0x180007b4c`
- `0x18000af30`
- `0x18000bb98`
- `0x180029684`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029861`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800298cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029861`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800298cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029836`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800297c8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800297c8`

## string_xrefs

- `0x1800296e6`: `Windows\System32`
- `0x180029749`: `CryptCatSvc.dll`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::RebuildCatDb(_QWORD *a1)
{
  __int64 v1; // rdx
  __int64 v2; // rdx
  HMODULE LibraryW; // rax
  const char *v5; // r9
  HMODULE v6; // rbx
  unsigned int LastError; // ebx
  FARPROC ProcAddress; // rax
  const char *v9; // r9
  int v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // eax
  const wchar_t *v13; // [rsp+20h] [rbp-50h]
  void *v14; // [rsp+30h] [rbp-40h] BYREF
  char *v15; // [rsp+38h] [rbp-38h]
  _WORD v16[8]; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+50h] [rbp-20h] BYREF
  _WORD v18[8]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v14 = v16;
  v15 = (char *)v16;
  v16[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &v14,
                           *a1,
                           (__int64)(a1[1] - *a1) >> 1) )
  {
    v1 = 1189;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v1,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v13);
LABEL_12:
    if ( v14 != v16 )
      operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v13 = L"Windows\\System32";
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)&v14) )
  {
    v1 = 1190;
    goto LABEL_3;
  }
  lpLibFileName[0] = v18;
  lpLibFileName[1] = v18;
  v18[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpLibFileName,
                           v14,
                           (v15 - (_BYTE *)v14) >> 1) )
  {
    v2 = 1193;
    goto LABEL_10;
  }
  v13 = L"CryptCatSvc.dll";
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)lpLibFileName) )
  {
    v2 = 1194;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v13);
    if ( lpLibFileName[0] != v18 )
      operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_12;
  }
  LibraryW = LoadLibraryW(lpLibFileName[0]);
  v6 = LibraryW;
  if ( !LibraryW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4AD,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
                  v5);
    if ( lpLibFileName[0] != v18 )
      operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v14 != v16 )
      operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
    return LastError;
  }
  ProcAddress = GetProcAddress(LibraryW, "CatDbOfflineRebuildDatabasesW");
  if ( !ProcAddress )
  {
    v10 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x4B3,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
            v9);
LABEL_23:
    v11 = v10;
    FreeLibrary(v6);
    if ( lpLibFileName[0] != v18 )
      operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v14 != v16 )
      operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
    return v11;
  }
  v12 = ((__int64 (__fastcall *)(void *, _QWORD))ProcAddress)(v14, 0);
  if ( v12 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4B5,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
            (const char *)v12,
            (unsigned int)L"CryptCatSvc.dll");
    goto LABEL_23;
  }
  FreeLibrary(v6);
  if ( lpLibFileName[0] != v18 )
    operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v14 != v16 )
    operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180029684  mov     [rsp-8+arg_0], rbx
0x180029689  mov     [rsp-8+arg_8], rdi
0x18002968e  push    rbp
0x18002968f  mov     rbp, rsp
0x180029692  sub     rsp, 70h
0x180029696  lea     rax, [rbp+var_30]
0x18002969a  mov     [rbp+var_40], rax
0x18002969e  lea     rax, [rbp+var_30]
0x1800296a2  mov     [rbp+var_38], rax
0x1800296a6  xor     eax, eax
0x1800296a8  mov     [rbp+var_30], ax
0x1800296ac  mov     r8, [rcx+8]
0x1800296b0  sub     r8, [rcx]
0x1800296b3  sar     r8, 1
0x1800296b6  mov     rdx, [rcx]
0x1800296b9  lea     rcx, [rbp+var_40]
0x1800296bd  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800296c2  test    al, al
0x1800296c4  jnz     short loc_1800296E6
0x1800296c6  mov     edx, 4A5h; void *
0x1800296cb  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800296d2  mov     r9d, 8007000Eh; char *
0x1800296d8  mov     rcx, [rbp+8]; this
0x1800296dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800296e1  jmp     loc_1800297A1
0x1800296e6  lea     rax, aWindowsSystem3_1; "Windows\\System32"
0x1800296ed  mov     [rbp+var_50], rax
0x1800296f1  mov     [rbp+var_48], 10h
0x1800296f9  lea     rdx, [rbp+var_50]
0x1800296fd  lea     rcx, [rbp+var_40]; this
0x180029701  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180029706  test    al, al
0x180029708  jnz     short loc_180029711
0x18002970a  mov     edx, 4A6h
0x18002970f  jmp     short loc_1800296CB
0x180029711  lea     rax, [rbp+var_10]
0x180029715  mov     [rbp+lpLibFileName], rax
0x180029719  lea     rax, [rbp+var_10]
0x18002971d  mov     [rbp+var_18], rax
0x180029721  xor     eax, eax
0x180029723  mov     [rbp+var_10], ax
0x180029727  mov     rdx, [rbp+var_40]
0x18002972b  mov     r8, [rbp+var_38]
0x18002972f  sub     r8, rdx
0x180029732  sar     r8, 1
0x180029735  lea     rcx, [rbp+lpLibFileName]
0x180029739  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002973e  test    al, al
0x180029740  jnz     short loc_180029749
0x180029742  mov     edx, 4A9h
0x180029747  jmp     short loc_180029772
0x180029749  lea     rax, aCryptcatsvcDll; "CryptCatSvc.dll"
0x180029750  mov     [rbp+var_50], rax
0x180029754  mov     [rbp+var_48], 0Fh
0x18002975c  lea     rdx, [rbp+var_50]
0x180029760  lea     rcx, [rbp+lpLibFileName]; this
0x180029764  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x180029769  test    al, al
0x18002976b  jnz     short loc_1800297C4
0x18002976d  mov     edx, 4AAh; void *
0x180029772  mov     r9d, 8007000Eh; char *
0x180029778  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x18002977f  mov     rcx, [rbp+8]; this
0x180029783  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029788  lea     rax, [rbp+var_10]
0x18002978c  mov     rcx, [rbp+lpLibFileName]; void *
0x180029790  cmp     rcx, rax
0x180029793  jz      short loc_1800297A1
0x180029795  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002979c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800297a1  lea     rax, [rbp+var_30]
0x1800297a5  mov     rcx, [rbp+var_40]; void *
0x1800297a9  cmp     rcx, rax
0x1800297ac  jz      short loc_1800297BA
0x1800297ae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800297b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800297ba  mov     eax, 8007000Eh
0x1800297bf  jmp     loc_18002990F
0x1800297c4  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800297c8  call    cs:__imp_LoadLibraryW
0x1800297cf  nop     dword ptr [rax+rax+00h]
0x1800297d4  mov     rbx, rax
0x1800297d7  test    rax, rax
0x1800297da  jnz     short loc_18002982C
0x1800297dc  mov     rcx, [rbp+8]; this
0x1800297e0  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800297e7  mov     edx, 4ADh; void *
0x1800297ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800297f1  mov     ebx, eax
0x1800297f3  mov     rcx, [rbp+lpLibFileName]; void *
0x1800297f7  lea     rax, [rbp+var_10]
0x1800297fb  cmp     rcx, rax
0x1800297fe  jz      short loc_18002980C
0x180029800  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029807  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002980c  mov     rcx, [rbp+var_40]; void *
0x180029810  lea     rax, [rbp+var_30]
0x180029814  cmp     rcx, rax
0x180029817  jz      short loc_180029825
0x180029819  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029820  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029825  mov     eax, ebx
0x180029827  jmp     loc_18002990F
0x18002982c  lea     rdx, aCatdbofflinere; "CatDbOfflineRebuildDatabasesW"
0x180029833  mov     rcx, rbx; hModule
0x180029836  call    cs:__imp_GetProcAddress
0x18002983d  nop     dword ptr [rax+rax+00h]
0x180029842  test    rax, rax
0x180029845  jnz     short loc_1800298A3
0x180029847  mov     rcx, [rbp+8]; this
0x18002984b  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x180029852  mov     edx, 4B3h; void *
0x180029857  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002985c  mov     edi, eax
0x18002985e  mov     rcx, rbx; hLibModule
0x180029861  call    cs:__imp_FreeLibrary
0x180029868  nop     dword ptr [rax+rax+00h]
0x18002986d  lea     rax, [rbp+var_10]
0x180029871  mov     rcx, [rbp+lpLibFileName]; void *
0x180029875  cmp     rcx, rax
0x180029878  jz      short loc_180029886
0x18002987a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029881  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029886  mov     rcx, [rbp+var_40]; void *
0x18002988a  lea     rax, [rbp+var_30]
0x18002988e  cmp     rcx, rax
0x180029891  jz      short loc_18002989F
0x180029893  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002989a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002989f  mov     eax, edi
0x1800298a1  jmp     short loc_18002990F
0x1800298a3  xor     edx, edx
0x1800298a5  mov     rcx, [rbp+var_40]
0x1800298a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298ae  test    eax, eax
0x1800298b0  jz      short loc_1800298CC
0x1800298b2  mov     rcx, [rbp+8]; this
0x1800298b6  mov     r9d, eax; char *
0x1800298b9  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1800298c0  mov     edx, 4B5h; void *
0x1800298c5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800298ca  jmp     short loc_18002985C
0x1800298cc  mov     rcx, rbx; hLibModule
0x1800298cf  call    cs:__imp_FreeLibrary
0x1800298d6  nop     dword ptr [rax+rax+00h]
0x1800298db  mov     rcx, [rbp+lpLibFileName]; void *
0x1800298df  lea     rax, [rbp+var_10]
0x1800298e3  cmp     rcx, rax
0x1800298e6  jz      short loc_1800298F4
0x1800298e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800298ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800298f4  mov     rcx, [rbp+var_40]; void *
0x1800298f8  lea     rax, [rbp+var_30]
0x1800298fc  cmp     rcx, rax
0x1800298ff  jz      short loc_18002990D
0x180029901  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029908  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002990d  xor     eax, eax
0x18002990f  lea     r11, [rsp+70h+var_s0]
0x180029914  mov     rbx, [r11+10h]
0x180029918  mov     rdi, [r11+18h]
0x18002991c  mov     rsp, r11
0x18002991f  pop     rbp
0x180029920  retn
```
