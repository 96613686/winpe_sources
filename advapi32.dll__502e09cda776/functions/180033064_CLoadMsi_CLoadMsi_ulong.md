# CLoadMsi::CLoadMsi(ulong &)

- ea: `0x180033064`
- end: `0x180033213`
- name: `??0CLoadMsi@@QEAA@AEAK@Z`
- size: `431`
- prototype: `CLoadMsi *__fastcall(CLoadMsi *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032b10`
- `0x18003a788`

## callees

- `0x180033064`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800331fe`
- `KERNEL32!GetLastError` at `0x1800331fe`
- `KERNEL32!GetProcAddress` at `0x1800330a5`
- `KERNEL32!GetProcAddress` at `0x1800330c2`
- `KERNEL32!GetProcAddress` at `0x1800330df`
- `KERNEL32!GetProcAddress` at `0x1800330fc`
- `KERNEL32!GetProcAddress` at `0x180033119`
- `KERNEL32!GetProcAddress` at `0x180033136`
- `KERNEL32!GetProcAddress` at `0x180033153`
- `KERNEL32!GetProcAddress` at `0x180033170`
- `KERNEL32!GetProcAddress` at `0x18003318d`
- `KERNEL32!GetProcAddress` at `0x1800330a5`
- `KERNEL32!GetProcAddress` at `0x1800330c2`
- `KERNEL32!GetProcAddress` at `0x1800330df`
- `KERNEL32!GetProcAddress` at `0x1800330fc`
- `KERNEL32!GetProcAddress` at `0x180033119`
- `KERNEL32!GetProcAddress` at `0x180033136`
- `KERNEL32!GetProcAddress` at `0x180033153`
- `KERNEL32!GetProcAddress` at `0x180033170`
- `KERNEL32!GetProcAddress` at `0x18003318d`
- `KERNEL32!LoadLibraryExW` at `0x180033083`
- `KERNEL32!LoadLibraryExW` at `0x180033083`

## string_xrefs

- `0x180033076`: `msiltcfg.dll`
- `0x1800330ee`: `MsiDecomposeDescriptorW`
- `0x18003310b`: `MsiGetProductInfoW`
- `0x180033162`: `MsiIsProductElevatedW`
- `0x18003317f`: `MsiReinstallProductW`
- `0x18003309b`: `MsiSetInternalUI`
- `0x180033145`: `MsiQueryProductStateW`
- `0x180033128`: `MsiAdvertiseScriptW`
- `0x1800330b4`: `MsiConfigureProductExW`
- `0x1800330d1`: `MsiProvideComponentFromDescriptorW`

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
0x180033064  mov     [rsp+arg_0], rbx
0x180033069  push    rdi
0x18003306a  sub     rsp, 20h
0x18003306e  mov     rdi, rdx
0x180033071  mov     rbx, rcx
0x180033074  xor     edx, edx; hFile
0x180033076  lea     rcx, aMsiltcfgDll; "msiltcfg.dll"
0x18003307d  mov     r8d, 800h; dwFlags
0x180033083  call    cs:__imp_LoadLibraryExW
0x18003308a  nop     dword ptr [rax+rax+00h]
0x18003308f  mov     [rbx], rax
0x180033092  test    rax, rax
0x180033095  jz      loc_1800331FE
0x18003309b  lea     rdx, aMsisetinternal; "MsiSetInternalUI"
0x1800330a2  mov     rcx, rax; hModule
0x1800330a5  call    cs:__imp_GetProcAddress
0x1800330ac  nop     dword ptr [rax+rax+00h]
0x1800330b1  mov     rcx, [rbx]; hModule
0x1800330b4  lea     rdx, aMsiconfigurepr; "MsiConfigureProductExW"
0x1800330bb  mov     cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA, rax; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x1800330c2  call    cs:__imp_GetProcAddress
0x1800330c9  nop     dword ptr [rax+rax+00h]
0x1800330ce  mov     rcx, [rbx]; hModule
0x1800330d1  lea     rdx, aMsiprovidecomp; "MsiProvideComponentFromDescriptorW"
0x1800330d8  mov     cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA, rax; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x1800330df  call    cs:__imp_GetProcAddress
0x1800330e6  nop     dword ptr [rax+rax+00h]
0x1800330eb  mov     rcx, [rbx]; hModule
0x1800330ee  lea     rdx, aMsidecomposede; "MsiDecomposeDescriptorW"
0x1800330f5  mov     cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA, rax; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x1800330fc  call    cs:__imp_GetProcAddress
0x180033103  nop     dword ptr [rax+rax+00h]
0x180033108  mov     rcx, [rbx]; hModule
0x18003310b  lea     rdx, aMsigetproducti; "MsiGetProductInfoW"
0x180033112  mov     cs:?gpfnMsiDecomposeDescriptor@@3P6AIPEBGPEAG11PEAK@ZEA, rax; uint (*gpfnMsiDecomposeDescriptor)(ushort const *,ushort *,ushort *,ushort *,ulong *)
0x180033119  call    cs:__imp_GetProcAddress
0x180033120  nop     dword ptr [rax+rax+00h]
0x180033125  mov     rcx, [rbx]; hModule
0x180033128  lea     rdx, aMsiadvertisesc; "MsiAdvertiseScriptW"
0x18003312f  mov     cs:?gpfnMsiGetProductInfo@@3P6AIPEBG0PEAGPEAK@ZEA, rax; uint (*gpfnMsiGetProductInfo)(ushort const *,ushort const *,ushort *,ulong *)
0x180033136  call    cs:__imp_GetProcAddress
0x18003313d  nop     dword ptr [rax+rax+00h]
0x180033142  mov     rcx, [rbx]; hModule
0x180033145  lea     rdx, aMsiqueryproduc; "MsiQueryProductStateW"
0x18003314c  mov     cs:?gpfnMsiAdvertiseScript@@3P6AIPEBGKPEAPEAUHKEY__@@H@ZEA, rax; uint (*gpfnMsiAdvertiseScript)(ushort const *,ulong,HKEY__ * *,int)
0x180033153  call    cs:__imp_GetProcAddress
0x18003315a  nop     dword ptr [rax+rax+00h]
0x18003315f  mov     rcx, [rbx]; hModule
0x180033162  lea     rdx, aMsiisproductel; "MsiIsProductElevatedW"
0x180033169  mov     cs:?gpfnMsiQueryProductState@@3P6A?AW4tagINSTALLSTATE@@PEBG@ZEA, rax; tagINSTALLSTATE (*gpfnMsiQueryProductState)(ushort const *)
0x180033170  call    cs:__imp_GetProcAddress
0x180033177  nop     dword ptr [rax+rax+00h]
0x18003317c  mov     rcx, [rbx]; hModule
0x18003317f  lea     rdx, aMsireinstallpr; "MsiReinstallProductW"
0x180033186  mov     cs:?gpfnMsiIsProductElevated@@3P6AIPEBGPEAH@ZEA, rax; uint (*gpfnMsiIsProductElevated)(ushort const *,int *)
0x18003318d  call    cs:__imp_GetProcAddress
0x180033194  nop     dword ptr [rax+rax+00h]
0x180033199  cmp     cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA, 0; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x1800331a1  mov     cs:?gpfnMsiReinstallProduct@@3P6AIPEBGK@ZEA, rax; uint (*gpfnMsiReinstallProduct)(ushort const *,ulong)
0x1800331a8  jz      short loc_18003320C
0x1800331aa  cmp     cs:?gpfnMsiConfigureProductEx@@3P6AIPEBGHW4tagINSTALLSTATE@@0@ZEA, 0; uint (*gpfnMsiConfigureProductEx)(ushort const *,int,tagINSTALLSTATE,ushort const *)
0x1800331b2  jz      short loc_18003320C
0x1800331b4  cmp     cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA, 0; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x1800331bc  jz      short loc_18003320C
0x1800331be  cmp     cs:?gpfnMsiDecomposeDescriptor@@3P6AIPEBGPEAG11PEAK@ZEA, 0; uint (*gpfnMsiDecomposeDescriptor)(ushort const *,ushort *,ushort *,ushort *,ulong *)
0x1800331c6  jz      short loc_18003320C
0x1800331c8  cmp     cs:?gpfnMsiAdvertiseScript@@3P6AIPEBGKPEAPEAUHKEY__@@H@ZEA, 0; uint (*gpfnMsiAdvertiseScript)(ushort const *,ulong,HKEY__ * *,int)
0x1800331d0  jz      short loc_18003320C
0x1800331d2  cmp     cs:?gpfnMsiQueryProductState@@3P6A?AW4tagINSTALLSTATE@@PEBG@ZEA, 0; tagINSTALLSTATE (*gpfnMsiQueryProductState)(ushort const *)
0x1800331da  jz      short loc_18003320C
0x1800331dc  cmp     cs:?gpfnMsiIsProductElevated@@3P6AIPEBGPEAH@ZEA, 0; uint (*gpfnMsiIsProductElevated)(ushort const *,int *)
0x1800331e4  jz      short loc_18003320C
0x1800331e6  test    rax, rax
0x1800331e9  jz      short loc_18003320C
0x1800331eb  xor     eax, eax
0x1800331ed  mov     [rdi], eax
0x1800331ef  mov     rax, rbx
0x1800331f2  mov     rbx, [rsp+28h+arg_0]
0x1800331f7  add     rsp, 20h
0x1800331fb  pop     rdi
0x1800331fc  retn
0x1800331fe  call    cs:__imp_GetLastError
0x180033205  nop     dword ptr [rax+rax+00h]
0x18003320a  jmp     short loc_1800331ED
0x18003320c  mov     eax, 7Fh
0x180033211  jmp     short loc_1800331ED
```
