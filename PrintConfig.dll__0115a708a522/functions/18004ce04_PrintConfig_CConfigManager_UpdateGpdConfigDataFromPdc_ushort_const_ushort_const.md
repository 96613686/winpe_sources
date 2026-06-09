# PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc(ushort const *,ushort const *)

- ea: `0x18004ce04`
- end: `0x18004d3d6`
- name: `?UpdateGpdConfigDataFromPdc@CConfigManager@PrintConfig@@QEAAXPEBG0@Z`
- size: `1490`
- prototype: `void __fastcall(PrintConfig::CConfigManager *this, const unsigned __int16 *, OLECHAR *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800189a4`

## callees

- `0x180003400`
- `0x180003430`
- `0x180004558`
- `0x180004564`
- `0x18000bf2c`
- `0x18000de1c`
- `0x18000e750`
- `0x18000f830`
- `0x18000fa4c`
- `0x1800100a0`
- `0x180018f00`
- `0x180018f58`
- `0x180019388`
- `0x180019410`
- `0x18003c8e0`
- `0x18004ce04`
- `0x18006ece4`
- `0x180092b14`
- `0x180092d78`
- `0x180092dfc`
- `0x1800e03bc`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18004d037`
- `KERNEL32!DeleteFileW` at `0x18004d253`
- `KERNEL32!DeleteFileW` at `0x18004d037`
- `KERNEL32!DeleteFileW` at `0x18004d253`
- `KERNEL32!GetLastError` at `0x18004d047`
- `KERNEL32!GetLastError` at `0x18004d1e0`
- `KERNEL32!GetLastError` at `0x18004d202`
- `KERNEL32!GetLastError` at `0x18004d047`
- `KERNEL32!GetLastError` at `0x18004d1e0`
- `KERNEL32!GetLastError` at `0x18004d202`
- `KERNEL32!MoveFileExW` at `0x18004d1d0`
- `KERNEL32!MoveFileExW` at `0x18004d1d0`
- `ole32!CoInitializeEx` at `0x18004cf5c`
- `ole32!CoInitializeEx` at `0x18004cf5c`
- `ole32!CoUninitialize` at `0x18004d086`
- `ole32!CoUninitialize` at `0x18004d086`
- `WINSPOOL!GetPrinterDataW` at `0x18004d0e3`
- `WINSPOOL!GetPrinterDataW` at `0x18004d0e3`

## string_xrefs

- `0x18004d0d8`: `V4_Merged_ConfigFile_Name`
- `0x18004d1ef`: `MoveFile failed: error=%d`
- `0x18004ce93`: `PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc`
- `0x18004d06b`: `PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc`
- `0x18004d1f6`: `PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc`
- `0x18004d064`: `Could not delete converted GPD file: %ws (LastError: %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc(
        PrintConfig::CConfigManager *this,
        const unsigned __int16 *a2,
        OLECHAR *a3)
{
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r8
  const wchar_t *v8; // rax
  __int128 *v9; // r9
  int v10; // eax
  signed int v11; // eax
  unsigned __int64 v12; // r8
  struct ISequentialStream *v13; // rdi
  int v14; // eax
  int v15; // ebx
  HRESULT v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int128 *v19; // r9
  const unsigned __int16 *v20; // r8
  wchar_t *v21; // rdx
  void *v22; // r15
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  const WCHAR *v25; // rcx
  DWORD LastError; // eax
  LPCWSTR *v27; // r8
  signed int PrinterDataW; // eax
  bool v29; // sf
  __int64 v30; // rdx
  char *v31; // r8
  _QWORD *v32; // rax
  const WCHAR *v33; // rdx
  DWORD v34; // eax
  signed int v35; // eax
  bool v36; // sf
  LPCWSTR *v37; // rcx
  const WCHAR *v38; // rcx
  DWORD pType; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbNeeded; // [rsp+44h] [rbp-BCh] BYREF
  int v41; // [rsp+48h] [rbp-B8h]
  struct ISequentialStream *v42; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v46; // [rsp+98h] [rbp-68h]
  __int128 v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v48; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v49; // [rsp+C0h] [rbp-40h]
  LPCWSTR v50[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v51; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v52; // [rsp+E0h] [rbp-20h]
  LPCWSTR lpNewFileName[2]; // [rsp+E8h] [rbp-18h] BYREF
  __m128i si128; // [rsp+F8h] [rbp-8h]
  _WORD pData[20]; // [rsp+108h] [rbp+8h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+130h] [rbp+30h] BYREF

  Block[1] = (void *)-2LL;
  if ( !*((_BYTE *)this + 28) )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, -2147418113);
    throw (hr_error *)pExceptionObject;
  }
  memset_0(ExistingFileName, 0, 0x208u);
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  std::wstring::_Construct<1,unsigned short const *>(&v47, a2, v7);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc",
    L"Enter");
  v8 = L"merged.gpd";
  if ( !*((_DWORD *)this + 6) )
    v8 = L"merged.ppd";
  v9 = &v47;
  if ( v49 > 7 )
    v9 = (__int128 *)v47;
  v10 = StringCchPrintfW(ExistingFileName, 0x104u, L"%ws%ws", v9, v8);
  if ( v10 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v10);
    throw (hr_error *)pExceptionObject;
  }
  v42 = 0;
  Block[0] = 0;
  v11 = PrintConfig::CConfigFileStream::Create(ExistingFileName, &v42);
  if ( v11 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v11);
    throw (hr_error *)pExceptionObject;
  }
  *(_OWORD *)v50 = 0;
  v51 = 0;
  v52 = 0;
  v12 = -1;
  do
    ++v12;
  while ( ExistingFileName[v12] );
  std::wstring::_Construct<1,unsigned short const *>(v50, ExistingFileName, v12);
  v13 = v42;
  v14 = PrintConfig::CConfigFilePreproc::Create(
          v42,
          *((struct PrintConfigData **)this + 9),
          (struct PrintConfig::CConfigFilePreproc **)Block);
  if ( v14 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v14);
    throw (hr_error *)pExceptionObject;
  }
  v15 = 0;
  v41 = 0;
  v16 = CoInitializeEx(0, 0);
  if ( v16 >= 0 )
  {
    v15 = 1;
    v41 = 1;
  }
  else if ( v16 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v16);
    throw (hr_error *)pExceptionObject;
  }
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl'::`2'::impl) )
    PrintConfig::IppPdcProvider::ClearPdcCache();
  if ( 0x7FFFFFFFFFFFFFFELL - v48 < 0xF )
    std::_Xlen_string();
  v19 = &v47;
  if ( v49 > 7 )
    v19 = (__int128 *)v47;
  std::wstring::wstring((char *)lpFileName, v17, v18, v19, v48, L"device_bidi.gpd", 15);
  v21 = (wchar_t *)lpFileName;
  if ( *((_QWORD *)&v46 + 1) > 7u )
    v21 = (wchar_t *)lpFileName[0];
  PrintDeviceCapabilitiesOM::ConvertToGPD(a3, v21, v20);
  v22 = Block[0];
  v23 = (const unsigned __int16 *)lpFileName;
  if ( *((_QWORD *)&v46 + 1) > 7u )
    v23 = lpFileName[0];
  v24 = PrintConfig::CConfigFilePreproc::PreProcessFile(
          (PrintConfig::CConfigFilePreproc *)Block[0],
          v23,
          (*(_BYTE *)(*((_QWORD *)this + 9) + 120LL) & 0x18) != 0);
  if ( v24 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v24);
    throw (hr_error *)pExceptionObject;
  }
  v25 = (const WCHAR *)lpFileName;
  if ( *((_QWORD *)&v46 + 1) > 7u )
    v25 = lpFileName[0];
  if ( !DeleteFileW(v25) )
  {
    LastError = GetLastError();
    v27 = lpFileName;
    if ( *((_QWORD *)&v46 + 1) > 7u )
      v27 = (LPCWSTR *)lpFileName[0];
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc",
      L"Could not delete converted GPD file: %ws (LastError: %d)",
      v27,
      LastError);
  }
  std::wstring::~wstring((char **)lpFileName);
  if ( v15 )
    CoUninitialize();
  memset(pData, 0, 26);
  *(_OWORD *)lpNewFileName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpNewFileName[0]) = 0;
  pType = 0;
  pcbNeeded = 0;
  PrinterDataW = GetPrinterDataW(
                   *((HANDLE *)this + 8),
                   (LPWSTR)L"V4_Merged_ConfigFile_Name",
                   &pType,
                   (LPBYTE)pData,
                   0x1Au,
                   &pcbNeeded);
  v29 = PrinterDataW < 0;
  if ( PrinterDataW > 0 )
  {
    PrinterDataW = (unsigned __int16)PrinterDataW | 0x80070000;
    v29 = PrinterDataW < 0;
  }
  if ( v29 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, PrinterDataW);
    throw (hr_error *)pExceptionObject;
  }
  if ( pType != 1 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, -2147418113);
    throw (hr_error *)pExceptionObject;
  }
  *(_OWORD *)lpFileName = 0;
  v46 = 0;
  do
    ++v6;
  while ( pData[v6] );
  std::wstring::_Construct<1,unsigned short const *>(lpFileName, pData, v6);
  v31 = (char *)&v47;
  if ( v49 > 7 )
    v31 = (char *)v47;
  v32 = std::wstring::_Insert<unsigned short>(lpFileName, v30, v31, v48);
  pExceptionObject[0] = *(_OWORD *)v32;
  pExceptionObject[1] = *((_OWORD *)v32 + 1);
  v32[2] = 0;
  v32[3] = 7;
  *(_WORD *)v32 = 0;
  std::wstring::operator=((char **)lpNewFileName, (__int64)pExceptionObject);
  std::wstring::~wstring((char **)pExceptionObject);
  std::wstring::~wstring((char **)lpFileName);
  if ( v13 )
  {
    ((void (__fastcall *)(struct ISequentialStream *))v13->lpVtbl->Release)(v13);
    v42 = 0;
  }
  v33 = (const WCHAR *)lpNewFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v33 = lpNewFileName[0];
  if ( !MoveFileExW(ExistingFileName, v33, 1u) )
  {
    v34 = GetLastError();
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc",
      L"MoveFile failed: error=%d",
      v34);
    v35 = GetLastError();
    v36 = v35 < 0;
    if ( v35 > 0 )
    {
      v35 = (unsigned __int16)v35 | 0x80070000;
      v36 = v35 < 0;
    }
    if ( v36 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v35);
      throw (hr_error *)pExceptionObject;
    }
  }
  v51 = 0;
  v37 = v50;
  if ( v52 > 7 )
    v37 = (LPCWSTR *)v50[0];
  *(_WORD *)v37 = 0;
  std::wstring::~wstring((char **)lpNewFileName);
  if ( v51 )
  {
    v38 = (const WCHAR *)v50;
    if ( v52 > 7 )
      v38 = v50[0];
    DeleteFileW(v38);
  }
  std::wstring::~wstring((char **)v50);
  if ( v22 )
    operator delete(v22);
  std::wstring::~wstring((char **)&v47);
}

