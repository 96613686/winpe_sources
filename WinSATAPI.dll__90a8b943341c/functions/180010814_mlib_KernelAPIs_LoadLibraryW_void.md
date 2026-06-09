# mlib::KernelAPIs::LoadLibraryW(void)

- ea: `0x180010814`
- end: `0x1800108ec`
- name: `?LoadLibraryW@KernelAPIs@mlib@@QEAAKXZ`
- size: `216`
- prototype: `unsigned int __fastcall(mlib::KernelAPIs *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180010744`
- `0x1800251a0`

## callees

- `0x180010814`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010853`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010872`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010891`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010853`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010872`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010891`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001083d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180010824`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180010824`

## string_xrefs

- `0x18001081d`: `Kernel32.dll`
- `0x18001086b`: `SetThreadPreferredUILanguages`
- `0x1800108cc`: `GetPhysicallyInstalledSystemMemory`

## pseudocode

```c
DWORD __fastcall mlib::KernelAPIs::LoadLibraryW(mlib::KernelAPIs *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax

  LibraryW = LoadLibraryW(L"Kernel32.dll");
  *(_QWORD *)this = LibraryW;
  if ( !LibraryW )
    return GetLastError();
  ProcAddress = GetProcAddress(LibraryW, "GetLogicalProcessorInformation");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !ProcAddress )
    return GetLastError();
  v5 = GetProcAddress(*(HMODULE *)this, "SetThreadPreferredUILanguages");
  *((_QWORD *)this + 2) = v5;
  if ( !v5 )
    return GetLastError();
  v6 = GetProcAddress(*(HMODULE *)this, "GetLocaleInfoEx");
  *((_QWORD *)this + 3) = v6;
  if ( !v6 )
    return GetLastError();
  v7 = GetProcAddress(*(HMODULE *)this, "GetNumberFormatEx");
  *((_QWORD *)this + 4) = v7;
  if ( !v7 )
    return GetLastError();
  *((_QWORD *)this + 5) = GetProcAddress(*(HMODULE *)this, "GetPhysicallyInstalledSystemMemory");
  return 0;
}

```

## disassembly

```asm
0x180010814  push    rbx
0x180010816  sub     rsp, 20h
0x18001081a  mov     rbx, rcx
0x18001081d  lea     rcx, aKernel32Dll_0; "Kernel32.dll"
0x180010824  call    cs:__imp_LoadLibraryW
0x18001082b  nop     dword ptr [rax+rax+00h]
0x180010830  mov     [rbx], rax
0x180010833  test    rax, rax
0x180010836  jnz     short loc_180010849
0x180010838  add     rsp, 20h
0x18001083c  pop     rbx
0x18001083d  jmp     cs:__imp_GetLastError
0x180010849  lea     rdx, aGetlogicalproc; "GetLogicalProcessorInformation"
0x180010850  mov     rcx, rax; hModule
0x180010853  call    cs:__imp_GetProcAddress
0x18001085a  nop     dword ptr [rax+rax+00h]
0x18001085f  mov     [rbx+8], rax
0x180010863  test    rax, rax
0x180010866  jz      short loc_180010838
0x180010868  mov     rcx, [rbx]; hModule
0x18001086b  lea     rdx, aSetthreadprefe; "SetThreadPreferredUILanguages"
0x180010872  call    cs:__imp_GetProcAddress
0x180010879  nop     dword ptr [rax+rax+00h]
0x18001087e  mov     [rbx+10h], rax
0x180010882  test    rax, rax
0x180010885  jz      short loc_180010838
0x180010887  mov     rcx, [rbx]; hModule
0x18001088a  lea     rdx, aGetlocaleinfoe; "GetLocaleInfoEx"
0x180010891  call    cs:__imp_GetProcAddress
0x180010898  nop     dword ptr [rax+rax+00h]
0x18001089d  mov     [rbx+18h], rax
0x1800108a1  test    rax, rax
0x1800108a4  jz      short loc_180010838
0x1800108a6  mov     rcx, [rbx]; hModule
0x1800108a9  lea     rdx, aGetnumberforma; "GetNumberFormatEx"
0x1800108b0  call    cs:__imp_GetProcAddress
0x1800108b7  nop     dword ptr [rax+rax+00h]
0x1800108bc  mov     [rbx+20h], rax
0x1800108c0  test    rax, rax
0x1800108c3  jz      loc_180010838
0x1800108c9  mov     rcx, [rbx]; hModule
0x1800108cc  lea     rdx, aGetphysicallyi; "GetPhysicallyInstalledSystemMemory"
0x1800108d3  call    cs:__imp_GetProcAddress
0x1800108da  nop     dword ptr [rax+rax+00h]
0x1800108df  mov     [rbx+28h], rax
0x1800108e3  xor     eax, eax
0x1800108e5  add     rsp, 20h
0x1800108e9  pop     rbx
0x1800108ea  retn
```
