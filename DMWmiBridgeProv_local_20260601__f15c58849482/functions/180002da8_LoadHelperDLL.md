# LoadHelperDLL

- ea: `0x180002da8`
- end: `0x180002e44`
- name: `LoadHelperDLL`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002c2c`

## callees

- `0x180002ca8`
- `0x180002da8`

## import_xrefs

- `msvcrt!free` at `0x180002def`
- `msvcrt!free` at `0x180002def`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e00`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002ddd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002ddd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002e2a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002e2a`

## pseudocode

```c
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
0x180002da8  mov     [rsp+arg_0], rbx
0x180002dad  push    rdi
0x180002dae  sub     rsp, 20h
0x180002db2  xor     ecx, ecx
0x180002db4  xor     eax, eax
0x180002db6  lock cmpxchg cs:g_hHelper, rcx
0x180002dbf  jnz     short loc_180002E36
0x180002dc1  call    GetHelperDllFullPath
0x180002dc6  mov     rbx, rax
0x180002dc9  test    rax, rax
0x180002dcc  jnz     short loc_180002DD5
0x180002dce  mov     eax, 80004005h
0x180002dd3  jmp     short loc_180002E38
0x180002dd5  xor     r8d, r8d; dwFlags
0x180002dd8  xor     edx, edx; hFile
0x180002dda  mov     rcx, rbx; lpLibFileName
0x180002ddd  call    cs:__imp_LoadLibraryExW
0x180002de4  nop     dword ptr [rax+rax+00h]
0x180002de9  mov     rcx, rbx; Block
0x180002dec  mov     rdi, rax
0x180002def  call    cs:__imp_free
0x180002df6  nop     dword ptr [rax+rax+00h]
0x180002dfb  test    rdi, rdi
0x180002dfe  jnz     short loc_180002E1A
0x180002e00  call    cs:__imp_GetLastError
0x180002e07  nop     dword ptr [rax+rax+00h]
0x180002e0c  test    eax, eax
0x180002e0e  jle     short loc_180002E38
0x180002e10  movzx   eax, ax
0x180002e13  or      eax, 80070000h
0x180002e18  jmp     short loc_180002E38
0x180002e1a  xor     eax, eax
0x180002e1c  lock cmpxchg cs:g_hHelper, rdi
0x180002e25  jz      short loc_180002E36
0x180002e27  mov     rcx, rdi; hLibModule
0x180002e2a  call    cs:__imp_FreeLibrary
0x180002e31  nop     dword ptr [rax+rax+00h]
0x180002e36  xor     eax, eax
0x180002e38  mov     rbx, [rsp+28h+arg_0]
0x180002e3d  add     rsp, 20h
0x180002e41  pop     rdi
0x180002e42  retn
```
