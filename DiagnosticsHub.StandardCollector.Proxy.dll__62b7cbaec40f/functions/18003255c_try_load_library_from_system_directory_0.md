# try_load_library_from_system_directory_0

- ea: `0x18003255c`
- end: `0x1800325b6`
- name: `try_load_library_from_system_directory_0`
- size: `90`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800145d0`
- `0x18003255c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18003256d`
- `KERNEL32!LoadLibraryExW` at `0x18003256d`
- `KERNEL32!LoadLibraryExW` at `0x1800325a7`
- `KERNEL32!GetLastError` at `0x180032578`
- `KERNEL32!GetLastError` at `0x180032578`

## pseudocode

```c
HMODULE __fastcall try_load_library_from_system_directory_0(wchar_t *String1)
{
  HMODULE result; // rax

  result = LoadLibraryExW(String1, 0, 0x800u);
  if ( !result )
  {
    if ( GetLastError() != 87 || !wcsncmp(String1, L"api-ms-", 7u) )
      return 0;
    else
      return LoadLibraryExW(String1, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18003255c  push    rbx
0x18003255e  sub     rsp, 20h
0x180032562  xor     edx, edx; hFile
0x180032564  mov     r8d, 800h; dwFlags
0x18003256a  mov     rbx, rcx
0x18003256d  call    cs:__imp_LoadLibraryExW
0x180032573  test    rax, rax
0x180032576  jnz     short loc_1800325B0
0x180032578  call    cs:__imp_GetLastError
0x18003257e  cmp     eax, 57h ; 'W'
0x180032581  jnz     short loc_1800325AE
0x180032583  lea     r8d, [rax-50h]; MaxCount
0x180032587  mov     rcx, rbx; String1
0x18003258a  lea     rdx, aApiMs; "api-ms-"
0x180032591  call    wcsncmp
0x180032596  test    eax, eax
0x180032598  jz      short loc_1800325AE
0x18003259a  xor     r8d, r8d
0x18003259d  xor     edx, edx
0x18003259f  mov     rcx, rbx
0x1800325a2  add     rsp, 20h
0x1800325a6  pop     rbx
0x1800325a7  jmp     cs:__imp_LoadLibraryExW
0x1800325ae  xor     eax, eax
0x1800325b0  add     rsp, 20h
0x1800325b4  pop     rbx
0x1800325b5  retn
```
