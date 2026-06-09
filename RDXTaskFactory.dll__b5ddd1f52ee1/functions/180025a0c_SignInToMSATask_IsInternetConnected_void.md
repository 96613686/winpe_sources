# SignInToMSATask::IsInternetConnected(void)

- ea: `0x180025a0c`
- end: `0x180025a70`
- name: `?IsInternetConnected@SignInToMSATask@@AEAA_NXZ`
- size: `100`
- prototype: `bool __fastcall(SignInToMSATask *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800253f0`

## callees

- `0x180024afc`
- `0x180025a0c`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025a27`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025a27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025a41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025a41`

## string_xrefs

- `0x180025a20`: `connect.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall SignInToMSATask::IsInternetConnected(SignInToMSATask *this)
{
  bool v1; // bl
  HMODULE Library; // rax
  unsigned int (*ProcAddress)(void); // rax
  SignInToMSATask *v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = this;
  v1 = 0;
  Library = LoadLibraryExW(L"connect.dll", 0, 0x800u);
  v5 = (SignInToMSATask *)Library;
  if ( Library )
  {
    ProcAddress = (unsigned int (*)(void))GetProcAddress(Library, "IsInternetConnected");
    if ( ProcAddress )
      v1 = ProcAddress() == 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v5);
  return v1;
}

```

## disassembly

```asm
0x180025a0c  mov     [rsp+arg_0], rcx
0x180025a11  push    rbx
0x180025a12  sub     rsp, 20h
0x180025a16  xor     bl, bl
0x180025a18  xor     edx, edx; hFile
0x180025a1a  mov     r8d, 800h; dwFlags
0x180025a20  lea     rcx, LibFileName; "connect.dll"
0x180025a27  call    cs:__imp_LoadLibraryExW
0x180025a2d  mov     [rsp+28h+arg_0], rax
0x180025a32  test    rax, rax
0x180025a35  jz      short loc_180025A5E
0x180025a37  lea     rdx, aIsinternetconn; "IsInternetConnected"
0x180025a3e  mov     rcx, rax; hModule
0x180025a41  call    cs:__imp_GetProcAddress
0x180025a47  test    rax, rax
0x180025a4a  jz      short loc_180025A5E
0x180025a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a51  movzx   ebx, bl
0x180025a54  mov     ecx, 1
0x180025a59  test    eax, eax
0x180025a5b  cmovz   ebx, ecx
0x180025a5e  lea     rcx, [rsp+28h+arg_0]
0x180025a63  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180025a68  mov     al, bl
0x180025a6a  add     rsp, 20h
0x180025a6e  pop     rbx
0x180025a6f  retn
```
