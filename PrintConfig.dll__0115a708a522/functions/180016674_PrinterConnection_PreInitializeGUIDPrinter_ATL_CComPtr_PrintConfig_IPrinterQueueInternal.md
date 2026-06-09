# PrinterConnection::PreInitializeGUIDPrinter(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)

- ea: `0x180016674`
- end: `0x180016cc3`
- name: `?PreInitializeGUIDPrinter@PrinterConnection@@SAXAEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z`
- size: `1615`
- prototype: `__int64 __fastcall(Win32Adapters::Version *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bb3c`
- `0x18001c364`

## callees

- `0x180003400`
- `0x180003c20`
- `0x180004564`
- `0x18000de1c`
- `0x18000ded0`
- `0x18000e750`
- `0x18000f830`
- `0x18000fa4c`
- `0x1800162fc`
- `0x180016450`
- `0x180016674`
- `0x180019388`
- `0x18001958c`
- `0x180019618`
- `0x1800197b4`
- `0x180037124`
- `0x180037b14`
- `0x180037d00`
- `0x180157fb8`
- `0x18015af04`
- `0x1801b56c8`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180016a15`
- `KERNEL32!GetLastError` at `0x180016a15`
- `ADVAPI32!RegCloseKey` at `0x180016882`
- `ADVAPI32!RegCloseKey` at `0x180016882`
- `WINSPOOL!SetPrinterDataW` at `0x180016a68`
- `WINSPOOL!SetPrinterDataW` at `0x180016adc`
- `WINSPOOL!SetPrinterDataW` at `0x180016a68`
- `WINSPOOL!SetPrinterDataW` at `0x180016adc`
- `WINSPOOL!ClosePrinter` at `0x180016b2a`
- `WINSPOOL!ClosePrinter` at `0x180016b2a`
- `WINSPOOL!OpenPrinterW` at `0x180016a00`
- `WINSPOOL!OpenPrinterW` at `0x180016a00`

## string_xrefs

- `0x180016774`: `\Monitors\Client Side Port\`
- `0x180016763`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Print\Providers\Client Side Rendering Print Provider\Servers\`
- `0x180016830`: `PrinterPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall PrinterConnection::PreInitializeGUIDPrinter(Win32Adapters::Version *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int128 *v5; // rax
  __int64 v6; // r8
  void **v7; // rax
  __int64 v8; // r8
  void **v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  void *v12; // rax
  signed int PrinterInfo1; // eax
  int v14; // ebx
  HKEY v15; // rbx
  void *v16; // rsi
  __int64 v17; // r8
  _WORD *v18; // r9
  unsigned __int64 v19; // rdx
  LPBYTE *v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  signed int LastError; // eax
  bool v24; // sf
  BYTE *v25; // r9
  signed int v26; // eax
  signed int v27; // ebx
  DWORD cbData; // ebx
  __int64 v29; // rax
  signed int v30; // ebx
  bool v31; // sf
  signed int v32; // eax
  int v33; // ebx
  char v35; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE phPrinter; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  char *v38; // [rsp+58h] [rbp-A8h]
  char v39; // [rsp+60h] [rbp-A0h]
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+80h] [rbp-80h]
  void *pExceptionObject[4]; // [rsp+88h] [rbp-78h] BYREF
  LPBYTE pData[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v44; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v45; // [rsp+C0h] [rbp-40h]
  __int128 Src; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v47; // [rsp+D8h] [rbp-28h]
  __int128 v48; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v49; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v50; // [rsp+100h] [rbp+0h]
  __int128 v51; // [rsp+108h] [rbp+8h] BYREF
  __int128 v52; // [rsp+118h] [rbp+18h]
  __int128 v53; // [rsp+128h] [rbp+28h] BYREF
  __int64 v54; // [rsp+138h] [rbp+38h]
  __int64 v55; // [rsp+140h] [rbp+40h]
  __int128 v56; // [rsp+148h] [rbp+48h] BYREF
  __int64 v57; // [rsp+158h] [rbp+58h]
  __int64 v58; // [rsp+160h] [rbp+60h]

  v41 = -2;
  *(_OWORD *)pData = 0;
  v44 = 0;
  v45 = 7;
  LOWORD(pData[0]) = 0;
  if ( Win32Adapters::Version::IsOlderThanWin8(a1) )
  {
    v48 = 0;
    v49 = 0;
    v50 = 7;
    LOWORD(v48) = 0;
    v53 = 0;
    v54 = 0;
    v55 = 7;
    LOWORD(v53) = 0;
    v2 = (*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1, pExceptionObject);
    PrinterConnectionUtil::ParseGUIDPrinterName(v2, (char **)&v53, (char **)&v48);
    std::wstring::~wstring((char **)pExceptionObject);
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v49) < 0x6A )
      std::_Xlen_string();
    v5 = &v48;
    if ( v50 > 7 )
      v5 = (__int128 *)v48;
    std::wstring::wstring(
      (char *)pExceptionObject,
      v3,
      v4,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Print\\Providers\\Client Side Rendering Print Provider\\Servers\\",
      106,
      v5,
      v49);
    v7 = std::wstring::append(pExceptionObject, L"\\Monitors\\Client Side Port\\", v6);
    Src = 0;
    v47 = 0u;
    Src = *(_OWORD *)v7;
    v47 = *((_OWORD *)v7 + 1);
    v7[2] = 0;
    v7[3] = (void *)7;
    *(_WORD *)v7 = 0;
    v9 = std::wstring::append((void **)&Src, &v53, v8);
    v51 = 0;
    v52 = 0u;
    v51 = *(_OWORD *)v9;
    v52 = *((_OWORD *)v9 + 1);
    v9[2] = 0;
    v9[3] = (void *)7;
    *(_WORD *)v9 = 0;
    std::wstring::~wstring((char **)&Src);
    std::wstring::~wstring((char **)pExceptionObject);
    hKey = 0;
    Win32Adapters::Registry::RegOpenKeyW(v10, (const WCHAR *)&v51, v11, &hKey);
    v56 = 0;
    v57 = 0;
    v58 = 7;
    LOWORD(v56) = 0;
    Src = 0;
    v47 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(&Src, L"PrinterPath", 0xBu);
    Win32Adapters::Registry::RegQueryValueW(&hKey, (const WCHAR *)&Src, 1, (__int64)&v56);
    std::wstring::~wstring((char **)&Src);
    PrinterConnectionUtil::ParseCSRPortPrinterPath(&v56, (char **)pData);
    std::wstring::~wstring((char **)&v56);
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    std::wstring::~wstring((char **)&v51);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring((char **)&v48);
  }
  else
  {
    hKey = 0;
    v12 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 40LL))(*(_QWORD *)a1);
    PrinterInfo1 = PrivateGetPrinterInfo1(v12, (struct _PRINTER_INFO_1W **)&hKey);
    v14 = PrinterInfo1;
    if ( PrinterInfo1 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x57u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          PrinterInfo1);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v14);
      throw (hr_error *)pExceptionObject;
    }
    v35 = 0;
    v15 = hKey;
    v38 = &v35;
    v39 = 1;
    v16 = operator new(0x18u);
    *(_OWORD *)v16 = 0;
    *((_DWORD *)v16 + 2) = 1;
    *((_DWORD *)v16 + 3) = 1;
    *(_QWORD *)v16 = &std::_Ref_count_resource<_PRINTER_INFO_1W *,_lambda_f5a2a3fa1d5012707ef3805cb89c45a1_>::`vftable';
    *((_QWORD *)v16 + 2) = v15;
    hKey = v15;
    v38 = (char *)v16;
    v18 = (_WORD *)*((_QWORD *)v15 + 3);
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    if ( v19 > v45 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)pData,
        v19,
        v17,
        v18);
    }
    else
    {
      v20 = pData;
      if ( v45 > 7 )
        v20 = (LPBYTE *)pData[0];
      v44 = v19;
      v21 = 2 * v19;
      memmove_0(v20, v18, 2 * v19);
      *(_WORD *)((char *)v20 + v21) = 0;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v16)(v16);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v22 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1, &v53);
  if ( *(_QWORD *)(v22 + 24) > 7u )
    v22 = *(_QWORD *)v22;
  phPrinter = 0;
  if ( !OpenPrinterW((LPWSTR)v22, &phPrinter, &pDefault) )
  {
    LastError = GetLastError();
    v24 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v24 = LastError < 0;
    }
    if ( v24 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, LastError);
      throw (hr_error *)pExceptionObject;
    }
  }
  std::wstring::~wstring((char **)&v53);
  v25 = (BYTE *)pData;
  if ( v45 > 7 )
    v25 = pData[0];
  v26 = SetPrinterDataW(phPrinter, (LPWSTR)L"V4_Connection_Name", 1u, v25, 2 * v44 + 2);
  v27 = v26;
  if ( v26 )
  {
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x58u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v27);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v27);
      throw (hr_error *)pExceptionObject;
    }
  }
  cbData = 2
         * *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1, &v51) + 16)
         + 2;
  v29 = (*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1, pExceptionObject);
  if ( *(_QWORD *)(v29 + 24) > 7u )
    v29 = *(_QWORD *)v29;
  v30 = SetPrinterDataW(phPrinter, (LPWSTR)L"V4_GUID_Printer_Name", 1u, (LPBYTE)v29, cbData);
  std::wstring::~wstring((char **)pExceptionObject);
  std::wstring::~wstring((char **)&v51);
  v31 = v30 < 0;
  if ( v30 )
  {
    if ( v30 > 0 )
    {
      v30 = (unsigned __int16)v30 | 0x80070000;
      v31 = v30 < 0;
    }
    if ( v31 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x59u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v30);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v30);
      throw (hr_error *)pExceptionObject;
    }
  }
  v32 = UpdateV4PrinterCacheChangeID(phPrinter);
  v33 = v32;
  if ( v32 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x5Au,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v32);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v33);
    throw (hr_error *)pExceptionObject;
  }
  if ( phPrinter )
  {
    ClosePrinter(phPrinter);
    phPrinter = 0;
  }
  return std::wstring::~wstring((char **)pData);
}

```

