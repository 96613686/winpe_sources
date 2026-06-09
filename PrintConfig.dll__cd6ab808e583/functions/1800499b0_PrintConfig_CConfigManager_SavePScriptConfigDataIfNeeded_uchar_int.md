# PrintConfig::CConfigManager::SavePScriptConfigDataIfNeeded(uchar *,int)

- ea: `0x1800499b0`
- end: `0x180049b10`
- name: `?SavePScriptConfigDataIfNeeded@CConfigManager@PrintConfig@@AEAAXPEAEH@Z`
- size: `352`
- prototype: `void __fastcall(PrintConfig::CConfigManager *this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180042dac`

## callees

- `0x18002025c`
- `0x180039880`
- `0x180048514`
- `0x1800499b0`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180049a0f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180049a0f`
- `KERNEL32!GetProcAddress` at `0x180049a71`
- `KERNEL32!GetProcAddress` at `0x180049a71`
- `KERNEL32!FreeLibrary` at `0x180049aca`
- `KERNEL32!FreeLibrary` at `0x180049aca`
- `KERNEL32!LoadLibraryExW` at `0x180049a2c`
- `KERNEL32!LoadLibraryExW` at `0x180049a2c`
- `ole32!CoTaskMemFree` at `0x180049ade`
- `ole32!CoTaskMemFree` at `0x180049ade`

## string_xrefs

- `0x180049a56`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x180049a96`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x180049afd`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x180049a7f`: `Failed to get function pointer for SavePScriptConfigData`
- `0x180049a67`: `SavePScriptConfigData`
- `0x180049a3f`: `Failed to load library ModernPrintConfigHelper.dll`
- `0x180049a25`: `ModernPrintConfigHelper.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      4u,
      (unsigned __int8 **)pv,
      (unsigned int *)&v13);
    if ( !(unsigned int)_o__wcsicmp(pv[0], L"application/postscript") )
    {
      Library = LoadLibraryExW(L"ModernPrintConfigHelper.dll", 0, 0x800u);
      v13 = Library;
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        1301,
        "printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        2147943557LL,
        Library,
        "Failed to load library ModernPrintConfigHelper.dll");
      ProcAddress = GetProcAddress(Library, "SavePScriptConfigData");
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        1303,
        "printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        2147942527LL,
        ProcAddress,
        "Failed to get function pointer for SavePScriptConfigData");
      v9 = ((__int64 (__fastcall *)(_QWORD, unsigned __int8 *, _QWORD))ProcAddress)(*((_QWORD *)this + 8), a2, a3);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x518,
          (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
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
      (void *)0x51B,
      (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x1800499b0  mov     r11, rsp
0x1800499b3  push    r12
0x1800499b5  push    r14
0x1800499b7  push    r15
0x1800499b9  sub     rsp, 40h
0x1800499bd  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFEh
0x1800499c5  mov     [r11+8], rsi
0x1800499c9  mov     [r11+10h], rdi
0x1800499cd  mov     r15d, r8d
0x1800499d0  mov     r12, rdx
0x1800499d3  mov     rsi, rcx
0x1800499d6  mov     qword ptr [r11-28h], 0
0x1800499de  lea     rax, [r11+20h]
0x1800499e2  mov     [r11-30h], rax
0x1800499e6  lea     rax, [r11-28h]
0x1800499ea  mov     [r11-38h], rax
0x1800499ee  mov     r9d, 4; unsigned int
0x1800499f4  xor     r8d, r8d; unsigned __int16 *
0x1800499f7  lea     rdx, aPrinterVirtual_0; "\\Printer.VirtualPrinter:PreferredInput"...
0x1800499fe  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x180049a03  lea     rdx, aApplicationPos; "application/postscript"
0x180049a0a  mov     rcx, [rsp+58h+pv]
0x180049a0f  call    cs:__imp__o__wcsicmp
0x180049a15  test    eax, eax
0x180049a17  jnz     loc_180049AD1
0x180049a1d  xor     edx, edx; hFile
0x180049a1f  mov     r8d, 800h; dwFlags
0x180049a25  lea     rcx, aModernprintcon; "ModernPrintConfigHelper.dll"
0x180049a2c  call    cs:__imp_LoadLibraryExW
0x180049a32  mov     rdi, rax
0x180049a35  mov     [rsp+58h+arg_18], rax
0x180049a3a  mov     rcx, [rsp+58h]
0x180049a3f  lea     rax, aFailedToLoadLi_0; "Failed to load library ModernPrintConfi"...
0x180049a46  mov     [rsp+58h+var_30], rax
0x180049a4b  mov     qword ptr [rsp+58h+var_38], rdi
0x180049a50  mov     r9d, 80070485h
0x180049a56  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x180049a5d  mov     edx, 515h
0x180049a62  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x180049a67  lea     rdx, aSavepscriptcon; "SavePScriptConfigData"
0x180049a6e  mov     rcx, rdi; hModule
0x180049a71  call    cs:__imp_GetProcAddress
0x180049a77  mov     r14, rax
0x180049a7a  mov     rcx, [rsp+58h]
0x180049a7f  lea     rax, aFailedToGetFun; "Failed to get function pointer for Save"...
0x180049a86  mov     [rsp+58h+var_30], rax
0x180049a8b  mov     qword ptr [rsp+58h+var_38], r14; int
0x180049a90  mov     r9d, 8007007Fh
0x180049a96  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x180049a9d  mov     edx, 517h
0x180049aa2  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x180049aa7  mov     r8d, r15d
0x180049aaa  mov     rdx, r12
0x180049aad  mov     rcx, [rsi+40h]
0x180049ab1  mov     rax, r14
0x180049ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ab9  mov     rcx, [rsp+58h]; this
0x180049abe  test    eax, eax
0x180049ac0  js      short loc_180049AFA
0x180049ac2  test    rdi, rdi
0x180049ac5  jz      short loc_180049AD1
0x180049ac7  mov     rcx, rdi; hLibModule
0x180049aca  call    cs:__imp_FreeLibrary
0x180049ad0  nop
0x180049ad1  cmp     [rsp+58h+pv], 0
0x180049ad7  jz      short loc_180049AE5
0x180049ad9  mov     rcx, [rsp+58h+pv]; pv
0x180049ade  call    cs:__imp_CoTaskMemFree
0x180049ae4  nop
0x180049ae5  mov     rsi, [rsp+58h+arg_0]
0x180049aea  mov     rdi, [rsp+58h+arg_8]
0x180049aef  add     rsp, 40h
0x180049af3  pop     r15
0x180049af5  pop     r14
0x180049af7  pop     r12
0x180049af9  retn
0x180049afa  mov     r9d, eax; char *
0x180049afd  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x180049b04  mov     edx, 518h; void *
0x180049b09  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
