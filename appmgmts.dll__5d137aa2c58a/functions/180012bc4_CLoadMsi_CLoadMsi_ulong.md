# CLoadMsi::CLoadMsi(ulong &)

- ea: `0x180012bc4`
- end: `0x180012d2f`
- name: `??0CLoadMsi@@QEAA@AEAK@Z`
- size: `363`
- prototype: `CLoadMsi *__fastcall(CLoadMsi *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002b90`
- `0x180003370`
- `0x18000b7e8`

## callees

- `0x180012bc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bf1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012be3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012be3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ca7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012cbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ca7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012cbe`

## string_xrefs

- `0x180012bd6`: `msiltcfg.dll`
- `0x180012bfc`: `MsiSetInternalUI`
- `0x180012c0f`: `MsiConfigureProductExW`
- `0x180012c26`: `MsiProvideComponentFromDescriptorW`
- `0x180012c3d`: `MsiDecomposeDescriptorW`
- `0x180012c54`: `MsiGetProductInfoW`
- `0x180012c6b`: `MsiAdvertiseScriptW`
- `0x180012c82`: `MsiQueryProductStateW`
- `0x180012c99`: `MsiIsProductElevatedW`
- `0x180012cb0`: `MsiReinstallProductW`

## pseudocode

```c
CLoadMsi *__fastcall CLoadMsi::CLoadMsi(CLoadMsi *this, unsigned int *a2)
{
  HMODULE Library; // rax
  DWORD LastError; // eax
  enum tagINSTALLUILEVEL (*ProcAddress)(enum tagINSTALLUILEVEL, HWND *); // rax
  HMODULE v7; // rcx
  unsigned int (*v8)(const unsigned __int16 *, int, enum tagINSTALLSTATE, const unsigned __int16 *); // rax
  HMODULE v9; // rcx
  unsigned int (*v10)(const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int *); // rax
  HMODULE v11; // rcx
  unsigned int (*v12)(const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *); // rax
  HMODULE v13; // rcx
  unsigned int (*v14)(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int *); // rax
  HMODULE v15; // rcx
  unsigned int (*v16)(const unsigned __int16 *, unsigned int, HKEY *, int); // rax
  HMODULE v17; // rcx
  enum tagINSTALLSTATE (*v18)(const unsigned __int16 *); // rax
  HMODULE v19; // rcx
  unsigned int (*v20)(const unsigned __int16 *, int *); // rax
  HMODULE v21; // rcx
  unsigned int (*v22)(const unsigned __int16 *, unsigned int); // rax

  Library = LoadLibraryExW(L"msiltcfg.dll", 0, 0x800u);
  *(_QWORD *)this = Library;
  if ( Library )
  {
    ProcAddress = (enum tagINSTALLUILEVEL (*)(enum tagINSTALLUILEVEL, HWND *))GetProcAddress(
                                                                                Library,
                                                                                "MsiSetInternalUI");
    v7 = *(HMODULE *)this;
    gpfnMsiSetInternalUI = ProcAddress;
    v8 = (unsigned int (*)(const unsigned __int16 *, int, enum tagINSTALLSTATE, const unsigned __int16 *))GetProcAddress(v7, "MsiConfigureProductExW");
    v9 = *(HMODULE *)this;
    gpfnMsiConfigureProductEx = v8;
    v10 = (unsigned int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int *))GetProcAddress(v9, "MsiProvideComponentFromDescriptorW");
    v11 = *(HMODULE *)this;
    gpfnMsiProvideComponentFromDescriptor = v10;
    v12 = (unsigned int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *))GetProcAddress(v11, "MsiDecomposeDescriptorW");
    v13 = *(HMODULE *)this;
    gpfnMsiDecomposeDescriptor = v12;
    v14 = (unsigned int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int *))GetProcAddress(v13, "MsiGetProductInfoW");
    v15 = *(HMODULE *)this;
    gpfnMsiGetProductInfo = v14;
    v16 = (unsigned int (*)(const unsigned __int16 *, unsigned int, HKEY *, int))GetProcAddress(
                                                                                   v15,
                                                                                   "MsiAdvertiseScriptW");
    v17 = *(HMODULE *)this;
    gpfnMsiAdvertiseScript = v16;
    v18 = (enum tagINSTALLSTATE (*)(const unsigned __int16 *))GetProcAddress(v17, "MsiQueryProductStateW");
    v19 = *(HMODULE *)this;
    gpfnMsiQueryProductState = v18;
    v20 = (unsigned int (*)(const unsigned __int16 *, int *))GetProcAddress(v19, "MsiIsProductElevatedW");
    v21 = *(HMODULE *)this;
    gpfnMsiIsProductElevated = v20;
    v22 = (unsigned int (*)(const unsigned __int16 *, unsigned int))GetProcAddress(v21, "MsiReinstallProductW");
    gpfnMsiReinstallProduct = v22;
    if ( gpfnMsiSetInternalUI
      && gpfnMsiConfigureProductEx
      && gpfnMsiProvideComponentFromDescriptor
      && gpfnMsiDecomposeDescriptor
      && gpfnMsiAdvertiseScript
      && gpfnMsiQueryProductState
      && gpfnMsiIsProductElevated
      && v22 )
    {
      LastError = 0;
    }
    else
    {
      LastError = 127;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  *a2 = LastError;
  return this;
}

```

