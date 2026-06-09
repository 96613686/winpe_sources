# BfspLoadVersionDll

- ea: `0x1800523b8`
- end: `0x1800523f8`
- name: `BfspLoadVersionDll`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005214c`

## callees

- `0x1800523b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800523d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800523d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800523e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800523e8`

## string_xrefs

- `0x1800523cf`: `version.dll`

## pseudocode

```c
__int64 BfspLoadVersionDll()
{
  unsigned int v0; // ebx

  v0 = 0;
  if ( !g_hInstVersionDLL )
  {
    g_hInstVersionDLL = LoadLibraryExW(L"version.dll", 0, 8u);
    if ( !g_hInstVersionDLL )
      return GetLastError();
  }
  return v0;
}

```

## disassembly

```asm
0x1800523b8  push    rbx
0x1800523ba  sub     rsp, 20h
0x1800523be  xor     ebx, ebx
0x1800523c0  cmp     cs:g_hInstVersionDLL, rbx
0x1800523c7  jnz     short loc_1800523F0
0x1800523c9  xor     edx, edx; hFile
0x1800523cb  lea     r8d, [rbx+8]; dwFlags
0x1800523cf  lea     rcx, aVersionDll; "version.dll"
0x1800523d6  call    cs:__imp_LoadLibraryExW
0x1800523dc  mov     cs:g_hInstVersionDLL, rax
0x1800523e3  test    rax, rax
0x1800523e6  jnz     short loc_1800523F0
0x1800523e8  call    cs:__imp_GetLastError
0x1800523ee  mov     ebx, eax
0x1800523f0  mov     eax, ebx
0x1800523f2  add     rsp, 20h
0x1800523f6  pop     rbx
0x1800523f7  retn
```
