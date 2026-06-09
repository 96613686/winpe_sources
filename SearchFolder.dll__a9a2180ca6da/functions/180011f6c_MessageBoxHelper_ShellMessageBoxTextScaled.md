# MessageBoxHelper::ShellMessageBoxTextScaled__

- ea: `0x180011f6c`
- end: `0x180012012`
- name: `MessageBoxHelper::ShellMessageBoxTextScaled__`
- size: `166`
- prototype: `__int64(__int64, HWND, __int64, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180013450`

## callees

- `0x180011f6c`
- `0x180012634`
- `0x180051010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180011ff3`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180011ff3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011fa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011fa6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011f8c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011f8c`

## string_xrefs

- `0x180011f85`: `shlwapi.dll`

## pseudocode

```c
__int64 MessageBoxHelper::ShellMessageBoxTextScaled__(__int64 a1, HWND a2, __int64 a3, ...)
{
  HINSTANCE v4; // rdi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v7; // eax
  unsigned int v8; // ebx
  HMODULE v10; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v10 = va_arg(va1, HMODULE);
  v4 = g_hinst;
  LibraryW = LoadLibraryW(L"shlwapi.dll");
  v10 = LibraryW;
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "ShellMessageBoxInternal")) != 0 )
    v7 = ((__int64 (__fastcall *)(HINSTANCE, HWND, __int64, __int64, __int64, int))ProcAddress)(
           v4,
           a2,
           1,
           9025,
           9024,
           16);
  else
    v7 = ShellMessageBoxW(v4, a2, (LPCWSTR)0x2341, (LPCWSTR)0x2340, 0x10u);
  v8 = v7;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((HMODULE *)va);
  return v8;
}

```

## disassembly

```asm
0x180011f6c  mov     [rsp+arg_0], rbx
0x180011f71  mov     [rsp+arg_18], r9
0x180011f76  push    rdi
0x180011f77  sub     rsp, 40h
0x180011f7b  mov     rbx, rdx
0x180011f7e  mov     rdi, cs:g_hinst
0x180011f85  lea     rcx, LibFileName; "shlwapi.dll"
0x180011f8c  call    cs:__imp_LoadLibraryW
0x180011f92  mov     [rsp+48h+arg_18], rax
0x180011f97  test    rax, rax
0x180011f9a  jz      short loc_180011FDB
0x180011f9c  lea     rdx, aShellmessagebo; "ShellMessageBoxInternal"
0x180011fa3  mov     rcx, rax; hModule
0x180011fa6  call    cs:__imp_GetProcAddress
0x180011fac  test    rax, rax
0x180011faf  jz      short loc_180011FDB
0x180011fb1  mov     [rsp+48h+var_20], 10h
0x180011fb9  mov     qword ptr [rsp+48h+fuStyle], 2340h
0x180011fc2  mov     r9d, 2341h
0x180011fc8  mov     r8d, 1
0x180011fce  mov     rdx, rbx
0x180011fd1  mov     rcx, rdi
0x180011fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fd9  jmp     short loc_180011FF9
0x180011fdb  mov     [rsp+48h+fuStyle], 10h; fuStyle
0x180011fe3  mov     r9d, 2340h; lpcTitle
0x180011fe9  lea     r8d, [r9+1]; lpcText
0x180011fed  mov     rdx, rbx; hWnd
0x180011ff0  mov     rcx, rdi; hAppInst
0x180011ff3  call    cs:__imp_ShellMessageBoxW
0x180011ff9  mov     ebx, eax
0x180011ffb  lea     rcx, [rsp+48h+arg_18]
0x180012000  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180012005  mov     eax, ebx
0x180012007  mov     rbx, [rsp+48h+arg_0]
0x18001200c  add     rsp, 40h
0x180012010  pop     rdi
0x180012011  retn
```
