# PrinterConnection::PreInitializeGUIDPrinter(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)

- ea: `0x180015cb0`
- end: `0x1800162da`
- name: `?PreInitializeGUIDPrinter@PrinterConnection@@SAXAEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z`
- size: `1578`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001aecc`
- `0x18001b6d0`

## callees

- `0x1800032e0`
- `0x180003b00`
- `0x180004424`
- `0x18000da28`
- `0x18000dadc`
- `0x18000e348`
- `0x18000f380`
- `0x18000f590`
- `0x18001593c`
- `0x180015a90`
- `0x180015cb0`
- `0x180018818`
- `0x18001899c`
- `0x180018a28`
- `0x180018bbc`
- `0x180035e18`
- `0x180036714`
- `0x1800368e8`
- `0x180150f14`
- `0x180153cd4`
- `0x1801adb58`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180016045`
- `KERNEL32!GetLastError` at `0x180016045`
- `ADVAPI32!RegCloseKey` at `0x180015ebe`
- `ADVAPI32!RegCloseKey` at `0x180015ebe`
- `WINSPOOL!SetPrinterDataW` at `0x180016092`
- `WINSPOOL!SetPrinterDataW` at `0x180016100`
- `WINSPOOL!SetPrinterDataW` at `0x180016092`
- `WINSPOOL!SetPrinterDataW` at `0x180016100`
- `WINSPOOL!ClosePrinter` at `0x180016148`
- `WINSPOOL!ClosePrinter` at `0x180016148`
- `WINSPOOL!OpenPrinterW` at `0x180016036`
- `WINSPOOL!OpenPrinterW` at `0x180016036`

## string_xrefs

