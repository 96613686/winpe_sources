# PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc(ushort const *,ushort const *)

- ea: `0x18004aebc`
- end: `0x18004b442`
- name: `?UpdateGpdConfigDataFromPdc@CConfigManager@PrintConfig@@QEAAXPEBG0@Z`
- size: `1414`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180017e70`

## callees

- `0x1800032e0`
- `0x180003310`
- `0x180004418`
- `0x180004424`
- `0x18000bed0`
- `0x18000da28`
- `0x18000e348`
- `0x18000f380`
- `0x18000f590`
- `0x18000fb88`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018818`
- `0x18003b314`
- `0x18004aebc`
- `0x18008f5d4`
- `0x18008f810`
- `0x18008f890`
- `0x1800dbe4c`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18004b0d4`
- `KERNEL32!DeleteFileW` at `0x18004b2c6`
- `KERNEL32!DeleteFileW` at `0x18004b0d4`
- `KERNEL32!DeleteFileW` at `0x18004b2c6`
- `KERNEL32!GetLastError` at `0x18004b0de`
- `KERNEL32!GetLastError` at `0x18004b25f`
- `KERNEL32!GetLastError` at `0x18004b27b`
- `KERNEL32!GetLastError` at `0x18004b0de`
- `KERNEL32!GetLastError` at `0x18004b25f`
- `KERNEL32!GetLastError` at `0x18004b27b`
- `KERNEL32!MoveFileExW` at `0x18004b255`
- `KERNEL32!MoveFileExW` at `0x18004b255`
- `ole32!CoInitializeEx` at `0x18004b014`
- `ole32!CoInitializeEx` at `0x18004b014`
- `ole32!CoUninitialize` at `0x18004b117`
- `ole32!CoUninitialize` at `0x18004b117`
- `WINSPOOL!GetPrinterDataW` at `0x18004b16e`
- `WINSPOOL!GetPrinterDataW` at `0x18004b16e`

## string_xrefs

- `0x18004b163`: `V4_Merged_ConfigFile_Name`
- `0x18004b268`: `MoveFile failed: error=%d`
- `0x18004af4b`: `PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc`
- `0x18004b0fc`: `PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc`
- `0x18004b26f`: `PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc`
- `0x18004b0f5`: `Could not delete converted GPD file: %ws (LastError: %d)`

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
  int v11; // eax
  unsigned __int64 v12; // r8
  struct ISequentialStream *v13; // rdi
  int v14; // eax
  int v15; // ebx
  HRESULT v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int128 *v19; // r9
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // rdx
  void *v22; // r15
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  const WCHAR *v25; // rcx
  DWORD LastError; // eax
  LPCWSTR *v27; // r8
  signed int PrinterDataW; // eax
  bool v29; // sf
  __int64 v30; // rax
  const WCHAR *v31; // rdx
  DWORD v32; // eax
  signed int v33; // eax
  bool v34; // sf
  LPCWSTR *v35; // rcx
  const WCHAR *v36; // rcx
  DWORD pType; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbNeeded; // [rsp+44h] [rbp-BCh] BYREF
  int v39; // [rsp+48h] [rbp-B8h]
  struct ISequentialStream *v40; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v44; // [rsp+98h] [rbp-68h]
  __int128 v45; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v47; // [rsp+C0h] [rbp-40h]
  LPCWSTR v48[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v50; // [rsp+E0h] [rbp-20h]
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
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v45, a2, v7);
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc",
    L"Enter");
  v8 = L"merged.gpd";
  if ( !*((_DWORD *)this + 6) )
    v8 = L"merged.ppd";
  v9 = &v45;
  if ( v47 > 7 )
    v9 = (__int128 *)v45;
  v10 = StringCchPrintfW(ExistingFileName, 0x104u, L"%ws%ws", v9, v8);
  if ( v10 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v10);
    throw (hr_error *)pExceptionObject;
  }
  v40 = 0;
  Block[0] = 0;
  v11 = PrintConfig::CConfigFileStream::Create(ExistingFileName, &v40);
  if ( v11 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v11);
    throw (hr_error *)pExceptionObject;
  }
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v50 = 0;
  v12 = -1;
  do
    ++v12;
  while ( ExistingFileName[v12] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v48, ExistingFileName, v12);
  v13 = v40;
  v14 = PrintConfig::CConfigFilePreproc::Create(
          v40,
          *((struct PrintConfigData **)this + 9),
          (struct PrintConfig::CConfigFilePreproc **)Block);
  if ( v14 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v14);
    throw (hr_error *)pExceptionObject;
  }
  v15 = 0;
  v39 = 0;
  v16 = CoInitializeEx(0, 0);
  if ( v16 >= 0 )
  {
    v15 = 1;
    v39 = 1;
  }
  else if ( v16 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v16);
    throw (hr_error *)pExceptionObject;
  }
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v46) < 0xF )
    std::_Xlen_string();
  v19 = &v45;
  if ( v47 > 7 )
    v19 = (__int128 *)v45;
  std::wstring::wstring(lpFileName, v17, v18, v19, v46, L"device_bidi.gpd", 15);
  v21 = (const unsigned __int16 *)lpFileName;
  if ( *((_QWORD *)&v44 + 1) > 7u )
    v21 = lpFileName[0];
  PrintDeviceCapabilitiesOM::ConvertToGPD(a3, v21, v20);
  v22 = Block[0];
  v23 = (const unsigned __int16 *)lpFileName;
  if ( *((_QWORD *)&v44 + 1) > 7u )
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
  if ( *((_QWORD *)&v44 + 1) > 7u )
    v25 = lpFileName[0];
  if ( !DeleteFileW(v25) )
  {
    LastError = GetLastError();
    v27 = lpFileName;
    if ( *((_QWORD *)&v44 + 1) > 7u )
      v27 = (LPCWSTR *)lpFileName[0];
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc",
      L"Could not delete converted GPD file: %ws (LastError: %d)",
      v27,
      LastError);
  }
  std::wstring::~wstring(lpFileName);
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
  v44 = 0;
  do
    ++v6;
  while ( pData[v6] );
  std::wstring::_Construct<1,unsigned short const *>((char **)lpFileName, pData, v6);
  v30 = std::wstring::_Insert<unsigned short>(lpFileName);
  pExceptionObject[0] = *(_OWORD *)v30;
  pExceptionObject[1] = *(_OWORD *)(v30 + 16);
  *(_QWORD *)(v30 + 16) = 0;
  *(_QWORD *)(v30 + 24) = 7;
  *(_WORD *)v30 = 0;
  std::wstring::operator=(lpNewFileName, pExceptionObject);
  std::wstring::~wstring(pExceptionObject);
  std::wstring::~wstring(lpFileName);
  if ( v13 )
  {
    ((void (__fastcall *)(struct ISequentialStream *))v13->lpVtbl->Release)(v13);
    v40 = 0;
  }
  v31 = (const WCHAR *)lpNewFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v31 = lpNewFileName[0];
  if ( !MoveFileExW(ExistingFileName, v31, 1u) )
  {
    v32 = GetLastError();
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::UpdateGpdConfigDataFromPdc",
      L"MoveFile failed: error=%d",
      v32);
    v33 = GetLastError();
    v34 = v33 < 0;
    if ( v33 > 0 )
    {
      v33 = (unsigned __int16)v33 | 0x80070000;
      v34 = v33 < 0;
    }
    if ( v34 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v33);
      throw (hr_error *)pExceptionObject;
    }
  }
  v49 = 0;
  v35 = v48;
  if ( v50 > 7 )
    v35 = (LPCWSTR *)v48[0];
  *(_WORD *)v35 = 0;
  std::wstring::~wstring(lpNewFileName);
  if ( v49 )
  {
    v36 = (const WCHAR *)v48;
    if ( v50 > 7 )
      v36 = v48[0];
    DeleteFileW(v36);
  }
  std::wstring::~wstring(v48);
  if ( v22 )
    operator delete(v22);
  std::wstring::~wstring(&v45);
}

```

