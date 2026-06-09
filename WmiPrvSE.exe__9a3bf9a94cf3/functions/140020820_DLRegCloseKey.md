# DLRegCloseKey

- ea: `0x140020820`
- end: `0x1400208d2`
- name: `DLRegCloseKey`
- size: `178`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140004a4c`
- `0x14000d9e4`
- `0x140038410`

## callees

- `0x140020820`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002086a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002086a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400208cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140020887`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400208a6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140020887`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400208a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002084b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002084b`

## string_xrefs

- `0x14002087c`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x14002089f`: `advapi32.dll`

## pseudocode

```c
DWORD __fastcall DLRegCloseKey(__int64 a1)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  DWORD result; // eax

  ProcAddress = (FARPROC)qword_140061648;
  if ( qword_140061648 )
    return ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
  Library = g_hInstRegistryDLL;
  if ( g_hInstRegistryDLL
    || (Library = LoadLibraryExW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll", 0, 8u), (g_hInstRegistryDLL = Library) != 0)
    || (Library = LoadLibraryExW(L"advapi32.dll", 0, 8u), (g_hInstRegistryDLL = Library) != 0) )
  {
LABEL_3:
    ProcAddress = GetProcAddress(Library, "RegCloseKey");
    qword_140061648 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return GetLastError();
    return ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
  }
  result = GetLastError();
  if ( !result )
  {
    Library = g_hInstRegistryDLL;
    goto LABEL_3;
  }
  return result;
}

```

## disassembly

```asm
0x140020820  push    rbx
0x140020822  sub     rsp, 20h
0x140020826  mov     rax, cs:qword_140061648
0x14002082d  mov     rbx, rcx
0x140020830  test    rax, rax
0x140020833  jnz     short loc_14002085D
0x140020835  mov     rax, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstRegistryDLL
0x14002083c  test    rax, rax
0x14002083f  jz      short loc_14002087A
0x140020841  lea     rdx, ProcName; "RegCloseKey"
0x140020848  mov     rcx, rax; hModule
0x14002084b  call    cs:__imp_GetProcAddress
0x140020851  mov     cs:qword_140061648, rax
0x140020858  test    rax, rax
0x14002085b  jz      short loc_1400208C6
0x14002085d  mov     rcx, rbx
0x140020860  add     rsp, 20h
0x140020864  pop     rbx
0x140020865  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x14002086a  call    cs:__imp_GetLastError
0x140020870  test    eax, eax
0x140020872  jz      short loc_1400208BA
0x140020874  add     rsp, 20h
0x140020878  pop     rbx
0x140020879  retn
0x14002087a  xor     edx, edx; hFile
0x14002087c  lea     rcx, LibFileName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x140020883  lea     r8d, [rdx+8]; dwFlags
0x140020887  call    cs:__imp_LoadLibraryExW
0x14002088d  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x140020894  test    rax, rax
0x140020897  jnz     short loc_140020841
0x140020899  xor     edx, edx; hFile
0x14002089b  lea     r8d, [rax+8]; dwFlags
0x14002089f  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1400208a6  call    cs:__imp_LoadLibraryExW
0x1400208ac  mov     cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInstRegistryDLL
0x1400208b3  test    rax, rax
0x1400208b6  jnz     short loc_140020841
0x1400208b8  jmp     short loc_14002086A
0x1400208ba  mov     rax, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstRegistryDLL
0x1400208c1  jmp     loc_140020841
0x1400208c6  add     rsp, 20h
0x1400208ca  pop     rbx
0x1400208cb  jmp     cs:__imp_GetLastError
```
