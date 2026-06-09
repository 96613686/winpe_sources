# CallRegisterComponent(ushort const *,char *)

- ea: `0x18001d4e0`
- end: `0x18001d5af`
- name: `?CallRegisterComponent@@YAJPEBGPEAD@Z`
- size: `207`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800169a0`
- `0x1800169c0`

## callees

- `0x18001d4e0`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18001d52c`
- `msvcrt!wcscat_s` at `0x18001d52c`
- `KERNEL32!GetSystemDirectoryW` at `0x18001d50c`
- `KERNEL32!GetSystemDirectoryW` at `0x18001d50c`
- `KERNEL32!GetProcAddress` at `0x18001d553`
- `KERNEL32!GetProcAddress` at `0x18001d553`
- `KERNEL32!FreeLibrary` at `0x18001d57f`
- `KERNEL32!FreeLibrary` at `0x18001d57f`
- `KERNEL32!LoadLibraryExW` at `0x18001d53f`
- `KERNEL32!LoadLibraryExW` at `0x18001d53f`

## string_xrefs

- `0x18001d56e`: `adsiis.dll`
- `0x18001d51b`: `\inetsrv\iisreg.dll`

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
    v6 = ((__int64 (__fastcall *)(const wchar_t *))ProcAddress)(L"adsiis.dll");
  FreeLibrary(v4);
  return v6;
}

```

## disassembly

```asm
0x18001d4e0  mov     [rsp+arg_0], rbx
0x18001d4e5  push    rdi
0x18001d4e6  sub     rsp, 240h
0x18001d4ed  mov     rax, cs:__security_cookie
0x18001d4f4  xor     rax, rsp
0x18001d4f7  mov     [rsp+248h+var_18], rax
0x18001d4ff  mov     rbx, rdx
0x18001d502  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18001d507  mov     edx, 0F0h; uSize
0x18001d50c  call    cs:__imp_GetSystemDirectoryW
0x18001d512  dec     eax
0x18001d514  cmp     eax, 0EFh
0x18001d519  ja      short loc_18001D589
0x18001d51b  lea     r8, aInetsrvIisregD; "\\inetsrv\\iisreg.dll"
0x18001d522  mov     edx, 104h; SizeInWords
0x18001d527  lea     rcx, [rsp+248h+Buffer]; Destination
0x18001d52c  call    cs:__imp_wcscat_s
0x18001d532  xor     edx, edx; hFile
0x18001d534  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x18001d539  mov     r8d, 900h; dwFlags
0x18001d53f  call    cs:__imp_LoadLibraryExW
0x18001d545  mov     rdi, rax
0x18001d548  test    rax, rax
0x18001d54b  jz      short loc_18001D589
0x18001d54d  mov     rdx, rbx; lpProcName
0x18001d550  mov     rcx, rax; hModule
0x18001d553  call    cs:__imp_GetProcAddress
0x18001d559  mov     rcx, rax
0x18001d55c  neg     rcx
0x18001d55f  sbb     ebx, ebx
0x18001d561  not     ebx
0x18001d563  and     ebx, 80004005h
0x18001d569  test    rax, rax
0x18001d56c  jz      short loc_18001D57C
0x18001d56e  lea     rcx, aAdsiisDll_0; "adsiis.dll"
0x18001d575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d57a  mov     ebx, eax
0x18001d57c  mov     rcx, rdi; hLibModule
0x18001d57f  call    cs:__imp_FreeLibrary
0x18001d585  mov     eax, ebx
0x18001d587  jmp     short loc_18001D58E
0x18001d589  mov     eax, 80070003h
0x18001d58e  mov     rcx, [rsp+248h+var_18]
0x18001d596  xor     rcx, rsp; StackCookie
0x18001d599  call    __security_check_cookie
0x18001d59e  mov     rbx, [rsp+248h+arg_0]
0x18001d5a6  add     rsp, 240h
0x18001d5ad  pop     rdi
0x18001d5ae  retn
```
