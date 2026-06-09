# try_load_library_from_system_directory_0

- ea: `0x180031dfc`
- end: `0x180031e56`
- name: `try_load_library_from_system_directory_0`
- size: `90`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180013e70`
- `0x180031dfc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180031e18`
- `KERNEL32!GetLastError` at `0x180031e18`
- `KERNEL32!LoadLibraryExW` at `0x180031e0d`
- `KERNEL32!LoadLibraryExW` at `0x180031e0d`
- `KERNEL32!LoadLibraryExW` at `0x180031e47`

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
0x180031dfc  push    rbx
0x180031dfe  sub     rsp, 20h
0x180031e02  xor     edx, edx; hFile
0x180031e04  mov     r8d, 800h; dwFlags
0x180031e0a  mov     rbx, rcx
0x180031e0d  call    cs:__imp_LoadLibraryExW
0x180031e13  test    rax, rax
0x180031e16  jnz     short loc_180031E50
0x180031e18  call    cs:__imp_GetLastError
0x180031e1e  cmp     eax, 57h ; 'W'
0x180031e21  jnz     short loc_180031E4E
0x180031e23  lea     r8d, [rax-50h]; MaxCount
0x180031e27  mov     rcx, rbx; String1
0x180031e2a  lea     rdx, aApiMs; "api-ms-"
0x180031e31  call    wcsncmp
0x180031e36  test    eax, eax
0x180031e38  jz      short loc_180031E4E
0x180031e3a  xor     r8d, r8d
0x180031e3d  xor     edx, edx
0x180031e3f  mov     rcx, rbx
0x180031e42  add     rsp, 20h
0x180031e46  pop     rbx
0x180031e47  jmp     cs:__imp_LoadLibraryExW
0x180031e4e  xor     eax, eax
0x180031e50  add     rsp, 20h
0x180031e54  pop     rbx
0x180031e55  retn
```
