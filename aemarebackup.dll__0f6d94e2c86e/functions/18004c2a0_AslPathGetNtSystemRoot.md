# AslPathGetNtSystemRoot

- ea: `0x18004c2a0`
- end: `0x18004c313`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180046ed4`
- `0x180049234`
- `0x18004aaa4`

## callees

- `0x18004c2a0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c2e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c2e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c2f8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c2f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004c2ca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004c2ca`

## string_xrefs

- `0x18004c2b8`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_18011BF60;
  if ( !qword_18011BF60 )
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
    qword_18011BF60 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x18004c2a0  mov     [rsp+arg_0], rbx
0x18004c2a5  push    rdi
0x18004c2a6  sub     rsp, 20h
0x18004c2aa  mov     rbx, cs:qword_18011BF60
0x18004c2b1  test    rbx, rbx
0x18004c2b4  jnz     short loc_18004C305
0x18004c2b6  xor     edx, edx; hFile
0x18004c2b8  lea     rcx, LibFileName; "ntdll.dll"
0x18004c2bf  mov     r8d, 800h; dwFlags
0x18004c2c5  mov     ebx, 7FFE0030h
0x18004c2ca  call    cs:__imp_LoadLibraryExW
0x18004c2d0  mov     rdi, rax
0x18004c2d3  test    rax, rax
0x18004c2d6  jz      short loc_18004C2FE
0x18004c2d8  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18004c2df  mov     rcx, rax; hModule
0x18004c2e2  call    cs:__imp_GetProcAddress
0x18004c2e8  test    rax, rax
0x18004c2eb  jz      short loc_18004C2F5
0x18004c2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2f2  mov     rbx, rax
0x18004c2f5  mov     rcx, rdi; hLibModule
0x18004c2f8  call    cs:__imp_FreeLibrary
0x18004c2fe  mov     cs:qword_18011BF60, rbx
0x18004c305  mov     rax, rbx
0x18004c308  mov     rbx, [rsp+28h+arg_0]
0x18004c30d  add     rsp, 20h
0x18004c311  pop     rdi
0x18004c312  retn
```
