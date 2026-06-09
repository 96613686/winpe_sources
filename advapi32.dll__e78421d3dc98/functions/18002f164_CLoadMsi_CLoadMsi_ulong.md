# CLoadMsi::CLoadMsi(ulong &)

- ea: `0x18002f164`
- end: `0x18002f2d0`
- name: `??0CLoadMsi@@QEAA@AEAK@Z`
- size: `364`
- prototype: `CLoadMsi *__fastcall(CLoadMsi *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002ec80`
- `0x1800367f0`

## callees

- `0x18002f164`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002f2c1`
- `KERNEL32!GetLastError` at `0x18002f2c1`
- `KERNEL32!GetProcAddress` at `0x18002f19f`
- `KERNEL32!GetProcAddress` at `0x18002f1b6`
- `KERNEL32!GetProcAddress` at `0x18002f1cd`
- `KERNEL32!GetProcAddress` at `0x18002f1e4`
- `KERNEL32!GetProcAddress` at `0x18002f1fb`
- `KERNEL32!GetProcAddress` at `0x18002f212`
- `KERNEL32!GetProcAddress` at `0x18002f229`
- `KERNEL32!GetProcAddress` at `0x18002f240`
- `KERNEL32!GetProcAddress` at `0x18002f257`
- `KERNEL32!GetProcAddress` at `0x18002f19f`
- `KERNEL32!GetProcAddress` at `0x18002f1b6`
- `KERNEL32!GetProcAddress` at `0x18002f1cd`
- `KERNEL32!GetProcAddress` at `0x18002f1e4`
- `KERNEL32!GetProcAddress` at `0x18002f1fb`
- `KERNEL32!GetProcAddress` at `0x18002f212`
- `KERNEL32!GetProcAddress` at `0x18002f229`
- `KERNEL32!GetProcAddress` at `0x18002f240`
- `KERNEL32!GetProcAddress` at `0x18002f257`
- `KERNEL32!LoadLibraryExW` at `0x18002f183`
- `KERNEL32!LoadLibraryExW` at `0x18002f183`

## string_xrefs

- `0x18002f176`: `msiltcfg.dll`
- `0x18002f1d6`: `MsiDecomposeDescriptorW`
- `0x18002f1ed`: `MsiGetProductInfoW`
- `0x18002f232`: `MsiIsProductElevatedW`
- `0x18002f249`: `MsiReinstallProductW`
- `0x18002f195`: `MsiSetInternalUI`
- `0x18002f21b`: `MsiQueryProductStateW`
- `0x18002f204`: `MsiAdvertiseScriptW`
- `0x18002f1a8`: `MsiConfigureProductExW`
- `0x18002f1bf`: `MsiProvideComponentFromDescriptorW`

## pseudocode

```c
CLoadMsi *__fastcall CLoadMsi::CLoadMsi(CLoadMsi *this, unsigned int *a2)
{
  HMODULE Library; // rax
  enum tagINSTALLUILEVEL (*ProcAddress)(enum tagINSTALLUILEVEL, HWND *); // rax
  HMODULE v6; // rcx
  unsigned int (*v7)(const unsigned __int16 *, int, enum tagINSTALLSTATE, const unsigned __int16 *); // rax
  HMODULE v8; // rcx
  unsigned int (*v9)(const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int *); // rax
  HMODULE v10; // rcx
  unsigned int (*v11)(const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *); // rax
  HMODULE v12; // rcx
  unsigned int (*v13)(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int *); // rax
  HMODULE v14; // rcx
  unsigned int (*v15)(const unsigned __int16 *, unsigned int, HKEY *, int); // rax
  HMODULE v16; // rcx
  enum tagINSTALLSTATE (*v17)(const unsigned __int16 *); // rax
  HMODULE v18; // rcx
  unsigned int (*v19)(const unsigned __int16 *, int *); // rax
  HMODULE v20; // rcx
  unsigned int (*v21)(const unsigned __int16 *, unsigned int); // rax
  DWORD LastError; // eax

  Library = LoadLibraryExW(L"msiltcfg.dll", 0, 0x800u);
  *(_QWORD *)this = Library;
  if ( Library )
  {
    ProcAddress = (enum tagINSTALLUILEVEL (*)(enum tagINSTALLUILEVEL, HWND *))GetProcAddress(
                                                                                Library,
                                                                                "MsiSetInternalUI");
    v6 = *(HMODULE *)this;
    gpfnMsiSetInternalUI = ProcAddress;
    v7 = (unsigned int (*)(const unsigned __int16 *, int, enum tagINSTALLSTATE, const unsigned __int16 *))GetProcAddress(v6, "MsiConfigureProductExW");
    v8 = *(HMODULE *)this;
    gpfnMsiConfigureProductEx = v7;
    v9 = (unsigned int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int *))GetProcAddress(v8, "MsiProvideComponentFromDescriptorW");
    v10 = *(HMODULE *)this;
    gpfnMsiProvideComponentFromDescriptor = v9;
    v11 = (unsigned int (*)(const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *))GetProcAddress(v10, "MsiDecomposeDescriptorW");
    v12 = *(HMODULE *)this;
    gpfnMsiDecomposeDescriptor = v11;
    v13 = (unsigned int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int *))GetProcAddress(v12, "MsiGetProductInfoW");
    v14 = *(HMODULE *)this;
    gpfnMsiGetProductInfo = v13;
    v15 = (unsigned int (*)(const unsigned __int16 *, unsigned int, HKEY *, int))GetProcAddress(
                                                                                   v14,
                                                                                   "MsiAdvertiseScriptW");
    v16 = *(HMODULE *)this;
    gpfnMsiAdvertiseScript = v15;
    v17 = (enum tagINSTALLSTATE (*)(const unsigned __int16 *))GetProcAddress(v16, "MsiQueryProductStateW");
    v18 = *(HMODULE *)this;
    gpfnMsiQueryProductState = v17;
    v19 = (unsigned int (*)(const unsigned __int16 *, int *))GetProcAddress(v18, "MsiIsProductElevatedW");
    v20 = *(HMODULE *)this;
    gpfnMsiIsProductElevated = v19;
    v21 = (unsigned int (*)(const unsigned __int16 *, unsigned int))GetProcAddress(v20, "MsiReinstallProductW");
    gpfnMsiReinstallProduct = v21;
    if ( gpfnMsiSetInternalUI
      && gpfnMsiConfigureProductEx
      && gpfnMsiProvideComponentFromDescriptor
      && gpfnMsiDecomposeDescriptor
      && gpfnMsiAdvertiseScript
      && gpfnMsiQueryProductState
      && gpfnMsiIsProductElevated
      && v21 )
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
0x18002f164  mov     [rsp+arg_0], rbx
0x18002f169  push    rdi
0x18002f16a  sub     rsp, 20h
0x18002f16e  mov     rdi, rdx
0x18002f171  mov     rbx, rcx
0x18002f174  xor     edx, edx; hFile
0x18002f176  lea     rcx, aMsiltcfgDll; "msiltcfg.dll"
0x18002f17d  mov     r8d, 800h; dwFlags
0x18002f183  call    cs:__imp_LoadLibraryExW
0x18002f189  mov     [rbx], rax
0x18002f18c  test    rax, rax
0x18002f18f  jz      loc_18002F2C1
0x18002f195  lea     rdx, aMsisetinternal; "MsiSetInternalUI"
0x18002f19c  mov     rcx, rax; hModule
0x18002f19f  call    cs:__imp_GetProcAddress
0x18002f1a5  mov     rcx, [rbx]; hModule
0x18002f1a8  lea     rdx, aMsiconfigurepr; "MsiConfigureProductExW"
0x18002f1af  mov     cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA, rax; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18002f1b6  call    cs:__imp_GetProcAddress
0x18002f1bc  mov     rcx, [rbx]; hModule
0x18002f1bf  lea     rdx, aMsiprovidecomp; "MsiProvideComponentFromDescriptorW"
0x18002f1c6  mov     cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA, rax; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x18002f1cd  call    cs:__imp_GetProcAddress
0x18002f1d3  mov     rcx, [rbx]; hModule
0x18002f1d6  lea     rdx, aMsidecomposede; "MsiDecomposeDescriptorW"
0x18002f1dd  mov     cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA, rax; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x18002f1e4  call    cs:__imp_GetProcAddress
0x18002f1ea  mov     rcx, [rbx]; hModule
0x18002f1ed  lea     rdx, aMsigetproducti; "MsiGetProductInfoW"
0x18002f1f4  mov     cs:?gpfnMsiDecomposeDescriptor@@3P6AIPEBGPEAG11PEAK@ZEA, rax; uint (*gpfnMsiDecomposeDescriptor)(ushort const *,ushort *,ushort *,ushort *,ulong *)
0x18002f1fb  call    cs:__imp_GetProcAddress
0x18002f201  mov     rcx, [rbx]; hModule
0x18002f204  lea     rdx, aMsiadvertisesc; "MsiAdvertiseScriptW"
0x18002f20b  mov     cs:?gpfnMsiGetProductInfo@@3P6AIPEBG0PEAGPEAK@ZEA, rax; uint (*gpfnMsiGetProductInfo)(ushort const *,ushort const *,ushort *,ulong *)
0x18002f212  call    cs:__imp_GetProcAddress
0x18002f218  mov     rcx, [rbx]; hModule
0x18002f21b  lea     rdx, aMsiqueryproduc; "MsiQueryProductStateW"
0x18002f222  mov     cs:?gpfnMsiAdvertiseScript@@3P6AIPEBGKPEAPEAUHKEY__@@H@ZEA, rax; uint (*gpfnMsiAdvertiseScript)(ushort const *,ulong,HKEY__ * *,int)
0x18002f229  call    cs:__imp_GetProcAddress
0x18002f22f  mov     rcx, [rbx]; hModule
0x18002f232  lea     rdx, aMsiisproductel; "MsiIsProductElevatedW"
0x18002f239  mov     cs:?gpfnMsiQueryProductState@@3P6A?AW4tagINSTALLSTATE@@PEBG@ZEA, rax; tagINSTALLSTATE (*gpfnMsiQueryProductState)(ushort const *)
0x18002f240  call    cs:__imp_GetProcAddress
0x18002f246  mov     rcx, [rbx]; hModule
0x18002f249  lea     rdx, aMsireinstallpr; "MsiReinstallProductW"
0x18002f250  mov     cs:?gpfnMsiIsProductElevated@@3P6AIPEBGPEAH@ZEA, rax; uint (*gpfnMsiIsProductElevated)(ushort const *,int *)
0x18002f257  call    cs:__imp_GetProcAddress
0x18002f25d  cmp     cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA, 0; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18002f265  mov     cs:?gpfnMsiReinstallProduct@@3P6AIPEBGK@ZEA, rax; uint (*gpfnMsiReinstallProduct)(ushort const *,ulong)
0x18002f26c  jz      short loc_18002F2C9
0x18002f26e  cmp     cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA, 0; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x18002f276  jz      short loc_18002F2C9
0x18002f278  cmp     cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA, 0; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x18002f280  jz      short loc_18002F2C9
0x18002f282  cmp     cs:?gpfnMsiDecomposeDescriptor@@3P6AIPEBGPEAG11PEAK@ZEA, 0; uint (*gpfnMsiDecomposeDescriptor)(ushort const *,ushort *,ushort *,ushort *,ulong *)
0x18002f28a  jz      short loc_18002F2C9
0x18002f28c  cmp     cs:?gpfnMsiAdvertiseScript@@3P6AIPEBGKPEAPEAUHKEY__@@H@ZEA, 0; uint (*gpfnMsiAdvertiseScript)(ushort const *,ulong,HKEY__ * *,int)
0x18002f294  jz      short loc_18002F2C9
0x18002f296  cmp     cs:?gpfnMsiQueryProductState@@3P6A?AW4tagINSTALLSTATE@@PEBG@ZEA, 0; tagINSTALLSTATE (*gpfnMsiQueryProductState)(ushort const *)
0x18002f29e  jz      short loc_18002F2C9
0x18002f2a0  cmp     cs:?gpfnMsiIsProductElevated@@3P6AIPEBGPEAH@ZEA, 0; uint (*gpfnMsiIsProductElevated)(ushort const *,int *)
0x18002f2a8  jz      short loc_18002F2C9
0x18002f2aa  test    rax, rax
0x18002f2ad  jz      short loc_18002F2C9
0x18002f2af  xor     eax, eax
0x18002f2b1  mov     [rdi], eax
0x18002f2b3  mov     rax, rbx
0x18002f2b6  mov     rbx, [rsp+28h+arg_0]
0x18002f2bb  add     rsp, 20h
0x18002f2bf  pop     rdi
0x18002f2c0  retn
0x18002f2c1  call    cs:__imp_GetLastError
0x18002f2c7  jmp     short loc_18002F2B1
0x18002f2c9  mov     eax, 7Fh
0x18002f2ce  jmp     short loc_18002F2B1
```
