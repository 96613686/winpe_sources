# SpoolerUtility::InstallPrintToPDFDriver(ushort)

- ea: `0x180033aa8`
- end: `0x180033cf9`
- name: `?InstallPrintToPDFDriver@SpoolerUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z`
- size: `593`
- prototype: `__int64 __fastcall(__int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000b310`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000f8a8`
- `0x180012498`
- `0x18001d058`
- `0x180027040`
- `0x18002b28c`
- `0x180032e6c`
- `0x180032f34`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033b6d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033b6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033baf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033be5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033baf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033be5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180033afa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180033afa`

## string_xrefs

- `0x180033b0c`: `GetSystemWindowsDirectory failed!`
- `0x180033b3f`: `\system32\spool\tools\Microsoft Print To PDF\prnms009.Inf`
- `0x180033b1c`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x180033c04`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x180033c90`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x180033b88`: `LoadLibraryEx failed!`
- `0x180033b66`: `Setupapi.dll`
- `0x180033bf5`: `GetProcAddress (DriverStoreAddDriverPackage) failed!`
- `0x180033bdb`: `DriverStoreAddDriverPackageW`
- `0x180033c81`: `DriverStoreAddDriverPackage failed!`

## pseudocode

```c
__int64 __fastcall SpoolerUtility::InstallPrintToPDFDriver(__int64 a1, unsigned __int16 a2)
{
  UINT SystemWindowsDirectoryW; // eax
  __int64 v5; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v7; // rdi
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  unsigned int v10; // eax
  char *v12; // [rsp+28h] [rbp-D8h]
  char *v13; // [rsp+28h] [rbp-D8h]
  char v14; // [rsp+28h] [rbp-D8h]
  char v15; // [rsp+28h] [rbp-D8h]
  char *v16; // [rsp+28h] [rbp-D8h]
  char v17[4]; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE v18[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[4]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v20[40]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v22[528]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  memset_0(Buffer, 0, 0x208u);
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x55,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)(SystemWindowsDirectoryW == 0),
    (bool)"GetSystemWindowsDirectory failed!",
    v12);
  v5 = std::wstring::wstring(v20, Buffer);
  std::operator+<unsigned short>(v19, v5, L"\\system32\\spool\\tools\\Microsoft Print To PDF\\prnms009.Inf");
  std::wstring::_Tidy_deallocate(v20);
  v18[0] = LoadLibraryExW(L"Setupapi.dll", 0, 0x800u);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x5C,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)(v18[0] == 0),
    (bool)"LoadLibraryEx failed!",
    v13);
  ProcAddress = GetProcAddress(v18[0], "SetupSetNonInteractiveMode");
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(unsigned short const *,unsigned long,void *,unsigned short,unsigned short *,unsigned long *),0>(
    (int)retaddr,
    95,
    (int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (int)ProcAddress,
    "GetProcAddress (SetupSetNonInteractiveMode) failed!",
    v14);
  v7 = GetProcAddress(v18[0], "DriverStoreAddDriverPackageW");
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(unsigned short const *,unsigned long,void *,unsigned short,unsigned short *,unsigned long *),0>(
    (int)retaddr,
    98,
    (int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (int)v7,
    "GetProcAddress (DriverStoreAddDriverPackage) failed!",
    v15);
  v8 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
  memset_0(v22, 0, 0x208u);
  *(_DWORD *)v17 = 260;
  v9 = v19;
  if ( v19[3] > 7u )
    v9 = (_QWORD *)v19[0];
  v10 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD, _QWORD, _BYTE *, char *))v7)(v9, 65, 0, a2, v22, v17);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x6B,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)v10,
    (int)"DriverStoreAddDriverPackage failed!",
    v16);
  ((void (__fastcall *)(_QWORD))ProcAddress)(v8);
  std::wstring::wstring(a1, v22);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v18);
  std::wstring::_Tidy_deallocate(v19);
  return a1;
}

