# GetCryptProcs(void)

- ea: `0x1800d970c`
- end: `0x1800d9773`
- name: `?GetCryptProcs@@YA_NXZ`
- size: `103`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800d957c`

## callees

- `0x1800d970c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d973b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9756`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d973b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9756`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d971f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d971f`

## string_xrefs

- `0x1800d9712`: `Crypt32.dll`

## pseudocode

```c
bool GetCryptProcs(void)
{
  HMODULE Library; // rax

  Library = LoadLibraryExW(L"Crypt32.dll", 0, 0x800u);
  g_hCrypt = Library;
  if ( Library )
  {
    g_pfnCryptProtectMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(Library, "CryptProtectMemory");
    g_pfnCryptUnprotectMemory = (int (*)(void *, unsigned int, unsigned int))GetProcAddress(
                                                                               g_hCrypt,
                                                                               "CryptUnprotectMemory");
    LOBYTE(Library) = g_pfnCryptProtectMemory != 0;
  }
  return (char)Library;
}

```

## disassembly

```asm
0x1800d970c  sub     rsp, 28h
0x1800d9710  xor     edx, edx; hFile
0x1800d9712  lea     rcx, aCrypt32Dll; "Crypt32.dll"
0x1800d9719  mov     r8d, 800h; dwFlags
0x1800d971f  call    cs:__imp_LoadLibraryExW
0x1800d9725  mov     cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hCrypt
0x1800d972c  test    rax, rax
0x1800d972f  jz      short loc_1800D976E
0x1800d9731  lea     rdx, aCryptprotectme; "CryptProtectMemory"
0x1800d9738  mov     rcx, rax; hModule
0x1800d973b  call    cs:__imp_GetProcAddress
0x1800d9741  mov     rcx, cs:?g_hCrypt@@3PEAUHINSTANCE__@@EA; hModule
0x1800d9748  lea     rdx, aCryptunprotect; "CryptUnprotectMemory"
0x1800d974f  mov     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x1800d9756  call    cs:__imp_GetProcAddress
0x1800d975c  cmp     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, 0; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x1800d9764  mov     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, rax; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x1800d976b  setnz   al
0x1800d976e  add     rsp, 28h
0x1800d9772  retn
```
