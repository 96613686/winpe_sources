# CallRegisterComponent(ushort const *,char *)

- ea: `0x180008254`
- end: `0x180008323`
- name: `?CallRegisterComponent@@YAJPEBGPEAD@Z`
- size: `207`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ca0`
- `0x180001cc0`

## callees

- `0x180008254`
- `0x180008410`
- `0x180009010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800082a0`
- `msvcrt!wcscat_s` at `0x1800082a0`
- `KERNEL32!LoadLibraryExW` at `0x1800082b3`
- `KERNEL32!LoadLibraryExW` at `0x1800082b3`
- `KERNEL32!GetSystemDirectoryW` at `0x180008280`
- `KERNEL32!GetSystemDirectoryW` at `0x180008280`
- `KERNEL32!GetProcAddress` at `0x1800082c7`
- `KERNEL32!GetProcAddress` at `0x1800082c7`
- `KERNEL32!FreeLibrary` at `0x1800082f3`
- `KERNEL32!FreeLibrary` at `0x1800082f3`

## string_xrefs

- `0x1800082e2`: `admwprox.dll`
- `0x18000828f`: `\inetsrv\iisreg.dll`

## pseudocode

```c
__int64 __fastcall CallRegisterComponent(const unsigned __int16 *a1, char *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v6; // ebx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0xF0u) - 1 > 0xEF )
    return 2147942403LL;
  wcscat_s(Buffer, 0x104u, L"\\inetsrv\\iisreg.dll");
  Library = LoadLibraryExW(Buffer, 0, 0x900u);
  v4 = Library;
  if ( !Library )
    return 2147942403LL;
  ProcAddress = GetProcAddress(Library, a2);
  v6 = ProcAddress == 0 ? 0x80004005 : 0;
  if ( ProcAddress )
    v6 = ((__int64 (__fastcall *)(const wchar_t *))ProcAddress)(L"admwprox.dll");
  FreeLibrary(v4);
  return v6;
}

```

## disassembly

```asm
0x180008254  mov     [rsp+arg_0], rbx
0x180008259  push    rdi
0x18000825a  sub     rsp, 240h
0x180008261  mov     rax, cs:__security_cookie
0x180008268  xor     rax, rsp
0x18000826b  mov     [rsp+248h+var_18], rax
0x180008273  mov     rbx, rdx
0x180008276  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18000827b  mov     edx, 0F0h; uSize
0x180008280  call    cs:__imp_GetSystemDirectoryW
0x180008286  dec     eax
0x180008288  cmp     eax, 0EFh
0x18000828d  ja      short loc_1800082FD
0x18000828f  lea     r8, aInetsrvIisregD; "\\inetsrv\\iisreg.dll"
0x180008296  mov     edx, 104h; SizeInWords
0x18000829b  lea     rcx, [rsp+248h+Buffer]; Destination
0x1800082a0  call    cs:__imp_wcscat_s
0x1800082a6  xor     edx, edx; hFile
0x1800082a8  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x1800082ad  mov     r8d, 900h; dwFlags
0x1800082b3  call    cs:__imp_LoadLibraryExW
0x1800082b9  mov     rdi, rax
0x1800082bc  test    rax, rax
0x1800082bf  jz      short loc_1800082FD
0x1800082c1  mov     rdx, rbx; lpProcName
0x1800082c4  mov     rcx, rax; hModule
0x1800082c7  call    cs:__imp_GetProcAddress
0x1800082cd  mov     rcx, rax
0x1800082d0  neg     rcx
0x1800082d3  sbb     ebx, ebx
0x1800082d5  not     ebx
0x1800082d7  and     ebx, 80004005h
0x1800082dd  test    rax, rax
0x1800082e0  jz      short loc_1800082F0
0x1800082e2  lea     rcx, aAdmwproxDll_0; "admwprox.dll"
0x1800082e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082ee  mov     ebx, eax
0x1800082f0  mov     rcx, rdi; hLibModule
0x1800082f3  call    cs:__imp_FreeLibrary
0x1800082f9  mov     eax, ebx
0x1800082fb  jmp     short loc_180008302
0x1800082fd  mov     eax, 80070003h
0x180008302  mov     rcx, [rsp+248h+var_18]
0x18000830a  xor     rcx, rsp; StackCookie
0x18000830d  call    __security_check_cookie
0x180008312  mov     rbx, [rsp+248h+arg_0]
0x18000831a  add     rsp, 240h
0x180008321  pop     rdi
0x180008322  retn
```
