# PrintConfig::CConfigManager::UpdateMergedConfigData(void)

- ea: `0x18004b448`
- end: `0x18004bcdd`
- name: `?UpdateMergedConfigData@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `2197`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001aecc`
- `0x18001b6d0`

## callees

- `0x1800032e0`
- `0x180003310`
- `0x180004418`
- `0x180004424`
- `0x18000be0c`
- `0x18000da28`
- `0x18000e348`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018818`
- `0x1800496d4`
- `0x18004b448`
- `0x18008f5d4`
- `0x18008f810`
- `0x18008f890`
- `0x1800dbe4c`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18004b777`
- `KERNEL32!CopyFileW` at `0x18004b777`
- `KERNEL32!DeleteFileW` at `0x18004b86e`
- `KERNEL32!DeleteFileW` at `0x18004bac0`
- `KERNEL32!DeleteFileW` at `0x18004b86e`
- `KERNEL32!DeleteFileW` at `0x18004bac0`
- `KERNEL32!GetLastError` at `0x18004b878`
- `KERNEL32!GetLastError` at `0x18004bc47`
- `KERNEL32!GetLastError` at `0x18004b878`
- `KERNEL32!GetLastError` at `0x18004bc47`
- `KERNEL32!GetFileAttributesW` at `0x18004b661`
- `KERNEL32!GetFileAttributesW` at `0x18004b994`
- `KERNEL32!GetFileAttributesW` at `0x18004b661`
- `KERNEL32!GetFileAttributesW` at `0x18004b994`
- `ole32!CoInitializeEx` at `0x18004b5d8`
- `ole32!CoInitializeEx` at `0x18004b5d8`
- `ole32!CoUninitialize` at `0x18004b8d3`
- `ole32!CoUninitialize` at `0x18004b8d3`
- `WINSPOOL!DeletePrinterDataW` at `0x18004b5bd`
- `WINSPOOL!DeletePrinterDataW` at `0x18004b5bd`
- `WINSPOOL!SetPrinterDataW` at `0x18004b7b2`
- `WINSPOOL!SetPrinterDataW` at `0x18004b7b2`
- `WINSPOOL!GetPrinterDataW` at `0x18004ba53`
- `WINSPOOL!GetPrinterDataW` at `0x18004ba53`

## string_xrefs

- `0x18004b62e`: `device_bidi_pdc.xml`
- `0x18004ba48`: `V4_Merged_ConfigFile_CRC`
- `0x18004b49b`: `PrintConfig::CConfigManager::UpdateMergedConfigData`
- `0x18004b685`: `PrintConfig::CConfigManager::UpdateMergedConfigData`
- `0x18004b896`: `PrintConfig::CConfigManager::UpdateMergedConfigData`
- `0x18004bb61`: `PrintConfig::CConfigManager::UpdateMergedConfigData`
- `0x18004b6b6`: `pdc.xml`
- `0x18004b88f`: `Could not delete converted GPD file: %ws (LastError: %d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
void __fastcall PrintConfig::CConfigManager::UpdateMergedConfigData(PrintConfig::CConfigManager *this)
{
  WCHAR *v2; // rdi
  WCHAR *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rdx
  WCHAR *v6; // r9
  WCHAR v7; // r8
  WCHAR *v8; // rcx
  const unsigned __int16 *v9; // r8
  int v10; // eax
  int v11; // eax
  unsigned __int64 v12; // rbx
  __int64 v13; // r8
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
  const unsigned __int16 *v41; // rdx
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
  const wchar_t *v54; // rax
  __int64 v55; // rcx
  const WCHAR *v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  const unsigned __int16 *v59; // rdx
  int v60; // eax
  bool v61; // bl
  const unsigned __int16 *v62; // rax
  int v63; // eax
  unsigned int v64; // ebx
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
  v10 = StringCchCatW(FileName, 0x104u, v9);
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
  std::wstring::_Construct<1,unsigned short const *>(v80, FileName);
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
    std::wstring::wstring(lpFileName, v20, v21, v23, v22, L"device_bidi_pdc.xml", 19);
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
          std::wstring::_Construct<1,unsigned short const *>(pData, L"pdc.xml");
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
          std::wstring::wstring(lpNewFileName, v84, v28, v30, v29, v32, v84);
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
          std::wstring::wstring(v78, v36, v37, v2, v39, L"device_bidi.gpd", 15);
          v41 = (const unsigned __int16 *)v78;
          if ( v79 > 7 )
            v41 = v78[0];
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
          std::wstring::~wstring(v78);
          std::wstring::~wstring(lpNewFileName);
          std::wstring::~wstring(pData);
          std::wstring::~wstring(lpFileName);
          if ( v18 )
            CoUninitialize();
          goto LABEL_92;
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
  std::wstring::wstring(lpNewFileName, 0, v52, v2, v55, v54, v12);
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
  std::wstring::~wstring(lpNewFileName);
LABEL_92:
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
  std::wstring::~wstring(v80);
  if ( v43 )
    operator delete(v43);
  if ( v14 )
    ((void (__fastcall *)(struct ISequentialStream *))v14->lpVtbl->Release)(v14);
}

```

