# Microsoft::Diagnostics::UtcApiWrapper::Initialize(ulong)

- ea: `0x1800150f8`
- end: `0x18001515f`
- name: `?Initialize@UtcApiWrapper@Diagnostics@Microsoft@@QEAAJK@Z`
- size: `103`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcApiWrapper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x1800150f8`
- `0x18001a40c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015142`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015142`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015110`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015110`

## string_xrefs

- `0x180015103`: `utcapi.dll`
- `0x180015138`: `UtcCreateSessionHandle`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcApiWrapper::Initialize(Microsoft::Diagnostics::UtcApiWrapper *this)
{
  HMODULE Library; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  FARPROC ProcAddress; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Library = LoadLibraryExW(L"utcapi.dll", 0, 0x800u);
  *((_QWORD *)this + 1) = Library;
  if ( !Library )
  {
    v4 = 88;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"OneCore\\internal\\Base\\inc\\UtcApiWrapperex.h",
             v3);
  }
  ProcAddress = GetProcAddress(Library, "UtcCreateSessionHandle");
  if ( !ProcAddress )
  {
    v4 = 91;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"OneCore\\internal\\Base\\inc\\UtcApiWrapperex.h",
             v3);
  }
  return ((__int64 (__fastcall *)(Microsoft::Diagnostics::UtcApiWrapper *))ProcAddress)(this);
}

```

## disassembly

```asm
0x1800150f8  push    rbx
0x1800150fa  sub     rsp, 20h
0x1800150fe  mov     rbx, rcx
0x180015101  xor     edx, edx; hFile
0x180015103  lea     rcx, LibFileName; "utcapi.dll"
0x18001510a  mov     r8d, 800h; dwFlags
0x180015110  call    cs:__imp_LoadLibraryExW
0x180015116  mov     [rbx+8], rax
0x18001511a  test    rax, rax
0x18001511d  jnz     short loc_180015138
0x18001511f  lea     edx, [rax+58h]; void *
0x180015122  mov     rcx, [rsp+28h]; this
0x180015127  lea     r8, aOnecoreInterna_2; "OneCore\\internal\\Base\\inc\\UtcApiWra"...
0x18001512e  add     rsp, 20h
0x180015132  pop     rbx
0x180015133  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015138  lea     rdx, aUtccreatesessi; "UtcCreateSessionHandle"
0x18001513f  mov     rcx, rax; hModule
0x180015142  call    cs:__imp_GetProcAddress
0x180015148  test    rax, rax
0x18001514b  jnz     short loc_180015152
0x18001514d  lea     edx, [rax+5Bh]
0x180015150  jmp     short loc_180015122
0x180015152  mov     rcx, rbx
0x180015155  add     rsp, 20h
0x180015159  pop     rbx
0x18001515a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
