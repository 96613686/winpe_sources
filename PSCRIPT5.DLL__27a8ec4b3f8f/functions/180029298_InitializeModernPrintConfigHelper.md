# InitializeModernPrintConfigHelper

- ea: `0x180029298`
- end: `0x180029480`
- name: `InitializeModernPrintConfigHelper`
- size: `488`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004240`
- `0x180005858`
- `0x180029180`

## callees

- `0x180027c54`
- `0x180029298`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800292c3`
- `KERNEL32!LoadLibraryExW` at `0x1800292c3`
- `KERNEL32!FreeLibrary` at `0x1800292ef`
- `KERNEL32!FreeLibrary` at `0x1800292ef`
- `KERNEL32!GetProcAddress` at `0x180029338`
- `KERNEL32!GetProcAddress` at `0x180029363`
- `KERNEL32!GetProcAddress` at `0x18002938e`
- `KERNEL32!GetProcAddress` at `0x1800293bc`
- `KERNEL32!GetProcAddress` at `0x1800293ea`
- `KERNEL32!GetProcAddress` at `0x180029418`
- `KERNEL32!GetProcAddress` at `0x180029446`
- `KERNEL32!GetProcAddress` at `0x180029338`
- `KERNEL32!GetProcAddress` at `0x180029363`
- `KERNEL32!GetProcAddress` at `0x18002938e`
- `KERNEL32!GetProcAddress` at `0x1800293bc`
- `KERNEL32!GetProcAddress` at `0x1800293ea`
- `KERNEL32!GetProcAddress` at `0x180029418`
- `KERNEL32!GetProcAddress` at `0x180029446`
- `KERNEL32!SetLastError` at `0x1800292fd`
- `KERNEL32!SetLastError` at `0x1800292fd`
- `KERNEL32!GetLastError` at `0x1800292de`
- `KERNEL32!GetLastError` at `0x1800292de`

## string_xrefs

