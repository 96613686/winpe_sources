# CallSetProcessWin32Capabilities(tagPROCESS_WIN32_CAPABILITIES *,ulong)

- ea: `0x18001096c`
- end: `0x180010a0d`
- name: `?CallSetProcessWin32Capabilities@@YAJPEAUtagPROCESS_WIN32_CAPABILITIES@@K@Z`
- size: `161`
- prototype: `__int64 __fastcall(struct tagPROCESS_WIN32_CAPABILITIES *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800103c0`
- `0x180010830`

## callees

- `0x1800090d4`
- `0x1800102fc`
- `0x18001096c`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800109a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800109a6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001098e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001098e`

## string_xrefs

- `0x180010987`: `user32.dll`

## pseudocode

```c
__int64 __fastcall CallSetProcessWin32Capabilities(struct tagPROCESS_WIN32_CAPABILITIES *a1, unsigned int a2)
{
  unsigned int (__fastcall *v2)(struct tagPROCESS_WIN32_CAPABILITIES *, _QWORD); // rax
  HMODULE LibraryW; // rax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE v9; // [rsp+40h] [rbp+18h] BYREF

  v2 = (unsigned int (__fastcall *)(struct tagPROCESS_WIN32_CAPABILITIES *, _QWORD))qword_18001C530;
  if ( !qword_18001C530 )
  {
    LibraryW = LoadLibraryW(L"user32.dll");
    v9 = LibraryW;
    if ( !LibraryW || (qword_18001C530 = (__int64)GetProcAddress(LibraryW, (LPCSTR)0xAF7)) == 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v9);
      return 2147549183LL;
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v9);
    v2 = (unsigned int (__fastcall *)(struct tagPROCESS_WIN32_CAPABILITIES *, _QWORD))qword_18001C530;
  }
  if ( v2(a1, a2) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x22,
             (unsigned int)"onecore\\base\\devices\\cam\\handler\\ntuser\\ntusercapabilityhandler.cpp",
             v6);
  else
    return 0;
}

```

## disassembly

```asm
0x18001096c  mov     [rsp+arg_0], rbx
0x180010971  push    rdi
0x180010972  sub     rsp, 20h
0x180010976  mov     rax, cs:qword_18001C530
0x18001097d  mov     ebx, edx
0x18001097f  mov     rdi, rcx
0x180010982  test    rax, rax
0x180010985  jnz     short loc_1800109C9
0x180010987  lea     rcx, LibFileName; "user32.dll"
0x18001098e  call    cs:__imp_LoadLibraryW
0x180010994  mov     [rsp+28h+arg_10], rax
0x180010999  test    rax, rax
0x18001099c  jz      short loc_1800109EF
0x18001099e  mov     edx, 0AF7h; lpProcName
0x1800109a3  mov     rcx, rax; hModule
0x1800109a6  call    cs:__imp_GetProcAddress
0x1800109ac  mov     cs:qword_18001C530, rax
0x1800109b3  test    rax, rax
0x1800109b6  jz      short loc_1800109EF
0x1800109b8  lea     rcx, [rsp+28h+arg_10]
0x1800109bd  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800109c2  mov     rax, cs:qword_18001C530
0x1800109c9  mov     edx, ebx
0x1800109cb  mov     rcx, rdi
0x1800109ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d3  test    eax, eax
0x1800109d5  jz      short loc_180010A00
0x1800109d7  mov     rcx, [rsp+28h]; this
0x1800109dc  lea     r8, aOnecoreBaseDev_1; "onecore\\base\\devices\\cam\\handler\\n"...
0x1800109e3  mov     edx, 22h ; '"'; void *
0x1800109e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800109ed  jmp     short loc_180010A02
0x1800109ef  lea     rcx, [rsp+28h+arg_10]
0x1800109f4  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800109f9  mov     eax, 8000FFFFh
0x1800109fe  jmp     short loc_180010A02
0x180010a00  xor     eax, eax
0x180010a02  mov     rbx, [rsp+28h+arg_0]
0x180010a07  add     rsp, 20h
0x180010a0b  pop     rdi
0x180010a0c  retn
```