## disassembly

```asm
0x18004aebc  push    rbp
0x18004aebe  push    rbx
0x18004aebf  push    rsi
0x18004aec0  push    rdi
0x18004aec1  push    r12
0x18004aec3  push    r14
0x18004aec5  push    r15
0x18004aec7  lea     rbp, [rsp-250h]
0x18004aecf  sub     rsp, 350h
0x18004aed6  mov     [rsp+380h+var_320], 0FFFFFFFFFFFFFFFEh
0x18004aedf  mov     rax, cs:__security_cookie
0x18004aee6  xor     rax, rsp
0x18004aee9  mov     [rbp+280h+var_40], rax
0x18004aef0  mov     r15, r8
0x18004aef3  mov     rbx, rdx
0x18004aef6  mov     r14, rcx
0x18004aef9  xor     r12d, r12d
0x18004aefc  cmp     [rcx+1Ch], r12b
0x18004af00  jz      loc_18004B385
0x18004af06  xor     edx, edx; Val
0x18004af08  mov     r8d, 208h; Size
0x18004af0e  lea     rcx, [rbp+280h+ExistingFileName]; void *
0x18004af12  call    memset_0
0x18004af17  xorps   xmm0, xmm0
0x18004af1a  movups  [rbp+280h+var_2D8], xmm0
0x18004af1e  mov     [rbp+280h+var_2C8], r12
0x18004af22  mov     [rbp+280h+var_2C0], r12
0x18004af26  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004af2a  mov     r8, rsi
0x18004af2d  inc     r8
0x18004af30  cmp     [rbx+r8*2], r12w
0x18004af35  jnz     short loc_18004AF2D
0x18004af37  mov     rdx, rbx
0x18004af3a  lea     rcx, [rbp+280h+var_2D8]
0x18004af3e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004af43  nop
0x18004af44  lea     rdx, aEnter_0; "Enter"
0x18004af4b  lea     rcx, aPrintconfigCco_15; "PrintConfig::CConfigManager::UpdateGpdC"...
0x18004af52  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004af57  lea     rcx, aMergedPpd; "merged.ppd"
0x18004af5e  lea     rax, aMergedGpd; "merged.gpd"
0x18004af65  cmp     [r14+18h], r12d
0x18004af69  cmovz   rax, rcx
0x18004af6d  lea     r9, [rbp+280h+var_2D8]
0x18004af71  cmp     [rbp+280h+var_2C0], 7
0x18004af76  cmova   r9, qword ptr [rbp+280h+var_2D8]
0x18004af7b  mov     qword ptr [rsp+380h+nSize], rax
0x18004af80  lea     r8, aWsWs; "%ws%ws"
0x18004af87  mov     edx, 104h; unsigned __int64
0x18004af8c  lea     rcx, [rbp+280h+ExistingFileName]; unsigned __int16 *
0x18004af90  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004af95  test    eax, eax
0x18004af97  js      loc_18004B3A6
0x18004af9d  mov     [rsp+380h+var_330], r12
0x18004afa2  mov     [rsp+380h+Block], r12
0x18004afa7  lea     rdx, [rsp+380h+var_330]; struct ISequentialStream **
0x18004afac  lea     rcx, [rbp+280h+ExistingFileName]; lpFileName
0x18004afb0  call    ?Create@CConfigFileStream@PrintConfig@@SAJPEBGPEAPEAUISequentialStream@@@Z; PrintConfig::CConfigFileStream::Create(ushort const *,ISequentialStream * *)
0x18004afb5  test    eax, eax
0x18004afb7  js      loc_18004B3C4
0x18004afbd  xorps   xmm0, xmm0
0x18004afc0  movups  xmmword ptr [rbp+280h+var_2B8], xmm0
0x18004afc4  mov     [rbp+280h+var_2A8], r12
0x18004afc8  mov     [rbp+280h+var_2A0], r12
0x18004afcc  lea     rax, [rbp+280h+ExistingFileName]
0x18004afd0  mov     r8, rsi
0x18004afd3  inc     r8
0x18004afd6  cmp     [rax+r8*2], r12w
0x18004afdb  jnz     short loc_18004AFD3
0x18004afdd  lea     rdx, [rbp+280h+ExistingFileName]
0x18004afe1  lea     rcx, [rbp+280h+var_2B8]
0x18004afe5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004afea  nop
0x18004afeb  mov     rdi, [rsp+380h+var_330]
0x18004aff0  lea     r8, [rsp+380h+Block]; struct PrintConfig::CConfigFilePreproc **
0x18004aff5  mov     rdx, [r14+48h]; struct PrintConfigData *
0x18004aff9  mov     rcx, rdi; struct ISequentialStream *
0x18004affc  call    ?Create@CConfigFilePreproc@PrintConfig@@SAJPEAUISequentialStream@@PEAVPrintConfigData@@PEAPEAV12@@Z; PrintConfig::CConfigFilePreproc::Create(ISequentialStream *,PrintConfigData *,PrintConfig::CConfigFilePreproc * *)
0x18004b001  test    eax, eax
0x18004b003  js      loc_18004B3E2
0x18004b009  mov     ebx, r12d
0x18004b00c  mov     [rsp+380h+var_338], ebx
0x18004b010  xor     edx, edx; dwCoInit
0x18004b012  xor     ecx, ecx; pvReserved
0x18004b014  call    cs:__imp_CoInitializeEx
0x18004b01a  test    eax, eax
0x18004b01c  jns     short loc_18004B02B
0x18004b01e  cmp     eax, 80010106h
0x18004b023  jnz     loc_18004B346
0x18004b029  jmp     short loc_18004B034
0x18004b02b  mov     ebx, 1
0x18004b030  mov     [rsp+380h+var_338], ebx
0x18004b034  mov     rcx, [rbp+280h+var_2C8]
0x18004b038  mov     rax, 7FFFFFFFFFFFFFFEh
0x18004b042  sub     rax, rcx
0x18004b045  cmp     rax, 0Fh
0x18004b049  jb      loc_18004B400
0x18004b04f  lea     r9, [rbp+280h+var_2D8]
0x18004b053  cmp     [rbp+280h+var_2C0], 7
0x18004b058  cmova   r9, qword ptr [rbp+280h+var_2D8]
0x18004b05d  mov     [rsp+380h+var_350], 0Fh
0x18004b066  lea     rax, aDeviceBidiGpd; "device_bidi.gpd"
0x18004b06d  mov     [rsp+380h+pcbNeeded], rax
0x18004b072  mov     qword ptr [rsp+380h+nSize], rcx
0x18004b077  lea     rcx, [rbp+280h+lpFileName]
0x18004b07b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004b080  nop
0x18004b081  lea     rdx, [rbp+280h+lpFileName]
0x18004b085  cmp     [rbp+280h+var_2E0], 7
0x18004b08a  cmova   rdx, [rbp+280h+lpFileName]; unsigned __int16 *
0x18004b08f  mov     rcx, r15; psz
0x18004b092  call    ?ConvertToGPD@PrintDeviceCapabilitiesOM@@YAXPEBG0@Z; PrintDeviceCapabilitiesOM::ConvertToGPD(ushort const *,ushort const *)
0x18004b097  mov     r15, [rsp+380h+Block]
0x18004b09c  mov     rax, [r14+48h]
0x18004b0a0  test    byte ptr [rax+78h], 18h
0x18004b0a4  setnz   r8b; bool
0x18004b0a8  lea     rdx, [rbp+280h+lpFileName]
0x18004b0ac  cmp     [rbp+280h+var_2E0], 7
0x18004b0b1  cmova   rdx, [rbp+280h+lpFileName]; unsigned __int16 *
0x18004b0b6  mov     rcx, r15; this
0x18004b0b9  call    ?PreProcessFile@CConfigFilePreproc@PrintConfig@@QEAAJPEBG_N@Z; PrintConfig::CConfigFilePreproc::PreProcessFile(ushort const *,bool)
0x18004b0be  test    eax, eax
0x18004b0c0  js      loc_18004B406
0x18004b0c6  lea     rcx, [rbp+280h+lpFileName]
0x18004b0ca  cmp     [rbp+280h+var_2E0], 7
0x18004b0cf  cmova   rcx, [rbp+280h+lpFileName]; lpFileName
0x18004b0d4  call    cs:__imp_DeleteFileW
0x18004b0da  test    eax, eax
0x18004b0dc  jnz     short loc_18004B109
0x18004b0de  call    cs:__imp_GetLastError
0x18004b0e4  lea     r8, [rbp+280h+lpFileName]
0x18004b0e8  cmp     [rbp+280h+var_2E0], 7
0x18004b0ed  cmova   r8, [rbp+280h+lpFileName]
0x18004b0f2  mov     r9d, eax
0x18004b0f5  lea     rdx, aCouldNotDelete; "Could not delete converted GPD file: %w"...
0x18004b0fc  lea     rcx, aPrintconfigCco_15; "PrintConfig::CConfigManager::UpdateGpdC"...
0x18004b103  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b108  nop
0x18004b109  lea     rcx, [rbp+280h+lpFileName]
0x18004b10d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b112  nop
0x18004b113  test    ebx, ebx
0x18004b115  jz      short loc_18004B11D
0x18004b117  call    cs:__imp_CoUninitialize
0x18004b11d  xorps   xmm0, xmm0
0x18004b120  movups  xmmword ptr [rbp+280h+pData], xmm0
0x18004b124  movups  xmmword ptr [rbp+280h+pData+0Ah], xmm0
0x18004b128  movups  xmmword ptr [rbp+280h+lpNewFileName], xmm0
0x18004b12c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004b134  movdqu  [rbp+280h+var_288], xmm1
0x18004b139  mov     word ptr [rbp+280h+lpNewFileName], r12w
0x18004b13e  mov     [rsp+380h+pType], r12d
0x18004b143  mov     [rsp+380h+var_33C], r12d
0x18004b148  lea     rax, [rsp+380h+var_33C]
0x18004b14d  mov     [rsp+380h+pcbNeeded], rax; pcbNeeded
0x18004b152  mov     [rsp+380h+nSize], 1Ah; nSize
0x18004b15a  lea     r9, [rbp+280h+pData]; pData
0x18004b15e  lea     r8, [rsp+380h+pType]; pType
0x18004b163  lea     rdx, aV4MergedConfig_0; "V4_Merged_ConfigFile_Name"
0x18004b16a  mov     rcx, [r14+40h]; hPrinter
0x18004b16e  call    cs:__imp_GetPrinterDataW
0x18004b174  mov     ebx, 80070000h
0x18004b179  test    eax, eax
0x18004b17b  jle     short loc_18004B184
0x18004b17d  movzx   eax, ax
0x18004b180  or      eax, ebx
0x18004b182  test    eax, eax
0x18004b184  js      loc_18004B424
0x18004b18a  cmp     [rsp+380h+pType], 1
0x18004b18f  jnz     loc_18004B364
0x18004b195  xorps   xmm0, xmm0
0x18004b198  movups  xmmword ptr [rbp+280h+lpFileName], xmm0
0x18004b19c  xorps   xmm1, xmm1
0x18004b19f  movdqu  xmmword ptr [rbp-68h], xmm1
0x18004b1a4  lea     rax, [rbp+280h+pData]
0x18004b1a8  inc     rsi
0x18004b1ab  cmp     [rax+rsi*2], r12w
0x18004b1b0  jnz     short loc_18004B1A8
0x18004b1b2  mov     r8, rsi
0x18004b1b5  lea     rdx, [rbp+280h+pData]
0x18004b1b9  lea     rcx, [rbp+280h+lpFileName]
0x18004b1bd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004b1c2  nop
0x18004b1c3  lea     r8, [rbp+280h+var_2D8]
0x18004b1c7  cmp     [rbp+280h+var_2C0], 7
0x18004b1cc  cmova   r8, qword ptr [rbp+280h+var_2D8]
0x18004b1d1  mov     r9, [rbp+280h+var_2C8]
0x18004b1d5  lea     rcx, [rbp+280h+lpFileName]; Src
0x18004b1d9  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18004b1de  movups  xmm0, xmmword ptr [rax]
0x18004b1e1  movups  [rsp+380h+pExceptionObject], xmm0
0x18004b1e6  movups  xmm1, xmmword ptr [rax+10h]
0x18004b1ea  movups  [rsp+380h+var_308], xmm1
0x18004b1ef  mov     [rax+10h], r12
0x18004b1f3  mov     qword ptr [rax+18h], 7
0x18004b1fb  mov     [rax], r12w
0x18004b1ff  lea     rdx, [rsp+380h+pExceptionObject]
0x18004b204  lea     rcx, [rbp+280h+lpNewFileName]
0x18004b208  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004b20d  lea     rcx, [rsp+380h+pExceptionObject]
0x18004b212  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b217  nop
0x18004b218  lea     rcx, [rbp+280h+lpFileName]
0x18004b21c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b221  test    rdi, rdi
0x18004b224  jz      short loc_18004B23D
0x18004b226  mov     rax, [rdi]
0x18004b229  mov     rcx, rdi
0x18004b22c  mov     rax, [rax+10h]
0x18004b230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b235  mov     rdi, r12
0x18004b238  mov     [rsp+380h+var_330], r12
0x18004b23d  lea     rdx, [rbp+280h+lpNewFileName]
0x18004b241  cmp     qword ptr [rbp+280h+var_288+8], 7
0x18004b246  cmova   rdx, [rbp+280h+lpNewFileName]; lpNewFileName
0x18004b24b  mov     r8d, 1; dwFlags
0x18004b251  lea     rcx, [rbp+280h+ExistingFileName]; lpExistingFileName
0x18004b255  call    cs:__imp_MoveFileExW
0x18004b25b  test    eax, eax
0x18004b25d  jnz     short loc_18004B292
0x18004b25f  call    cs:__imp_GetLastError
0x18004b265  mov     r8d, eax
0x18004b268  lea     rdx, aMovefileFailed; "MoveFile failed: error=%d"
0x18004b26f  lea     rcx, aPrintconfigCco_15; "PrintConfig::CConfigManager::UpdateGpdC"...
0x18004b276  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b27b  call    cs:__imp_GetLastError
0x18004b281  test    eax, eax
0x18004b283  jle     short loc_18004B28C
0x18004b285  movzx   eax, ax
0x18004b288  or      eax, ebx
0x18004b28a  test    eax, eax
0x18004b28c  js      loc_18004B328
0x18004b292  mov     [rbp+280h+var_2A8], r12
0x18004b296  lea     rcx, [rbp+280h+var_2B8]
0x18004b29a  cmp     [rbp+280h+var_2A0], 7
0x18004b29f  cmova   rcx, [rbp+280h+var_2B8]
0x18004b2a4  mov     [rcx], r12w
0x18004b2a8  lea     rcx, [rbp+280h+lpNewFileName]
0x18004b2ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b2b1  nop
0x18004b2b2  cmp     [rbp+280h+var_2A8], r12
0x18004b2b6  jz      short loc_18004B2CC
0x18004b2b8  lea     rcx, [rbp+280h+var_2B8]
0x18004b2bc  cmp     [rbp+280h+var_2A0], 7
0x18004b2c1  cmova   rcx, [rbp+280h+var_2B8]; lpFileName
0x18004b2c6  call    cs:__imp_DeleteFileW
0x18004b2cc  lea     rcx, [rbp+280h+var_2B8]
0x18004b2d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b2d5  nop
0x18004b2d6  test    r15, r15
0x18004b2d9  jz      short loc_18004B2E9
0x18004b2db  mov     edx, 18h
0x18004b2e0  mov     rcx, r15; Block
0x18004b2e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004b2e8  nop
0x18004b2e9  test    rdi, rdi
0x18004b2ec  jz      short loc_18004B2FE
0x18004b2ee  mov     rax, [rdi]
0x18004b2f1  mov     rcx, rdi
0x18004b2f4  mov     rax, [rax+10h]
0x18004b2f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b2fd  nop
0x18004b2fe  lea     rcx, [rbp+280h+var_2D8]
0x18004b302  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b307  mov     rcx, [rbp+280h+var_40]
0x18004b30e  xor     rcx, rsp; StackCookie
0x18004b311  call    __security_check_cookie
0x18004b316  add     rsp, 350h
0x18004b31d  pop     r15
0x18004b31f  pop     r14
0x18004b321  pop     r12
0x18004b323  pop     rdi
0x18004b324  pop     rsi
0x18004b325  pop     rbx
0x18004b326  pop     rbp
0x18004b327  retn
0x18004b328  mov     edx, eax; int
0x18004b32a  lea     rcx, [rsp+380h+pExceptionObject]; this
0x18004b32f  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b334  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b33b  lea     rcx, [rsp+380h+pExceptionObject]; pExceptionObject
0x18004b340  call    _CxxThrowException_0
0x18004b346  mov     edx, eax; int
0x18004b348  lea     rcx, [rsp+380h+pExceptionObject]; this
0x18004b34d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b352  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b359  lea     rcx, [rsp+380h+pExceptionObject]; pExceptionObject
0x18004b35e  call    _CxxThrowException_0
0x18004b364  mov     edx, 8000FFFFh; int
0x18004b369  lea     rcx, [rsp+380h+pExceptionObject]; this
0x18004b36e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b373  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b37a  lea     rcx, [rsp+380h+pExceptionObject]; pExceptionObject
0x18004b37f  call    _CxxThrowException_0
0x18004b385  mov     edx, 8000FFFFh; int
0x18004b38a  lea     rcx, [rsp+380h+pExceptionObject]; this
0x18004b38f  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b394  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b39b  lea     rcx, [rsp+380h+pExceptionObject]; pExceptionObject
0x18004b3a0  call    _CxxThrowException_0
  ... truncated ...
```
