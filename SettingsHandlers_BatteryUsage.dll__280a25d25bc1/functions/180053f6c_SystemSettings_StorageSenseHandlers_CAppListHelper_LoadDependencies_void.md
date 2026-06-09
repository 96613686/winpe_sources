# SystemSettings::StorageSenseHandlers::CAppListHelper::LoadDependencies(void)

- ea: `0x180053f6c`
- end: `0x180054000`
- name: `?LoadDependencies@CAppListHelper@StorageSenseHandlers@SystemSettings@@AEAAJXZ`
- size: `148`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppListHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180031ce0`

## callees

- `0x180053f6c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180053f88`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180053f88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053fa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053fb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053fcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053fa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053fb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053fcb`

## string_xrefs

- `0x180053f7f`: `MSI.DLL`
- `0x180053fab`: `MsiGetProductInfoW`
- `0x180053f97`: `MsiEnumProductsW`
- `0x180053fc0`: `MsiQueryProductStateW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppListHelper::LoadDependencies(
        SystemSettings::StorageSenseHandlers::CAppListHelper *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v4; // rcx
  FARPROC v5; // rax
  HMODULE v6; // rcx

  if ( !*((_QWORD *)this + 12) )
  {
    Library = LoadLibraryExW(L"MSI.DLL", 0, 0);
    *((_QWORD *)this + 12) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "MsiEnumProductsW");
      v4 = (HMODULE)*((_QWORD *)this + 12);
      *((_QWORD *)this + 1) = ProcAddress;
      v5 = GetProcAddress(v4, "MsiGetProductInfoW");
      v6 = (HMODULE)*((_QWORD *)this + 12);
      *((_QWORD *)this + 2) = v5;
      *((_QWORD *)this + 3) = GetProcAddress(v6, "MsiQueryProductStateW");
    }
  }
  if ( *((_QWORD *)this + 12) && *((_QWORD *)this + 1) && *((_QWORD *)this + 2) && *((_QWORD *)this + 3) )
    return 0;
  else
    return 2147942527LL;
}

```

## disassembly

```asm
0x180053f6c  push    rbx
0x180053f6e  sub     rsp, 20h
0x180053f72  cmp     qword ptr [rcx+60h], 0
0x180053f77  mov     rbx, rcx
0x180053f7a  jnz     short loc_180053FD5
0x180053f7c  xor     r8d, r8d; dwFlags
0x180053f7f  lea     rcx, aMsiDll; "MSI.DLL"
0x180053f86  xor     edx, edx; hFile
0x180053f88  call    cs:__imp_LoadLibraryExW
0x180053f8e  mov     [rbx+60h], rax
0x180053f92  test    rax, rax
0x180053f95  jz      short loc_180053FD5
0x180053f97  lea     rdx, aMsienumproduct; "MsiEnumProductsW"
0x180053f9e  mov     rcx, rax; hModule
0x180053fa1  call    cs:__imp_GetProcAddress
0x180053fa7  mov     rcx, [rbx+60h]; hModule
0x180053fab  lea     rdx, aMsigetproducti; "MsiGetProductInfoW"
0x180053fb2  mov     [rbx+8], rax
0x180053fb6  call    cs:__imp_GetProcAddress
0x180053fbc  mov     rcx, [rbx+60h]; hModule
0x180053fc0  lea     rdx, aMsiqueryproduc; "MsiQueryProductStateW"
0x180053fc7  mov     [rbx+10h], rax
0x180053fcb  call    cs:__imp_GetProcAddress
0x180053fd1  mov     [rbx+18h], rax
0x180053fd5  cmp     qword ptr [rbx+60h], 0
0x180053fda  jz      short loc_180053FF5
0x180053fdc  cmp     qword ptr [rbx+8], 0
0x180053fe1  jz      short loc_180053FF5
0x180053fe3  cmp     qword ptr [rbx+10h], 0
0x180053fe8  jz      short loc_180053FF5
0x180053fea  cmp     qword ptr [rbx+18h], 0
0x180053fef  jz      short loc_180053FF5
0x180053ff1  xor     eax, eax
0x180053ff3  jmp     short loc_180053FFA
0x180053ff5  mov     eax, 8007007Fh
0x180053ffa  add     rsp, 20h
0x180053ffe  pop     rbx
0x180053fff  retn
```
