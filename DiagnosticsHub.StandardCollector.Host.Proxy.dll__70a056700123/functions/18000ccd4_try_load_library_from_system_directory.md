# try_load_library_from_system_directory

- ea: `0x18000ccd4`
- end: `0x18000cd47`
- name: `try_load_library_from_system_directory`
- size: `115`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ccd4`
- `0x180013e70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ccf0`
- `KERNEL32!GetLastError` at `0x18000ccf0`
- `KERNEL32!LoadLibraryExW` at `0x18000cce5`
- `KERNEL32!LoadLibraryExW` at `0x18000cce5`
- `KERNEL32!LoadLibraryExW` at `0x18000cd38`

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
0x18000ccd4  push    rbx
0x18000ccd6  sub     rsp, 20h
0x18000ccda  xor     edx, edx; hFile
0x18000ccdc  mov     r8d, 800h; dwFlags
0x18000cce2  mov     rbx, rcx
0x18000cce5  call    cs:__imp_LoadLibraryExW
0x18000cceb  test    rax, rax
0x18000ccee  jnz     short loc_18000CD41
0x18000ccf0  call    cs:__imp_GetLastError
0x18000ccf6  cmp     eax, 57h ; 'W'
0x18000ccf9  jnz     short loc_18000CD3F
0x18000ccfb  lea     r8d, [rax-50h]; MaxCount
0x18000ccff  mov     rcx, rbx; String1
0x18000cd02  lea     rdx, aApiMs; "api-ms-"
0x18000cd09  call    wcsncmp
0x18000cd0e  test    eax, eax
0x18000cd10  jz      short loc_18000CD3F
0x18000cd12  mov     r8d, 7; MaxCount
0x18000cd18  lea     rdx, aExtMs; "ext-ms-"
0x18000cd1f  mov     rcx, rbx; String1
0x18000cd22  call    wcsncmp
0x18000cd27  test    eax, eax
0x18000cd29  jz      short loc_18000CD3F
0x18000cd2b  xor     r8d, r8d
0x18000cd2e  xor     edx, edx
0x18000cd30  mov     rcx, rbx
0x18000cd33  add     rsp, 20h
0x18000cd37  pop     rbx
0x18000cd38  jmp     cs:__imp_LoadLibraryExW
0x18000cd3f  xor     eax, eax
0x18000cd41  add     rsp, 20h
0x18000cd45  pop     rbx
0x18000cd46  retn
```