```

## disassembly

```asm
0x18004ce04  push    rbp
0x18004ce06  push    rbx
0x18004ce07  push    rsi
0x18004ce08  push    rdi
0x18004ce09  push    r12
0x18004ce0b  push    r14
0x18004ce0d  push    r15
0x18004ce0f  lea     rbp, [rsp-250h]
0x18004ce17  sub     rsp, 350h
0x18004ce1e  mov     [rsp+380h+var_320], 0FFFFFFFFFFFFFFFEh
0x18004ce27  mov     rax, cs:__security_cookie
0x18004ce2e  xor     rax, rsp
0x18004ce31  mov     [rbp+280h+var_40], rax
0x18004ce38  mov     r15, r8
0x18004ce3b  mov     rbx, rdx
0x18004ce3e  mov     r14, rcx
0x18004ce41  xor     r12d, r12d
0x18004ce44  cmp     [rcx+1Ch], r12b
0x18004ce48  jz      loc_18004D319
0x18004ce4e  xor     edx, edx; Val
0x18004ce50  mov     r8d, 208h; Size
0x18004ce56  lea     rcx, [rbp+280h+ExistingFileName]; void *
0x18004ce5a  call    memset_0
0x18004ce5f  xorps   xmm0, xmm0
0x18004ce62  movups  [rbp+280h+var_2D8], xmm0
0x18004ce66  mov     [rbp+280h+var_2C8], r12
0x18004ce6a  mov     [rbp+280h+var_2C0], r12
0x18004ce6e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004ce72  mov     r8, rsi
0x18004ce75  inc     r8
0x18004ce78  cmp     [rbx+r8*2], r12w
0x18004ce7d  jnz     short loc_18004CE75
0x18004ce7f  mov     rdx, rbx
0x18004ce82  lea     rcx, [rbp+280h+var_2D8]
0x18004ce86  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004ce8b  nop
0x18004ce8c  lea     rdx, aEnter_0; "Enter"
0x18004ce93  lea     rcx, aPrintconfigCco_15; "PrintConfig::CConfigManager::UpdateGpdC"...
0x18004ce9a  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004ce9f  lea     rcx, aMergedPpd; "merged.ppd"
0x18004cea6  lea     rax, aMergedGpd; "merged.gpd"
0x18004cead  cmp     [r14+18h], r12d
0x18004ceb1  cmovz   rax, rcx
0x18004ceb5  lea     r9, [rbp+280h+var_2D8]
0x18004ceb9  cmp     [rbp+280h+var_2C0], 7
0x18004cebe  cmova   r9, qword ptr [rbp+280h+var_2D8]
0x18004cec3  mov     qword ptr [rsp+380h+nSize], rax
0x18004cec8  lea     r8, aWsWs; "%ws%ws"
0x18004cecf  mov     edx, 104h; unsigned __int64
0x18004ced4  lea     rcx, [rbp+280h+ExistingFileName]; unsigned __int16 *
0x18004ced8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004cedd  test    eax, eax
0x18004cedf  js      loc_18004D33A
0x18004cee5  mov     [rsp+380h+var_330], r12
0x18004ceea  mov     [rsp+380h+Block], r12
0x18004ceef  lea     rdx, [rsp+380h+var_330]; struct ISequentialStream **
0x18004cef4  lea     rcx, [rbp+280h+ExistingFileName]; lpFileName
0x18004cef8  call    ?Create@CConfigFileStream@PrintConfig@@SAJPEBGPEAPEAUISequentialStream@@@Z; PrintConfig::CConfigFileStream::Create(ushort const *,ISequentialStream * *)
0x18004cefd  test    eax, eax
0x18004ceff  js      loc_18004D358
0x18004cf05  xorps   xmm0, xmm0
0x18004cf08  movups  xmmword ptr [rbp+280h+var_2B8], xmm0
0x18004cf0c  mov     [rbp+280h+var_2A8], r12
0x18004cf10  mov     [rbp+280h+var_2A0], r12
0x18004cf14  lea     rax, [rbp+280h+ExistingFileName]
0x18004cf18  mov     r8, rsi
0x18004cf1b  inc     r8
0x18004cf1e  cmp     [rax+r8*2], r12w
0x18004cf23  jnz     short loc_18004CF1B
0x18004cf25  lea     rdx, [rbp+280h+ExistingFileName]
0x18004cf29  lea     rcx, [rbp+280h+var_2B8]
0x18004cf2d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004cf32  nop
0x18004cf33  mov     rdi, [rsp+380h+var_330]
0x18004cf38  lea     r8, [rsp+380h+Block]; struct PrintConfig::CConfigFilePreproc **
0x18004cf3d  mov     rdx, [r14+48h]; struct PrintConfigData *
0x18004cf41  mov     rcx, rdi; struct ISequentialStream *
0x18004cf44  call    ?Create@CConfigFilePreproc@PrintConfig@@SAJPEAUISequentialStream@@PEAVPrintConfigData@@PEAPEAV12@@Z; PrintConfig::CConfigFilePreproc::Create(ISequentialStream *,PrintConfigData *,PrintConfig::CConfigFilePreproc * *)
0x18004cf49  test    eax, eax
0x18004cf4b  js      loc_18004D376
0x18004cf51  mov     ebx, r12d
0x18004cf54  mov     [rsp+380h+var_338], ebx
0x18004cf58  xor     edx, edx; dwCoInit
0x18004cf5a  xor     ecx, ecx; pvReserved
0x18004cf5c  call    cs:__imp_CoInitializeEx
0x18004cf63  nop     dword ptr [rax+rax+00h]
0x18004cf68  test    eax, eax
0x18004cf6a  jns     short loc_18004CF79
0x18004cf6c  cmp     eax, 80010106h
0x18004cf71  jnz     loc_18004D2DA
0x18004cf77  jmp     short loc_18004CF82
0x18004cf79  mov     ebx, 1
0x18004cf7e  mov     [rsp+380h+var_338], ebx
0x18004cf82  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505> `wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl(void)'::`2'::impl
0x18004cf89  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled(void)
0x18004cf8e  test    al, al
0x18004cf90  jnz     short loc_18004CF97
0x18004cf92  call    ?ClearPdcCache@IppPdcProvider@PrintConfig@@SAXXZ; PrintConfig::IppPdcProvider::ClearPdcCache(void)
0x18004cf97  mov     rcx, [rbp+280h+var_2C8]
0x18004cf9b  mov     rax, 7FFFFFFFFFFFFFFEh
0x18004cfa5  sub     rax, rcx
0x18004cfa8  cmp     rax, 0Fh
0x18004cfac  jb      loc_18004D394
0x18004cfb2  lea     r9, [rbp+280h+var_2D8]
0x18004cfb6  cmp     [rbp+280h+var_2C0], 7
0x18004cfbb  cmova   r9, qword ptr [rbp+280h+var_2D8]
0x18004cfc0  mov     [rsp+380h+var_350], 0Fh
0x18004cfc9  lea     rax, aDeviceBidiGpd; "device_bidi.gpd"
0x18004cfd0  mov     [rsp+380h+pcbNeeded], rax
0x18004cfd5  mov     qword ptr [rsp+380h+nSize], rcx
0x18004cfda  lea     rcx, [rbp+280h+lpFileName]
0x18004cfde  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004cfe3  nop
0x18004cfe4  lea     rdx, [rbp+280h+lpFileName]
0x18004cfe8  cmp     [rbp+280h+var_2E0], 7
0x18004cfed  cmova   rdx, [rbp+280h+lpFileName]; unsigned __int16 *
0x18004cff2  mov     rcx, r15; psz
0x18004cff5  call    ?ConvertToGPD@PrintDeviceCapabilitiesOM@@YAXPEBG0@Z; PrintDeviceCapabilitiesOM::ConvertToGPD(ushort const *,ushort const *)
0x18004cffa  mov     r15, [rsp+380h+Block]
0x18004cfff  mov     rax, [r14+48h]
0x18004d003  test    byte ptr [rax+78h], 18h
0x18004d007  setnz   r8b; bool
0x18004d00b  lea     rdx, [rbp+280h+lpFileName]
0x18004d00f  cmp     [rbp+280h+var_2E0], 7
0x18004d014  cmova   rdx, [rbp+280h+lpFileName]; unsigned __int16 *
0x18004d019  mov     rcx, r15; this
0x18004d01c  call    ?PreProcessFile@CConfigFilePreproc@PrintConfig@@QEAAJPEBG_N@Z; PrintConfig::CConfigFilePreproc::PreProcessFile(ushort const *,bool)
0x18004d021  test    eax, eax
0x18004d023  js      loc_18004D39A
0x18004d029  lea     rcx, [rbp+280h+lpFileName]
0x18004d02d  cmp     [rbp+280h+var_2E0], 7
0x18004d032  cmova   rcx, [rbp+280h+lpFileName]; lpFileName
0x18004d037  call    cs:__imp_DeleteFileW
0x18004d03e  nop     dword ptr [rax+rax+00h]
0x18004d043  test    eax, eax
0x18004d045  jnz     short loc_18004D078
0x18004d047  call    cs:__imp_GetLastError
0x18004d04e  nop     dword ptr [rax+rax+00h]
0x18004d053  lea     r8, [rbp+280h+lpFileName]
0x18004d057  cmp     [rbp+280h+var_2E0], 7
0x18004d05c  cmova   r8, [rbp+280h+lpFileName]
0x18004d061  mov     r9d, eax
0x18004d064  lea     rdx, aCouldNotDelete; "Could not delete converted GPD file: %w"...
0x18004d06b  lea     rcx, aPrintconfigCco_15; "PrintConfig::CConfigManager::UpdateGpdC"...
0x18004d072  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004d077  nop
0x18004d078  lea     rcx, [rbp+280h+lpFileName]
0x18004d07c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d081  nop
0x18004d082  test    ebx, ebx
0x18004d084  jz      short loc_18004D092
0x18004d086  call    cs:__imp_CoUninitialize
0x18004d08d  nop     dword ptr [rax+rax+00h]
0x18004d092  xorps   xmm0, xmm0
0x18004d095  movups  xmmword ptr [rbp+280h+pData], xmm0
0x18004d099  movups  xmmword ptr [rbp+280h+pData+0Ah], xmm0
0x18004d09d  movups  xmmword ptr [rbp+280h+lpNewFileName], xmm0
0x18004d0a1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004d0a9  movdqu  [rbp+280h+var_288], xmm1
0x18004d0ae  mov     word ptr [rbp+280h+lpNewFileName], r12w
0x18004d0b3  mov     [rsp+380h+pType], r12d
0x18004d0b8  mov     [rsp+380h+var_33C], r12d
0x18004d0bd  lea     rax, [rsp+380h+var_33C]
0x18004d0c2  mov     [rsp+380h+pcbNeeded], rax; pcbNeeded
0x18004d0c7  mov     [rsp+380h+nSize], 1Ah; nSize
0x18004d0cf  lea     r9, [rbp+280h+pData]; pData
0x18004d0d3  lea     r8, [rsp+380h+pType]; pType
0x18004d0d8  lea     rdx, aV4MergedConfig_0; "V4_Merged_ConfigFile_Name"
0x18004d0df  mov     rcx, [r14+40h]; hPrinter
0x18004d0e3  call    cs:__imp_GetPrinterDataW
0x18004d0ea  nop     dword ptr [rax+rax+00h]
0x18004d0ef  mov     ebx, 80070000h
0x18004d0f4  test    eax, eax
0x18004d0f6  jle     short loc_18004D0FF
0x18004d0f8  movzx   eax, ax
0x18004d0fb  or      eax, ebx
0x18004d0fd  test    eax, eax
0x18004d0ff  js      loc_18004D3B8
0x18004d105  cmp     [rsp+380h+pType], 1
0x18004d10a  jnz     loc_18004D2F8
0x18004d110  xorps   xmm0, xmm0
0x18004d113  movups  xmmword ptr [rbp+280h+lpFileName], xmm0
0x18004d117  xorps   xmm1, xmm1
0x18004d11a  movdqu  xmmword ptr [rbp-68h], xmm1
0x18004d11f  lea     rax, [rbp+280h+pData]
0x18004d123  inc     rsi
0x18004d126  cmp     [rax+rsi*2], r12w
0x18004d12b  jnz     short loc_18004D123
0x18004d12d  mov     r8, rsi
0x18004d130  lea     rdx, [rbp+280h+pData]
0x18004d134  lea     rcx, [rbp+280h+lpFileName]
0x18004d138  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004d13d  nop
0x18004d13e  lea     r8, [rbp+280h+var_2D8]
0x18004d142  cmp     [rbp+280h+var_2C0], 7
0x18004d147  cmova   r8, qword ptr [rbp+280h+var_2D8]
0x18004d14c  mov     r9, [rbp+280h+var_2C8]
0x18004d150  lea     rcx, [rbp+280h+lpFileName]; Src
0x18004d154  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18004d159  movups  xmm0, xmmword ptr [rax]
0x18004d15c  movups  [rsp+380h+pExceptionObject], xmm0
0x18004d161  movups  xmm1, xmmword ptr [rax+10h]
0x18004d165  movups  [rsp+380h+var_308], xmm1
0x18004d16a  mov     [rax+10h], r12
0x18004d16e  mov     qword ptr [rax+18h], 7
0x18004d176  mov     [rax], r12w
0x18004d17a  lea     rdx, [rsp+380h+pExceptionObject]
0x18004d17f  lea     rcx, [rbp+280h+lpNewFileName]
0x18004d183  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004d188  lea     rcx, [rsp+380h+pExceptionObject]
0x18004d18d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d192  nop
0x18004d193  lea     rcx, [rbp+280h+lpFileName]
0x18004d197  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d19c  test    rdi, rdi
0x18004d19f  jz      short loc_18004D1B8
0x18004d1a1  mov     rax, [rdi]
0x18004d1a4  mov     rcx, rdi
0x18004d1a7  mov     rax, [rax+10h]
0x18004d1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1b0  mov     rdi, r12
0x18004d1b3  mov     [rsp+380h+var_330], r12
0x18004d1b8  lea     rdx, [rbp+280h+lpNewFileName]
0x18004d1bc  cmp     qword ptr [rbp+280h+var_288+8], 7
0x18004d1c1  cmova   rdx, [rbp+280h+lpNewFileName]; lpNewFileName
0x18004d1c6  mov     r8d, 1; dwFlags
0x18004d1cc  lea     rcx, [rbp+280h+ExistingFileName]; lpExistingFileName
0x18004d1d0  call    cs:__imp_MoveFileExW
0x18004d1d7  nop     dword ptr [rax+rax+00h]
0x18004d1dc  test    eax, eax
0x18004d1de  jnz     short loc_18004D21F
0x18004d1e0  call    cs:__imp_GetLastError
0x18004d1e7  nop     dword ptr [rax+rax+00h]
0x18004d1ec  mov     r8d, eax
0x18004d1ef  lea     rdx, aMovefileFailed; "MoveFile failed: error=%d"
0x18004d1f6  lea     rcx, aPrintconfigCco_15; "PrintConfig::CConfigManager::UpdateGpdC"...
0x18004d1fd  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004d202  call    cs:__imp_GetLastError
0x18004d209  nop     dword ptr [rax+rax+00h]
0x18004d20e  test    eax, eax
0x18004d210  jle     short loc_18004D219
0x18004d212  movzx   eax, ax
0x18004d215  or      eax, ebx
0x18004d217  test    eax, eax
0x18004d219  js      loc_18004D2BC
0x18004d21f  mov     [rbp+280h+var_2A8], r12
0x18004d223  lea     rcx, [rbp+280h+var_2B8]
0x18004d227  cmp     [rbp+280h+var_2A0], 7
0x18004d22c  cmova   rcx, [rbp+280h+var_2B8]
0x18004d231  mov     [rcx], r12w
0x18004d235  lea     rcx, [rbp+280h+lpNewFileName]
0x18004d239  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d23e  nop
0x18004d23f  cmp     [rbp+280h+var_2A8], r12
0x18004d243  jz      short loc_18004D25F
0x18004d245  lea     rcx, [rbp+280h+var_2B8]
0x18004d249  cmp     [rbp+280h+var_2A0], 7
0x18004d24e  cmova   rcx, [rbp+280h+var_2B8]; lpFileName
0x18004d253  call    cs:__imp_DeleteFileW
0x18004d25a  nop     dword ptr [rax+rax+00h]
0x18004d25f  lea     rcx, [rbp+280h+var_2B8]
0x18004d263  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d268  nop
0x18004d269  test    r15, r15
0x18004d26c  jz      short loc_18004D27C
0x18004d26e  mov     edx, 18h
0x18004d273  mov     rcx, r15; Block
0x18004d276  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004d27b  nop
0x18004d27c  test    rdi, rdi
0x18004d27f  jz      short loc_18004D291
0x18004d281  mov     rax, [rdi]
0x18004d284  mov     rcx, rdi
0x18004d287  mov     rax, [rax+10h]
0x18004d28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d290  nop
0x18004d291  lea     rcx, [rbp+280h+var_2D8]
0x18004d295  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d29a  mov     rcx, [rbp+280h+var_40]
0x18004d2a1  xor     rcx, rsp; StackCookie
0x18004d2a4  call    __security_check_cookie
0x18004d2a9  add     rsp, 350h
0x18004d2b0  pop     r15
0x18004d2b2  pop     r14
0x18004d2b4  pop     r12
0x18004d2b6  pop     rdi
0x18004d2b7  pop     rsi
0x18004d2b8  pop     rbx
0x18004d2b9  pop     rbp
0x18004d2ba  retn
0x18004d2bc  mov     edx, eax; int
0x18004d2be  lea     rcx, [rsp+380h+pExceptionObject]; this
0x18004d2c3  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004d2c8  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004d2cf  lea     rcx, [rsp+380h+pExceptionObject]; pExceptionObject
0x18004d2d4  call    _CxxThrowException_0
0x18004d2da  mov     edx, eax; int
0x18004d2dc  lea     rcx, [rsp+380h+pExceptionObject]; this
0x18004d2e1  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004d2e6  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
  ... truncated ...
```
