# PrintConfig::CConfigManager::UpdateMergedConfigData(void)

- ea: `0x18004d3dc`
- end: `0x18004dccf`
- name: `?UpdateMergedConfigData@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `2291`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001bb3c`
- `0x18001c364`

## callees

- `0x180003400`
- `0x180003430`
- `0x180004558`
- `0x180004564`
- `0x18000be68`
- `0x18000de1c`
- `0x18000e750`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x180019388`
- `0x180019410`
- `0x18004b544`
- `0x18004d3dc`
- `0x18006ece4`
- `0x180092b14`
- `0x180092d78`
- `0x180092dfc`
- `0x1800e03bc`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18004d71d`
- `KERNEL32!CopyFileW` at `0x18004d71d`
- `KERNEL32!DeleteFileW` at `0x18004d835`
- `KERNEL32!DeleteFileW` at `0x18004daa5`
- `KERNEL32!DeleteFileW` at `0x18004d835`
- `KERNEL32!DeleteFileW` at `0x18004daa5`
- `KERNEL32!GetLastError` at `0x18004d845`
- `KERNEL32!GetLastError` at `0x18004dc33`
- `KERNEL32!GetLastError` at `0x18004d845`
- `KERNEL32!GetLastError` at `0x18004dc33`
- `KERNEL32!GetFileAttributesW` at `0x18004d601`
- `KERNEL32!GetFileAttributesW` at `0x18004d96d`
- `KERNEL32!GetFileAttributesW` at `0x18004d601`
- `KERNEL32!GetFileAttributesW` at `0x18004d96d`
- `ole32!CoInitializeEx` at `0x18004d572`
- `ole32!CoInitializeEx` at `0x18004d572`
- `ole32!CoUninitialize` at `0x18004d8a6`
- `ole32!CoUninitialize` at `0x18004d8a6`
- `WINSPOOL!DeletePrinterDataW` at `0x18004d551`
- `WINSPOOL!DeletePrinterDataW` at `0x18004d551`
- `WINSPOOL!SetPrinterDataW` at `0x18004d773`
- `WINSPOOL!SetPrinterDataW` at `0x18004d773`
- `WINSPOOL!GetPrinterDataW` at `0x18004da32`
- `WINSPOOL!GetPrinterDataW` at `0x18004da32`

## string_xrefs