- `0x180015db0`: `\Monitors\Client Side Port\`
- `0x180015d9f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Print\Providers\Client Side Rendering Print Provider\Servers\`
- `0x180015e6c`: `PrinterPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall PrinterConnection::PreInitializeGUIDPrinter(Win32Adapters::Version *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int128 *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r8
  void *v11; // rax
  int PrinterInfo1; // eax
  int v13; // ebx
  HKEY v14; // rbx
  void *v15; // rsi
  _WORD *v16; // r9
  unsigned __int64 v17; // rdx
  LPBYTE *v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rax
  signed int LastError; // eax
  bool v22; // sf
  BYTE *v23; // r9
  signed int v24; // eax
  signed int v25; // ebx
  DWORD cbData; // ebx
  __int64 v27; // rax
  signed int v28; // ebx
  bool v29; // sf
  int v30; // eax
  int v31; // ebx
  char v33; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE phPrinter; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  char *v36; // [rsp+58h] [rbp-A8h]
  char v37; // [rsp+60h] [rbp-A0h]
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+68h] [rbp-98h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h]
  _BYTE pExceptionObject[32]; // [rsp+88h] [rbp-78h] BYREF
  LPBYTE pData[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v42; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v43; // [rsp+C0h] [rbp-40h]
  __int128 Src; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v45; // [rsp+D8h] [rbp-28h]
  __int128 v46; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v47; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v48; // [rsp+100h] [rbp+0h]
  __int128 v49; // [rsp+108h] [rbp+8h] BYREF
  __int128 v50; // [rsp+118h] [rbp+18h]
  __int128 v51; // [rsp+128h] [rbp+28h] BYREF
  __int64 v52; // [rsp+138h] [rbp+38h]
  __int64 v53; // [rsp+140h] [rbp+40h]
  __int128 v54; // [rsp+148h] [rbp+48h] BYREF
  __int64 v55; // [rsp+158h] [rbp+58h]
  __int64 v56; // [rsp+160h] [rbp+60h]

  v39 = -2;
  *(_OWORD *)pData = 0;
  v42 = 0;
  v43 = 7;
  LOWORD(pData[0]) = 0;
  if ( Win32Adapters::Version::IsOlderThanWin8(a1) )
  {
    v46 = 0;
    v47 = 0;
    v48 = 7;
    LOWORD(v46) = 0;
    v51 = 0;
    v52 = 0;
    v53 = 7;
    LOWORD(v51) = 0;
    v2 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1, pExceptionObject);
    PrinterConnectionUtil::ParseGUIDPrinterName(v2, &v51, &v46);
    std::wstring::~wstring(pExceptionObject);
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v47) < 0x6A )
      std::_Xlen_string();
    v5 = &v46;
    if ( v48 > 7 )
      v5 = (__int128 *)v46;
    std::wstring::wstring(
      pExceptionObject,
      v3,
      v4,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\Providers\\Client Side Rendering Print Provider\\Servers\\",
      106,
      v5,
      v47);
    v6 = std::wstring::append(pExceptionObject, L"\\Monitors\\Client Side Port\\");
    Src = 0;
    v45 = 0u;
    Src = *(_OWORD *)v6;
    v45 = *(_OWORD *)(v6 + 16);
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)(v6 + 24) = 7;
    *(_WORD *)v6 = 0;
    v7 = std::wstring::append(&Src);
    v49 = 0;
    v50 = 0u;
    v49 = *(_OWORD *)v7;
    v50 = *(_OWORD *)(v7 + 16);
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v7 + 24) = 7;
    *(_WORD *)v7 = 0;
    std::wstring::~wstring(&Src);
    std::wstring::~wstring(pExceptionObject);
    hKey = 0;
    Win32Adapters::Registry::RegOpenKeyW(v8, &v49, v9, &hKey);
    v54 = 0;
    v55 = 0;
    v56 = 7;
    LOWORD(v54) = 0;
    Src = 0;
    v45 = 0u;
    std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"PrinterPath", 0xBu);
    LOBYTE(v10) = 1;
    Win32Adapters::Registry::RegQueryValueW(&hKey, &Src, v10, &v54);
    std::wstring::~wstring(&Src);
    PrinterConnectionUtil::ParseCSRPortPrinterPath(&v54, pData);
    std::wstring::~wstring(&v54);
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    std::wstring::~wstring(&v49);
    std::wstring::~wstring(&v51);
    std::wstring::~wstring(&v46);
  }
  else
  {
    hKey = 0;
    v11 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 40LL))(*(_QWORD *)a1);
    PrinterInfo1 = PrivateGetPrinterInfo1(v11, (struct _PRINTER_INFO_1W **)&hKey);
    v13 = PrinterInfo1;
    if ( PrinterInfo1 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          87,
          WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
          (unsigned int)PrinterInfo1);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v13);
      throw (hr_error *)pExceptionObject;
    }
    v33 = 0;
    v14 = hKey;
    v36 = &v33;
    v37 = 1;
    v15 = operator new(0x18u);
    *(_OWORD *)v15 = 0;
    *((_DWORD *)v15 + 2) = 1;
    *((_DWORD *)v15 + 3) = 1;
    *(_QWORD *)v15 = &std::_Ref_count_resource<_PRINTER_INFO_1W *,_lambda_f5a2a3fa1d5012707ef3805cb89c45a1_>::`vftable';
    *((_QWORD *)v15 + 2) = v14;
    hKey = v14;
    v36 = (char *)v15;
    v16 = (_WORD *)*((_QWORD *)v14 + 3);
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    if ( v17 > v43 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(pData);
    }
    else
    {
      v18 = pData;
      if ( v43 > 7 )
        v18 = (LPBYTE *)pData[0];
      v42 = v17;
      v19 = 2 * v17;
      memmove_0(v18, v16, 2 * v17);
      *(_WORD *)((char *)v18 + v19) = 0;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v15)(v15);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v20 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1, &v51);
  if ( *(_QWORD *)(v20 + 24) > 7u )
    v20 = *(_QWORD *)v20;
  phPrinter = 0;
  if ( !OpenPrinterW((LPWSTR)v20, &phPrinter, &pDefault) )
  {
    LastError = GetLastError();
    v22 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v22 = LastError < 0;
    }
    if ( v22 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, LastError);
      throw (hr_error *)pExceptionObject;
    }
  }
  std::wstring::~wstring(&v51);
  v23 = (BYTE *)pData;
  if ( v43 > 7 )
    v23 = pData[0];
  v24 = SetPrinterDataW(phPrinter, (LPWSTR)L"V4_Connection_Name", 1u, v23, 2 * v42 + 2);
  v25 = v24;
  if ( v24 )
  {
    if ( v24 > 0 )
      v25 = (unsigned __int16)v24 | 0x80070000;
    if ( v25 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          88,
          WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
          (unsigned int)v25);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v25);
      throw (hr_error *)pExceptionObject;
    }
  }
  cbData = 2
         * *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1, &v49) + 16)
         + 2;
  v27 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1, pExceptionObject);
  if ( *(_QWORD *)(v27 + 24) > 7u )
    v27 = *(_QWORD *)v27;
  v28 = SetPrinterDataW(phPrinter, (LPWSTR)L"V4_GUID_Printer_Name", 1u, (LPBYTE)v27, cbData);
  std::wstring::~wstring(pExceptionObject);
  std::wstring::~wstring(&v49);
  v29 = v28 < 0;
  if ( v28 )
  {
    if ( v28 > 0 )
    {
      v28 = (unsigned __int16)v28 | 0x80070000;
      v29 = v28 < 0;
    }
    if ( v29 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          89,
          WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
          (unsigned int)v28);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v28);
      throw (hr_error *)pExceptionObject;
    }
  }
  v30 = UpdateV4PrinterCacheChangeID(phPrinter);
  v31 = v30;
  if ( v30 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        90,
        WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
        (unsigned int)v30);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v31);
    throw (hr_error *)pExceptionObject;
  }
  if ( phPrinter )
  {
    ClosePrinter(phPrinter);
    phPrinter = 0;
  }
  return std::wstring::~wstring(pData);
}

```

