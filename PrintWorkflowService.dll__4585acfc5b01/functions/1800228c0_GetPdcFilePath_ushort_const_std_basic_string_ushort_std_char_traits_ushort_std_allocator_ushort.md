# GetPdcFilePath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800228c0`
- end: `0x180022d37`
- name: `?GetPdcFilePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1143`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18003ed20`
- `0x18004390c`

## callees

- `0x180003ca0`
- `0x18000495c`
- `0x180008698`
- `0x18000a014`
- `0x18000ef60`
- `0x1800113d4`
- `0x180012754`
- `0x180012784`
- `0x1800127a4`
- `0x180012820`
- `0x180020e8c`
- `0x180021198`
- `0x1800213ec`
- `0x1800220ec`
- `0x1800228c0`
- `0x180022d40`
- `0x180022da4`
- `0x180023664`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180022a9b`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180022ad6`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180022c2f`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180022a9b`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180022ad6`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180022c2f`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180022a35`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180022a35`
- `Print.PrintSupport.Source!IsPrinterConnection` at `0x18002291d`
- `Print.PrintSupport.Source!IsPrinterConnection` at `0x18002291d`

## string_xrefs

- `0x18002292b`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180022b39`: `PrintQueueV4DriverDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetPdcFilePath(__int64 a1, __int64 a2)
{
  int v4; // eax
  __int64 ConnectionSubKey; // rax
  __int64 v6; // rbx
  __int64 v7; // r8
  const WCHAR *v8; // rax
  PCWSTR v9; // r9
  HRESULT v10; // eax
  __int64 v11; // r8
  const char *v12; // r9
  __int64 result; // rax
  DWORD cbBuf; // [rsp+20h] [rbp-358h]
  DWORD cbBufa; // [rsp+20h] [rbp-358h]
  _BYTE v16[3]; // [rsp+31h] [rbp-347h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-340h] BYREF
  _BYTE v18[32]; // [rsp+48h] [rbp-330h] BYREF
  _BYTE v19[32]; // [rsp+68h] [rbp-310h] BYREF
  _BYTE v20[32]; // [rsp+88h] [rbp-2F0h] BYREF
  _BYTE v21[32]; // [rsp+A8h] [rbp-2D0h] BYREF
  _BYTE v22[32]; // [rsp+C8h] [rbp-2B0h] BYREF
  _BYTE v23[32]; // [rsp+E8h] [rbp-290h] BYREF
  BYTE v24[56]; // [rsp+108h] [rbp-270h] BYREF
  WCHAR pDriverDirectory[264]; // [rsp+140h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) = 0;
  memset_0(pDriverDirectory, 0, 0x208u);
  v16[0] = 0;
  v4 = IsPrinterConnection(a1, v16);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      (const char *)(unsigned int)v4,
      cbBuf);
  try
  {
    if ( v16[0] )
    {
      ConnectionSubKey = GetConnectionSubKey(v20, a1);
      v17[0] = -2147483646;
      v6 = PrintCore::RegHelpers::OpenKey(v17, ConnectionSubKey);
      v17[1] = v6;
      std::wstring::_Tidy_deallocate(v20);
      v17[0] = v6;
      PrintCore::RegHelpers::GetStringValue(v18, v17, v7, L"PrintDeviceCapabilities");
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)0x8000FFFFLL,
        cbBuf);
    }
    std::wstring::wstring(v18, a1);
    PrintCore::WinSpoolUtil::WinSpoolUtil((__int64)v24);
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::wstring(v21, L"PrintQueueV4DriverDirectory");
    std::wstring::wstring(v19, L"PrinterDriverData");
    PrintCore::WinSpoolUtil::GetPrinterDataAsString(v24, v20, v19, v21);
    std::wstring::_Tidy_deallocate(v19);
    std::wstring::_Tidy_deallocate(v21);
    std::wstring::wstring(v22, L"V4_PrintDeviceCapabilities");
    std::wstring::wstring(v18, L"PrinterDriverData");
    PrintCore::WinSpoolUtil::GetPrinterDataAsString(v24, v23, v18, v22);
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::_Tidy_deallocate(v22);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
    v10 = PathCchCombineEx(pDriverDirectory, 0x104u, v8, v9, 0);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v10,
        cbBufa);
    std::wstring::_Tidy_deallocate(v23);
    std::wstring::_Tidy_deallocate(v20);
    PrintCore::WinSpoolUtil::~WinSpoolUtil((PrintCore::WinSpoolUtil *)v24);
    v11 = -1;
    do
      ++v11;
    while ( pDriverDirectory[v11] );
    std::wstring::_Assign<unsigned short>(a2, pDriverDirectory);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1F3,
                           (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800228c0  mov     [rsp+arg_10], rbx
0x1800228c5  push    rsi
0x1800228c6  push    rdi
0x1800228c7  push    r14
0x1800228c9  sub     rsp, 360h
0x1800228d0  mov     rax, cs:__security_cookie
0x1800228d7  xor     rax, rsp
0x1800228da  mov     [rsp+378h+var_28], rax
0x1800228e2  mov     rsi, rdx
0x1800228e5  mov     rbx, rcx
0x1800228e8  xor     r14d, r14d
0x1800228eb  mov     [rdx+10h], r14
0x1800228ef  mov     rcx, rdx
0x1800228f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800228f7  mov     [rax], r14w
0x1800228fb  xor     edx, edx; Val
0x1800228fd  mov     r8d, 208h; Size
0x180022903  lea     rcx, [rsp+378h+pDriverDirectory]; void *
0x18002290b  call    memset_0
0x180022910  mov     [rsp+378h+var_347], r14b
0x180022915  lea     rdx, [rsp+378h+var_347]
0x18002291a  mov     rcx, rbx
0x18002291d  call    cs:__imp_IsPrinterConnection
0x180022923  mov     rcx, [rsp+378h]; this
0x18002292b  lea     rdi, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180022932  test    eax, eax
0x180022934  jns     short loc_180022946
0x180022936  mov     r9d, eax; char *
0x180022939  mov     r8, rdi; unsigned int
0x18002293c  mov     edx, 1D0h; void *
0x180022941  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022946  mov     rdx, rbx
0x180022949  cmp     [rsp+378h+var_347], r14b
0x18002294e  jz      loc_180022B11
0x180022954  lea     rcx, [rsp+378h+var_2F0]
0x18002295c  call    ?GetConnectionSubKey@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetConnectionSubKey(ushort const *)
0x180022961  nop
0x180022962  mov     [rsp+378h+var_340], 0FFFFFFFF80000002h
0x18002296b  mov     rdx, rax
0x18002296e  lea     rcx, [rsp+378h+var_340]
0x180022973  call    ?OpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; PrintCore::RegHelpers::OpenKey(HKEY__ * const &,std::wstring const &,ulong)
0x180022978  mov     rbx, rax
0x18002297b  mov     [rsp+378h+var_338], rax
0x180022980  lea     rcx, [rsp+378h+var_2F0]
0x180022988  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002298d  mov     [rsp+378h+var_348], r14b
0x180022992  mov     [rsp+378h+var_340], rbx
0x180022997  lea     rax, [rsp+378h+var_348]
0x18002299c  mov     [rsp+378h+pcbNeeded], rax
0x1800229a1  lea     r9, aPrintdevicecap; "PrintDeviceCapabilities"
0x1800229a8  lea     rdx, [rsp+378h+var_340]
0x1800229ad  lea     rcx, [rsp+378h+var_330]
0x1800229b2  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x1800229b7  nop
0x1800229b8  cmp     [rsp+378h+var_348], r14b
0x1800229bd  setz    al
0x1800229c0  mov     rcx, [rsp+378h]; this
0x1800229c8  test    al, al
0x1800229ca  jnz     loc_180022CC0
0x1800229d0  mov     [rsp+378h+var_340], rbx
0x1800229d5  lea     rax, [rsp+378h+var_348]
0x1800229da  mov     [rsp+378h+pcbNeeded], rax
0x1800229df  lea     r9, aConnectionguid; "ConnectionGUID"
0x1800229e6  lea     rdx, [rsp+378h+var_340]
0x1800229eb  lea     rcx, [rsp+378h+var_310]
0x1800229f0  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x1800229f5  nop
0x1800229f6  cmp     [rsp+378h+var_348], r14b
0x1800229fb  setz    al
0x1800229fe  mov     rcx, [rsp+378h]; this
0x180022a06  test    al, al
0x180022a08  jnz     loc_180022CD4
0x180022a0e  mov     [rsp+378h+var_344], r14d
0x180022a13  lea     rax, [rsp+378h+var_344]
0x180022a18  mov     [rsp+378h+pcbNeeded], rax; pcbNeeded
0x180022a1d  mov     [rsp+378h+cbBuf], 208h; int
0x180022a25  lea     r9, [rsp+378h+pDriverDirectory]; pDriverDirectory
0x180022a2d  xor     edx, edx; pEnvironment
0x180022a2f  xor     ecx, ecx; pName
0x180022a31  lea     r8d, [rdx+1]; Level
0x180022a35  call    cs:__imp_GetPrinterDriverDirectoryW
0x180022a3b  mov     rcx, [rsp+378h]; this
0x180022a43  test    eax, eax
0x180022a45  jz      loc_180022CE7
0x180022a4b  lea     r8, aV4connections; "\\V4Connections\\"
0x180022a52  mov     ebx, 104h
0x180022a57  mov     edx, ebx; unsigned __int64
0x180022a59  lea     rcx, [rsp+378h+pDriverDirectory]; unsigned __int16 *
0x180022a61  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022a66  mov     rcx, [rsp+378h]; this
0x180022a6e  test    eax, eax
0x180022a70  js      loc_180022CF4
0x180022a76  lea     rcx, [rsp+378h+var_310]
0x180022a7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022a80  mov     r9, rax; pszMore
0x180022a83  mov     [rsp+378h+cbBuf], r14d; int
0x180022a88  lea     r8, [rsp+378h+pDriverDirectory]; pszPathIn
0x180022a90  mov     rdx, rbx; cchPathOut
0x180022a93  lea     rcx, [rsp+378h+pDriverDirectory]; pszPathOut
0x180022a9b  call    cs:__imp_PathCchCombineEx
0x180022aa1  mov     rcx, [rsp+378h]; this
0x180022aa9  test    eax, eax
0x180022aab  js      loc_180022D04
0x180022ab1  lea     rcx, [rsp+378h+var_330]
0x180022ab6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022abb  mov     r9, rax; pszMore
0x180022abe  mov     [rsp+378h+cbBuf], r14d; int
0x180022ac3  lea     r8, [rsp+378h+pDriverDirectory]; pszPathIn
0x180022acb  mov     rdx, rbx; cchPathOut
0x180022ace  lea     rcx, [rsp+378h+pDriverDirectory]; pszPathOut
0x180022ad6  call    cs:__imp_PathCchCombineEx
0x180022adc  mov     rcx, [rsp+378h]; this
0x180022ae4  test    eax, eax
0x180022ae6  js      loc_180022D14
0x180022aec  lea     rcx, [rsp+378h+var_310]
0x180022af1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022af6  nop
0x180022af7  lea     rcx, [rsp+378h+var_330]
0x180022afc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b01  nop
0x180022b02  lea     rcx, [rsp+378h+var_338]
0x180022b07  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022b0c  jmp     loc_180022C6E
0x180022b11  lea     rcx, [rsp+378h+var_330]
0x180022b16  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022b1b  nop
0x180022b1c  lea     rdx, [rsp+378h+var_330]
0x180022b21  lea     rcx, [rsp+378h+var_270]
0x180022b29  call    ??0WinSpoolUtil@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; PrintCore::WinSpoolUtil::WinSpoolUtil(std::wstring const &,bool)
0x180022b2e  nop
0x180022b2f  lea     rcx, [rsp+378h+var_330]
0x180022b34  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b39  lea     rdx, pValueName; "PrintQueueV4DriverDirectory"
0x180022b40  lea     rcx, [rsp+378h+var_2D0]
0x180022b48  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022b4d  nop
0x180022b4e  lea     rdx, aPrinterdriverd; "PrinterDriverData"
0x180022b55  lea     rcx, [rsp+378h+var_310]
0x180022b5a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022b5f  nop
0x180022b60  lea     r9, [rsp+378h+var_2D0]
0x180022b68  lea     r8, [rsp+378h+var_310]
0x180022b6d  lea     rdx, [rsp+378h+var_2F0]
0x180022b75  lea     rcx, [rsp+378h+var_270]
0x180022b7d  call    ?GetPrinterDataAsString@WinSpoolUtil@PrintCore@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@0@Z; PrintCore::WinSpoolUtil::GetPrinterDataAsString(std::wstring const &,std::wstring const &)
0x180022b82  nop
0x180022b83  lea     rcx, [rsp+378h+var_310]
0x180022b88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b8d  nop
0x180022b8e  lea     rcx, [rsp+378h+var_2D0]
0x180022b96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b9b  lea     rdx, aV4Printdevicec; "V4_PrintDeviceCapabilities"
0x180022ba2  lea     rcx, [rsp+378h+var_2B0]
0x180022baa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022baf  nop
0x180022bb0  lea     rdx, aPrinterdriverd; "PrinterDriverData"
0x180022bb7  lea     rcx, [rsp+378h+var_330]
0x180022bbc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022bc1  nop
0x180022bc2  lea     r9, [rsp+378h+var_2B0]
0x180022bca  lea     r8, [rsp+378h+var_330]
0x180022bcf  lea     rdx, [rsp+378h+var_290]
0x180022bd7  lea     rcx, [rsp+378h+var_270]
0x180022bdf  call    ?GetPrinterDataAsString@WinSpoolUtil@PrintCore@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@0@Z; PrintCore::WinSpoolUtil::GetPrinterDataAsString(std::wstring const &,std::wstring const &)
0x180022be4  nop
0x180022be5  lea     rcx, [rsp+378h+var_330]
0x180022bea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022bef  nop
0x180022bf0  lea     rcx, [rsp+378h+var_2B0]
0x180022bf8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022bfd  lea     rcx, [rsp+378h+var_290]
0x180022c05  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022c0a  mov     r9, rax
0x180022c0d  lea     rcx, [rsp+378h+var_2F0]
0x180022c15  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022c1a  mov     r8, rax; pszPathIn
0x180022c1d  mov     [rsp+378h+cbBuf], r14d; int
0x180022c22  mov     edx, 104h; cchPathOut
0x180022c27  lea     rcx, [rsp+378h+pDriverDirectory]; pszPathOut
0x180022c2f  call    cs:__imp_PathCchCombineEx
0x180022c35  mov     rcx, [rsp+378h]; this
0x180022c3d  test    eax, eax
0x180022c3f  js      loc_180022D25
0x180022c45  lea     rcx, [rsp+378h+var_290]
0x180022c4d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022c52  nop
0x180022c53  lea     rcx, [rsp+378h+var_2F0]
0x180022c5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022c60  nop
0x180022c61  lea     rcx, [rsp+378h+var_270]; this
0x180022c69  call    ??1WinSpoolUtil@PrintCore@@QEAA@XZ; PrintCore::WinSpoolUtil::~WinSpoolUtil(void)
0x180022c6e  lea     rax, [rsp+378h+pDriverDirectory]
0x180022c76  or      r8, 0FFFFFFFFFFFFFFFFh
0x180022c7a  inc     r8
0x180022c7d  cmp     [rax+r8*2], r14w
0x180022c82  jnz     short loc_180022C7A
0x180022c84  lea     rdx, [rsp+378h+pDriverDirectory]
0x180022c8c  mov     rcx, rsi
0x180022c8f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180022c94  xor     eax, eax
0x180022c96  jmp     short loc_180022C9C
0x180022c98  mov     eax, [rsp+378h+var_344]
0x180022c9c  mov     rcx, [rsp+378h+var_28]
0x180022ca4  xor     rcx, rsp; StackCookie
0x180022ca7  call    __security_check_cookie
0x180022cac  mov     rbx, [rsp+378h+arg_10]
0x180022cb4  add     rsp, 360h
0x180022cbb  pop     r14
0x180022cbd  pop     rdi
0x180022cbe  pop     rsi
0x180022cbf  retn
0x180022cc0  mov     r9d, 8000FFFFh; char *
0x180022cc6  mov     r8, rdi; unsigned int
0x180022cc9  mov     edx, 1D8h; void *
0x180022cce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022cd4  mov     r9d, 8000FFFFh; char *
0x180022cda  mov     r8, rdi; unsigned int
0x180022cdd  mov     edx, 1DBh; void *
0x180022ce2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022ce7  mov     r8, rdi; unsigned int
0x180022cea  mov     edx, 1E1h; void *
0x180022cef  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180022cf4  mov     r9d, eax; char *
0x180022cf7  mov     r8, rdi; unsigned int
0x180022cfa  mov     edx, 1E2h; void *
0x180022cff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022d04  mov     r9d, eax; char *
0x180022d07  mov     r8, rdi; unsigned int
0x180022d0a  mov     edx, 1E3h; void *
0x180022d0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022d14  mov     r9d, eax; char *
0x180022d17  mov     r8, rdi; unsigned int
0x180022d1a  mov     edx, 1E4h; void *
0x180022d1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022d25  mov     r9d, eax; char *
0x180022d28  mov     r8, rdi; unsigned int
0x180022d2b  mov     edx, 1ECh; void *
0x180022d30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
