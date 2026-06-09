# try_load_library_from_system_directory

- ea: `0x18000d434`
- end: `0x18000d4a7`
- name: `try_load_library_from_system_directory`
- size: `115`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000d434`
- `0x1800145d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000d445`
- `KERNEL32!LoadLibraryExW` at `0x18000d445`
- `KERNEL32!LoadLibraryExW` at `0x18000d498`
- `KERNEL32!GetLastError` at `0x18000d450`
- `KERNEL32!GetLastError` at `0x18000d450`

## pseudocode

```c
HMODULE __fastcall try_load_library_from_system_directory(wchar_t *String1)
{
  HMODULE result; // rax

  result = LoadLibraryExW(String1, 0, 0x800u);
  if ( !result )
  {
    if ( GetLastError() != 87 || !wcsncmp(String1, L"api-ms-", 7u) || !wcsncmp(String1, L"ext-ms-", 7u) )
      return 0;
    else
      return LoadLibraryExW(String1, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18000d434  push    rbx
0x18000d436  sub     rsp, 20h
0x18000d43a  xor     edx, edx; hFile
0x18000d43c  mov     r8d, 800h; dwFlags
0x18000d442  mov     rbx, rcx
0x18000d445  call    cs:__imp_LoadLibraryExW
0x18000d44b  test    rax, rax
0x18000d44e  jnz     short loc_18000D4A1
0x18000d450  call    cs:__imp_GetLastError
0x18000d456  cmp     eax, 57h ; 'W'
0x18000d459  jnz     short loc_18000D49F
0x18000d45b  lea     r8d, [rax-50h]; MaxCount
0x18000d45f  mov     rcx, rbx; String1
0x18000d462  lea     rdx, aApiMs; "api-ms-"
0x18000d469  call    wcsncmp
0x18000d46e  test    eax, eax
0x18000d470  jz      short loc_18000D49F
0x18000d472  mov     r8d, 7; MaxCount
0x18000d478  lea     rdx, aExtMs; "ext-ms-"
0x18000d47f  mov     rcx, rbx; String1
0x18000d482  call    wcsncmp
0x18000d487  test    eax, eax
0x18000d489  jz      short loc_18000D49F
0x18000d48b  xor     r8d, r8d
0x18000d48e  xor     edx, edx
0x18000d490  mov     rcx, rbx
0x18000d493  add     rsp, 20h
0x18000d497  pop     rbx
0x18000d498  jmp     cs:__imp_LoadLibraryExW
0x18000d49f  xor     eax, eax
0x18000d4a1  add     rsp, 20h
0x18000d4a5  pop     rbx
0x18000d4a6  retn
```
