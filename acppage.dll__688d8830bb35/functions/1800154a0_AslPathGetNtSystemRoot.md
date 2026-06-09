# AslPathGetNtSystemRoot

- ea: `0x1800154a0`
- end: `0x180015513`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800137e0`
- `0x180015050`

## callees

- `0x1800154a0`
- `0x180017010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800154f8`
- `KERNEL32!FreeLibrary` at `0x1800154f8`
- `KERNEL32!LoadLibraryExW` at `0x1800154ca`
- `KERNEL32!LoadLibraryExW` at `0x1800154ca`
- `KERNEL32!GetProcAddress` at `0x1800154e2`
- `KERNEL32!GetProcAddress` at `0x1800154e2`

## string_xrefs

- `0x1800154b8`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_180020DF0;
  if ( !qword_180020DF0 )
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
    qword_180020DF0 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x1800154a0  mov     [rsp+arg_0], rbx
0x1800154a5  push    rdi
0x1800154a6  sub     rsp, 20h
0x1800154aa  mov     rbx, cs:qword_180020DF0
0x1800154b1  test    rbx, rbx
0x1800154b4  jnz     short loc_180015505
0x1800154b6  xor     edx, edx; hFile
0x1800154b8  lea     rcx, ModuleName; "ntdll.dll"
0x1800154bf  mov     r8d, 800h; dwFlags
0x1800154c5  mov     ebx, 7FFE0030h
0x1800154ca  call    cs:__imp_LoadLibraryExW
0x1800154d0  mov     rdi, rax
0x1800154d3  test    rax, rax
0x1800154d6  jz      short loc_1800154FE
0x1800154d8  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x1800154df  mov     rcx, rax; hModule
0x1800154e2  call    cs:__imp_GetProcAddress
0x1800154e8  test    rax, rax
0x1800154eb  jz      short loc_1800154F5
0x1800154ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154f2  mov     rbx, rax
0x1800154f5  mov     rcx, rdi; hLibModule
0x1800154f8  call    cs:__imp_FreeLibrary
0x1800154fe  mov     cs:qword_180020DF0, rbx
0x180015505  mov     rax, rbx
0x180015508  mov     rbx, [rsp+28h+arg_0]
0x18001550d  add     rsp, 20h
0x180015511  pop     rdi
0x180015512  retn
```
