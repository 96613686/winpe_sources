# Tsf3OverrideUtil::GetDeviceFamily(void)

- ea: `0x180047230`
- end: `0x1800472b4`
- name: `?GetDeviceFamily@Tsf3OverrideUtil@@YAKXZ`
- size: `132`
- prototype: `unsigned int __fastcall(Tsf3OverrideUtil *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800471c4`
- `0x18004faf4`
- `0x180096924`

## callees

- `0x180047230`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180047249`
- `KERNEL32!LoadLibraryExW` at `0x180047249`
- `KERNEL32!FreeLibrary` at `0x18004728a`
- `KERNEL32!FreeLibrary` at `0x18004729d`
- `KERNEL32!FreeLibrary` at `0x18004728a`
- `KERNEL32!FreeLibrary` at `0x18004729d`
- `KERNEL32!GetProcAddress` at `0x18004725c`
- `KERNEL32!GetProcAddress` at `0x18004725c`

## string_xrefs

- `0x180047242`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Tsf3OverrideUtil::GetDeviceFamily(Tsf3OverrideUtil *this)
{
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v3; // edi
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  ProcAddress = GetProcAddress(Library, "RtlGetDeviceFamilyInfoEnum");
  if ( ProcAddress )
  {
    v5 = 0;
    ((void (__fastcall *)(_QWORD, unsigned int *, _QWORD))ProcAddress)(0, &v5, 0);
    v3 = v5;
    if ( Library )
      FreeLibrary(Library);
    return v3;
  }
  else
  {
    if ( Library )
      FreeLibrary(Library);
    return 3;
  }
}

```

## disassembly

```asm
0x180047230  mov     [rsp+arg_8], rbx
0x180047235  push    rdi
0x180047236  sub     rsp, 20h
0x18004723a  xor     edx, edx; hFile
0x18004723c  mov     r8d, 800h; dwFlags
0x180047242  lea     rcx, ModuleName; "ntdll.dll"
0x180047249  call    cs:__imp_LoadLibraryExW
0x18004724f  mov     rbx, rax
0x180047252  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x180047259  mov     rcx, rax; hModule
0x18004725c  call    cs:__imp_GetProcAddress
0x180047262  test    rax, rax
0x180047265  jz      short loc_180047295
0x180047267  mov     [rsp+28h+arg_0], 0
0x18004726f  xor     r8d, r8d
0x180047272  lea     rdx, [rsp+28h+arg_0]
0x180047277  xor     ecx, ecx
0x180047279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004727e  mov     edi, [rsp+28h+arg_0]
0x180047282  test    rbx, rbx
0x180047285  jz      short loc_180047291
0x180047287  mov     rcx, rbx; hLibModule
0x18004728a  call    cs:__imp_FreeLibrary
0x180047290  nop
0x180047291  mov     eax, edi
0x180047293  jmp     short loc_1800472A9
0x180047295  test    rbx, rbx
0x180047298  jz      short loc_1800472A4
0x18004729a  mov     rcx, rbx; hLibModule
0x18004729d  call    cs:__imp_FreeLibrary
0x1800472a3  nop
0x1800472a4  mov     eax, 3
0x1800472a9  mov     rbx, [rsp+28h+arg_8]
0x1800472ae  add     rsp, 20h
0x1800472b2  pop     rdi
0x1800472b3  retn
```