## disassembly

```asm
0x180015cb0  mov     rax, rsp
0x180015cb3  push    rbp
0x180015cb4  push    rdi
0x180015cb5  push    r12
0x180015cb7  push    r13
0x180015cb9  push    r15
0x180015cbb  lea     rbp, [rsp-70h]
0x180015cc0  sub     rsp, 170h
0x180015cc7  mov     [rbp+90h+var_110], 0FFFFFFFFFFFFFFFEh
0x180015ccf  mov     [rax+10h], rbx
0x180015cd3  mov     [rax+18h], rsi
0x180015cd7  mov     rax, cs:__security_cookie
0x180015cde  xor     rax, rsp
0x180015ce1  mov     [rbp+90h+var_28], rax
0x180015ce5  mov     r15, rcx
0x180015ce8  xor     r12d, r12d
0x180015ceb  xorps   xmm0, xmm0
0x180015cee  movups  xmmword ptr [rbp+90h+pData], xmm0
0x180015cf2  mov     [rbp+90h+var_D8], r12
0x180015cf6  lea     r13d, [r12+7]
0x180015cfb  mov     [rbp+90h+var_D0], r13
0x180015cff  mov     word ptr [rbp+90h+pData], r12w
0x180015d04  call    ?IsOlderThanWin8@Version@Win32Adapters@@YA_NXZ; Win32Adapters::Version::IsOlderThanWin8(void)
0x180015d09  test    al, al
0x180015d0b  jz      loc_180015EEB
0x180015d11  xorps   xmm0, xmm0
0x180015d14  movups  [rbp+90h+var_A8], xmm0
0x180015d18  mov     [rbp+90h+var_98], r12
0x180015d1c  mov     [rbp+90h+var_90], r13
0x180015d20  mov     word ptr [rbp+90h+var_A8], r12w
0x180015d25  movups  [rbp+90h+var_68], xmm0
0x180015d29  mov     [rbp+90h+var_58], r12
0x180015d2d  mov     [rbp+90h+var_50], r13
0x180015d31  mov     word ptr [rbp+90h+var_68], r12w
0x180015d36  mov     rcx, [r15]
0x180015d39  mov     rax, [rcx]
0x180015d3c  lea     rdx, [rbp+90h+pExceptionObject]
0x180015d40  mov     rax, [rax+20h]
0x180015d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d49  nop
0x180015d4a  lea     r8, [rbp+90h+var_A8]
0x180015d4e  lea     rdx, [rbp+90h+var_68]
0x180015d52  mov     rcx, rax
0x180015d55  call    ?ParseGUIDPrinterName@PrinterConnectionUtil@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@1@Z; PrinterConnectionUtil::ParseGUIDPrinterName(std::wstring const &,std::wstring &,std::wstring &)
0x180015d5a  nop
0x180015d5b  lea     rcx, [rbp+90h+pExceptionObject]
0x180015d5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015d64  mov     rcx, [rbp+90h+var_98]
0x180015d68  mov     rax, 7FFFFFFFFFFFFFFEh
0x180015d72  sub     rax, rcx
0x180015d75  cmp     rax, 6Ah ; 'j'
0x180015d79  jb      loc_1800161D1
0x180015d7f  lea     rax, [rbp+90h+var_A8]
0x180015d83  cmp     [rbp+90h+var_90], r13
0x180015d87  cmova   rax, qword ptr [rbp+90h+var_A8]
0x180015d8c  mov     [rsp+190h+var_160], rcx
0x180015d91  mov     [rsp+190h+var_168], rax
0x180015d96  mov     qword ptr [rsp+190h+cbData], 6Ah ; 'j'
0x180015d9f  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180015da6  lea     rcx, [rbp+90h+pExceptionObject]
0x180015daa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180015daf  nop
0x180015db0  lea     rdx, aMonitorsClient; "\\Monitors\\Client Side Port\\"
0x180015db7  lea     rcx, [rbp+90h+pExceptionObject]; Src
0x180015dbb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180015dc0  xorps   xmm0, xmm0
0x180015dc3  movups  [rbp+90h+Src], xmm0
0x180015dc7  mov     qword ptr [rbp+90h+var_B8], r12
0x180015dcb  mov     qword ptr [rbp+90h+var_B8+8], r12
0x180015dcf  movups  xmm0, xmmword ptr [rax]
0x180015dd2  movups  [rbp+90h+Src], xmm0
0x180015dd6  movups  xmm1, xmmword ptr [rax+10h]
0x180015dda  movups  [rbp+90h+var_B8], xmm1
0x180015dde  mov     [rax+10h], r12
0x180015de2  mov     [rax+18h], r13
0x180015de6  mov     [rax], r12w
0x180015dea  lea     rdx, [rbp+90h+var_68]
0x180015dee  lea     rcx, [rbp+90h+Src]; Src
0x180015df2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180015df7  xorps   xmm0, xmm0
0x180015dfa  movups  [rbp+90h+var_88], xmm0
0x180015dfe  mov     qword ptr [rbp+90h+var_78], r12
0x180015e02  mov     qword ptr [rbp+90h+var_78+8], r12
0x180015e06  movups  xmm0, xmmword ptr [rax]
0x180015e09  movups  [rbp+90h+var_88], xmm0
0x180015e0d  movups  xmm1, xmmword ptr [rax+10h]
0x180015e11  movups  [rbp+90h+var_78], xmm1
0x180015e15  mov     [rax+10h], r12
0x180015e19  mov     [rax+18h], r13
0x180015e1d  mov     [rax], r12w
0x180015e21  lea     rcx, [rbp+90h+Src]
0x180015e25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015e2a  nop
0x180015e2b  lea     rcx, [rbp+90h+pExceptionObject]
0x180015e2f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015e34  mov     [rsp+190h+hKey], r12
0x180015e39  lea     r9, [rsp+190h+hKey]
0x180015e3e  lea     rdx, [rbp+90h+var_88]
0x180015e42  call    ?RegOpenKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegOpenKeyW(HKEY__ *,std::wstring const &,bool,RegistryHandleRAII &)
0x180015e47  xorps   xmm0, xmm0
0x180015e4a  movups  [rbp+90h+var_48], xmm0
0x180015e4e  mov     [rbp+90h+var_38], r12
0x180015e52  mov     [rbp+90h+var_30], r13
0x180015e56  mov     word ptr [rbp+90h+var_48], r12w
0x180015e5b  movups  [rbp+90h+Src], xmm0
0x180015e5f  mov     qword ptr [rbp+90h+var_B8], r12
0x180015e63  mov     qword ptr [rbp+90h+var_B8+8], r12
0x180015e67  lea     r8d, [r12+0Bh]
0x180015e6c  lea     rdx, aPrinterpath; "PrinterPath"
0x180015e73  lea     rcx, [rbp+90h+Src]
0x180015e77  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180015e7c  nop
0x180015e7d  lea     r9, [rbp+90h+var_48]
0x180015e81  mov     r8b, 1
0x180015e84  lea     rdx, [rbp+90h+Src]
0x180015e88  lea     rcx, [rsp+190h+hKey]
0x180015e8d  call    ?RegQueryValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV45@@Z; Win32Adapters::Registry::RegQueryValueW(RegistryHandleRAII &,std::wstring const &,bool,std::wstring &)
0x180015e92  nop
0x180015e93  lea     rcx, [rbp+90h+Src]
0x180015e97  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015e9c  lea     rdx, [rbp+90h+pData]
0x180015ea0  lea     rcx, [rbp+90h+var_48]
0x180015ea4  call    ?ParseCSRPortPrinterPath@PrinterConnectionUtil@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; PrinterConnectionUtil::ParseCSRPortPrinterPath(std::wstring const &,std::wstring &)
0x180015ea9  nop
0x180015eaa  lea     rcx, [rbp+90h+var_48]
0x180015eae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015eb3  nop
0x180015eb4  mov     rcx, [rsp+190h+hKey]; hKey
0x180015eb9  test    rcx, rcx
0x180015ebc  jz      short loc_180015EC9
0x180015ebe  call    cs:__imp_RegCloseKey
0x180015ec4  mov     [rsp+190h+hKey], r12
0x180015ec9  lea     rcx, [rbp+90h+var_88]
0x180015ecd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015ed2  nop
0x180015ed3  lea     rcx, [rbp+90h+var_68]
0x180015ed7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015edc  nop
0x180015edd  lea     rcx, [rbp+90h+var_A8]
0x180015ee1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015ee6  jmp     loc_180015FF5
0x180015eeb  mov     [rsp+190h+hKey], r12
0x180015ef0  mov     rcx, [r15]
0x180015ef3  mov     rax, [rcx]
0x180015ef6  mov     rax, [rax+28h]
0x180015efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eff  mov     rcx, rax; hPrinter
0x180015f02  lea     rdx, [rsp+190h+hKey]; struct _PRINTER_INFO_1W **
0x180015f07  call    ?PrivateGetPrinterInfo1@@YAJPEAXPEAPEAU_PRINTER_INFO_1W@@@Z; PrivateGetPrinterInfo1(void *,_PRINTER_INFO_1W * *)
0x180015f0c  mov     ebx, eax
0x180015f0e  test    eax, eax
0x180015f10  js      loc_1800161D7
0x180015f16  mov     [rsp+190h+var_150], r12b
0x180015f1b  mov     rbx, [rsp+190h+hKey]
0x180015f20  mov     [rsp+190h+hKey], rbx
0x180015f25  lea     rax, [rsp+190h+var_150]
0x180015f2a  mov     [rsp+190h+var_138], rax
0x180015f2f  mov     [rsp+190h+var_130], 1
0x180015f34  mov     ecx, 18h; Size
0x180015f39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015f3e  mov     rsi, rax
0x180015f41  mov     [rsp+190h+hKey], rax
0x180015f46  xorps   xmm0, xmm0
0x180015f49  movups  xmmword ptr [rax], xmm0
0x180015f4c  mov     dword ptr [rax+8], 1
0x180015f53  mov     dword ptr [rax+0Ch], 1
0x180015f5a  lea     rax, ??_7?$_Ref_count_resource@PEAU_PRINTER_INFO_1W@@V_lambda_f5a2a3fa1d5012707ef3805cb89c45a1_@@@std@@6B@; const std::_Ref_count_resource<_PRINTER_INFO_1W *,_lambda_f5a2a3fa1d5012707ef3805cb89c45a1_>::`vftable'
0x180015f61  mov     [rsi], rax
0x180015f64  mov     [rsi+10h], rbx
0x180015f68  mov     [rsp+190h+hKey], rbx
0x180015f6d  mov     [rsp+190h+var_138], rsi
0x180015f72  mov     r9, [rbx+18h]
0x180015f76  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015f7a  inc     rdx
0x180015f7d  cmp     [r9+rdx*2], r12w
0x180015f82  jnz     short loc_180015F7A
0x180015f84  cmp     rdx, [rbp+90h+var_D0]
0x180015f88  ja      short loc_180015FB4
0x180015f8a  lea     rdi, [rbp+90h+pData]
0x180015f8e  cmp     [rbp+90h+var_D0], r13
0x180015f92  cmova   rdi, [rbp+90h+pData]
0x180015f97  mov     [rbp+90h+var_D8], rdx
0x180015f9b  lea     rbx, [rdx+rdx]
0x180015f9f  mov     r8, rbx; Size
0x180015fa2  mov     rdx, r9; Src
0x180015fa5  mov     rcx, rdi; void *
0x180015fa8  call    memmove_0
0x180015fad  mov     [rdi+rbx], r12w
0x180015fb2  jmp     short loc_180015FBE
0x180015fb4  lea     rcx, [rbp+90h+pData]
0x180015fb8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015fbd  nop
0x180015fbe  or      eax, 0FFFFFFFFh
0x180015fc1  lock xadd [rsi+8], eax
0x180015fc6  cmp     eax, 1
0x180015fc9  jnz     short loc_180015FF5
0x180015fcb  mov     rax, [rsi]
0x180015fce  mov     rcx, rsi
0x180015fd1  mov     rax, [rax]
0x180015fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fd9  or      eax, 0FFFFFFFFh
0x180015fdc  lock xadd [rsi+0Ch], eax
0x180015fe1  cmp     eax, 1
0x180015fe4  jnz     short loc_180015FF5
0x180015fe6  mov     rax, [rsi]
0x180015fe9  mov     rcx, rsi
0x180015fec  mov     rax, [rax+8]
0x180015ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ff5  xorps   xmm0, xmm0
0x180015ff8  movdqu  xmmword ptr [rsp+190h+pDefault.pDatatype], xmm0
0x180015ffe  mov     qword ptr [rsp+190h+pDefault.DesiredAccess], 0F000Ch
0x180016007  mov     rcx, [r15]
0x18001600a  mov     rax, [rcx]
0x18001600d  lea     rdx, [rbp+90h+var_68]
0x180016011  mov     rax, [rax+20h]
0x180016015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001601a  nop
0x18001601b  cmp     [rax+18h], r13
0x18001601f  jbe     short loc_180016024
0x180016021  mov     rax, [rax]
0x180016024  mov     [rsp+190h+phPrinter], r12
0x180016029  lea     r8, [rsp+190h+pDefault]; pDefault
0x18001602e  lea     rdx, [rsp+190h+phPrinter]; phPrinter
0x180016033  mov     rcx, rax; pPrinterName
0x180016036  call    cs:__imp_OpenPrinterW
0x18001603c  mov     edi, 80070000h
0x180016041  test    eax, eax
0x180016043  jnz     short loc_18001605C
0x180016045  call    cs:__imp_GetLastError
0x18001604b  test    eax, eax
0x18001604d  jle     short loc_180016056
0x18001604f  movzx   eax, ax
0x180016052  or      eax, edi
0x180016054  test    eax, eax
0x180016056  js      loc_180016224
0x18001605c  lea     rcx, [rbp+90h+var_68]
0x180016060  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016065  mov     eax, dword ptr [rbp+90h+var_D8]
0x180016068  lea     eax, ds:2[rax*2]
0x18001606f  lea     r9, [rbp+90h+pData]
0x180016073  cmp     [rbp+90h+var_D0], r13
0x180016077  cmova   r9, [rbp+90h+pData]; pData
0x18001607c  mov     [rsp+190h+cbData], eax; cbData
0x180016080  mov     r8d, 1; Type
0x180016086  lea     rdx, pValueName; "V4_Connection_Name"
0x18001608d  mov     rcx, [rsp+190h+phPrinter]; hPrinter
0x180016092  call    cs:__imp_SetPrinterDataW
0x180016098  mov     ebx, eax
0x18001609a  test    eax, eax
0x18001609c  jz      short loc_1800160AD
0x18001609e  jle     short loc_1800160A5
0x1800160a0  movzx   ebx, ax
0x1800160a3  or      ebx, edi
0x1800160a5  test    ebx, ebx
0x1800160a7  js      loc_180016240
0x1800160ad  mov     rcx, [r15]
0x1800160b0  mov     rax, [rcx]
0x1800160b3  lea     rdx, [rbp+90h+var_88]
0x1800160b7  mov     rax, [rax+20h]
0x1800160bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160c0  nop
0x1800160c1  mov     eax, [rax+10h]
0x1800160c4  lea     ebx, ds:2[rax*2]
0x1800160cb  mov     rcx, [r15]
0x1800160ce  mov     rax, [rcx]
0x1800160d1  lea     rdx, [rbp+90h+pExceptionObject]
0x1800160d5  mov     rax, [rax+20h]
0x1800160d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160de  cmp     [rax+18h], r13
0x1800160e2  jbe     short loc_1800160E7
0x1800160e4  mov     rax, [rax]
0x1800160e7  mov     [rsp+190h+cbData], ebx; cbData
0x1800160eb  mov     r9, rax; pData
0x1800160ee  mov     r8d, 1; Type
0x1800160f4  lea     rdx, aV4GuidPrinterN; "V4_GUID_Printer_Name"
0x1800160fb  mov     rcx, [rsp+190h+phPrinter]; hPrinter
0x180016100  call    cs:__imp_SetPrinterDataW
0x180016106  mov     ebx, eax
0x180016108  lea     rcx, [rbp+90h+pExceptionObject]
0x18001610c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016111  nop
0x180016112  lea     rcx, [rbp+90h+var_88]
0x180016116  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001611b  test    ebx, ebx
0x18001611d  jz      short loc_18001612E
0x18001611f  jle     short loc_180016128
0x180016121  movzx   ebx, bx
0x180016124  or      ebx, edi
0x180016126  test    ebx, ebx
0x180016128  js      loc_18001628D
0x18001612e  mov     rcx, [rsp+190h+phPrinter]; hPrinter
0x180016133  call    UpdateV4PrinterCacheChangeID
0x180016138  mov     ebx, eax
0x18001613a  test    eax, eax
0x18001613c  js      short loc_180016184
0x18001613e  mov     rcx, [rsp+190h+phPrinter]; hPrinter
0x180016143  test    rcx, rcx
0x180016146  jz      short loc_180016153
0x180016148  call    cs:__imp_ClosePrinter
0x18001614e  mov     [rsp+190h+phPrinter], r12
  ... truncated ...
```
