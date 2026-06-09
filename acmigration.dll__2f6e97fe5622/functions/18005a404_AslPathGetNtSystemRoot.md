# AslPathGetNtSystemRoot

- ea: `0x18005a404`
- end: `0x18005a477`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005377c`
- `0x18005a53c`
- `0x18005b258`
- `0x18005cd40`
- `0x18005f30c`

## callees

- `0x18005a404`
- `0x18006a010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18005a45c`
- `KERNEL32!FreeLibrary` at `0x18005a45c`
- `KERNEL32!LoadLibraryExW` at `0x18005a42e`
- `KERNEL32!LoadLibraryExW` at `0x18005a42e`
- `KERNEL32!GetProcAddress` at `0x18005a446`
- `KERNEL32!GetProcAddress` at `0x18005a446`

## string_xrefs

- `0x18005a41c`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_180097B70;
  if ( !qword_180097B70 )
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
    qword_180097B70 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x18005a404  mov     [rsp+arg_0], rbx
0x18005a409  push    rdi
0x18005a40a  sub     rsp, 20h
0x18005a40e  mov     rbx, cs:qword_180097B70
0x18005a415  test    rbx, rbx
0x18005a418  jnz     short loc_18005A469
0x18005a41a  xor     edx, edx; hFile
0x18005a41c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18005a423  mov     r8d, 800h; dwFlags
0x18005a429  mov     ebx, 7FFE0030h
0x18005a42e  call    cs:__imp_LoadLibraryExW
0x18005a434  mov     rdi, rax
0x18005a437  test    rax, rax
0x18005a43a  jz      short loc_18005A462
0x18005a43c  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18005a443  mov     rcx, rax; hModule
0x18005a446  call    cs:__imp_GetProcAddress
0x18005a44c  test    rax, rax
0x18005a44f  jz      short loc_18005A459
0x18005a451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a456  mov     rbx, rax
0x18005a459  mov     rcx, rdi; hLibModule
0x18005a45c  call    cs:__imp_FreeLibrary
0x18005a462  mov     cs:qword_180097B70, rbx
0x18005a469  mov     rax, rbx
0x18005a46c  mov     rbx, [rsp+28h+arg_0]
0x18005a471  add     rsp, 20h
0x18005a475  pop     rdi
0x18005a476  retn
```
