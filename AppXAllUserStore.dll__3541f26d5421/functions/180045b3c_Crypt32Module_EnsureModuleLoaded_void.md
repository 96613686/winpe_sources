# Crypt32Module::EnsureModuleLoaded(void)

- ea: `0x180045b3c`
- end: `0x180045ba5`
- name: `?EnsureModuleLoaded@Crypt32Module@@AEAAJXZ`
- size: `105`
- prototype: `__int64 __fastcall(Crypt32Module *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180045610`
- `0x1800456c4`
- `0x180045774`
- `0x180045824`
- `0x1800458dc`
- `0x18004598c`
- `0x180045a40`

## callees

- `0x18001a324`
- `0x18001fe4c`
- `0x180038508`
- `0x180045b3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180045b5a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180045b5a`

## string_xrefs

- `0x180045b4d`: `Crypt32.dll`

## pseudocode

```c
__int64 __fastcall Crypt32Module::EnsureModuleLoaded(Crypt32Module *this)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE Library; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_QWORD *)this )
    return 0;
  Library = LoadLibraryExW(L"Crypt32.dll", 0, 0x800u);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
    this,
    &Library);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
  if ( *(_QWORD *)this )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xE,
             (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\crypt32module.cpp",
             v2);
}

```

## disassembly

```asm
0x180045b3c  push    rbx
0x180045b3e  sub     rsp, 20h
0x180045b42  cmp     qword ptr [rcx], 0
0x180045b46  mov     rbx, rcx
0x180045b49  jnz     short loc_180045B9D
0x180045b4b  xor     edx, edx; hFile
0x180045b4d  lea     rcx, aCrypt32Dll; "Crypt32.dll"
0x180045b54  mov     r8d, 800h; dwFlags
0x180045b5a  call    cs:__imp_LoadLibraryExW
0x180045b60  lea     rdx, [rsp+28h+arg_0]
0x180045b65  mov     rcx, rbx
0x180045b68  mov     [rsp+28h+arg_0], rax
0x180045b6d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x180045b72  lea     rcx, [rsp+28h+arg_0]
0x180045b77  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180045b7c  cmp     qword ptr [rbx], 0
0x180045b80  jnz     short loc_180045B9D
0x180045b82  mov     rcx, [rsp+28h]; this
0x180045b87  lea     r8, aOnecoreAdminAp_20; "onecore\\admin\\appmodel\\appxalluserst"...
0x180045b8e  mov     edx, 0Eh; void *
0x180045b93  add     rsp, 20h
0x180045b97  pop     rbx
0x180045b98  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180045b9d  xor     eax, eax
0x180045b9f  add     rsp, 20h
0x180045ba3  pop     rbx
0x180045ba4  retn
```
