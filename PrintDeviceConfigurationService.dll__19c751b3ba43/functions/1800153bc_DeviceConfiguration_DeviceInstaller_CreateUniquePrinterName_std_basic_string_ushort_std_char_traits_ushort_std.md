# DeviceConfiguration::DeviceInstaller::_CreateUniquePrinterName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800153bc`
- end: `0x180015672`
- name: `?_CreateUniquePrinterName@DeviceInstaller@DeviceConfiguration@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z`
- size: `694`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180015e58`

## callees

- `0x1800020c0`
- `0x180002b28`
- `0x180008f4c`
- `0x18000aeac`
- `0x18000d284`
- `0x18000d89c`
- `0x18000e628`
- `0x18000eb80`
- `0x18000f9ec`
- `0x180011510`
- `0x1800115a0`
- `0x180014d90`
- `0x1800153bc`
- `0x18001596c`
- `0x180016284`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015472`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015472`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800154f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800154f5`

## string_xrefs

- `0x18001544a`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x18001546b`: `printui.dll`
- `0x180015487`: `Failed to load library printui.dll!`
- `0x1800155f8`: `Created unique printer name %ws`
- `0x1800155ff`: `DeviceConfiguration::DeviceInstaller::_CreateUniquePrinterName`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_CreateUniquePrinterName(__int64 a1, _QWORD *a2, __int64 a3)
{
  _WORD *v5; // rcx
  unsigned int v6; // eax
  int StringW; // eax
  unsigned int v8; // esi
  unsigned int v9; // eax
  _QWORD *v10; // r9
  unsigned int v11; // eax
  __int64 v12; // rcx
  char IsPrinterNameUnique; // bl
  unsigned int v14; // ebx
  __int64 v15; // rax
  char *v17; // [rsp+28h] [rbp-D8h]
  char *v18; // [rsp+28h] [rbp-D8h]
  char *v19; // [rsp+28h] [rbp-D8h]
  HINSTANCE Library; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h]
  _BYTE v23[40]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v24[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[520]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v26[520]; // [rsp+8A0h] [rbp+7A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CE8h] [rbp+BE8h]

  *(_QWORD *)(a3 + 16) = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v5 = (_WORD *)a3;
  else
    v5 = *(_WORD **)a3;
  *v5 = 0;
  v21 = 0;
  v22 = 0;
  v6 = DeviceConfiguration::EnumeratePrinters(0xAu);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x118,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
    (const char *)v6,
    (int)"EnumeratePrinters failed!",
    v17);
  Library = LoadLibraryExW(L"printui.dll", 0, 0x802u);
  wil::details::in1diag3::Throw_HrIfNullMsg<HINSTANCE__ *,0>(
    (_DWORD)retaddr,
    287,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
    -2147418113,
    (__int64)Library);
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v26, 0, sizeof(v26));
  memset_0(v24, 0, sizeof(v24));
  StringW = LoadStringW(Library, 0x4A38u, Buffer, 520);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x133,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
    (const char *)(StringW == 0),
    (bool)"LoadString failed!",
    "Failed to load library printui.dll!");
  v8 = 1;
  while ( 1 )
  {
    v9 = StringCchPrintfW(v26, 0x208u, Buffer, v8);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x136,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)v9,
      (int)"StringCchPrintf (first format) failed!",
      v18);
    v10 = a2[3] <= 7u ? a2 : (_QWORD *)*a2;
    v11 = StringCchPrintfW(v24, 0x208u, v26, v10);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x137,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)v11,
      (int)"StringCchPrintf (second format) failed!",
      v19);
    std::wstring::wstring(v23, v24);
    IsPrinterNameUnique = DeviceConfiguration::DeviceInstaller::_IsPrinterNameUnique(v12, v23, 0, 0);
    std::wstring::_Tidy_deallocate(v23);
    if ( IsPrinterNameUnique )
      break;
    if ( ++v8 >= 0x3E8 )
    {
      v14 = -2147023728;
      goto LABEL_12;
    }
  }
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::DeviceInstaller::_CreateUniquePrinterName",
    L"Created unique printer name %ws",
    v24);
  v15 = std::wstring::wstring(v23, v24);
  std::wstring::operator=(a3, v15);
  std::wstring::_Tidy_deallocate(v23);
  v14 = 0;
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
  std::vector<unsigned char>::_Tidy(&v21);
  return v14;
}

```

## disassembly