## disassembly

```asm
0x180012bc4  mov     [rsp+arg_0], rbx
0x180012bc9  push    rdi
0x180012bca  sub     rsp, 20h
0x180012bce  mov     rdi, rdx
0x180012bd1  mov     rbx, rcx
0x180012bd4  xor     edx, edx; hFile
0x180012bd6  lea     rcx, aMsiltcfgDll; "msiltcfg.dll"
0x180012bdd  mov     r8d, 800h; dwFlags
0x180012be3  call    cs:__imp_LoadLibraryExW
0x180012be9  mov     [rbx], rax
0x180012bec  test    rax, rax
0x180012bef  jnz     short loc_180012BFC
0x180012bf1  call    cs:__imp_GetLastError
0x180012bf7  jmp     loc_180012D1F
0x180012bfc  lea     rdx, aMsisetinternal; "MsiSetInternalUI"
0x180012c03  mov     rcx, rax; hModule
0x180012c06  call    cs:__imp_GetProcAddress
0x180012c0c  mov     rcx, [rbx]; hModule
0x180012c0f  lea     rdx, aMsiconfigurepr; "MsiConfigureProductExW"
0x180012c16  mov     cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA, rax; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x180012c1d  call    cs:__imp_GetProcAddress
0x180012c23  mov     rcx, [rbx]; hModule
0x180012c26  lea     rdx, aMsiprovidecomp; "MsiProvideComponentFromDescriptorW"
0x180012c2d  mov     cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA, rax; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x180012c34  call    cs:__imp_GetProcAddress
0x180012c3a  mov     rcx, [rbx]; hModule
0x180012c3d  lea     rdx, aMsidecomposede; "MsiDecomposeDescriptorW"
0x180012c44  mov     cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA, rax; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x180012c4b  call    cs:__imp_GetProcAddress
0x180012c51  mov     rcx, [rbx]; hModule
0x180012c54  lea     rdx, aMsigetproducti; "MsiGetProductInfoW"
0x180012c5b  mov     cs:?gpfnMsiDecomposeDescriptor@@3P6AIPEBGPEAG11PEAK@ZEA, rax; uint (*gpfnMsiDecomposeDescriptor)(ushort const *,ushort *,ushort *,ushort *,ulong *)
0x180012c62  call    cs:__imp_GetProcAddress
0x180012c68  mov     rcx, [rbx]; hModule
0x180012c6b  lea     rdx, aMsiadvertisesc; "MsiAdvertiseScriptW"
0x180012c72  mov     cs:?gpfnMsiGetProductInfo@@3P6AIPEBG0PEAGPEAK@ZEA, rax; uint (*gpfnMsiGetProductInfo)(ushort const *,ushort const *,ushort *,ulong *)
0x180012c79  call    cs:__imp_GetProcAddress
0x180012c7f  mov     rcx, [rbx]; hModule
0x180012c82  lea     rdx, aMsiqueryproduc; "MsiQueryProductStateW"
0x180012c89  mov     cs:?gpfnMsiAdvertiseScript@@3P6AIPEBGKPEAPEAUHKEY__@@H@ZEA, rax; uint (*gpfnMsiAdvertiseScript)(ushort const *,ulong,HKEY__ * *,int)
0x180012c90  call    cs:__imp_GetProcAddress
0x180012c96  mov     rcx, [rbx]; hModule
0x180012c99  lea     rdx, aMsiisproductel; "MsiIsProductElevatedW"
0x180012ca0  mov     cs:?gpfnMsiQueryProductState@@3P6A?AW4tagINSTALLSTATE@@PEBG@ZEA, rax; tagINSTALLSTATE (*gpfnMsiQueryProductState)(ushort const *)
0x180012ca7  call    cs:__imp_GetProcAddress
0x180012cad  mov     rcx, [rbx]; hModule
0x180012cb0  lea     rdx, aMsireinstallpr; "MsiReinstallProductW"
0x180012cb7  mov     cs:?gpfnMsiIsProductElevated@@3P6AIPEBGPEAH@ZEA, rax; uint (*gpfnMsiIsProductElevated)(ushort const *,int *)
0x180012cbe  call    cs:__imp_GetProcAddress
0x180012cc4  cmp     cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA, 0; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x180012ccc  mov     cs:?gpfnMsiReinstallProduct@@3P6AIPEBGK@ZEA, rax; uint (*gpfnMsiReinstallProduct)(ushort const *,ulong)
0x180012cd3  jz      short loc_180012D1A
0x180012cd5  cmp     cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA, 0; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x180012cdd  jz      short loc_180012D1A
0x180012cdf  cmp     cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA, 0; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x180012ce7  jz      short loc_180012D1A
0x180012ce9  cmp     cs:?gpfnMsiDecomposeDescriptor@@3P6AIPEBGPEAG11PEAK@ZEA, 0; uint (*gpfnMsiDecomposeDescriptor)(ushort const *,ushort *,ushort *,ushort *,ulong *)
0x180012cf1  jz      short loc_180012D1A
0x180012cf3  cmp     cs:?gpfnMsiAdvertiseScript@@3P6AIPEBGKPEAPEAUHKEY__@@H@ZEA, 0; uint (*gpfnMsiAdvertiseScript)(ushort const *,ulong,HKEY__ * *,int)
0x180012cfb  jz      short loc_180012D1A
0x180012cfd  cmp     cs:?gpfnMsiQueryProductState@@3P6A?AW4tagINSTALLSTATE@@PEBG@ZEA, 0; tagINSTALLSTATE (*gpfnMsiQueryProductState)(ushort const *)
0x180012d05  jz      short loc_180012D1A
0x180012d07  cmp     cs:?gpfnMsiIsProductElevated@@3P6AIPEBGPEAH@ZEA, 0; uint (*gpfnMsiIsProductElevated)(ushort const *,int *)
0x180012d0f  jz      short loc_180012D1A
0x180012d11  test    rax, rax
0x180012d14  jz      short loc_180012D1A
0x180012d16  xor     eax, eax
0x180012d18  jmp     short loc_180012D1F
0x180012d1a  mov     eax, 7Fh
0x180012d1f  mov     [rdi], eax
0x180012d21  mov     rax, rbx
0x180012d24  mov     rbx, [rsp+28h+arg_0]
0x180012d29  add     rsp, 20h
0x180012d2d  pop     rdi
0x180012d2e  retn
```