- `0x18004d5ce`: `device_bidi_pdc.xml`
- `0x18004da27`: `V4_Merged_ConfigFile_CRC`
- `0x18004d42f`: `PrintConfig::CConfigManager::UpdateMergedConfigData`
- `0x18004d62b`: `PrintConfig::CConfigManager::UpdateMergedConfigData`
- `0x18004d869`: `PrintConfig::CConfigManager::UpdateMergedConfigData`
- `0x18004db4d`: `PrintConfig::CConfigManager::UpdateMergedConfigData`
- `0x18004d65c`: `pdc.xml`
- `0x18004d862`: `Could not delete converted GPD file: %ws (LastError: %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall PrintConfig::CConfigManager::UpdateMergedConfigData(PrintConfig::CConfigManager *this)
{
  WCHAR *v2; // rdi
  WCHAR *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rdx
  WCHAR *v6; // r9
  WCHAR v7; // r8
  WCHAR *v8; // rcx
  unsigned __int16 *v9; // r8
  int v10; // eax
  signed int v11; // eax
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r8
  struct ISequentialStream *v14; // r14
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // ebx
  HRESULT v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rcx
  WCHAR *v23; // r9
  __int64 v24; // r8
  const WCHAR *v25; // rcx
  LPCWSTR *v26; // r8
  const WCHAR *v27; // r12
  __int64 v28; // r8
  __int64 v29; // rcx
  WCHAR *v30; // r9
  __int64 v31; // r9
  LPBYTE *v32; // rax
  const WCHAR *v33; // rdx
  BYTE *v34; // r9
  signed int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  bool v38; // sf
  __int64 v39; // rcx
  const unsigned __int16 *v40; // r8
  wchar_t *v41; // rdx
  OLECHAR *v42; // rcx
  PrintConfig::CConfigFilePreproc *v43; // r13
  const unsigned __int16 *v44; // rdx
  int v45; // eax
  const WCHAR *v46; // rcx
  DWORD v47; // eax
  LPCWSTR *v48; // r8
  char v49; // r12
  bool v50; // r15
  const unsigned __int16 *v51; // rax
  __int64 v52; // r8
  int v53; // eax
  wchar_t *v54; // rax
  __int64 v55; // rcx
  const WCHAR *v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  const unsigned __int16 *v59; // rdx
  int v60; // eax
  bool v61; // bl
  const unsigned __int16 *v62; // rax
  int v63; // eax
  int v64; // ebx
  DWORD PrinterDataW; // eax
  LPCWSTR *v66; // rcx
  const WCHAR *v67; // rcx
  signed int LastError; // eax
  BYTE v69[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pType; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE pExceptionObject[32]; // [rsp+48h] [rbp-B8h] BYREF
  int v72; // [rsp+68h] [rbp-98h]
  DWORD pcbNeeded; // [rsp+6Ch] [rbp-94h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  struct ISequentialStream *v75[2]; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpNewFileName[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v77; // [rsp+A0h] [rbp-60h]
  LPCWSTR v78[3]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v79; // [rsp+C0h] [rbp-40h]
  LPCWSTR v80[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v82; // [rsp+E0h] [rbp-20h]
  LPBYTE pData[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v84; // [rsp+F8h] [rbp-8h]
  LPCWSTR lpFileName[3]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 v86; // [rsp+120h] [rbp+20h]
  WCHAR FileName[264]; // [rsp+130h] [rbp+30h] BYREF

  v75[1] = (struct ISequentialStream *)-2LL;
  memset_0(FileName, 0, 0x208u);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::UpdateMergedConfigData",
    L"Enter");
  v2 = (WCHAR *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) <= 7u )
    v3 = (WCHAR *)((char *)this + 32);
  else
    v3 = *(WCHAR **)v2;
  v4 = 2147483646;
  v5 = 260;
  v6 = FileName;
  do
  {
    if ( !v4 )
      break;
    v7 = *v3;
    if ( !*v3 )
      break;
    ++v3;
    *v6++ = v7;
    --v4;
    --v5;
  }
  while ( v5 );
  v8 = v6 - 1;
  if ( v5 )
    v8 = v6;
  *v8 = 0;
  if ( !v5 )
  {
    hr_error::hr_error((hr_error *)lpNewFileName, -2147024774);
    throw (hr_error *)lpNewFileName;
  }
  v9 = L"merged.gpd";
  if ( !*((_DWORD *)this + 6) )
    v9 = L"merged.ppd";
  v10 = StringCchCatW(FileName, 260, v9);
  if ( v10 < 0 )
  {
    hr_error::hr_error((hr_error *)lpNewFileName, v10);
    throw (hr_error *)lpNewFileName;
  }
  v75[0] = 0;
  Block = 0;
  v11 = PrintConfig::CConfigFileStream::Create(FileName, v75);
  if ( v11 < 0 )
  {
    hr_error::hr_error((hr_error *)lpNewFileName, v11);
    throw (hr_error *)lpNewFileName;
  }
  *(_OWORD *)v80 = 0;
  v81 = 0;
  v82 = 0;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( FileName[v13] );
  std::wstring::_Construct<1,unsigned short const *>(v80, FileName, v13);
  v14 = v75[0];
  v15 = PrintConfig::CConfigFilePreproc::Create(
          v75[0],
          *((struct PrintConfigData **)this + 9),
          (struct PrintConfig::CConfigFilePreproc **)&Block);
  if ( v15 < 0 )
  {
    hr_error::hr_error((hr_error *)lpNewFileName, v15);
    throw (hr_error *)lpNewFileName;
  }
  DeletePrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_PrintDeviceCapabilities");
  if ( *((_BYTE *)this + 28) )
  {
    v18 = 0;
    v72 = 0;
    v19 = CoInitializeEx(0, 0);
    if ( v19 >= 0 )
    {
      v18 = 1;
      v72 = 1;
    }
    else if ( v19 != -2147417850 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v19);
      throw (hr_error *)pExceptionObject;
    }
    v22 = *((_QWORD *)this + 6);
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v22) < 0x13 )
      std::_Xlen_string();
    if ( *((_QWORD *)this + 7) <= 7u )
      v23 = (WCHAR *)((char *)this + 32);
    else
      v23 = *(WCHAR **)v2;
    std::wstring::wstring((char *)lpFileName, v20, v21, v23, v22, L"device_bidi_pdc.xml", 19);
    if ( *((_BYTE *)this + 29) )
    {
      v25 = (const WCHAR *)lpFileName;
      if ( v86 > 7 )
        v25 = lpFileName[0];
      if ( GetFileAttributesW(v25) != -1 )
      {
        v26 = lpFileName;
        if ( v86 > 7 )
          v26 = (LPCWSTR *)lpFileName[0];
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "PrintConfig::CConfigManager::UpdateMergedConfigData",
          L"Using a device-based PrintDeviceCapabilities file: %ws",
          v26);
        if ( v86 <= 7 )
        {
          v27 = (const WCHAR *)lpFileName;
          goto LABEL_35;
        }
        v27 = lpFileName[0];
        if ( lpFileName[0] )
        {
LABEL_35:
          *(_OWORD *)pData = 0;
          v84 = 0;
          std::wstring::_Construct<1,unsigned short const *>(pData, L"pdc.xml", 7u);
          v29 = *((_QWORD *)this + 6);
          if ( 0x7FFFFFFFFFFFFFFELL - v29 < (unsigned __int64)v84 )
            std::_Xlen_string();
          if ( *((_QWORD *)this + 7) <= 7u )
            v30 = (WCHAR *)((char *)this + 32);
          else
            v30 = *(WCHAR **)v2;
          v32 = pData;
          if ( *((_QWORD *)&v84 + 1) > 7u )
            v32 = (LPBYTE *)pData[0];
          std::wstring::wstring((char *)lpNewFileName, v84, v28, v30, v29, v32, v84);
          v33 = (const WCHAR *)lpNewFileName;
          if ( v77 > 7 )
            v33 = lpNewFileName[0];
          if ( !CopyFileW(v27, v33, 0) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            hr_error::hr_error((hr_error *)pExceptionObject, LastError);
            throw (hr_error *)pExceptionObject;
          }
          if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl'::`2'::impl) )
            PrintConfig::IppPdcProvider::ClearPdcCache();
          v34 = (BYTE *)pData;
          if ( *((_QWORD *)&v84 + 1) > 7u )
            v34 = pData[0];
          v35 = SetPrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_PrintDeviceCapabilities", 1u, v34, 2 * v84 + 2);
          v38 = v35 < 0;
          if ( v35 > 0 )
          {
            v35 = (unsigned __int16)v35 | 0x80070000;
            v38 = v35 < 0;
          }
          if ( v38 )
          {
            hr_error::hr_error((hr_error *)pExceptionObject, v35);
            throw (hr_error *)pExceptionObject;
          }
          v39 = *((_QWORD *)this + 6);
          if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v39) < 0xF )
            std::_Xlen_string();
          if ( *((_QWORD *)this + 7) > 7u )
            v2 = *(WCHAR **)v2;
          std::wstring::wstring((char *)v78, v36, v37, v2, v39, L"device_bidi.gpd", 15);
          v41 = (wchar_t *)v78;
          if ( v79 > 7 )
            v41 = (wchar_t *)v78[0];
          v42 = (OLECHAR *)lpNewFileName;
          if ( v77 > 7 )
            v42 = (OLECHAR *)lpNewFileName[0];
          PrintDeviceCapabilitiesOM::ConvertToGPD(v42, v41, v40);
          v43 = (PrintConfig::CConfigFilePreproc *)Block;
          v44 = (const unsigned __int16 *)v78;
          if ( v79 > 7 )
            v44 = v78[0];
          v45 = PrintConfig::CConfigFilePreproc::PreProcessFile(
                  (PrintConfig::CConfigFilePreproc *)Block,
                  v44,
                  (*(_BYTE *)(*((_QWORD *)this + 9) + 120LL) & 0x18) != 0);
          if ( v45 < 0 )
          {
            hr_error::hr_error((hr_error *)pExceptionObject, v45);
            throw (hr_error *)pExceptionObject;
          }
          v46 = (const WCHAR *)v78;
          if ( v79 > 7 )
            v46 = v78[0];
          if ( !DeleteFileW(v46) )
          {
            v47 = GetLastError();
            v48 = v78;
            if ( v79 > 7 )
              v48 = (LPCWSTR *)v78[0];
            Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
              "PrintConfig::CConfigManager::UpdateMergedConfigData",
              L"Could not delete converted GPD file: %ws (LastError: %d)",
              v48,
              v47);
          }
          std::wstring::~wstring((char **)v78);
          std::wstring::~wstring((char **)lpNewFileName);
          std::wstring::~wstring((char **)pData);
          std::wstring::~wstring((char **)lpFileName);
          if ( v18 )
            CoUninitialize();
          goto LABEL_94;
        }
      }
    }
    LOBYTE(v24) = 1;
    v27 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 9) + 8LL))(
                           *((_QWORD *)this + 9),
                           0,
                           v24);
    if ( !v27 )
    {
      LOBYTE(v31) = 1;
      v27 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 9) + 8LL))(
                             *((_QWORD *)this + 9),
                             0,
                             0,
                             v31);
      if ( !v27 )
      {
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "PrintConfig::CConfigManager::UpdateMergedConfigData",
          L"Could not find a PrintDeviceCapabilities file in a PrintDeviceCapabilities-based driver.");
        hr_error::hr_error((hr_error *)pExceptionObject, -2147418113);
        throw (hr_error *)pExceptionObject;
      }
    }
    goto LABEL_35;
  }
  v49 = 0;
  v50 = *((_DWORD *)this + 6) != 0;
  LOBYTE(v17) = 1;
  LOBYTE(v16) = v50;
  v51 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 9)
                                                                                              + 8LL))(
                                    *((_QWORD *)this + 9),
                                    0,
                                    v16,
                                    v17);
  v43 = (PrintConfig::CConfigFilePreproc *)Block;
  if ( v51 )
  {
    v53 = PrintConfig::CConfigFilePreproc::PreProcessFile((PrintConfig::CConfigFilePreproc *)Block, v51, v50);
    if ( v53 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v53);
      throw (hr_error *)pExceptionObject;
    }
    v49 = 1;
  }
  v54 = L"device_bidi.gpd";
  if ( !*((_DWORD *)this + 6) )
    v54 = L"device_bidi.ppd";
  v55 = *((_QWORD *)this + 6);
  do
    ++v12;
  while ( v54[v12] );
  if ( 0x7FFFFFFFFFFFFFFELL - v55 < v12 )
    std::_Xlen_string();
  if ( *((_QWORD *)this + 7) > 7u )
    v2 = *(WCHAR **)v2;
  std::wstring::wstring((char *)lpNewFileName, 0, v52, v2, v55, v54, v12);
  v56 = (const WCHAR *)lpNewFileName;
  if ( v77 > 7 )
    v56 = lpNewFileName[0];
  if ( GetFileAttributesW(v56) != -1 )
  {
    v59 = (const unsigned __int16 *)lpNewFileName;
    if ( v77 > 7 )
      v59 = lpNewFileName[0];
    v60 = PrintConfig::CConfigFilePreproc::PreProcessFile(
            v43,
            v59,
            (*(_BYTE *)(*((_QWORD *)this + 9) + 120LL) & 0x18) != 0);
    if ( v60 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v60);
      throw (hr_error *)pExceptionObject;
    }
  }
  v61 = *((_DWORD *)this + 6) == 0;
  LOBYTE(v58) = 1;
  LOBYTE(v57) = v61;
  v62 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)this + 9)
                                                                                              + 8LL))(
                                    *((_QWORD *)this + 9),
                                    0,
                                    v57,
                                    v58);
  if ( v62 )
  {
    v63 = PrintConfig::CConfigFilePreproc::PreProcessFile(v43, v62, v61);
    if ( v63 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v63);
      throw (hr_error *)pExceptionObject;
    }
  }
  else if ( !v49 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024894);
    throw (hr_error *)pExceptionObject;
  }
  std::wstring::~wstring((char **)lpNewFileName);
