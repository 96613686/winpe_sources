# My_CM_MapCrToWin32Err(ulong,ulong)

- ea: `0x180029664`
- end: `0x1800296f3`
- name: `?My_CM_MapCrToWin32Err@@YAKKK@Z`
- size: `143`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180028df0`
- `0x18002900c`
- `0x1800290b8`
- `0x18002923c`
- `0x180029528`
- `0x1800296fc`

## callees

- `0x180029664`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800296d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800296dd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800296d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800296dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002967f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002969c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002967f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002969c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800296b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800296b4`

## string_xrefs

- `0x180029672`: `api-ms-win-devices-config-l1.dll`
- `0x18002968f`: `cfgmgr32.dll`

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
0x180029664  mov     [rsp+arg_0], rbx
0x180029669  push    rdi
0x18002966a  sub     rsp, 20h
0x18002966e  mov     ebx, ecx
0x180029670  xor     edx, edx; hFile
0x180029672  lea     rcx, LibFileName; "api-ms-win-devices-config-l1.dll"
0x180029679  mov     r8d, 800h; dwFlags
0x18002967f  call    cs:__imp_LoadLibraryExW
0x180029685  mov     rdi, rax
0x180029688  test    rax, rax
0x18002968b  jnz     short loc_1800296AA
0x18002968d  xor     edx, edx; hFile
0x18002968f  lea     rcx, aCfgmgr32Dll; "cfgmgr32.dll"
0x180029696  mov     r8d, 800h; dwFlags
0x18002969c  call    cs:__imp_LoadLibraryExW
0x1800296a2  mov     rdi, rax
0x1800296a5  test    rax, rax
0x1800296a8  jz      short loc_1800296E3
0x1800296aa  lea     rdx, aCmMapcrtowin32; "CM_MapCrToWin32Err"
0x1800296b1  mov     rcx, rdi; hModule
0x1800296b4  call    cs:__imp_GetProcAddress
0x1800296ba  test    rax, rax
0x1800296bd  jz      short loc_1800296DA
0x1800296bf  mov     edx, 0Dh
0x1800296c4  mov     ecx, ebx
0x1800296c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296cb  mov     rcx, rdi; hLibModule
0x1800296ce  mov     ebx, eax
0x1800296d0  call    cs:__imp_FreeLibrary
0x1800296d6  mov     eax, ebx
0x1800296d8  jmp     short loc_1800296E8
0x1800296da  mov     rcx, rdi; hLibModule
0x1800296dd  call    cs:__imp_FreeLibrary
0x1800296e3  mov     eax, 0Dh
0x1800296e8  mov     rbx, [rsp+28h+arg_0]
0x1800296ed  add     rsp, 20h
0x1800296f1  pop     rdi
0x1800296f2  retn
```
