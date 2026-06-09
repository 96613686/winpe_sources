# My_CM_MapCrToWin32Err(ulong,ulong)

- ea: `0x180006360`
- end: `0x1800063ef`
- name: `?My_CM_MapCrToWin32Err@@YAKKK@Z`
- size: `143`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180005edc`
- `0x180005fbc`
- `0x180006208`

## callees

- `0x180006360`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800063b0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800063b0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800063cc`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800063d9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800063cc`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800063d9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000637b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180006398`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000637b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180006398`

## string_xrefs

- `0x18000636e`: `api-ms-win-devices-config-l1.dll`
- `0x18000638b`: `cfgmgr32.dll`

## pseudocode

```c
__int64 __fastcall My_CM_MapCrToWin32Err(unsigned int a1)
{
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v4; // ebx

  Library = LoadLibraryExW(L"api-ms-win-devices-config-l1.dll", 0, 0x800u);
  if ( Library || (Library = LoadLibraryExW(L"cfgmgr32.dll", 0, 0x800u)) != 0 )
  {
    ProcAddress = GetProcAddress(Library, "CM_MapCrToWin32Err");
    if ( ProcAddress )
    {
      v4 = ((__int64 (__fastcall *)(_QWORD, __int64))ProcAddress)(a1, 13);
      FreeLibrary(Library);
      return v4;
    }
    FreeLibrary(Library);
  }
  return 13;
}

```

## disassembly

```asm
0x180006360  mov     [rsp+arg_0], rbx
0x180006365  push    rdi
0x180006366  sub     rsp, 20h
0x18000636a  mov     ebx, ecx
0x18000636c  xor     edx, edx; hFile
0x18000636e  lea     rcx, LibFileName; "api-ms-win-devices-config-l1.dll"
0x180006375  mov     r8d, 800h; dwFlags
0x18000637b  call    cs:__imp_LoadLibraryExW
0x180006381  mov     rdi, rax
0x180006384  test    rax, rax
0x180006387  jnz     short loc_1800063A6
0x180006389  xor     edx, edx; hFile
0x18000638b  lea     rcx, aCfgmgr32Dll; "cfgmgr32.dll"
0x180006392  mov     r8d, 800h; dwFlags
0x180006398  call    cs:__imp_LoadLibraryExW
0x18000639e  mov     rdi, rax
0x1800063a1  test    rax, rax
0x1800063a4  jz      short loc_1800063DF
0x1800063a6  lea     rdx, aCmMapcrtowin32; "CM_MapCrToWin32Err"
0x1800063ad  mov     rcx, rdi; hModule
0x1800063b0  call    cs:__imp_GetProcAddress
0x1800063b6  test    rax, rax
0x1800063b9  jz      short loc_1800063D6
0x1800063bb  mov     edx, 0Dh
0x1800063c0  mov     ecx, ebx
0x1800063c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c7  mov     rcx, rdi; hLibModule
0x1800063ca  mov     ebx, eax
0x1800063cc  call    cs:__imp_FreeLibrary
0x1800063d2  mov     eax, ebx
0x1800063d4  jmp     short loc_1800063E4
0x1800063d6  mov     rcx, rdi; hLibModule
0x1800063d9  call    cs:__imp_FreeLibrary
0x1800063df  mov     eax, 0Dh
0x1800063e4  mov     rbx, [rsp+28h+arg_0]
0x1800063e9  add     rsp, 20h
0x1800063ed  pop     rdi
0x1800063ee  retn
```
