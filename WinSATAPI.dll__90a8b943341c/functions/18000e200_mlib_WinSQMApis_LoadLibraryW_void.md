# mlib::WinSQMApis::LoadLibraryW(void)

- ea: `0x18000e200`
- end: `0x18000e304`
- name: `?LoadLibraryW@WinSQMApis@mlib@@QEAAKXZ`
- size: `260`
- prototype: `unsigned int __fastcall(mlib::WinSQMApis *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001270`
- `0x180010650`

## callees

- `0x18000e200`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e23f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e25e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e27d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e29c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e2bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e2e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e23f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e25e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e27d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e29c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e2bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e2e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e229`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000e210`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000e210`

## string_xrefs

- `0x18000e209`: `ntdll.dll`

## pseudocode

```c
DWORD __fastcall mlib::WinSQMApis::LoadLibraryW(mlib::WinSQMApis *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax

  LibraryW = LoadLibraryW(L"ntdll.dll");
  *(_QWORD *)this = LibraryW;
  if ( !LibraryW )
    return GetLastError();
  ProcAddress = GetProcAddress(LibraryW, "WinSqmSetDWORD");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !ProcAddress )
    return GetLastError();
  v5 = GetProcAddress(*(HMODULE *)this, "WinSqmStartSession");
  *((_QWORD *)this + 2) = v5;
  if ( !v5 )
    return GetLastError();
  v6 = GetProcAddress(*(HMODULE *)this, "WinSqmEndSession");
  *((_QWORD *)this + 3) = v6;
  if ( !v6 )
    return GetLastError();
  v7 = GetProcAddress(*(HMODULE *)this, "WinSqmIncrementDWORD");
  *((_QWORD *)this + 4) = v7;
  if ( v7
    && (v8 = GetProcAddress(*(HMODULE *)this, "WinSqmSetString"), (*((_QWORD *)this + 5) = v8) != 0)
    && (v9 = GetProcAddress(*(HMODULE *)this, "WinSqmAddToStream"), (*((_QWORD *)this + 6) = v9) != 0) )
  {
    return 0;
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x18000e200  push    rbx
0x18000e202  sub     rsp, 20h
0x18000e206  mov     rbx, rcx
0x18000e209  lea     rcx, LibFileName; "ntdll.dll"
0x18000e210  call    cs:__imp_LoadLibraryW
0x18000e217  nop     dword ptr [rax+rax+00h]
0x18000e21c  mov     [rbx], rax
0x18000e21f  test    rax, rax
0x18000e222  jnz     short loc_18000E235
0x18000e224  add     rsp, 20h
0x18000e228  pop     rbx
0x18000e229  jmp     cs:__imp_GetLastError
0x18000e235  lea     rdx, ProcName; "WinSqmSetDWORD"
0x18000e23c  mov     rcx, rax; hModule
0x18000e23f  call    cs:__imp_GetProcAddress
0x18000e246  nop     dword ptr [rax+rax+00h]
0x18000e24b  mov     [rbx+8], rax
0x18000e24f  test    rax, rax
0x18000e252  jz      short loc_18000E224
0x18000e254  mov     rcx, [rbx]; hModule
0x18000e257  lea     rdx, aWinsqmstartses; "WinSqmStartSession"
0x18000e25e  call    cs:__imp_GetProcAddress
0x18000e265  nop     dword ptr [rax+rax+00h]
0x18000e26a  mov     [rbx+10h], rax
0x18000e26e  test    rax, rax
0x18000e271  jz      short loc_18000E224
0x18000e273  mov     rcx, [rbx]; hModule
0x18000e276  lea     rdx, aWinsqmendsessi; "WinSqmEndSession"
0x18000e27d  call    cs:__imp_GetProcAddress
0x18000e284  nop     dword ptr [rax+rax+00h]
0x18000e289  mov     [rbx+18h], rax
0x18000e28d  test    rax, rax
0x18000e290  jz      short loc_18000E224
0x18000e292  mov     rcx, [rbx]; hModule
0x18000e295  lea     rdx, aWinsqmincremen; "WinSqmIncrementDWORD"
0x18000e29c  call    cs:__imp_GetProcAddress
0x18000e2a3  nop     dword ptr [rax+rax+00h]
0x18000e2a8  mov     [rbx+20h], rax
0x18000e2ac  test    rax, rax
0x18000e2af  jz      loc_18000E224
0x18000e2b5  mov     rcx, [rbx]; hModule
0x18000e2b8  lea     rdx, aWinsqmsetstrin; "WinSqmSetString"
0x18000e2bf  call    cs:__imp_GetProcAddress
0x18000e2c6  nop     dword ptr [rax+rax+00h]
0x18000e2cb  mov     [rbx+28h], rax
0x18000e2cf  test    rax, rax
0x18000e2d2  jz      loc_18000E224
0x18000e2d8  mov     rcx, [rbx]; hModule
0x18000e2db  lea     rdx, aWinsqmaddtostr; "WinSqmAddToStream"
0x18000e2e2  call    cs:__imp_GetProcAddress
0x18000e2e9  nop     dword ptr [rax+rax+00h]
0x18000e2ee  mov     [rbx+30h], rax
0x18000e2f2  test    rax, rax
0x18000e2f5  jz      loc_18000E224
0x18000e2fb  xor     eax, eax
0x18000e2fd  add     rsp, 20h
0x18000e301  pop     rbx
0x18000e302  retn
```
