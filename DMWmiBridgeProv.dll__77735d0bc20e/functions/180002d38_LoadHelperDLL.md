# LoadHelperDLL

- ea: `0x180002d38`
- end: `0x180002dbb`
- name: `LoadHelperDLL`
- size: `131`
- prototype: `signed int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002bdc`

## callees

- `0x180002c4c`
- `0x180002d38`

## import_xrefs

- `msvcrt!free` at `0x180002d79`
- `msvcrt!free` at `0x180002d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d84`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002d6d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002d6d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002da8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002da8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int LoadHelperDLL()
{
  const WCHAR *HelperDllFullPath; // rax
  WCHAR *v1; // rbx
  signed int result; // eax
  HMODULE Library; // rdi

  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hHelper, 0, 0) )
    return 0;
  HelperDllFullPath = (const WCHAR *)GetHelperDllFullPath();
  v1 = (WCHAR *)HelperDllFullPath;
  if ( !HelperDllFullPath )
    return -2147467259;
  Library = LoadLibraryExW(HelperDllFullPath, 0, 0);
  free(v1);
  if ( Library )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hHelper, (signed __int64)Library, 0) )
      FreeLibrary(Library);
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002d38  mov     [rsp+arg_0], rbx
0x180002d3d  push    rdi
0x180002d3e  sub     rsp, 20h
0x180002d42  xor     ecx, ecx
0x180002d44  xor     eax, eax
0x180002d46  lock cmpxchg cs:g_hHelper, rcx
0x180002d4f  jnz     short loc_180002DAE
0x180002d51  call    GetHelperDllFullPath
0x180002d56  mov     rbx, rax
0x180002d59  test    rax, rax
0x180002d5c  jnz     short loc_180002D65
0x180002d5e  mov     eax, 80004005h
0x180002d63  jmp     short loc_180002DB0
0x180002d65  xor     r8d, r8d; dwFlags
0x180002d68  xor     edx, edx; hFile
0x180002d6a  mov     rcx, rbx; lpLibFileName
0x180002d6d  call    cs:__imp_LoadLibraryExW
0x180002d73  mov     rcx, rbx; Block
0x180002d76  mov     rdi, rax
0x180002d79  call    cs:__imp_free
0x180002d7f  test    rdi, rdi
0x180002d82  jnz     short loc_180002D98
0x180002d84  call    cs:__imp_GetLastError
0x180002d8a  test    eax, eax
0x180002d8c  jle     short loc_180002DB0
0x180002d8e  movzx   eax, ax
0x180002d91  or      eax, 80070000h
0x180002d96  jmp     short loc_180002DB0
0x180002d98  xor     eax, eax
0x180002d9a  lock cmpxchg cs:g_hHelper, rdi
0x180002da3  jz      short loc_180002DAE
0x180002da5  mov     rcx, rdi; hLibModule
0x180002da8  call    cs:__imp_FreeLibrary
0x180002dae  xor     eax, eax
0x180002db0  mov     rbx, [rsp+28h+arg_0]
0x180002db5  add     rsp, 20h
0x180002db9  pop     rdi
0x180002dba  retn
```