```

## disassembly

```asm
0x180033aa8  mov     [rsp-8+arg_10], rbx
0x180033aad  push    rbp
0x180033aae  push    rsi
0x180033aaf  push    rdi
0x180033ab0  push    r14
0x180033ab2  push    r15
0x180033ab4  lea     rbp, [rsp-3D0h]
0x180033abc  sub     rsp, 4D0h
0x180033ac3  mov     rax, cs:__security_cookie
0x180033aca  xor     rax, rsp
0x180033acd  mov     [rbp+3F0h+var_30], rax
0x180033ad4  movzx   r14d, dx
0x180033ad8  mov     r15, rcx
0x180033adb  mov     [rsp+4F0h+var_4A8], rcx
0x180033ae0  xor     edx, edx; Val
0x180033ae2  mov     r8d, 208h; Size
0x180033ae8  lea     rcx, [rbp+3F0h+Buffer]; void *
0x180033aec  call    memset_0
0x180033af1  mov     edx, 104h; uSize
0x180033af6  lea     rcx, [rbp+3F0h+Buffer]; lpBuffer
0x180033afa  call    cs:__imp_GetSystemWindowsDirectoryW
0x180033b00  test    eax, eax
0x180033b02  setz    al
0x180033b05  mov     rcx, [rbp+3F8h]; this
0x180033b0c  lea     rdx, aGetsystemwindo; "GetSystemWindowsDirectory failed!"
0x180033b13  mov     [rsp+4F0h+var_4D0], rdx; bool
0x180033b18  movzx   r9d, al; char *
0x180033b1c  lea     rdi, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033b23  mov     r8, rdi; unsigned int
0x180033b26  mov     edx, 55h ; 'U'; void *
0x180033b2b  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180033b30  lea     rdx, [rbp+3F0h+Buffer]
0x180033b34  lea     rcx, [rsp+4F0h+var_478]
0x180033b39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033b3e  nop
0x180033b3f  lea     r8, aSystem32SpoolT; "\\system32\\spool\\tools\\Microsoft Pri"...
0x180033b46  mov     rdx, rax
0x180033b49  lea     rcx, [rsp+4F0h+var_498]
0x180033b4e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180033b53  nop
0x180033b54  lea     rcx, [rsp+4F0h+var_478]
0x180033b59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033b5e  xor     edx, edx; hFile
0x180033b60  mov     r8d, 800h; dwFlags
0x180033b66  lea     rcx, aSetupapiDll_0; "Setupapi.dll"
0x180033b6d  call    cs:__imp_LoadLibraryExW
0x180033b73  mov     rbx, rax
0x180033b76  mov     [rsp+4F0h+var_4A8], rax
0x180033b7b  test    rax, rax
0x180033b7e  setz    al
0x180033b81  mov     rcx, [rbp+3F8h]; this
0x180033b88  lea     rdx, aLoadlibraryexF; "LoadLibraryEx failed!"
0x180033b8f  mov     [rsp+4F0h+var_4D0], rdx; bool
0x180033b94  movzx   r9d, al; char *
0x180033b98  mov     r8, rdi; unsigned int
0x180033b9b  mov     edx, 5Ch ; '\'; void *
0x180033ba0  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180033ba5  lea     rdx, aSetupsetnonint; "SetupSetNonInteractiveMode"
0x180033bac  mov     rcx, rbx; hModule
0x180033baf  call    cs:__imp_GetProcAddress
0x180033bb5  mov     rsi, rax
0x180033bb8  mov     rcx, [rbp+3F8h]; int
0x180033bbf  lea     rax, aGetprocaddress_0; "GetProcAddress (SetupSetNonInteractiveM"...
0x180033bc6  mov     [rsp+4F0h+var_4D0], rax; void *
0x180033bcb  mov     r9, rsi; int
0x180033bce  mov     r8, rdi; int
0x180033bd1  mov     edx, 5Fh ; '_'; int
0x180033bd6  call    ??$Throw_GetLastErrorIfNullMsg@P6AJPEBGKPEAXGPEAGPEAK@Z$0A@@in1diag3@details@wil@@YAP6AJPEBGKPEAXGPEAGPEAK@Z1IPEBDP6AJ0K1G23@Z4ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(ushort const *,ulong,void *,ushort,ushort *,ulong *),0>(void *,uint,char const *,long (*)(ushort const *,ulong,void *,ushort,ushort *,ulong *),char const *,...)
0x180033bdb  lea     rdx, aDriverstoreadd; "DriverStoreAddDriverPackageW"
0x180033be2  mov     rcx, rbx; hModule
0x180033be5  call    cs:__imp_GetProcAddress
0x180033beb  mov     rdi, rax
0x180033bee  mov     rcx, [rbp+3F8h]; int
0x180033bf5  lea     rax, aGetprocaddress; "GetProcAddress (DriverStoreAddDriverPac"...
0x180033bfc  mov     [rsp+4F0h+var_4D0], rax; void *
0x180033c01  mov     r9, rdi; int
0x180033c04  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033c0b  mov     edx, 62h ; 'b'; int
0x180033c10  call    ??$Throw_GetLastErrorIfNullMsg@P6AJPEBGKPEAXGPEAGPEAK@Z$0A@@in1diag3@details@wil@@YAP6AJPEBGKPEAXGPEAGPEAK@Z1IPEBDP6AJ0K1G23@Z4ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(ushort const *,ulong,void *,ushort,ushort *,ulong *),0>(void *,uint,char const *,long (*)(ushort const *,ulong,void *,ushort,ushort *,ulong *),char const *,...)
0x180033c15  mov     ecx, 1
0x180033c1a  mov     rax, rsi
0x180033c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c22  mov     ebx, eax
0x180033c24  xor     edx, edx; Val
0x180033c26  mov     r8d, 208h; Size
0x180033c2c  lea     rcx, [rbp+3F0h+var_240]; void *
0x180033c33  call    memset_0
0x180033c38  mov     dword ptr [rsp+4F0h+var_4B0], 104h
0x180033c40  lea     rcx, [rsp+4F0h+var_498]
0x180033c45  cmp     [rsp+4F0h+var_480], 7
0x180033c4b  cmova   rcx, [rsp+4F0h+var_498]
0x180033c51  lea     rax, [rsp+4F0h+var_4B0]
0x180033c56  mov     [rsp+4F0h+var_4C8], rax; char *
0x180033c5b  lea     rax, [rbp+3F0h+var_240]
0x180033c62  mov     [rsp+4F0h+var_4D0], rax
0x180033c67  movzx   r9d, r14w
0x180033c6b  xor     r8d, r8d
0x180033c6e  lea     edx, [r8+41h]
0x180033c72  mov     rax, rdi
0x180033c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c7a  mov     rcx, [rbp+3F8h]; this
0x180033c81  lea     rdx, aDriverstoreadd_0; "DriverStoreAddDriverPackage failed!"
0x180033c88  mov     [rsp+4F0h+var_4D0], rdx; int
0x180033c8d  mov     r9d, eax; char *
0x180033c90  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033c97  mov     edx, 6Bh ; 'k'; void *
0x180033c9c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033ca1  mov     ecx, ebx
0x180033ca3  mov     rax, rsi
0x180033ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cab  lea     rdx, [rbp+3F0h+var_240]
0x180033cb2  mov     rcx, r15
0x180033cb5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033cba  nop
0x180033cbb  lea     rcx, [rsp+4F0h+var_4A8]
0x180033cc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180033cc5  nop
0x180033cc6  lea     rcx, [rsp+4F0h+var_498]
0x180033ccb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033cd0  mov     rax, r15
0x180033cd3  mov     rcx, [rbp+3F0h+var_30]
0x180033cda  xor     rcx, rsp; StackCookie
0x180033cdd  call    __security_check_cookie
0x180033ce2  mov     rbx, [rsp+4F0h+arg_10]
0x180033cea  add     rsp, 4D0h
0x180033cf1  pop     r15
0x180033cf3  pop     r14
0x180033cf5  pop     rdi
0x180033cf6  pop     rsi
0x180033cf7  pop     rbp
0x180033cf8  retn
```