## disassembly

```asm
0x18004b448  push    rbp
0x18004b44a  push    rbx
0x18004b44b  push    rsi
0x18004b44c  push    rdi
0x18004b44d  push    r12
0x18004b44f  push    r13
0x18004b451  push    r14
0x18004b453  push    r15
0x18004b455  lea     rbp, [rsp-258h]
0x18004b45d  sub     rsp, 358h
0x18004b464  mov     [rbp+290h+var_310], 0FFFFFFFFFFFFFFFEh
0x18004b46c  mov     rax, cs:__security_cookie
0x18004b473  xor     rax, rsp
0x18004b476  mov     [rbp+290h+var_50], rax
0x18004b47d  mov     rsi, rcx
0x18004b480  xor     r13d, r13d
0x18004b483  xor     edx, edx; Val
0x18004b485  mov     r8d, 208h; Size
0x18004b48b  lea     rcx, [rbp+290h+FileName]; void *
0x18004b48f  call    memset_0
0x18004b494  lea     rdx, aEnter_0; "Enter"
0x18004b49b  lea     rcx, aPrintconfigCco_12; "PrintConfig::CConfigManager::UpdateMerg"...
0x18004b4a2  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004b4a7  lea     rdi, [rsi+20h]
0x18004b4ab  cmp     qword ptr [rdi+18h], 7
0x18004b4b0  jbe     short loc_18004B4B7
0x18004b4b2  mov     rax, [rdi]
0x18004b4b5  jmp     short loc_18004B4BA
0x18004b4b7  mov     rax, rdi
0x18004b4ba  mov     ecx, 7FFFFFFEh
0x18004b4bf  mov     r10d, 104h
0x18004b4c5  mov     edx, r10d
0x18004b4c8  lea     r9, [rbp+290h+FileName]
0x18004b4cc  test    rcx, rcx
0x18004b4cf  jz      short loc_18004B4F0
0x18004b4d1  movzx   r8d, word ptr [rax]
0x18004b4d5  test    r8w, r8w
0x18004b4d9  jz      short loc_18004B4F0
0x18004b4db  add     rax, 2
0x18004b4df  mov     [r9], r8w
0x18004b4e3  add     r9, 2
0x18004b4e7  dec     rcx
0x18004b4ea  sub     rdx, 1
0x18004b4ee  jnz     short loc_18004B4CC
0x18004b4f0  mov     rax, rdx
0x18004b4f3  neg     rax
0x18004b4f6  sbb     r8d, r8d
0x18004b4f9  not     r8d
0x18004b4fc  and     r8d, 8007007Ah
0x18004b503  lea     rcx, [r9-2]
0x18004b507  test    rdx, rdx
0x18004b50a  cmovnz  rcx, r9
0x18004b50e  mov     [rcx], r13w
0x18004b512  jz      loc_18004BBCA
0x18004b518  lea     rax, aMergedPpd; "merged.ppd"
0x18004b51f  lea     r8, aMergedGpd; "merged.gpd"
0x18004b526  cmp     [rsi+18h], r13d
0x18004b52a  cmovz   r8, rax; unsigned __int16 *
0x18004b52e  mov     rdx, r10; unsigned __int64
0x18004b531  lea     rcx, [rbp+290h+FileName]; unsigned __int16 *
0x18004b535  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004b53a  test    eax, eax
0x18004b53c  js      loc_18004BBE7
0x18004b542  mov     [rsp+390h+var_318], r13
0x18004b547  mov     [rsp+390h+Block], r13
0x18004b54c  lea     rdx, [rsp+390h+var_318]; struct ISequentialStream **
0x18004b551  lea     rcx, [rbp+290h+FileName]; lpFileName
0x18004b555  call    ?Create@CConfigFileStream@PrintConfig@@SAJPEBGPEAPEAUISequentialStream@@@Z; PrintConfig::CConfigFileStream::Create(ushort const *,ISequentialStream * *)
0x18004b55a  test    eax, eax
0x18004b55c  js      loc_18004BC03
0x18004b562  xorps   xmm0, xmm0
0x18004b565  movups  xmmword ptr [rbp+290h+var_2C8], xmm0
0x18004b569  mov     [rbp+290h+var_2B8], r13
0x18004b56d  mov     [rbp+290h+var_2B0], r13
0x18004b571  lea     rax, [rbp+290h+FileName]
0x18004b575  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004b579  mov     r8, rbx
0x18004b57c  inc     r8
0x18004b57f  cmp     [rax+r8*2], r13w
0x18004b584  jnz     short loc_18004B57C
0x18004b586  lea     rdx, [rbp+290h+FileName]
0x18004b58a  lea     rcx, [rbp+290h+var_2C8]
0x18004b58e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004b593  nop
0x18004b594  mov     r14, [rsp+390h+var_318]
0x18004b599  lea     r8, [rsp+390h+Block]; struct PrintConfig::CConfigFilePreproc **
0x18004b59e  mov     rdx, [rsi+48h]; struct PrintConfigData *
0x18004b5a2  mov     rcx, r14; struct ISequentialStream *
0x18004b5a5  call    ?Create@CConfigFilePreproc@PrintConfig@@SAJPEAUISequentialStream@@PEAVPrintConfigData@@PEAPEAV12@@Z; PrintConfig::CConfigFilePreproc::Create(ISequentialStream *,PrintConfigData *,PrintConfig::CConfigFilePreproc * *)
0x18004b5aa  test    eax, eax
0x18004b5ac  js      loc_18004BC1F
0x18004b5b2  lea     rdx, aV4Printdevicec; "V4_PrintDeviceCapabilities"
0x18004b5b9  mov     rcx, [rsi+40h]; hPrinter
0x18004b5bd  call    cs:__imp_DeletePrinterDataW
0x18004b5c3  cmp     [rsi+1Ch], r13b
0x18004b5c7  jz      loc_18004B8DE
0x18004b5cd  mov     ebx, r13d
0x18004b5d0  mov     [rsp+390h+var_328], ebx
0x18004b5d4  xor     edx, edx; dwCoInit
0x18004b5d6  xor     ecx, ecx; pvReserved
0x18004b5d8  call    cs:__imp_CoInitializeEx
0x18004b5de  test    eax, eax
0x18004b5e0  jns     short loc_18004B5EF
0x18004b5e2  cmp     eax, 80010106h
0x18004b5e7  jnz     loc_18004BB3C
0x18004b5ed  jmp     short loc_18004B5F8
0x18004b5ef  mov     ebx, 1
0x18004b5f4  mov     [rsp+390h+var_328], ebx
0x18004b5f8  mov     rcx, [rdi+10h]
0x18004b5fc  mov     r15, 7FFFFFFFFFFFFFFEh
0x18004b606  mov     rax, r15
0x18004b609  sub     rax, rcx
0x18004b60c  cmp     rax, 13h
0x18004b610  jb      loc_18004BC3B
0x18004b616  cmp     qword ptr [rdi+18h], 7
0x18004b61b  jbe     short loc_18004B622
0x18004b61d  mov     r9, [rdi]
0x18004b620  jmp     short loc_18004B625
0x18004b622  mov     r9, rdi
0x18004b625  mov     [rsp+390h+var_360], 13h
0x18004b62e  lea     rax, aDeviceBidiPdcX; "device_bidi_pdc.xml"
0x18004b635  mov     [rsp+390h+pcbNeeded], rax
0x18004b63a  mov     qword ptr [rsp+390h+cbData], rcx
0x18004b63f  lea     rcx, [rbp+290h+lpFileName]
0x18004b643  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004b648  nop
0x18004b649  cmp     [rsi+1Dh], r13b
0x18004b64d  jz      loc_18004B6F0
0x18004b653  lea     rcx, [rbp+290h+lpFileName]
0x18004b657  cmp     [rbp+290h+var_270], 7
0x18004b65c  cmova   rcx, [rbp+290h+lpFileName]; lpFileName
0x18004b661  call    cs:__imp_GetFileAttributesW
0x18004b667  cmp     eax, 0FFFFFFFFh
0x18004b66a  jz      loc_18004B6F0
0x18004b670  lea     r8, [rbp+290h+lpFileName]
0x18004b674  cmp     [rbp+290h+var_270], 7
0x18004b679  cmova   r8, [rbp+290h+lpFileName]
0x18004b67e  lea     rdx, aUsingADeviceBa; "Using a device-based PrintDeviceCapabil"...
0x18004b685  lea     rcx, aPrintconfigCco_12; "PrintConfig::CConfigManager::UpdateMerg"...
0x18004b68c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004b691  cmp     [rbp+290h+var_270], 7
0x18004b696  jbe     short loc_18004B6EA
0x18004b698  mov     r12, [rbp+290h+lpFileName]
0x18004b69c  test    r12, r12
0x18004b69f  jz      short loc_18004B6F0
0x18004b6a1  xorps   xmm0, xmm0
0x18004b6a4  movups  xmmword ptr [rbp+290h+pData], xmm0
0x18004b6a8  xorps   xmm1, xmm1
0x18004b6ab  movdqu  [rbp+290h+var_298], xmm1
0x18004b6b0  mov     r8d, 7
0x18004b6b6  lea     rdx, aPdcXml; "pdc.xml"
0x18004b6bd  lea     rcx, [rbp+290h+pData]
0x18004b6c1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004b6c6  nop
0x18004b6c7  mov     rcx, [rdi+10h]
0x18004b6cb  mov     rdx, qword ptr [rbp+290h+var_298]
0x18004b6cf  mov     rax, r15
0x18004b6d2  sub     rax, rcx
0x18004b6d5  cmp     rax, rdx
0x18004b6d8  jb      loc_18004BC41
0x18004b6de  cmp     qword ptr [rdi+18h], 7
0x18004b6e3  jbe     short loc_18004B739
0x18004b6e5  mov     r9, [rdi]
0x18004b6e8  jmp     short loc_18004B73C
0x18004b6ea  lea     r12, [rbp+290h+lpFileName]
0x18004b6ee  jmp     short loc_18004B6A1
0x18004b6f0  mov     rcx, [rsi+48h]
0x18004b6f4  mov     rax, [rcx]
0x18004b6f7  mov     r9b, 1
0x18004b6fa  mov     r8b, r9b
0x18004b6fd  xor     edx, edx
0x18004b6ff  mov     rax, [rax+8]
0x18004b703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b708  mov     r12, rax
0x18004b70b  test    rax, rax
0x18004b70e  jnz     short loc_18004B6A1
0x18004b710  mov     rcx, [rsi+48h]
0x18004b714  mov     rax, [rcx]
0x18004b717  mov     r9b, 1
0x18004b71a  xor     r8d, r8d
0x18004b71d  xor     edx, edx
0x18004b71f  mov     rax, [rax+8]
0x18004b723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b728  mov     r12, rax
0x18004b72b  test    rax, rax
0x18004b72e  jz      loc_18004BB5A
0x18004b734  jmp     loc_18004B6A1
0x18004b739  mov     r9, rdi
0x18004b73c  lea     rax, [rbp+290h+pData]
0x18004b740  cmp     qword ptr [rbp+290h+var_298+8], 7
0x18004b745  cmova   rax, [rbp+290h+pData]
0x18004b74a  mov     [rsp+390h+var_360], rdx
0x18004b74f  mov     [rsp+390h+pcbNeeded], rax
0x18004b754  mov     qword ptr [rsp+390h+cbData], rcx
0x18004b759  lea     rcx, [rbp+290h+lpNewFileName]
0x18004b75d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004b762  nop
0x18004b763  lea     rdx, [rbp+290h+lpNewFileName]
0x18004b767  cmp     [rbp+290h+var_2F0], 7
0x18004b76c  cmova   rdx, [rbp+290h+lpNewFileName]; lpNewFileName
0x18004b771  xor     r8d, r8d; bFailIfExists
0x18004b774  mov     rcx, r12; lpExistingFileName
0x18004b777  call    cs:__imp_CopyFileW
0x18004b77d  test    eax, eax
0x18004b77f  jz      loc_18004BC47
0x18004b785  mov     eax, dword ptr [rbp+290h+var_298]
0x18004b788  lea     r9, [rbp+290h+pData]
0x18004b78c  cmp     qword ptr [rbp+290h+var_298+8], 7
0x18004b791  cmova   r9, [rbp+290h+pData]; pData
0x18004b796  lea     eax, ds:2[rax*2]
0x18004b79d  mov     [rsp+390h+cbData], eax; cbData
0x18004b7a1  mov     r8d, 1; Type
0x18004b7a7  lea     rdx, aV4Printdevicec; "V4_PrintDeviceCapabilities"
0x18004b7ae  mov     rcx, [rsi+40h]; hPrinter
0x18004b7b2  call    cs:__imp_SetPrinterDataW
0x18004b7b8  test    eax, eax
0x18004b7ba  jle     short loc_18004B7C6
0x18004b7bc  movzx   eax, ax
0x18004b7bf  or      eax, 80070000h
0x18004b7c4  test    eax, eax
0x18004b7c6  js      loc_18004BC77
0x18004b7cc  mov     rcx, [rdi+10h]
0x18004b7d0  sub     r15, rcx
0x18004b7d3  cmp     r15, 0Fh
0x18004b7d7  jb      loc_18004BC95
0x18004b7dd  cmp     qword ptr [rdi+18h], 7
0x18004b7e2  jbe     short loc_18004B7E7
0x18004b7e4  mov     rdi, [rdi]
0x18004b7e7  mov     [rsp+390h+var_360], 0Fh
0x18004b7f0  lea     rax, aDeviceBidiGpd; "device_bidi.gpd"
0x18004b7f7  mov     [rsp+390h+pcbNeeded], rax
0x18004b7fc  mov     qword ptr [rsp+390h+cbData], rcx
0x18004b801  mov     r9, rdi
0x18004b804  lea     rcx, [rbp+290h+var_2E8]
0x18004b808  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004b80d  nop
0x18004b80e  lea     rdx, [rbp+290h+var_2E8]
0x18004b812  cmp     [rbp+290h+var_2D0], 7
0x18004b817  cmova   rdx, [rbp+290h+var_2E8]; unsigned __int16 *
0x18004b81c  lea     rcx, [rbp+290h+lpNewFileName]
0x18004b820  cmp     [rbp+290h+var_2F0], 7
0x18004b825  cmova   rcx, [rbp+290h+lpNewFileName]; psz
0x18004b82a  call    ?ConvertToGPD@PrintDeviceCapabilitiesOM@@YAXPEBG0@Z; PrintDeviceCapabilitiesOM::ConvertToGPD(ushort const *,ushort const *)
0x18004b82f  mov     r13, [rsp+390h+Block]
0x18004b834  mov     rax, [rsi+48h]
0x18004b838  test    byte ptr [rax+78h], 18h
0x18004b83c  setnz   r8b; bool
0x18004b840  lea     rdx, [rbp+290h+var_2E8]
0x18004b844  cmp     [rbp+290h+var_2D0], 7
0x18004b849  cmova   rdx, [rbp+290h+var_2E8]; unsigned __int16 *
0x18004b84e  mov     rcx, r13; this
0x18004b851  call    ?PreProcessFile@CConfigFilePreproc@PrintConfig@@QEAAJPEBG_N@Z; PrintConfig::CConfigFilePreproc::PreProcessFile(ushort const *,bool)
0x18004b856  xor     edi, edi
0x18004b858  test    eax, eax
0x18004b85a  js      loc_18004BC9B
0x18004b860  lea     rcx, [rbp+290h+var_2E8]
0x18004b864  cmp     [rbp+290h+var_2D0], 7
0x18004b869  cmova   rcx, [rbp+290h+var_2E8]; lpFileName
0x18004b86e  call    cs:__imp_DeleteFileW
0x18004b874  test    eax, eax
0x18004b876  jnz     short loc_18004B8A3
0x18004b878  call    cs:__imp_GetLastError
0x18004b87e  lea     r8, [rbp+290h+var_2E8]
0x18004b882  cmp     [rbp+290h+var_2D0], 7
0x18004b887  cmova   r8, [rbp+290h+var_2E8]
0x18004b88c  mov     r9d, eax
0x18004b88f  lea     rdx, aCouldNotDelete; "Could not delete converted GPD file: %w"...
0x18004b896  lea     rcx, aPrintconfigCco_12; "PrintConfig::CConfigManager::UpdateMerg"...
0x18004b89d  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b8a2  nop
0x18004b8a3  lea     rcx, [rbp+290h+var_2E8]
0x18004b8a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b8ac  nop
0x18004b8ad  lea     rcx, [rbp+290h+lpNewFileName]
0x18004b8b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b8b6  nop
0x18004b8b7  lea     rcx, [rbp+290h+pData]
0x18004b8bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b8c0  nop
0x18004b8c1  lea     rcx, [rbp+290h+lpFileName]
0x18004b8c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b8ca  nop
0x18004b8cb  test    ebx, ebx
0x18004b8cd  jz      loc_18004BA1C
0x18004b8d3  call    cs:__imp_CoUninitialize
0x18004b8d9  jmp     loc_18004BA1C
0x18004b8de  mov     r12b, r13b
0x18004b8e1  cmp     [rsi+18h], r13d
0x18004b8e5  setnz   r15b
0x18004b8e9  mov     rcx, [rsi+48h]
0x18004b8ed  mov     rax, [rcx]
0x18004b8f0  mov     r9b, 1
0x18004b8f3  mov     r8b, r15b
0x18004b8f6  xor     edx, edx
0x18004b8f8  mov     rax, [rax+8]
0x18004b8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b901  mov     r13, [rsp+390h+Block]
0x18004b906  xor     edx, edx
0x18004b908  test    rax, rax
0x18004b90b  jz      short loc_18004B928
  ... truncated ...
```
