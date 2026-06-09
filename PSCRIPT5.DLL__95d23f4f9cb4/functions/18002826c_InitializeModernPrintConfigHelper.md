# InitializeModernPrintConfigHelper

- ea: `0x18002826c`
- end: `0x180028411`
- name: `InitializeModernPrintConfigHelper`
- size: `421`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800041a0`
- `0x1800057c4`
- `0x180028154`

## callees

- `0x180026e60`
- `0x18002826c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180028297`
- `KERNEL32!LoadLibraryExW` at `0x180028297`
- `KERNEL32!FreeLibrary` at `0x1800282b7`
- `KERNEL32!FreeLibrary` at `0x1800282b7`
- `KERNEL32!GetProcAddress` at `0x1800282f4`
- `KERNEL32!GetProcAddress` at `0x180028319`
- `KERNEL32!GetProcAddress` at `0x18002833e`
- `KERNEL32!GetProcAddress` at `0x180028366`
- `KERNEL32!GetProcAddress` at `0x18002838e`
- `KERNEL32!GetProcAddress` at `0x1800283b6`
- `KERNEL32!GetProcAddress` at `0x1800283de`
- `KERNEL32!GetProcAddress` at `0x1800282f4`
- `KERNEL32!GetProcAddress` at `0x180028319`
- `KERNEL32!GetProcAddress` at `0x18002833e`
- `KERNEL32!GetProcAddress` at `0x180028366`
- `KERNEL32!GetProcAddress` at `0x18002838e`
- `KERNEL32!GetProcAddress` at `0x1800283b6`
- `KERNEL32!GetProcAddress` at `0x1800283de`
- `KERNEL32!SetLastError` at `0x1800282bf`
- `KERNEL32!SetLastError` at `0x1800282bf`
- `KERNEL32!GetLastError` at `0x1800282ac`
- `KERNEL32!GetLastError` at `0x1800282ac`

## string_xrefs

- `0x18002828a`: `ModernPrintConfigHelper.dll`
- `0x1800282ea`: `LoadRawPScriptPpdConfigForGpdDriver`
- `0x180028312`: `UnloadRawPScriptPpdConfig`

## pseudocode

```c
__int64 InitializeModernPrintConfigHelper()
{
  HMODULE Library; // rax
  const char *v1; // r9
  HMODULE v2; // rsi
  HMODULE v3; // rdi
  DWORD LastError; // ebx
  __int64 v5; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !byte_1800745A8 )
  {
    Library = LoadLibraryExW(L"ModernPrintConfigHelper.dll", 0, 0x800u);
    v2 = g_modernPrintConfigHelper;
    v3 = Library;
    if ( g_modernPrintConfigHelper )
    {
      LastError = GetLastError();
      FreeLibrary(v2);
      SetLastError(LastError);
    }
    g_modernPrintConfigHelper = v3;
    if ( !v3 )
    {
      v5 = 65;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_loadRawPScriptPpdConfigForGpdDriver = (__int64)GetProcAddress(v3, "LoadRawPScriptPpdConfigForGpdDriver");
    if ( !g_loadRawPScriptPpdConfigForGpdDriver )
    {
      v5 = 69;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_unloadRawPScriptPpdConfig = (__int64)GetProcAddress(g_modernPrintConfigHelper, "UnloadRawPScriptPpdConfig");
    if ( !g_unloadRawPScriptPpdConfig )
    {
      v5 = 73;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_getPScriptDevModeFromIppdevMode = (__int64)GetProcAddress(
                                                   g_modernPrintConfigHelper,
                                                   "GetPScriptDevModeFromIppDevMode");
    if ( !g_getPScriptDevModeFromIppdevMode )
    {
      v5 = 77;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_freePScriptDevMode = (__int64)GetProcAddress(g_modernPrintConfigHelper, "FreePScriptDevMode");
    if ( !g_freePScriptDevMode )
    {
      v5 = 81;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_getPrinterDataForGpdDriver = (__int64)GetProcAddress(g_modernPrintConfigHelper, "GetPrinterDataForGpdDriver");
    if ( !g_getPrinterDataForGpdDriver )
    {
      v5 = 85;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_getPsRedirectedDriverInfo = (__int64)GetProcAddress(g_modernPrintConfigHelper, "GetPsRedirectedDriverInfo");
    if ( !g_getPsRedirectedDriverInfo )
    {
      v5 = 89;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_freePsRedirectedDriverInfo = (__int64)GetProcAddress(g_modernPrintConfigHelper, "FreePsRedirectedDriverInfo");
    if ( !g_freePsRedirectedDriverInfo )
    {
      v5 = 93;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    byte_1800745A8 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002826c  mov     [rsp+arg_0], rbx
0x180028271  mov     [rsp+arg_8], rsi
0x180028276  push    rdi
0x180028277  sub     rsp, 20h
0x18002827b  cmp     cs:byte_1800745A8, 0
0x180028282  jnz     loc_1800283FF
0x180028288  xor     edx, edx; hFile
0x18002828a  lea     rcx, LibFileName; "ModernPrintConfigHelper.dll"
0x180028291  mov     r8d, 800h; dwFlags
0x180028297  call    cs:__imp_LoadLibraryExW
0x18002829d  mov     rsi, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_modernPrintConfigHelper
0x1800282a4  mov     rdi, rax
0x1800282a7  test    rsi, rsi
0x1800282aa  jz      short loc_1800282C5
0x1800282ac  call    cs:__imp_GetLastError
0x1800282b2  mov     rcx, rsi; hLibModule
0x1800282b5  mov     ebx, eax
0x1800282b7  call    cs:__imp_FreeLibrary
0x1800282bd  mov     ecx, ebx; dwErrCode
0x1800282bf  call    cs:__imp_SetLastError
0x1800282c5  mov     cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rdi; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_modernPrintConfigHelper
0x1800282cc  test    rdi, rdi
0x1800282cf  jnz     short loc_1800282EA
0x1800282d1  lea     edx, [rdi+41h]; void *
0x1800282d4  mov     rcx, [rsp+28h]; this
0x1800282d9  lea     r8, aPrintscanPrint; "printscan\\print\\drivers\\usermode\\ps"...
0x1800282e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800282e5  jmp     loc_180028401
0x1800282ea  lea     rdx, aLoadrawpscript; "LoadRawPScriptPpdConfigForGpdDriver"
0x1800282f1  mov     rcx, rdi; hModule
0x1800282f4  call    cs:__imp_GetProcAddress
0x1800282fa  mov     cs:?g_loadRawPScriptPpdConfigForGpdDriver@@3P6AJPEAXPEAPEAU_RAWBINARYDATA@@PEAK@_EEA, rax
0x180028301  test    rax, rax
0x180028304  jnz     short loc_18002830B
0x180028306  lea     edx, [rax+45h]
0x180028309  jmp     short loc_1800282D4
0x18002830b  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x180028312  lea     rdx, aUnloadrawpscri; "UnloadRawPScriptPpdConfig"
0x180028319  call    cs:__imp_GetProcAddress
0x18002831f  mov     cs:?g_unloadRawPScriptPpdConfig@@3P6AJPEAU_RAWBINARYDATA@@@_EEA, rax
0x180028326  test    rax, rax
0x180028329  jnz     short loc_180028330
0x18002832b  lea     edx, [rax+49h]
0x18002832e  jmp     short loc_1800282D4
0x180028330  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x180028337  lea     rdx, aGetpscriptdevm; "GetPScriptDevModeFromIppDevMode"
0x18002833e  call    cs:__imp_GetProcAddress
0x180028344  mov     cs:?g_getPScriptDevModeFromIppdevMode@@3P6AJPEAXPEAU_RAWBINARYDATA@@QEAU_devicemodeW@@KPEAU_OPTSELECT@@PEAU_RECTL@@PEA_NPEAHPEAPEAU2@PEAK@_EEA, rax
0x18002834b  test    rax, rax
0x18002834e  jnz     short loc_180028358
0x180028350  lea     edx, [rax+4Dh]
0x180028353  jmp     loc_1800282D4
0x180028358  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x18002835f  lea     rdx, aFreepscriptdev; "FreePScriptDevMode"
0x180028366  call    cs:__imp_GetProcAddress
0x18002836c  mov     cs:?g_freePScriptDevMode@@3P6AJPEAU_devicemodeW@@@_EEA, rax
0x180028373  test    rax, rax
0x180028376  jnz     short loc_180028380
0x180028378  lea     edx, [rax+51h]
0x18002837b  jmp     loc_1800282D4
0x180028380  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x180028387  lea     rdx, aGetprinterdata; "GetPrinterDataForGpdDriver"
0x18002838e  call    cs:__imp_GetProcAddress
0x180028394  mov     cs:?g_getPrinterDataForGpdDriver@@3P6AJPEAXPEAU_RAWBINARYDATA@@PEAU_PRINTERDATA@@@_EEA, rax
0x18002839b  test    rax, rax
0x18002839e  jnz     short loc_1800283A8
0x1800283a0  lea     edx, [rax+55h]
0x1800283a3  jmp     loc_1800282D4
0x1800283a8  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x1800283af  lea     rdx, aGetpsredirecte; "GetPsRedirectedDriverInfo"
0x1800283b6  call    cs:__imp_GetProcAddress
0x1800283bc  mov     cs:?g_getPsRedirectedDriverInfo@@3P6AJPEAXPEAPEAU_DRIVER_INFO_3W@@PEAK@_EEA, rax
0x1800283c3  test    rax, rax
0x1800283c6  jnz     short loc_1800283D0
0x1800283c8  lea     edx, [rax+59h]
0x1800283cb  jmp     loc_1800282D4
0x1800283d0  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x1800283d7  lea     rdx, aFreepsredirect; "FreePsRedirectedDriverInfo"
0x1800283de  call    cs:__imp_GetProcAddress
0x1800283e4  mov     cs:?g_freePsRedirectedDriverInfo@@3P6AJPEAU_DRIVER_INFO_3W@@@_EEA, rax
0x1800283eb  test    rax, rax
0x1800283ee  jnz     short loc_1800283F8
0x1800283f0  lea     edx, [rax+5Dh]
0x1800283f3  jmp     loc_1800282D4
0x1800283f8  mov     cs:byte_1800745A8, 1
0x1800283ff  xor     eax, eax
0x180028401  mov     rbx, [rsp+28h+arg_0]
0x180028406  mov     rsi, [rsp+28h+arg_8]
0x18002840b  add     rsp, 20h
0x18002840f  pop     rdi
0x180028410  retn
```
