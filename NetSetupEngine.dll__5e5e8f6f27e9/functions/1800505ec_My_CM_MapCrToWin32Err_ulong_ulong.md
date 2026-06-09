# My_CM_MapCrToWin32Err(ulong,ulong)

- ea: `0x1800505ec`
- end: `0x18005067b`
- name: `?My_CM_MapCrToWin32Err@@YAKKK@Z`
- size: `143`
- prototype: `unsigned int __fastcall(unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f670`
- `0x18000ffb0`
- `0x180017814`
- `0x1800178c4`
- `0x18004490c`
- `0x18004e158`
- `0x18004e768`
- `0x1800502a8`
- `0x180050370`
- `0x180050558`
- `0x18007fee8`
- `0x18007ffcc`

## callees

- `0x1800505ec`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180050658`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180050665`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180050658`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180050665`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18005063c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18005063c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180050607`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180050624`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180050607`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180050624`

## string_xrefs

- `0x180050617`: `cfgmgr32.dll`
- `0x1800505fa`: `api-ms-win-devices-config-l1.dll`

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
0x1800505ec  mov     [rsp+arg_0], rbx
0x1800505f1  push    rdi
0x1800505f2  sub     rsp, 20h
0x1800505f6  mov     ebx, ecx
0x1800505f8  xor     edx, edx; hFile
0x1800505fa  lea     rcx, LibFileName; "api-ms-win-devices-config-l1.dll"
0x180050601  mov     r8d, 800h; dwFlags
0x180050607  call    cs:__imp_LoadLibraryExW
0x18005060d  mov     rdi, rax
0x180050610  test    rax, rax
0x180050613  jnz     short loc_180050632
0x180050615  xor     edx, edx; hFile
0x180050617  lea     rcx, aCfgmgr32Dll; "cfgmgr32.dll"
0x18005061e  mov     r8d, 800h; dwFlags
0x180050624  call    cs:__imp_LoadLibraryExW
0x18005062a  mov     rdi, rax
0x18005062d  test    rax, rax
0x180050630  jz      short loc_18005066B
0x180050632  lea     rdx, aCmMapcrtowin32; "CM_MapCrToWin32Err"
0x180050639  mov     rcx, rdi; hModule
0x18005063c  call    cs:__imp_GetProcAddress
0x180050642  test    rax, rax
0x180050645  jz      short loc_180050662
0x180050647  mov     edx, 0Dh
0x18005064c  mov     ecx, ebx
0x18005064e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050653  mov     rcx, rdi; hLibModule
0x180050656  mov     ebx, eax
0x180050658  call    cs:__imp_FreeLibrary
0x18005065e  mov     eax, ebx
0x180050660  jmp     short loc_180050670
0x180050662  mov     rcx, rdi; hLibModule
0x180050665  call    cs:__imp_FreeLibrary
0x18005066b  mov     eax, 0Dh
0x180050670  mov     rbx, [rsp+28h+arg_0]
0x180050675  add     rsp, 20h
0x180050679  pop     rdi
0x18005067a  retn
```