## disassembly

```asm
0x180016674  mov     rax, rsp
0x180016677  push    rbp
0x180016678  push    rdi
0x180016679  push    r12
0x18001667b  push    r13
0x18001667d  push    r15
0x18001667f  lea     rbp, [rsp-70h]
0x180016684  sub     rsp, 170h
0x18001668b  mov     [rbp+90h+var_110], 0FFFFFFFFFFFFFFFEh
0x180016693  mov     [rax+10h], rbx
0x180016697  mov     [rax+18h], rsi
0x18001669b  mov     rax, cs:__security_cookie
0x1800166a2  xor     rax, rsp
0x1800166a5  mov     [rbp+90h+var_28], rax
0x1800166a9  mov     r15, rcx
0x1800166ac  xor     r12d, r12d
0x1800166af  xorps   xmm0, xmm0
0x1800166b2  movups  xmmword ptr [rbp+90h+pData], xmm0
0x1800166b6  mov     [rbp+90h+var_D8], r12
0x1800166ba  lea     r13d, [r12+7]
0x1800166bf  mov     [rbp+90h+var_D0], r13
0x1800166c3  mov     word ptr [rbp+90h+pData], r12w
0x1800166c8  call    ?IsOlderThanWin8@Version@Win32Adapters@@YA_NXZ; Win32Adapters::Version::IsOlderThanWin8(void)
0x1800166cd  test    al, al
0x1800166cf  jz      loc_1800168B5
0x1800166d5  xorps   xmm0, xmm0
0x1800166d8  movups  [rbp+90h+var_A8], xmm0
0x1800166dc  mov     [rbp+90h+var_98], r12
0x1800166e0  mov     [rbp+90h+var_90], r13
0x1800166e4  mov     word ptr [rbp+90h+var_A8], r12w
0x1800166e9  movups  [rbp+90h+var_68], xmm0
0x1800166ed  mov     [rbp+90h+var_58], r12
0x1800166f1  mov     [rbp+90h+var_50], r13
0x1800166f5  mov     word ptr [rbp+90h+var_68], r12w
0x1800166fa  mov     rcx, [r15]
0x1800166fd  mov     rax, [rcx]
0x180016700  lea     rdx, [rbp+90h+pExceptionObject]
0x180016704  mov     rax, [rax+20h]
0x180016708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001670d  nop
0x18001670e  lea     r8, [rbp+90h+var_A8]
0x180016712  lea     rdx, [rbp+90h+var_68]
0x180016716  mov     rcx, rax
0x180016719  call    ?ParseGUIDPrinterName@PrinterConnectionUtil@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@1@Z; PrinterConnectionUtil::ParseGUIDPrinterName(std::wstring const &,std::wstring &,std::wstring &)
0x18001671e  nop
0x18001671f  lea     rcx, [rbp+90h+pExceptionObject]
0x180016723  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016728  mov     rcx, [rbp+90h+var_98]
0x18001672c  mov     rax, 7FFFFFFFFFFFFFFEh
0x180016736  sub     rax, rcx
0x180016739  cmp     rax, 6Ah ; 'j'
0x18001673d  jb      loc_180016BBA
0x180016743  lea     rax, [rbp+90h+var_A8]
0x180016747  cmp     [rbp+90h+var_90], r13
0x18001674b  cmova   rax, qword ptr [rbp+90h+var_A8]
0x180016750  mov     [rsp+190h+var_160], rcx
0x180016755  mov     [rsp+190h+var_168], rax
0x18001675a  mov     qword ptr [rsp+190h+cbData], 6Ah ; 'j'
0x180016763  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001676a  lea     rcx, [rbp+90h+pExceptionObject]
0x18001676e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180016773  nop
0x180016774  lea     rdx, aMonitorsClient; "\\Monitors\\Client Side Port\\"
0x18001677b  lea     rcx, [rbp+90h+pExceptionObject]; Src
0x18001677f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016784  xorps   xmm0, xmm0
0x180016787  movups  [rbp+90h+Src], xmm0
0x18001678b  mov     qword ptr [rbp+90h+var_B8], r12
0x18001678f  mov     qword ptr [rbp+90h+var_B8+8], r12
0x180016793  movups  xmm0, xmmword ptr [rax]
0x180016796  movups  [rbp+90h+Src], xmm0
0x18001679a  movups  xmm1, xmmword ptr [rax+10h]
0x18001679e  movups  [rbp+90h+var_B8], xmm1
0x1800167a2  mov     [rax+10h], r12
0x1800167a6  mov     [rax+18h], r13
0x1800167aa  mov     [rax], r12w
0x1800167ae  lea     rdx, [rbp+90h+var_68]
0x1800167b2  lea     rcx, [rbp+90h+Src]; Src
0x1800167b6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800167bb  xorps   xmm0, xmm0
0x1800167be  movups  [rbp+90h+var_88], xmm0
0x1800167c2  mov     qword ptr [rbp+90h+var_78], r12
0x1800167c6  mov     qword ptr [rbp+90h+var_78+8], r12
0x1800167ca  movups  xmm0, xmmword ptr [rax]
0x1800167cd  movups  [rbp+90h+var_88], xmm0
0x1800167d1  movups  xmm1, xmmword ptr [rax+10h]
0x1800167d5  movups  [rbp+90h+var_78], xmm1
0x1800167d9  mov     [rax+10h], r12
0x1800167dd  mov     [rax+18h], r13
0x1800167e1  mov     [rax], r12w
0x1800167e5  lea     rcx, [rbp+90h+Src]
0x1800167e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800167ee  nop
0x1800167ef  lea     rcx, [rbp+90h+pExceptionObject]
0x1800167f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800167f8  mov     [rsp+190h+hKey], r12
0x1800167fd  lea     r9, [rsp+190h+hKey]
0x180016802  lea     rdx, [rbp+90h+var_88]
0x180016806  call    ?RegOpenKeyW@Registry@Win32Adapters@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::RegOpenKeyW(HKEY__ *,std::wstring const &,bool,RegistryHandleRAII &)
0x18001680b  xorps   xmm0, xmm0
0x18001680e  movups  [rbp+90h+var_48], xmm0
0x180016812  mov     [rbp+90h+var_38], r12
0x180016816  mov     [rbp+90h+var_30], r13
0x18001681a  mov     word ptr [rbp+90h+var_48], r12w
0x18001681f  movups  [rbp+90h+Src], xmm0
0x180016823  mov     qword ptr [rbp+90h+var_B8], r12
0x180016827  mov     qword ptr [rbp+90h+var_B8+8], r12
0x18001682b  lea     r8d, [r12+0Bh]
0x180016830  lea     rdx, aPrinterpath; "PrinterPath"
0x180016837  lea     rcx, [rbp+90h+Src]
0x18001683b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016840  nop
0x180016841  lea     r9, [rbp+90h+var_48]
0x180016845  mov     r8b, 1
0x180016848  lea     rdx, [rbp+90h+Src]
0x18001684c  lea     rcx, [rsp+190h+hKey]
0x180016851  call    ?RegQueryValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV45@@Z; Win32Adapters::Registry::RegQueryValueW(RegistryHandleRAII &,std::wstring const &,bool,std::wstring &)
0x180016856  nop
0x180016857  lea     rcx, [rbp+90h+Src]
0x18001685b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016860  lea     rdx, [rbp+90h+pData]
0x180016864  lea     rcx, [rbp+90h+var_48]
0x180016868  call    ?ParseCSRPortPrinterPath@PrinterConnectionUtil@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; PrinterConnectionUtil::ParseCSRPortPrinterPath(std::wstring const &,std::wstring &)
0x18001686d  nop
0x18001686e  lea     rcx, [rbp+90h+var_48]
0x180016872  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016877  nop
0x180016878  mov     rcx, [rsp+190h+hKey]; hKey
0x18001687d  test    rcx, rcx
0x180016880  jz      short loc_180016893
0x180016882  call    cs:__imp_RegCloseKey
0x180016889  nop     dword ptr [rax+rax+00h]
0x18001688e  mov     [rsp+190h+hKey], r12
0x180016893  lea     rcx, [rbp+90h+var_88]
0x180016897  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001689c  nop
0x18001689d  lea     rcx, [rbp+90h+var_68]
0x1800168a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800168a6  nop
0x1800168a7  lea     rcx, [rbp+90h+var_A8]
0x1800168ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800168b0  jmp     loc_1800169BF
0x1800168b5  mov     [rsp+190h+hKey], r12
0x1800168ba  mov     rcx, [r15]
0x1800168bd  mov     rax, [rcx]
0x1800168c0  mov     rax, [rax+28h]
0x1800168c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168c9  mov     rcx, rax; hPrinter
0x1800168cc  lea     rdx, [rsp+190h+hKey]; struct _PRINTER_INFO_1W **
0x1800168d1  call    ?PrivateGetPrinterInfo1@@YAJPEAXPEAPEAU_PRINTER_INFO_1W@@@Z; PrivateGetPrinterInfo1(void *,_PRINTER_INFO_1W * *)
0x1800168d6  mov     ebx, eax
0x1800168d8  test    eax, eax
0x1800168da  js      loc_180016BC0
0x1800168e0  mov     [rsp+190h+var_150], r12b
0x1800168e5  mov     rbx, [rsp+190h+hKey]
0x1800168ea  mov     [rsp+190h+hKey], rbx
0x1800168ef  lea     rax, [rsp+190h+var_150]
0x1800168f4  mov     [rsp+190h+var_138], rax
0x1800168f9  mov     [rsp+190h+var_130], 1
0x1800168fe  mov     ecx, 18h; Size
0x180016903  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016908  mov     rsi, rax
0x18001690b  mov     [rsp+190h+hKey], rax
0x180016910  xorps   xmm0, xmm0
0x180016913  movups  xmmword ptr [rax], xmm0
0x180016916  mov     dword ptr [rax+8], 1
0x18001691d  mov     dword ptr [rax+0Ch], 1
0x180016924  lea     rax, ??_7?$_Ref_count_resource@PEAU_PRINTER_INFO_1W@@V_lambda_f5a2a3fa1d5012707ef3805cb89c45a1_@@@std@@6B@; const std::_Ref_count_resource<_PRINTER_INFO_1W *,_lambda_f5a2a3fa1d5012707ef3805cb89c45a1_>::`vftable'
0x18001692b  mov     [rsi], rax
0x18001692e  mov     [rsi+10h], rbx
0x180016932  mov     [rsp+190h+hKey], rbx
0x180016937  mov     [rsp+190h+var_138], rsi
0x18001693c  mov     r9, [rbx+18h]
0x180016940  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180016944  inc     rdx
0x180016947  cmp     [r9+rdx*2], r12w
0x18001694c  jnz     short loc_180016944
0x18001694e  cmp     rdx, [rbp+90h+var_D0]
0x180016952  ja      short loc_18001697E
0x180016954  lea     rdi, [rbp+90h+pData]
0x180016958  cmp     [rbp+90h+var_D0], r13
0x18001695c  cmova   rdi, [rbp+90h+pData]
0x180016961  mov     [rbp+90h+var_D8], rdx
0x180016965  lea     rbx, [rdx+rdx]
0x180016969  mov     r8, rbx; Size
0x18001696c  mov     rdx, r9; Src
0x18001696f  mov     rcx, rdi; void *
0x180016972  call    memmove_0
0x180016977  mov     [rdi+rbx], r12w
0x18001697c  jmp     short loc_180016988
0x18001697e  lea     rcx, [rbp+90h+pData]
0x180016982  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180016987  nop
0x180016988  or      eax, 0FFFFFFFFh
0x18001698b  lock xadd [rsi+8], eax
0x180016990  cmp     eax, 1
0x180016993  jnz     short loc_1800169BF
0x180016995  mov     rax, [rsi]
0x180016998  mov     rcx, rsi
0x18001699b  mov     rax, [rax]
0x18001699e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169a3  or      eax, 0FFFFFFFFh
0x1800169a6  lock xadd [rsi+0Ch], eax
0x1800169ab  cmp     eax, 1
0x1800169ae  jnz     short loc_1800169BF
0x1800169b0  mov     rax, [rsi]
0x1800169b3  mov     rcx, rsi
0x1800169b6  mov     rax, [rax+8]
0x1800169ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169bf  xorps   xmm0, xmm0
0x1800169c2  movdqu  xmmword ptr [rsp+190h+pDefault.pDatatype], xmm0
0x1800169c8  mov     qword ptr [rsp+190h+pDefault.DesiredAccess], 0F000Ch
0x1800169d1  mov     rcx, [r15]
0x1800169d4  mov     rax, [rcx]
0x1800169d7  lea     rdx, [rbp+90h+var_68]
0x1800169db  mov     rax, [rax+20h]
0x1800169df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169e4  nop
0x1800169e5  cmp     [rax+18h], r13
0x1800169e9  jbe     short loc_1800169EE
0x1800169eb  mov     rax, [rax]
0x1800169ee  mov     [rsp+190h+phPrinter], r12
0x1800169f3  lea     r8, [rsp+190h+pDefault]; pDefault
0x1800169f8  lea     rdx, [rsp+190h+phPrinter]; phPrinter
0x1800169fd  mov     rcx, rax; pPrinterName
0x180016a00  call    cs:__imp_OpenPrinterW
0x180016a07  nop     dword ptr [rax+rax+00h]
0x180016a0c  mov     edi, 80070000h
0x180016a11  test    eax, eax
0x180016a13  jnz     short loc_180016A32
0x180016a15  call    cs:__imp_GetLastError
0x180016a1c  nop     dword ptr [rax+rax+00h]
0x180016a21  test    eax, eax
0x180016a23  jle     short loc_180016A2C
0x180016a25  movzx   eax, ax
0x180016a28  or      eax, edi
0x180016a2a  test    eax, eax
0x180016a2c  js      loc_180016C0D
0x180016a32  lea     rcx, [rbp+90h+var_68]
0x180016a36  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016a3b  mov     eax, dword ptr [rbp+90h+var_D8]
0x180016a3e  lea     eax, ds:2[rax*2]
0x180016a45  lea     r9, [rbp+90h+pData]
0x180016a49  cmp     [rbp+90h+var_D0], r13
0x180016a4d  cmova   r9, [rbp+90h+pData]; pData
0x180016a52  mov     [rsp+190h+cbData], eax; cbData
0x180016a56  mov     r8d, 1; Type
0x180016a5c  lea     rdx, pValueName; "V4_Connection_Name"
0x180016a63  mov     rcx, [rsp+190h+phPrinter]; hPrinter
0x180016a68  call    cs:__imp_SetPrinterDataW
0x180016a6f  nop     dword ptr [rax+rax+00h]
0x180016a74  mov     ebx, eax
0x180016a76  test    eax, eax
0x180016a78  jz      short loc_180016A89
0x180016a7a  jle     short loc_180016A81
0x180016a7c  movzx   ebx, ax
0x180016a7f  or      ebx, edi
0x180016a81  test    ebx, ebx
0x180016a83  js      loc_180016C29
0x180016a89  mov     rcx, [r15]
0x180016a8c  mov     rax, [rcx]
0x180016a8f  lea     rdx, [rbp+90h+var_88]
0x180016a93  mov     rax, [rax+20h]
0x180016a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a9c  nop
0x180016a9d  mov     eax, [rax+10h]
0x180016aa0  lea     ebx, ds:2[rax*2]
0x180016aa7  mov     rcx, [r15]
0x180016aaa  mov     rax, [rcx]
0x180016aad  lea     rdx, [rbp+90h+pExceptionObject]
0x180016ab1  mov     rax, [rax+20h]
0x180016ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aba  cmp     [rax+18h], r13
0x180016abe  jbe     short loc_180016AC3
0x180016ac0  mov     rax, [rax]
0x180016ac3  mov     [rsp+190h+cbData], ebx; cbData
0x180016ac7  mov     r9, rax; pData
0x180016aca  mov     r8d, 1; Type
0x180016ad0  lea     rdx, aV4GuidPrinterN; "V4_GUID_Printer_Name"
0x180016ad7  mov     rcx, [rsp+190h+phPrinter]; hPrinter
0x180016adc  call    cs:__imp_SetPrinterDataW
0x180016ae3  nop     dword ptr [rax+rax+00h]
0x180016ae8  mov     ebx, eax
0x180016aea  lea     rcx, [rbp+90h+pExceptionObject]
0x180016aee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016af3  nop
0x180016af4  lea     rcx, [rbp+90h+var_88]
0x180016af8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016afd  test    ebx, ebx
0x180016aff  jz      short loc_180016B10
0x180016b01  jle     short loc_180016B0A
0x180016b03  movzx   ebx, bx
0x180016b06  or      ebx, edi
0x180016b08  test    ebx, ebx
0x180016b0a  js      loc_180016C76
0x180016b10  mov     rcx, [rsp+190h+phPrinter]; hPrinter
0x180016b15  call    UpdateV4PrinterCacheChangeID
0x180016b1a  mov     ebx, eax
0x180016b1c  test    eax, eax
0x180016b1e  js      short loc_180016B6D
  ... truncated ...
```