LABEL_94:
  v64 = *((_DWORD *)v43 + 4);
  pType = 0;
  *(_DWORD *)v69 = 0;
  pcbNeeded = 0;
  PrinterDataW = GetPrinterDataW(
                   *((HANDLE *)this + 8),
                   (LPWSTR)L"V4_Merged_ConfigFile_CRC",
                   &pType,
                   v69,
                   4u,
                   &pcbNeeded);
  if ( PrinterDataW == 2 || !PrinterDataW && *(_DWORD *)v69 != v64 )
  {
    if ( v14 )
    {
      ((void (__fastcall *)(struct ISequentialStream *))v14->lpVtbl->Release)(v14);
      v14 = 0;
      v75[0] = 0;
    }
    PrintConfig::CConfigManager::SaveMergedConfigFileAndReg(this, *((void **)this + 8), FileName, v64);
  }
  v81 = 0;
  v66 = v80;
  if ( v82 > 7 )
    v66 = (LPCWSTR *)v80[0];
  *(_WORD *)v66 = 0;
  if ( v81 )
  {
    v67 = (const WCHAR *)v80;
    if ( v82 > 7 )
      v67 = v80[0];
    DeleteFileW(v67);
  }
  std::wstring::~wstring((char **)v80);
  if ( v43 )
    operator delete(v43);
  if ( v14 )
    ((void (__fastcall *)(struct ISequentialStream *))v14->lpVtbl->Release)(v14);
}

