# CallRegisterComponent(ushort const *,char *)

- ea: `0x18000b3fc`
- end: `0x18000b4cb`
- name: `?CallRegisterComponent@@YAJPEBGPEAD@Z`
- size: `207`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007250`
- `0x180007270`

## callees

- `0x18000b3fc`
- `0x18000b640`
- `0x18000d010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000b448`
- `msvcrt!wcscat_s` at `0x18000b448`
- `KERNEL32!LoadLibraryExW` at `0x18000b45b`
- `KERNEL32!LoadLibraryExW` at `0x18000b45b`
- `KERNEL32!GetSystemDirectoryW` at `0x18000b428`
- `KERNEL32!GetSystemDirectoryW` at `0x18000b428`
- `KERNEL32!FreeLibrary` at `0x18000b49b`
- `KERNEL32!FreeLibrary` at `0x18000b49b`
- `KERNEL32!GetProcAddress` at `0x18000b46f`
- `KERNEL32!GetProcAddress` at `0x18000b46f`

## string_xrefs

- `0x18000b48a`: `browscap.dll`
- `0x18000b437`: `\inetsrv\iisreg.dll`

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
    v6 = ((__int64 (__fastcall *)(const wchar_t *))ProcAddress)(L"browscap.dll");
  FreeLibrary(v4);
  return v6;
}

```

## disassembly

```asm
0x18000b3fc  mov     [rsp+arg_0], rbx
0x18000b401  push    rdi
0x18000b402  sub     rsp, 240h
0x18000b409  mov     rax, cs:__security_cookie
0x18000b410  xor     rax, rsp
0x18000b413  mov     [rsp+248h+var_18], rax
0x18000b41b  mov     rbx, rdx
0x18000b41e  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18000b423  mov     edx, 0F0h; uSize
0x18000b428  call    cs:__imp_GetSystemDirectoryW
0x18000b42e  dec     eax
0x18000b430  cmp     eax, 0EFh
0x18000b435  ja      short loc_18000B4A5
0x18000b437  lea     r8, aInetsrvIisregD; "\\inetsrv\\iisreg.dll"
0x18000b43e  mov     edx, 104h; SizeInWords
0x18000b443  lea     rcx, [rsp+248h+Buffer]; Destination
0x18000b448  call    cs:__imp_wcscat_s
0x18000b44e  xor     edx, edx; hFile
0x18000b450  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x18000b455  mov     r8d, 900h; dwFlags
0x18000b45b  call    cs:__imp_LoadLibraryExW
0x18000b461  mov     rdi, rax
0x18000b464  test    rax, rax
0x18000b467  jz      short loc_18000B4A5
0x18000b469  mov     rdx, rbx; lpProcName
0x18000b46c  mov     rcx, rax; hModule
0x18000b46f  call    cs:__imp_GetProcAddress
0x18000b475  mov     rcx, rax
0x18000b478  neg     rcx
0x18000b47b  sbb     ebx, ebx
0x18000b47d  not     ebx
0x18000b47f  and     ebx, 80004005h
0x18000b485  test    rax, rax
0x18000b488  jz      short loc_18000B498
0x18000b48a  lea     rcx, aBrowscapDll_0; "browscap.dll"
0x18000b491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b496  mov     ebx, eax
0x18000b498  mov     rcx, rdi; hLibModule
0x18000b49b  call    cs:__imp_FreeLibrary
0x18000b4a1  mov     eax, ebx
0x18000b4a3  jmp     short loc_18000B4AA
0x18000b4a5  mov     eax, 80070003h
0x18000b4aa  mov     rcx, [rsp+248h+var_18]
0x18000b4b2  xor     rcx, rsp; StackCookie
0x18000b4b5  call    __security_check_cookie
0x18000b4ba  mov     rbx, [rsp+248h+arg_0]
0x18000b4c2  add     rsp, 240h
0x18000b4c9  pop     rdi
0x18000b4ca  retn
```
