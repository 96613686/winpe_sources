# DLpLoadSecurityDll(void)

- ea: `0x180017008`
- end: `0x180017067`
- name: `?DLpLoadSecurityDll@@YAKXZ`
- size: `95`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012030`
- `0x1800120a0`
- `0x180012110`

## callees

- `0x180017008`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017026`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017045`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017026`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017057`

## string_xrefs

- `0x18001701f`: `API-MS-Win-Security-Base-L1-1-0.dll`
- `0x18001703e`: `advapi32.dll`

## pseudocode

```c
__int64 DLpLoadSecurityDll(void)
{
  unsigned int v0; // ebx

  v0 = 0;
  if ( !g_hInstSecurityDLL )
  {
    g_hInstSecurityDLL = LoadLibraryExW(L"API-MS-Win-Security-Base-L1-1-0.dll", 0, 8u);
    if ( !g_hInstSecurityDLL )
    {
      g_hInstSecurityDLL = LoadLibraryExW(L"advapi32.dll", 0, 8u);
      if ( !g_hInstSecurityDLL )
        return GetLastError();
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180017008  push    rbx
0x18001700a  sub     rsp, 20h
0x18001700e  xor     ebx, ebx
0x180017010  cmp     cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstSecurityDLL
0x180017017  jnz     short loc_18001705F
0x180017019  xor     edx, edx; hFile
0x18001701b  lea     r8d, [rbx+8]; dwFlags
0x18001701f  lea     rcx, aApiMsWinSecuri_0; "API-MS-Win-Security-Base-L1-1-0.dll"
0x180017026  call    cs:__imp_LoadLibraryExW
0x18001702c  mov     cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstSecurityDLL
0x180017033  test    rax, rax
0x180017036  jnz     short loc_18001705F
0x180017038  xor     edx, edx; hFile
0x18001703a  lea     r8d, [rbx+8]; dwFlags
0x18001703e  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180017045  call    cs:__imp_LoadLibraryExW
0x18001704b  mov     cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstSecurityDLL
0x180017052  test    rax, rax
0x180017055  jnz     short loc_18001705F
0x180017057  call    cs:__imp_GetLastError
0x18001705d  mov     ebx, eax
0x18001705f  mov     eax, ebx
0x180017061  add     rsp, 20h
0x180017065  pop     rbx
0x180017066  retn
```