```

## disassembly

```asm
0x18004d3dc  push    rbp
0x18004d3de  push    rbx
0x18004d3df  push    rsi
0x18004d3e0  push    rdi
0x18004d3e1  push    r12
0x18004d3e3  push    r13
0x18004d3e5  push    r14
0x18004d3e7  push    r15
0x18004d3e9  lea     rbp, [rsp-258h]
0x18004d3f1  sub     rsp, 358h
0x18004d3f8  mov     [rbp+290h+var_310], 0FFFFFFFFFFFFFFFEh
0x18004d400  mov     rax, cs:__security_cookie
0x18004d407  xor     rax, rsp
0x18004d40a  mov     [rbp+290h+var_50], rax
0x18004d411  mov     rsi, rcx
0x18004d414  xor     r13d, r13d
0x18004d417  xor     edx, edx; Val
0x18004d419  mov     r8d, 208h; Size
0x18004d41f  lea     rcx, [rbp+290h+FileName]; void *
0x18004d423  call    memset_0
0x18004d428  lea     rdx, aEnter_0; "Enter"
0x18004d42f  lea     rcx, aPrintconfigCco_12; "PrintConfig::CConfigManager::UpdateMerg"...
0x18004d436  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004d43b  lea     rdi, [rsi+20h]
0x18004d43f  cmp     qword ptr [rdi+18h], 7
0x18004d444  jbe     short loc_18004D44B
0x18004d446  mov     rax, [rdi]
0x18004d449  jmp     short loc_18004D44E
0x18004d44b  mov     rax, rdi
0x18004d44e  mov     ecx, 7FFFFFFEh
0x18004d453  mov     r10d, 104h
0x18004d459  mov     edx, r10d
0x18004d45c  lea     r9, [rbp+290h+FileName]
0x18004d460  test    rcx, rcx
0x18004d463  jz      short loc_18004D484
0x18004d465  movzx   r8d, word ptr [rax]
0x18004d469  test    r8w, r8w
0x18004d46d  jz      short loc_18004D484
0x18004d46f  add     rax, 2
0x18004d473  mov     [r9], r8w
0x18004d477  add     r9, 2
0x18004d47b  dec     rcx
0x18004d47e  sub     rdx, 1
0x18004d482  jnz     short loc_18004D460
0x18004d484  mov     rax, rdx
0x18004d487  neg     rax
0x18004d48a  sbb     r8d, r8d
0x18004d48d  not     r8d
0x18004d490  and     r8d, 8007007Ah
0x18004d497  lea     rcx, [r9-2]
0x18004d49b  test    rdx, rdx
0x18004d49e  cmovnz  rcx, r9
0x18004d4a2  mov     [rcx], r13w
0x18004d4a6  jz      loc_18004DBB6
0x18004d4ac  lea     rax, aMergedPpd; "merged.ppd"
0x18004d4b3  lea     r8, aMergedGpd; "merged.gpd"
0x18004d4ba  cmp     [rsi+18h], r13d
0x18004d4be  cmovz   r8, rax; unsigned __int16 *
0x18004d4c2  mov     rdx, r10; unsigned __int64
0x18004d4c5  lea     rcx, [rbp+290h+FileName]; unsigned __int16 *
0x18004d4c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004d4ce  test    eax, eax
0x18004d4d0  js      loc_18004DBD3
0x18004d4d6  mov     [rsp+390h+var_318], r13
0x18004d4db  mov     [rsp+390h+Block], r13
0x18004d4e0  lea     rdx, [rsp+390h+var_318]; struct ISequentialStream **
0x18004d4e5  lea     rcx, [rbp+290h+FileName]; lpFileName
0x18004d4e9  call    ?Create@CConfigFileStream@PrintConfig@@SAJPEBGPEAPEAUISequentialStream@@@Z; PrintConfig::CConfigFileStream::Create(ushort const *,ISequentialStream * *)
0x18004d4ee  test    eax, eax
0x18004d4f0  js      loc_18004DBEF
0x18004d4f6  xorps   xmm0, xmm0
0x18004d4f9  movups  xmmword ptr [rbp+290h+var_2C8], xmm0
0x18004d4fd  mov     [rbp+290h+var_2B8], r13
0x18004d501  mov     [rbp+290h+var_2B0], r13
0x18004d505  lea     rax, [rbp+290h+FileName]
0x18004d509  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004d50d  mov     r8, rbx
0x18004d510  inc     r8
0x18004d513  cmp     [rax+r8*2], r13w
0x18004d518  jnz     short loc_18004D510
0x18004d51a  lea     rdx, [rbp+290h+FileName]
0x18004d51e  lea     rcx, [rbp+290h+var_2C8]
0x18004d522  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004d527  nop
0x18004d528  mov     r14, [rsp+390h+var_318]
0x18004d52d  lea     r8, [rsp+390h+Block]; struct PrintConfig::CConfigFilePreproc **
0x18004d532  mov     rdx, [rsi+48h]; struct PrintConfigData *
0x18004d536  mov     rcx, r14; struct ISequentialStream *
0x18004d539  call    ?Create@CConfigFilePreproc@PrintConfig@@SAJPEAUISequentialStream@@PEAVPrintConfigData@@PEAPEAV12@@Z; PrintConfig::CConfigFilePreproc::Create(ISequentialStream *,PrintConfigData *,PrintConfig::CConfigFilePreproc * *)
0x18004d53e  test    eax, eax
0x18004d540  js      loc_18004DC0B
0x18004d546  lea     rdx, aV4Printdevicec; "V4_PrintDeviceCapabilities"
0x18004d54d  mov     rcx, [rsi+40h]; hPrinter
0x18004d551  call    cs:__imp_DeletePrinterDataW
0x18004d558  nop     dword ptr [rax+rax+00h]
0x18004d55d  cmp     [rsi+1Ch], r13b
0x18004d561  jz      loc_18004D8B7
0x18004d567  mov     ebx, r13d
0x18004d56a  mov     [rsp+390h+var_328], ebx
0x18004d56e  xor     edx, edx; dwCoInit
0x18004d570  xor     ecx, ecx; pvReserved
0x18004d572  call    cs:__imp_CoInitializeEx
0x18004d579  nop     dword ptr [rax+rax+00h]
0x18004d57e  test    eax, eax
0x18004d580  jns     short loc_18004D58F
0x18004d582  cmp     eax, 80010106h
0x18004d587  jnz     loc_18004DB28
0x18004d58d  jmp     short loc_18004D598
0x18004d58f  mov     ebx, 1
0x18004d594  mov     [rsp+390h+var_328], ebx
0x18004d598  mov     rcx, [rdi+10h]
0x18004d59c  mov     r15, 7FFFFFFFFFFFFFFEh
0x18004d5a6  mov     rax, r15
0x18004d5a9  sub     rax, rcx
0x18004d5ac  cmp     rax, 13h
0x18004d5b0  jb      loc_18004DC27
0x18004d5b6  cmp     qword ptr [rdi+18h], 7
0x18004d5bb  jbe     short loc_18004D5C2
0x18004d5bd  mov     r9, [rdi]
0x18004d5c0  jmp     short loc_18004D5C5
0x18004d5c2  mov     r9, rdi
0x18004d5c5  mov     [rsp+390h+var_360], 13h
0x18004d5ce  lea     rax, aDeviceBidiPdcX; "device_bidi_pdc.xml"
0x18004d5d5  mov     [rsp+390h+pcbNeeded], rax
0x18004d5da  mov     qword ptr [rsp+390h+cbData], rcx
0x18004d5df  lea     rcx, [rbp+290h+lpFileName]
0x18004d5e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004d5e8  nop
0x18004d5e9  cmp     [rsi+1Dh], r13b
0x18004d5ed  jz      loc_18004D696
0x18004d5f3  lea     rcx, [rbp+290h+lpFileName]
0x18004d5f7  cmp     [rbp+290h+var_270], 7
0x18004d5fc  cmova   rcx, [rbp+290h+lpFileName]; lpFileName
0x18004d601  call    cs:__imp_GetFileAttributesW
0x18004d608  nop     dword ptr [rax+rax+00h]
0x18004d60d  cmp     eax, 0FFFFFFFFh
0x18004d610  jz      loc_18004D696
0x18004d616  lea     r8, [rbp+290h+lpFileName]
0x18004d61a  cmp     [rbp+290h+var_270], 7
0x18004d61f  cmova   r8, [rbp+290h+lpFileName]
0x18004d624  lea     rdx, aUsingADeviceBa; "Using a device-based PrintDeviceCapabil"...
0x18004d62b  lea     rcx, aPrintconfigCco_12; "PrintConfig::CConfigManager::UpdateMerg"...
0x18004d632  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004d637  cmp     [rbp+290h+var_270], 7
0x18004d63c  jbe     short loc_18004D690
0x18004d63e  mov     r12, [rbp+290h+lpFileName]
0x18004d642  test    r12, r12
0x18004d645  jz      short loc_18004D696
0x18004d647  xorps   xmm0, xmm0
0x18004d64a  movups  xmmword ptr [rbp+290h+pData], xmm0
0x18004d64e  xorps   xmm1, xmm1
0x18004d651  movdqu  [rbp+290h+var_298], xmm1
0x18004d656  mov     r8d, 7
0x18004d65c  lea     rdx, aPdcXml; "pdc.xml"
0x18004d663  lea     rcx, [rbp+290h+pData]
0x18004d667  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004d66c  nop
0x18004d66d  mov     rcx, [rdi+10h]
0x18004d671  mov     rdx, qword ptr [rbp+290h+var_298]
0x18004d675  mov     rax, r15
0x18004d678  sub     rax, rcx
0x18004d67b  cmp     rax, rdx
0x18004d67e  jb      loc_18004DC2D
0x18004d684  cmp     qword ptr [rdi+18h], 7
0x18004d689  jbe     short loc_18004D6DF
0x18004d68b  mov     r9, [rdi]
0x18004d68e  jmp     short loc_18004D6E2
0x18004d690  lea     r12, [rbp+290h+lpFileName]
0x18004d694  jmp     short loc_18004D647
0x18004d696  mov     rcx, [rsi+48h]
0x18004d69a  mov     rax, [rcx]
0x18004d69d  mov     r9b, 1
0x18004d6a0  mov     r8b, r9b
0x18004d6a3  xor     edx, edx
0x18004d6a5  mov     rax, [rax+8]
0x18004d6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6ae  mov     r12, rax
0x18004d6b1  test    rax, rax
0x18004d6b4  jnz     short loc_18004D647
0x18004d6b6  mov     rcx, [rsi+48h]
0x18004d6ba  mov     rax, [rcx]
0x18004d6bd  mov     r9b, 1
0x18004d6c0  xor     r8d, r8d
0x18004d6c3  xor     edx, edx
0x18004d6c5  mov     rax, [rax+8]
0x18004d6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6ce  mov     r12, rax
0x18004d6d1  test    rax, rax
0x18004d6d4  jz      loc_18004DB46
0x18004d6da  jmp     loc_18004D647
0x18004d6df  mov     r9, rdi
0x18004d6e2  lea     rax, [rbp+290h+pData]
0x18004d6e6  cmp     qword ptr [rbp+290h+var_298+8], 7
0x18004d6eb  cmova   rax, [rbp+290h+pData]
0x18004d6f0  mov     [rsp+390h+var_360], rdx
0x18004d6f5  mov     [rsp+390h+pcbNeeded], rax
0x18004d6fa  mov     qword ptr [rsp+390h+cbData], rcx
0x18004d6ff  lea     rcx, [rbp+290h+lpNewFileName]
0x18004d703  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004d708  nop
0x18004d709  lea     rdx, [rbp+290h+lpNewFileName]
0x18004d70d  cmp     [rbp+290h+var_2F0], 7
0x18004d712  cmova   rdx, [rbp+290h+lpNewFileName]; lpNewFileName
0x18004d717  xor     r8d, r8d; bFailIfExists
0x18004d71a  mov     rcx, r12; lpExistingFileName
0x18004d71d  call    cs:__imp_CopyFileW
0x18004d724  nop     dword ptr [rax+rax+00h]
0x18004d729  test    eax, eax
0x18004d72b  jz      loc_18004DC33
0x18004d731  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505> `wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl(void)'::`2'::impl
0x18004d738  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled(void)
0x18004d73d  test    al, al
0x18004d73f  jnz     short loc_18004D746
0x18004d741  call    ?ClearPdcCache@IppPdcProvider@PrintConfig@@SAXXZ; PrintConfig::IppPdcProvider::ClearPdcCache(void)
0x18004d746  mov     eax, dword ptr [rbp+290h+var_298]
0x18004d749  lea     r9, [rbp+290h+pData]
0x18004d74d  cmp     qword ptr [rbp+290h+var_298+8], 7
0x18004d752  cmova   r9, [rbp+290h+pData]; pData
0x18004d757  lea     eax, ds:2[rax*2]
0x18004d75e  mov     [rsp+390h+cbData], eax; cbData
0x18004d762  mov     r8d, 1; Type
0x18004d768  lea     rdx, aV4Printdevicec; "V4_PrintDeviceCapabilities"
0x18004d76f  mov     rcx, [rsi+40h]; hPrinter
0x18004d773  call    cs:__imp_SetPrinterDataW
0x18004d77a  nop     dword ptr [rax+rax+00h]
0x18004d77f  test    eax, eax
0x18004d781  jle     short loc_18004D78D
0x18004d783  movzx   eax, ax
0x18004d786  or      eax, 80070000h
0x18004d78b  test    eax, eax
0x18004d78d  js      loc_18004DC69
0x18004d793  mov     rcx, [rdi+10h]
0x18004d797  sub     r15, rcx
0x18004d79a  cmp     r15, 0Fh
0x18004d79e  jb      loc_18004DC87
0x18004d7a4  cmp     qword ptr [rdi+18h], 7
0x18004d7a9  jbe     short loc_18004D7AE
0x18004d7ab  mov     rdi, [rdi]
0x18004d7ae  mov     [rsp+390h+var_360], 0Fh
0x18004d7b7  lea     rax, aDeviceBidiGpd; "device_bidi.gpd"
0x18004d7be  mov     [rsp+390h+pcbNeeded], rax
0x18004d7c3  mov     qword ptr [rsp+390h+cbData], rcx
0x18004d7c8  mov     r9, rdi
0x18004d7cb  lea     rcx, [rbp+290h+var_2E8]
0x18004d7cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004d7d4  nop
0x18004d7d5  lea     rdx, [rbp+290h+var_2E8]
0x18004d7d9  cmp     [rbp+290h+var_2D0], 7
0x18004d7de  cmova   rdx, [rbp+290h+var_2E8]; unsigned __int16 *
0x18004d7e3  lea     rcx, [rbp+290h+lpNewFileName]
0x18004d7e7  cmp     [rbp+290h+var_2F0], 7
0x18004d7ec  cmova   rcx, [rbp+290h+lpNewFileName]; psz
0x18004d7f1  call    ?ConvertToGPD@PrintDeviceCapabilitiesOM@@YAXPEBG0@Z; PrintDeviceCapabilitiesOM::ConvertToGPD(ushort const *,ushort const *)
0x18004d7f6  mov     r13, [rsp+390h+Block]
0x18004d7fb  mov     rax, [rsi+48h]
0x18004d7ff  test    byte ptr [rax+78h], 18h
0x18004d803  setnz   r8b; bool
0x18004d807  lea     rdx, [rbp+290h+var_2E8]
0x18004d80b  cmp     [rbp+290h+var_2D0], 7
0x18004d810  cmova   rdx, [rbp+290h+var_2E8]; unsigned __int16 *
0x18004d815  mov     rcx, r13; this
0x18004d818  call    ?PreProcessFile@CConfigFilePreproc@PrintConfig@@QEAAJPEBG_N@Z; PrintConfig::CConfigFilePreproc::PreProcessFile(ushort const *,bool)
0x18004d81d  xor     edi, edi
0x18004d81f  test    eax, eax
0x18004d821  js      loc_18004DC8D
0x18004d827  lea     rcx, [rbp+290h+var_2E8]
0x18004d82b  cmp     [rbp+290h+var_2D0], 7
0x18004d830  cmova   rcx, [rbp+290h+var_2E8]; lpFileName
0x18004d835  call    cs:__imp_DeleteFileW
0x18004d83c  nop     dword ptr [rax+rax+00h]
0x18004d841  test    eax, eax
0x18004d843  jnz     short loc_18004D876
0x18004d845  call    cs:__imp_GetLastError
0x18004d84c  nop     dword ptr [rax+rax+00h]
0x18004d851  lea     r8, [rbp+290h+var_2E8]
0x18004d855  cmp     [rbp+290h+var_2D0], 7
0x18004d85a  cmova   r8, [rbp+290h+var_2E8]
0x18004d85f  mov     r9d, eax
0x18004d862  lea     rdx, aCouldNotDelete; "Could not delete converted GPD file: %w"...
0x18004d869  lea     rcx, aPrintconfigCco_12; "PrintConfig::CConfigManager::UpdateMerg"...
0x18004d870  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004d875  nop
0x18004d876  lea     rcx, [rbp+290h+var_2E8]
0x18004d87a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d87f  nop
0x18004d880  lea     rcx, [rbp+290h+lpNewFileName]
0x18004d884  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d889  nop
0x18004d88a  lea     rcx, [rbp+290h+pData]
0x18004d88e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d893  nop
0x18004d894  lea     rcx, [rbp+290h+lpFileName]
0x18004d898  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d89d  nop
0x18004d89e  test    ebx, ebx
0x18004d8a0  jz      loc_18004D9FB
0x18004d8a6  call    cs:__imp_CoUninitialize
0x18004d8ad  nop     dword ptr [rax+rax+00h]
0x18004d8b2  jmp     loc_18004D9FB
0x18004d8b7  mov     r12b, r13b
  ... truncated ...
```
