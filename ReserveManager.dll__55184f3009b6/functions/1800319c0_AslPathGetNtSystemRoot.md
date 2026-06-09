# AslPathGetNtSystemRoot

- ea: `0x1800319c0`
- end: `0x180031a33`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002f0f4`
- `0x180030964`

## callees

- `0x1800319c0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800319ea`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800319ea`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180031a18`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180031a18`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180031a02`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180031a02`

## string_xrefs

- `0x1800319d8`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_18004EC80;
  if ( !qword_18004EC80 )
  {
    v0 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v2 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v0 = ProcAddress();
      FreeLibrary(v2);
    }
    qword_18004EC80 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x1800319c0  mov     [rsp+arg_0], rbx
0x1800319c5  push    rdi
0x1800319c6  sub     rsp, 20h
0x1800319ca  mov     rbx, cs:qword_18004EC80
0x1800319d1  test    rbx, rbx
0x1800319d4  jnz     short loc_180031A25
0x1800319d6  xor     edx, edx; hFile
0x1800319d8  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800319df  mov     r8d, 800h; dwFlags
0x1800319e5  mov     ebx, 7FFE0030h
0x1800319ea  call    cs:__imp_LoadLibraryExW
0x1800319f0  mov     rdi, rax
0x1800319f3  test    rax, rax
0x1800319f6  jz      short loc_180031A1E
0x1800319f8  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x1800319ff  mov     rcx, rax; hModule
0x180031a02  call    cs:__imp_GetProcAddress
0x180031a08  test    rax, rax
0x180031a0b  jz      short loc_180031A15
0x180031a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a12  mov     rbx, rax
0x180031a15  mov     rcx, rdi; hLibModule
0x180031a18  call    cs:__imp_FreeLibrary
0x180031a1e  mov     cs:qword_18004EC80, rbx
0x180031a25  mov     rax, rbx
0x180031a28  mov     rbx, [rsp+28h+arg_0]
0x180031a2d  add     rsp, 20h
0x180031a31  pop     rdi
0x180031a32  retn
```
