# DLpLoadRegistryDll(void)

- ea: `0x140020dac`
- end: `0x140020e0d`
- name: `?DLpLoadRegistryDll@@YAKXZ`
- size: `97`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x140020d50`

## callees

- `0x140020dac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020e03`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140020dca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140020df1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140020dca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140020df1`

## string_xrefs

- `0x140020dc3`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x140020de6`: `advapi32.dll`

## pseudocode

```c
__int64 DLpLoadRegistryDll(void)
{
  unsigned int v0; // ebx

  v0 = 0;
  if ( !g_hInstRegistryDLL )
  {
    g_hInstRegistryDLL = LoadLibraryExW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll", 0, 8u);
    if ( !g_hInstRegistryDLL )
    {
      g_hInstRegistryDLL = LoadLibraryExW(L"advapi32.dll", 0, 8u);
      if ( !g_hInstRegistryDLL )
        return GetLastError();
    }
  }
  return v0;
}

```

## disassembly

```asm
0x140020dac  push    rbx
0x140020dae  sub     rsp, 20h
0x140020db2  xor     ebx, ebx
0x140020db4  cmp     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstRegistryDLL
0x140020dbb  jnz     short loc_140020DDC
0x140020dbd  xor     edx, edx; hFile
0x140020dbf  lea     r8d, [rbx+8]; dwFlags
0x140020dc3  lea     rcx, LibFileName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x140020dca  call    cs:__imp_LoadLibraryExW
0x140020dd0  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x140020dd7  test    rax, rax
0x140020dda  jz      short loc_140020DE4
0x140020ddc  mov     eax, ebx
0x140020dde  add     rsp, 20h
0x140020de2  pop     rbx
0x140020de3  retn
0x140020de4  xor     edx, edx; hFile
0x140020de6  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x140020ded  lea     r8d, [rdx+8]; dwFlags
0x140020df1  call    cs:__imp_LoadLibraryExW
0x140020df7  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x140020dfe  test    rax, rax
0x140020e01  jnz     short loc_140020DDC
0x140020e03  call    cs:__imp_GetLastError
0x140020e09  mov     ebx, eax
0x140020e0b  jmp     short loc_140020DDC
```