- `0x1800292b6`: `ModernPrintConfigHelper.dll`
- `0x18002932e`: `LoadRawPScriptPpdConfigForGpdDriver`
- `0x18002935c`: `UnloadRawPScriptPpdConfig`

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

  if ( !byte_180076598 )
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
               (int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_loadRawPScriptPpdConfigForGpdDriver = (__int64)GetProcAddress(v3, "LoadRawPScriptPpdConfigForGpdDriver");
    if ( !g_loadRawPScriptPpdConfigForGpdDriver )
    {
      v5 = 69;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_unloadRawPScriptPpdConfig = (__int64)GetProcAddress(g_modernPrintConfigHelper, "UnloadRawPScriptPpdConfig");
    if ( !g_unloadRawPScriptPpdConfig )
    {
      v5 = 73;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
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
               (int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_freePScriptDevMode = (__int64)GetProcAddress(g_modernPrintConfigHelper, "FreePScriptDevMode");
    if ( !g_freePScriptDevMode )
    {
      v5 = 81;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_getPrinterDataForGpdDriver = (__int64)GetProcAddress(g_modernPrintConfigHelper, "GetPrinterDataForGpdDriver");
    if ( !g_getPrinterDataForGpdDriver )
    {
      v5 = 85;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_getPsRedirectedDriverInfo = (__int64)GetProcAddress(g_modernPrintConfigHelper, "GetPsRedirectedDriverInfo");
    if ( !g_getPsRedirectedDriverInfo )
    {
      v5 = 89;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    g_freePsRedirectedDriverInfo = (__int64)GetProcAddress(g_modernPrintConfigHelper, "FreePsRedirectedDriverInfo");
    if ( !g_freePsRedirectedDriverInfo )
    {
      v5 = 93;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v5,
               (int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
               v1);
    }
    byte_180076598 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180029298  mov     [rsp+arg_0], rbx
0x18002929d  mov     [rsp+arg_8], rsi
0x1800292a2  push    rdi
0x1800292a3  sub     rsp, 20h
0x1800292a7  cmp     cs:byte_180076598, 0
0x1800292ae  jnz     loc_18002946D
0x1800292b4  xor     edx, edx; hFile
0x1800292b6  lea     rcx, LibFileName; "ModernPrintConfigHelper.dll"
0x1800292bd  mov     r8d, 800h; dwFlags
0x1800292c3  call    cs:__imp_LoadLibraryExW
0x1800292ca  nop     dword ptr [rax+rax+00h]
0x1800292cf  mov     rsi, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_modernPrintConfigHelper
0x1800292d6  mov     rdi, rax
0x1800292d9  test    rsi, rsi
0x1800292dc  jz      short loc_180029309
0x1800292de  call    cs:__imp_GetLastError
0x1800292e5  nop     dword ptr [rax+rax+00h]
0x1800292ea  mov     rcx, rsi; hLibModule
0x1800292ed  mov     ebx, eax
0x1800292ef  call    cs:__imp_FreeLibrary
0x1800292f6  nop     dword ptr [rax+rax+00h]
0x1800292fb  mov     ecx, ebx; dwErrCode
0x1800292fd  call    cs:__imp_SetLastError
0x180029304  nop     dword ptr [rax+rax+00h]
0x180029309  mov     cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rdi; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_modernPrintConfigHelper
0x180029310  test    rdi, rdi
0x180029313  jnz     short loc_18002932E
0x180029315  lea     edx, [rdi+41h]; void *
0x180029318  mov     rcx, [rsp+28h]; this
0x18002931d  lea     r8, aPrintscanPrint; "printscan\\print\\drivers\\usermode\\ps"...
0x180029324  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180029329  jmp     loc_18002946F
0x18002932e  lea     rdx, aLoadrawpscript; "LoadRawPScriptPpdConfigForGpdDriver"
0x180029335  mov     rcx, rdi; hModule
0x180029338  call    cs:__imp_GetProcAddress
0x18002933f  nop     dword ptr [rax+rax+00h]
0x180029344  mov     cs:?g_loadRawPScriptPpdConfigForGpdDriver@@3P6AJPEAXPEAPEAU_RAWBINARYDATA@@PEAK@_EEA, rax
0x18002934b  test    rax, rax
0x18002934e  jnz     short loc_180029355
0x180029350  lea     edx, [rax+45h]
0x180029353  jmp     short loc_180029318
0x180029355  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x18002935c  lea     rdx, aUnloadrawpscri; "UnloadRawPScriptPpdConfig"
0x180029363  call    cs:__imp_GetProcAddress
0x18002936a  nop     dword ptr [rax+rax+00h]
0x18002936f  mov     cs:?g_unloadRawPScriptPpdConfig@@3P6AJPEAU_RAWBINARYDATA@@@_EEA, rax
0x180029376  test    rax, rax
0x180029379  jnz     short loc_180029380
0x18002937b  lea     edx, [rax+49h]
0x18002937e  jmp     short loc_180029318
0x180029380  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x180029387  lea     rdx, aGetpscriptdevm; "GetPScriptDevModeFromIppDevMode"
0x18002938e  call    cs:__imp_GetProcAddress
0x180029395  nop     dword ptr [rax+rax+00h]
0x18002939a  mov     cs:?g_getPScriptDevModeFromIppdevMode@@3P6AJPEAXPEAU_RAWBINARYDATA@@QEAU_devicemodeW@@KPEAU_OPTSELECT@@PEAU_RECTL@@PEA_NPEAHPEAPEAU2@PEAK@_EEA, rax
0x1800293a1  test    rax, rax
0x1800293a4  jnz     short loc_1800293AE
0x1800293a6  lea     edx, [rax+4Dh]
0x1800293a9  jmp     loc_180029318
0x1800293ae  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x1800293b5  lea     rdx, aFreepscriptdev; "FreePScriptDevMode"
0x1800293bc  call    cs:__imp_GetProcAddress
0x1800293c3  nop     dword ptr [rax+rax+00h]
0x1800293c8  mov     cs:?g_freePScriptDevMode@@3P6AJPEAU_devicemodeW@@@_EEA, rax
0x1800293cf  test    rax, rax
0x1800293d2  jnz     short loc_1800293DC
0x1800293d4  lea     edx, [rax+51h]
0x1800293d7  jmp     loc_180029318
0x1800293dc  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x1800293e3  lea     rdx, aGetprinterdata; "GetPrinterDataForGpdDriver"
0x1800293ea  call    cs:__imp_GetProcAddress
0x1800293f1  nop     dword ptr [rax+rax+00h]
0x1800293f6  mov     cs:?g_getPrinterDataForGpdDriver@@3P6AJPEAXPEAU_RAWBINARYDATA@@PEAU_PRINTERDATA@@@_EEA, rax
0x1800293fd  test    rax, rax
0x180029400  jnz     short loc_18002940A
0x180029402  lea     edx, [rax+55h]
0x180029405  jmp     loc_180029318
0x18002940a  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x180029411  lea     rdx, aGetpsredirecte; "GetPsRedirectedDriverInfo"
0x180029418  call    cs:__imp_GetProcAddress
0x18002941f  nop     dword ptr [rax+rax+00h]
0x180029424  mov     cs:?g_getPsRedirectedDriverInfo@@3P6AJPEAXPEAPEAU_DRIVER_INFO_3W@@PEAK@_EEA, rax
0x18002942b  test    rax, rax
0x18002942e  jnz     short loc_180029438
0x180029430  lea     edx, [rax+59h]
0x180029433  jmp     loc_180029318
0x180029438  mov     rcx, cs:?g_modernPrintConfigHelper@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hModule
0x18002943f  lea     rdx, aFreepsredirect; "FreePsRedirectedDriverInfo"
0x180029446  call    cs:__imp_GetProcAddress
0x18002944d  nop     dword ptr [rax+rax+00h]
0x180029452  mov     cs:?g_freePsRedirectedDriverInfo@@3P6AJPEAU_DRIVER_INFO_3W@@@_EEA, rax
0x180029459  test    rax, rax
0x18002945c  jnz     short loc_180029466
0x18002945e  lea     edx, [rax+5Dh]
0x180029461  jmp     loc_180029318
0x180029466  mov     cs:byte_180076598, 1
0x18002946d  xor     eax, eax
0x18002946f  mov     rbx, [rsp+28h+arg_0]
0x180029474  mov     rsi, [rsp+28h+arg_8]
0x180029479  add     rsp, 20h
0x18002947d  pop     rdi
0x18002947e  retn
```
