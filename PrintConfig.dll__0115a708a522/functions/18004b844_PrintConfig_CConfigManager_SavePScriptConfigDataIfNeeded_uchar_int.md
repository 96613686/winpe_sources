# PrintConfig::CConfigManager::SavePScriptConfigDataIfNeeded(uchar *,int)

- ea: `0x18004b844`
- end: `0x18004b9c3`
- name: `?SavePScriptConfigDataIfNeeded@CConfigManager@PrintConfig@@AEAAXPEAEH@Z`
- size: `383`
- prototype: `void __fastcall(PrintConfig::CConfigManager *this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800446d8`

## callees

- `0x180020c8c`
- `0x18003ae44`
- `0x18004a36c`
- `0x18004b844`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b8a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b8a3`
- `KERNEL32!GetProcAddress` at `0x18004b911`
- `KERNEL32!GetProcAddress` at `0x18004b911`
- `KERNEL32!FreeLibrary` at `0x18004b970`
- `KERNEL32!FreeLibrary` at `0x18004b970`
- `KERNEL32!LoadLibraryExW` at `0x18004b8c6`
- `KERNEL32!LoadLibraryExW` at `0x18004b8c6`
- `ole32!CoTaskMemFree` at `0x18004b98a`
- `ole32!CoTaskMemFree` at `0x18004b98a`

## string_xrefs

- `0x18004b8f6`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x18004b93c`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x18004b9b0`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x18004b925`: `Failed to get function pointer for SavePScriptConfigData`
- `0x18004b907`: `SavePScriptConfigData`
- `0x18004b8df`: `Failed to load library ModernPrintConfigHelper.dll`
- `0x18004b8bf`: `ModernPrintConfigHelper.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PrintConfig::CConfigManager::SavePScriptConfigDataIfNeeded(
        PrintConfig::CConfigManager *this,
        unsigned __int8 *a2,
        unsigned int a3)
{
  const char *v6; // r9
  HMODULE Library; // rdi
  FARPROC ProcAddress; // r14
  int v9; // eax
  int v10; // [rsp+20h] [rbp-38h]
  LPVOID pv[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HMODULE v13; // [rsp+78h] [rbp+20h] BYREF

  pv[1] = (LPVOID)-2LL;
  pv[0] = 0;
  try
  {
    PrintConfig::CConfigManager::RetrieveBidiData(
      this,
      L"\\Printer.VirtualPrinter:PreferredInputFormat",
      0,
      4,
      (unsigned __int8 **)pv,
      (unsigned int *)&v13);
    if ( !(unsigned int)_o__wcsicmp(pv[0], L"application/postscript") )
    {
      Library = LoadLibraryExW(L"ModernPrintConfigHelper.dll", 0, 0x800u);
      v13 = Library;
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        (void *)0x52B,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        -2147023739,
        (__int64)Library,
        (int)"Failed to load library ModernPrintConfigHelper.dll");
      ProcAddress = GetProcAddress(Library, "SavePScriptConfigData");
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        (void *)0x52D,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        -2147024769,
        (__int64)ProcAddress,
        (int)"Failed to get function pointer for SavePScriptConfigData");
      v9 = ((__int64 (__fastcall *)(_QWORD, unsigned __int8 *, _QWORD))ProcAddress)(*((_QWORD *)this + 8), a2, a3);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          1326,
          (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
          (const char *)(unsigned int)v9,
          v10);
      if ( Library )
        FreeLibrary(Library);
    }
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x531,
      (int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x18004b844  mov     r11, rsp
0x18004b847  push    r12
0x18004b849  push    r14
0x18004b84b  push    r15
0x18004b84d  sub     rsp, 40h
0x18004b851  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFEh
0x18004b859  mov     [r11+8], rsi
0x18004b85d  mov     [r11+10h], rdi
0x18004b861  mov     r15d, r8d
0x18004b864  mov     r12, rdx
0x18004b867  mov     rsi, rcx
0x18004b86a  mov     qword ptr [r11-28h], 0
0x18004b872  lea     rax, [r11+20h]
0x18004b876  mov     [r11-30h], rax
0x18004b87a  lea     rax, [r11-28h]
0x18004b87e  mov     [r11-38h], rax
0x18004b882  mov     r9d, 4; unsigned int
0x18004b888  xor     r8d, r8d; unsigned __int16 *
0x18004b88b  lea     rdx, aPrinterVirtual_0; "\\Printer.VirtualPrinter:PreferredInput"...
0x18004b892  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18004b897  lea     rdx, aApplicationPos; "application/postscript"
0x18004b89e  mov     rcx, [rsp+58h+pv]
0x18004b8a3  call    cs:__imp__o__wcsicmp
0x18004b8aa  nop     dword ptr [rax+rax+00h]
0x18004b8af  test    eax, eax
0x18004b8b1  jnz     loc_18004B97D
0x18004b8b7  xor     edx, edx; hFile
0x18004b8b9  mov     r8d, 800h; dwFlags
0x18004b8bf  lea     rcx, aModernprintcon; "ModernPrintConfigHelper.dll"
0x18004b8c6  call    cs:__imp_LoadLibraryExW
0x18004b8cd  nop     dword ptr [rax+rax+00h]
0x18004b8d2  mov     rdi, rax
0x18004b8d5  mov     [rsp+58h+arg_18], rax
0x18004b8da  mov     rcx, [rsp+58h]
0x18004b8df  lea     rax, aFailedToLoadLi_0; "Failed to load library ModernPrintConfi"...
0x18004b8e6  mov     [rsp+58h+var_30], rax
0x18004b8eb  mov     qword ptr [rsp+58h+var_38], rdi
0x18004b8f0  mov     r9d, 80070485h
0x18004b8f6  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x18004b8fd  mov     edx, 52Bh
0x18004b902  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18004b907  lea     rdx, aSavepscriptcon; "SavePScriptConfigData"
0x18004b90e  mov     rcx, rdi; hModule
0x18004b911  call    cs:__imp_GetProcAddress
0x18004b918  nop     dword ptr [rax+rax+00h]
0x18004b91d  mov     r14, rax
0x18004b920  mov     rcx, [rsp+58h]
0x18004b925  lea     rax, aFailedToGetFun; "Failed to get function pointer for Save"...
0x18004b92c  mov     [rsp+58h+var_30], rax
0x18004b931  mov     qword ptr [rsp+58h+var_38], r14; int
0x18004b936  mov     r9d, 8007007Fh
0x18004b93c  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x18004b943  mov     edx, 52Dh
0x18004b948  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18004b94d  mov     r8d, r15d
0x18004b950  mov     rdx, r12
0x18004b953  mov     rcx, [rsi+40h]
0x18004b957  mov     rax, r14
0x18004b95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b95f  mov     rcx, [rsp+58h]; this
0x18004b964  test    eax, eax
0x18004b966  js      short loc_18004B9AD
0x18004b968  test    rdi, rdi
0x18004b96b  jz      short loc_18004B97D
0x18004b96d  mov     rcx, rdi; hLibModule
0x18004b970  call    cs:__imp_FreeLibrary
0x18004b977  nop     dword ptr [rax+rax+00h]
0x18004b97c  nop
0x18004b97d  cmp     [rsp+58h+pv], 0
0x18004b983  jz      short loc_18004B997
0x18004b985  mov     rcx, [rsp+58h+pv]; pv
0x18004b98a  call    cs:__imp_CoTaskMemFree
0x18004b991  nop     dword ptr [rax+rax+00h]
0x18004b996  nop
0x18004b997  mov     rsi, [rsp+58h+arg_0]
0x18004b99c  mov     rdi, [rsp+58h+arg_8]
0x18004b9a1  add     rsp, 40h
0x18004b9a5  pop     r15
0x18004b9a7  pop     r14
0x18004b9a9  pop     r12
0x18004b9ab  retn
0x18004b9ad  mov     r9d, eax; char *
0x18004b9b0  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x18004b9b7  mov     edx, 52Eh; void *
0x18004b9bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