```asm
0x1800153bc  mov     [rsp-8+arg_0], rbx
0x1800153c1  mov     [rsp-8+arg_18], rsi
0x1800153c6  push    rbp
0x1800153c7  push    rdi
0x1800153c8  push    r13
0x1800153ca  push    r14
0x1800153cc  push    r15
0x1800153ce  lea     rbp, [rsp-0BC0h]
0x1800153d6  sub     rsp, 0CC0h
0x1800153dd  mov     rax, cs:__security_cookie
0x1800153e4  xor     rax, rsp
0x1800153e7  mov     [rbp+0BE0h+var_30], rax
0x1800153ee  mov     rdi, r8
0x1800153f1  mov     r14, rdx
0x1800153f4  mov     qword ptr [r8+10h], 0
0x1800153fc  cmp     qword ptr [r8+18h], 7
0x180015401  jbe     short loc_180015408
0x180015403  mov     rcx, [r8]
0x180015406  jmp     short loc_18001540B
0x180015408  mov     rcx, rdi
0x18001540b  xor     eax, eax
0x18001540d  mov     [rcx], ax
0x180015410  mov     [rsp+0CE0h+var_CB0], eax
0x180015414  xorps   xmm0, xmm0
0x180015417  movdqu  [rsp+0CE0h+var_CA0], xmm0
0x18001541d  mov     [rsp+0CE0h+var_C90], rax
0x180015422  lea     r9, [rsp+0CE0h+var_CA0]
0x180015427  lea     r8, [rsp+0CE0h+var_CB0]
0x18001542c  lea     ecx, [rax+0Ah]; Flags
0x18001542f  call    ?EnumeratePrinters@DeviceConfiguration@@YAJKKPEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; DeviceConfiguration::EnumeratePrinters(ulong,ulong,ulong *,std::vector<uchar> &)
0x180015434  mov     rcx, [rbp+0BE8h]; this
0x18001543b  lea     rdx, aEnumerateprint; "EnumeratePrinters failed!"
0x180015442  mov     qword ptr [rsp+0CE0h+var_CC0], rdx; int
0x180015447  mov     r9d, eax; char *
0x18001544a  lea     r13, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015451  mov     r8, r13; unsigned int
0x180015454  mov     edx, 118h; void *
0x180015459  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001545e  mov     r15, qword ptr [rsp+0CE0h+var_CA0]
0x180015463  xor     edx, edx; hFile
0x180015465  mov     r8d, 802h; dwFlags
0x18001546b  lea     rcx, LibFileName; "printui.dll"
0x180015472  call    cs:__imp_LoadLibraryExW
0x180015478  mov     rbx, rax
0x18001547b  mov     [rsp+0CE0h+var_CA8], rax
0x180015480  mov     rcx, [rbp+0BE8h]
0x180015487  lea     rax, aFailedToLoadLi; "Failed to load library printui.dll!"
0x18001548e  mov     [rsp+0CE0h+var_CB8], rax; char *
0x180015493  mov     qword ptr [rsp+0CE0h+var_CC0], rbx
0x180015498  mov     r9d, 8000FFFFh
0x18001549e  mov     r8, r13
0x1800154a1  mov     edx, 11Fh
0x1800154a6  call    ??$Throw_HrIfNullMsg@PEAUHINSTANCE__@@$0A@@in1diag3@details@wil@@YAPEAUHINSTANCE__@@PEAXIPEBDJPEAU3@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<HINSTANCE__ *,0>(void *,uint,char const *,long,HINSTANCE__ *,char const *,...)
0x1800154ab  mov     esi, 410h
0x1800154b0  mov     r8d, esi; Size
0x1800154b3  xor     edx, edx; Val
0x1800154b5  lea     rcx, [rbp+0BE0h+Buffer]; void *
0x1800154bc  call    memset_0
0x1800154c1  mov     r8d, esi; Size
0x1800154c4  xor     edx, edx; Val
0x1800154c6  lea     rcx, [rbp+0BE0h+var_440]; void *
0x1800154cd  call    memset_0
0x1800154d2  mov     r8d, esi; Size
0x1800154d5  xor     edx, edx; Val
0x1800154d7  lea     rcx, [rbp+0BE0h+var_C60]; void *
0x1800154db  call    memset_0
0x1800154e0  mov     r9d, 208h; cchBufferMax
0x1800154e6  lea     r8, [rbp+0BE0h+Buffer]; lpBuffer
0x1800154ed  mov     edx, 4A38h; uID
0x1800154f2  mov     rcx, rbx; hInstance
0x1800154f5  call    cs:__imp_LoadStringW
0x1800154fb  test    eax, eax
0x1800154fd  setz    al
0x180015500  mov     rcx, [rbp+0BE8h]; this
0x180015507  lea     rdx, aLoadstringFail; "LoadString failed!"
0x18001550e  mov     qword ptr [rsp+0CE0h+var_CC0], rdx; bool
0x180015513  movzx   r9d, al; char *
0x180015517  mov     r8, r13; unsigned int
0x18001551a  mov     edx, 133h; void *
0x18001551f  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180015524  mov     esi, 1
0x180015529  mov     r9d, esi
0x18001552c  lea     r8, [rbp+0BE0h+Buffer]; unsigned __int16 *
0x180015533  mov     ebx, 208h
0x180015538  mov     edx, ebx; unsigned __int64
0x18001553a  lea     rcx, [rbp+0BE0h+var_440]; unsigned __int16 *
0x180015541  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015546  mov     rcx, [rbp+0BE8h]; this
0x18001554d  lea     rdx, aStringcchprint; "StringCchPrintf (first format) failed!"
0x180015554  mov     qword ptr [rsp+0CE0h+var_CC0], rdx; int
0x180015559  mov     r9d, eax; char *
0x18001555c  mov     r8, r13; unsigned int
0x18001555f  mov     edx, 136h; void *
0x180015564  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015569  cmp     qword ptr [r14+18h], 7
0x18001556e  jbe     short loc_180015575
0x180015570  mov     r9, [r14]
0x180015573  jmp     short loc_180015578
0x180015575  mov     r9, r14
0x180015578  lea     r8, [rbp+0BE0h+var_440]; unsigned __int16 *
0x18001557f  mov     rdx, rbx; unsigned __int64
0x180015582  lea     rcx, [rbp+0BE0h+var_C60]; unsigned __int16 *
0x180015586  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001558b  mov     rcx, [rbp+0BE8h]; this
0x180015592  lea     rdx, aStringcchprint_0; "StringCchPrintf (second format) failed!"
0x180015599  mov     qword ptr [rsp+0CE0h+var_CC0], rdx; int
0x18001559e  mov     r9d, eax; char *
0x1800155a1  mov     r8, r13; unsigned int
0x1800155a4  mov     edx, 137h; void *
0x1800155a9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800155ae  lea     rdx, [rbp+0BE0h+var_C60]
0x1800155b2  lea     rcx, [rsp+0CE0h+var_C88]
0x1800155b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800155bc  nop
0x1800155bd  mov     r9, r15
0x1800155c0  mov     r8d, [rsp+0CE0h+var_CB0]
0x1800155c5  lea     rdx, [rsp+0CE0h+var_C88]
0x1800155ca  call    ?_IsPrinterNameUnique@DeviceInstaller@DeviceConfiguration@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAU_PRINTER_INFO_2W@@@Z; DeviceConfiguration::DeviceInstaller::_IsPrinterNameUnique(std::wstring const &,ulong,_PRINTER_INFO_2W *)
0x1800155cf  mov     bl, al
0x1800155d1  lea     rcx, [rsp+0CE0h+var_C88]
0x1800155d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800155db  test    bl, bl
0x1800155dd  jnz     short loc_1800155F4
0x1800155df  inc     esi
0x1800155e1  cmp     esi, 3E8h
0x1800155e7  jb      loc_180015529
0x1800155ed  mov     ebx, 80070490h
0x1800155f2  jmp     short loc_180015630
0x1800155f4  lea     r8, [rbp+0BE0h+var_C60]
0x1800155f8  lea     rdx, aCreatedUniqueP; "Created unique printer name %ws"
0x1800155ff  lea     rcx, aDeviceconfigur_4; "DeviceConfiguration::DeviceInstaller::_"...
0x180015606  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001560b  lea     rdx, [rbp+0BE0h+var_C60]
0x18001560f  lea     rcx, [rsp+0CE0h+var_C88]
0x180015614  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015619  mov     rdx, rax
0x18001561c  mov     rcx, rdi
0x18001561f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180015624  lea     rcx, [rsp+0CE0h+var_C88]
0x180015629  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001562e  xor     ebx, ebx
0x180015630  lea     rcx, [rsp+0CE0h+var_CA8]
0x180015635  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001563a  nop
0x18001563b  lea     rcx, [rsp+0CE0h+var_CA0]
0x180015640  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180015645  mov     eax, ebx
0x180015647  mov     rcx, [rbp+0BE0h+var_30]
0x18001564e  xor     rcx, rsp; StackCookie
0x180015651  call    __security_check_cookie
0x180015656  lea     r11, [rsp+0CE0h+var_20]
0x18001565e  mov     rbx, [r11+30h]
0x180015662  mov     rsi, [r11+48h]
0x180015666  mov     rsp, r11
0x180015669  pop     r15
0x18001566b  pop     r14
0x18001566d  pop     r13
0x18001566f  pop     rdi
0x180015670  pop     rbp
0x180015671  retn
```
