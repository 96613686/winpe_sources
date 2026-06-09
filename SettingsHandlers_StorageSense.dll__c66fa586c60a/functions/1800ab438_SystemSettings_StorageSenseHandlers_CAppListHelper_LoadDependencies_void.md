# SystemSettings::StorageSenseHandlers::CAppListHelper::LoadDependencies(void)

- ea: `0x1800ab438`
- end: `0x1800ab4ed`
- name: `?LoadDependencies@CAppListHelper@StorageSenseHandlers@SystemSettings@@AEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppListHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800abd30`

## callees

- `0x1800ab438`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab473`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab48e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab4a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab473`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab48e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ab4a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ab457`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ab457`

## string_xrefs

- `0x1800ab44e`: `MSI.DLL`
- `0x1800ab469`: `MsiEnumProductsW`
- `0x1800ab480`: `MsiGetProductInfoW`
- `0x1800ab49b`: `MsiQueryProductStateW`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppListHelper::LoadDependencies(
        SystemSettings::StorageSenseHandlers::CAppListHelper *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v4; // rcx
  FARPROC v5; // rax
  HMODULE v6; // rcx

  if ( !*((_QWORD *)this + 52) )
  {
    Library = LoadLibraryExW(L"MSI.DLL", 0, 0);
    *((_QWORD *)this + 52) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "MsiEnumProductsW");
      v4 = (HMODULE)*((_QWORD *)this + 52);
      *((_QWORD *)this + 33) = ProcAddress;
      v5 = GetProcAddress(v4, "MsiGetProductInfoW");
      v6 = (HMODULE)*((_QWORD *)this + 52);
      *((_QWORD *)this + 34) = v5;
      *((_QWORD *)this + 35) = GetProcAddress(v6, "MsiQueryProductStateW");
    }
  }
  if ( *((_QWORD *)this + 52) && *((_QWORD *)this + 33) && *((_QWORD *)this + 34) && *((_QWORD *)this + 35) )
    return 0;
  else
    return 2147942527LL;
}

```

## disassembly

```asm
0x1800ab438  push    rbx
0x1800ab43a  sub     rsp, 20h
0x1800ab43e  cmp     qword ptr [rcx+1A0h], 0
0x1800ab446  mov     rbx, rcx
0x1800ab449  jnz     short loc_1800AB4B6
0x1800ab44b  xor     r8d, r8d; dwFlags
0x1800ab44e  lea     rcx, aMsiDll; "MSI.DLL"
0x1800ab455  xor     edx, edx; hFile
0x1800ab457  call    cs:__imp_LoadLibraryExW
0x1800ab45d  mov     [rbx+1A0h], rax
0x1800ab464  test    rax, rax
0x1800ab467  jz      short loc_1800AB4B6
0x1800ab469  lea     rdx, aMsienumproduct; "MsiEnumProductsW"
0x1800ab470  mov     rcx, rax; hModule
0x1800ab473  call    cs:__imp_GetProcAddress
0x1800ab479  mov     rcx, [rbx+1A0h]; hModule
0x1800ab480  lea     rdx, aMsigetproducti; "MsiGetProductInfoW"
0x1800ab487  mov     [rbx+108h], rax
0x1800ab48e  call    cs:__imp_GetProcAddress
0x1800ab494  mov     rcx, [rbx+1A0h]; hModule
0x1800ab49b  lea     rdx, aMsiqueryproduc; "MsiQueryProductStateW"
0x1800ab4a2  mov     [rbx+110h], rax
0x1800ab4a9  call    cs:__imp_GetProcAddress
0x1800ab4af  mov     [rbx+118h], rax
0x1800ab4b6  cmp     qword ptr [rbx+1A0h], 0
0x1800ab4be  jz      short loc_1800AB4E2
0x1800ab4c0  cmp     qword ptr [rbx+108h], 0
0x1800ab4c8  jz      short loc_1800AB4E2
0x1800ab4ca  cmp     qword ptr [rbx+110h], 0
0x1800ab4d2  jz      short loc_1800AB4E2
0x1800ab4d4  cmp     qword ptr [rbx+118h], 0
0x1800ab4dc  jz      short loc_1800AB4E2
0x1800ab4de  xor     eax, eax
0x1800ab4e0  jmp     short loc_1800AB4E7
0x1800ab4e2  mov     eax, 8007007Fh
0x1800ab4e7  add     rsp, 20h
0x1800ab4eb  pop     rbx
0x1800ab4ec  retn
```
