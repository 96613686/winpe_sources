# DllUnregisterServer

- ea: `0x18000cf20`
- end: `0x18000cf86`
- name: `DllUnregisterServer`
- size: `102`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000cf20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000cf50`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000cf50`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000cf73`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000cf73`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18000cf31`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18000cf31`

## string_xrefs

- `0x18000cf2a`: `crypt32.dll`
- `0x18000cf46`: `CryptSIPRemoveProvider`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rdi
  FARPROC ProcAddress; // rax
  HRESULT v4; // ebx

  LibraryW = LoadLibraryW(L"crypt32.dll");
  v1 = LibraryW;
  if ( !LibraryW )
    return -2147467259;
  ProcAddress = GetProcAddress(LibraryW, "CryptSIPRemoveProvider");
  if ( ProcAddress )
  {
    ((void (__fastcall *)(GUID *))ProcAddress)(&gMSI);
    v4 = 0;
  }
  else
  {
    v4 = -2147467259;
  }
  FreeLibrary(v1);
  return v4;
}

```

## disassembly

```asm
0x18000cf20  mov     [rsp+arg_0], rbx
0x18000cf25  push    rdi
0x18000cf26  sub     rsp, 20h
0x18000cf2a  lea     rcx, aCrypt32Dll; "crypt32.dll"
0x18000cf31  call    cs:__imp_LoadLibraryW
0x18000cf37  mov     rdi, rax
0x18000cf3a  test    rax, rax
0x18000cf3d  jnz     short loc_18000CF46
0x18000cf3f  mov     eax, 80004005h
0x18000cf44  jmp     short loc_18000CF7B
0x18000cf46  lea     rdx, aCryptsipremove; "CryptSIPRemoveProvider"
0x18000cf4d  mov     rcx, rdi; hModule
0x18000cf50  call    cs:__imp_GetProcAddress
0x18000cf56  test    rax, rax
0x18000cf59  jnz     short loc_18000CF62
0x18000cf5b  mov     ebx, 80004005h
0x18000cf60  jmp     short loc_18000CF70
0x18000cf62  lea     rcx, ?gMSI@@3U_GUID@@A; _GUID gMSI
0x18000cf69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf6e  xor     ebx, ebx
0x18000cf70  mov     rcx, rdi; hLibModule
0x18000cf73  call    cs:__imp_FreeLibrary
0x18000cf79  mov     eax, ebx
0x18000cf7b  mov     rbx, [rsp+28h+arg_0]
0x18000cf80  add     rsp, 20h
0x18000cf84  pop     rdi
0x18000cf85  retn
```
