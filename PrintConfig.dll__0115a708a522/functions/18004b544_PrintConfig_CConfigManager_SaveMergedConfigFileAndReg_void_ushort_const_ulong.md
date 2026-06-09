# PrintConfig::CConfigManager::SaveMergedConfigFileAndReg(void *,ushort const *,ulong)

- ea: `0x18004b544`
- end: `0x18004b83e`
- name: `?SaveMergedConfigFileAndReg@CConfigManager@PrintConfig@@AEAAXPEAXPEBGK@Z`
- size: `762`
- prototype: `void __fastcall(PrintConfig::CConfigManager *this, void *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18004d3dc`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000bf2c`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x1800100a0`
- `0x180018f00`
- `0x180018f58`
- `0x18003c8e0`
- `0x18004b544`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004b6a6`
- `KERNEL32!GetLastError` at `0x18004b6c8`
- `KERNEL32!GetLastError` at `0x18004b724`
- `KERNEL32!GetLastError` at `0x18004b6a6`
- `KERNEL32!GetLastError` at `0x18004b6c8`
- `KERNEL32!GetLastError` at `0x18004b724`
- `KERNEL32!MoveFileExW` at `0x18004b691`
- `KERNEL32!MoveFileExW` at `0x18004b691`
- `WINSPOOL!SetPrinterDataW` at `0x18004b712`
- `WINSPOOL!SetPrinterDataW` at `0x18004b773`
- `WINSPOOL!SetPrinterDataW` at `0x18004b712`
- `WINSPOOL!SetPrinterDataW` at `0x18004b773`

## string_xrefs

- `0x18004b5a7`: `PrintConfig::CConfigManager::SaveMergedConfigFileAndReg`
- `0x18004b6bc`: `PrintConfig::CConfigManager::SaveMergedConfigFileAndReg`
- `0x18004b73d`: `PrintConfig::CConfigManager::SaveMergedConfigFileAndReg`
- `0x18004b78f`: `PrintConfig::CConfigManager::SaveMergedConfigFileAndReg`
- `0x18004b769`: `V4_Merged_ConfigFile_CRC`
- `0x18004b708`: `V4_Merged_ConfigFile_Name`
- `0x18004b6b5`: `MoveFile failed: error=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PrintConfig::CConfigManager::SaveMergedConfigFileAndReg(
        PrintConfig::CConfigManager *this,
        void *a2,
        const unsigned __int16 *a3,
        int a4)
{
  const wchar_t *v7; // rax
  int v8; // eax
  __int64 v9; // rbx
  unsigned __int64 v10; // r8
  __int64 v11; // rdx
  char *v12; // r8
  _QWORD *v13; // rax
  const WCHAR *v14; // rdx
  DWORD LastError; // eax
  signed int v16; // eax
  bool v17; // sf
  signed int v18; // ebx
  DWORD v19; // eax
  bool v20; // sf
  DWORD v21; // eax
  signed int v22; // ebx
  bool v23; // sf
  BYTE v24[4]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v25; // [rsp+40h] [rbp-69h]
  _OWORD pExceptionObject[2]; // [rsp+48h] [rbp-61h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+68h] [rbp-41h] BYREF
  __m128i si128; // [rsp+78h] [rbp-31h]
  _OWORD Src[2]; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int16 pData[16]; // [rsp+A8h] [rbp-1h] BYREF

  v25 = -2;
  *(_DWORD *)v24 = a4;
  memset(pData, 0, 26);
  *(_OWORD *)lpNewFileName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpNewFileName[0]) = 0;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::SaveMergedConfigFileAndReg",
    L"Enter");
  v7 = L".gpd";
  if ( !*((_DWORD *)this + 6) )
    v7 = L".ppd";
  v8 = StringCchPrintfW(pData, 0xDu, L"%x%s", *(unsigned int *)v24, v7);
  if ( v8 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v8);
    throw (hr_error *)pExceptionObject;
  }
  memset(Src, 0, sizeof(Src));
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( pData[v10] );
  std::wstring::_Construct<1,unsigned short const *>(Src, pData, v10);
  v12 = (char *)this + 32;
  if ( *((_QWORD *)this + 7) > 7u )
    v12 = *(char **)v12;
  v13 = std::wstring::_Insert<unsigned short>(Src, v11, v12, *((_QWORD *)this + 6));
  pExceptionObject[0] = *(_OWORD *)v13;
  pExceptionObject[1] = *((_OWORD *)v13 + 1);
  v13[2] = 0;
  v13[3] = 7;
  *(_WORD *)v13 = 0;
  std::wstring::operator=((char **)lpNewFileName, (__int64)pExceptionObject);
  std::wstring::~wstring((char **)pExceptionObject);
  std::wstring::~wstring((char **)Src);
  v14 = (const WCHAR *)lpNewFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v14 = lpNewFileName[0];
  if ( !MoveFileExW(a3, v14, 1u) )
  {
    LastError = GetLastError();
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::SaveMergedConfigFileAndReg",
      L"MoveFile failed: error=%d",
      LastError);
    v16 = GetLastError();
    v17 = v16 < 0;
    if ( v16 > 0 )
    {
      v16 = (unsigned __int16)v16 | 0x80070000;
      v17 = v16 < 0;
    }
    if ( v17 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v16);
      throw (hr_error *)pExceptionObject;
    }
  }
  do
    ++v9;
  while ( pData[v9] );
  v18 = SetPrinterDataW(a2, (LPWSTR)L"V4_Merged_ConfigFile_Name", 1u, (LPBYTE)pData, 2 * v9 + 2);
  if ( v18 )
  {
    v19 = GetLastError();
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::SaveMergedConfigFileAndReg",
      L"SetPrinterData failed: dwStatus=%d, error=%d",
      (unsigned int)v18,
      v19);
    v20 = v18 < 0;
    if ( v18 > 0 )
    {
      v18 = (unsigned __int16)v18 | 0x80070000;
      v20 = v18 < 0;
    }
    if ( v20 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v18);
      throw (hr_error *)pExceptionObject;
    }
  }
  v21 = SetPrinterDataW(a2, (LPWSTR)L"V4_Merged_ConfigFile_CRC", 4u, v24, 4u);
  v22 = v21;
  if ( v21 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::SaveMergedConfigFileAndReg",
      L"SetPrinterData failed: dwStatus=%d",
      v21);
    v23 = v22 < 0;
    if ( v22 > 0 )
    {
      v22 = (unsigned __int16)v22 | 0x80070000;
      v23 = v22 < 0;
    }
    if ( v23 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v22);
      throw (hr_error *)pExceptionObject;
    }
  }
  std::wstring::~wstring((char **)lpNewFileName);
}

```

## disassembly

```asm
0x18004b544  push    rbp
0x18004b546  push    rbx
0x18004b547  push    rsi
0x18004b548  push    rdi
0x18004b549  push    r14
0x18004b54b  push    r15
0x18004b54d  lea     rbp, [rsp-2Fh]
0x18004b552  sub     rsp, 0D8h
0x18004b559  mov     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFEh
0x18004b561  mov     rax, cs:__security_cookie
0x18004b568  xor     rax, rsp
0x18004b56b  mov     [rbp+57h+var_38], rax
0x18004b56f  mov     r14, r8
0x18004b572  mov     rsi, rdx
0x18004b575  mov     rdi, rcx
0x18004b578  mov     dword ptr [rbp+57h+var_D0], r9d
0x18004b57c  xor     r15d, r15d
0x18004b57f  xorps   xmm0, xmm0
0x18004b582  movups  xmmword ptr [rbp+57h+pData], xmm0
0x18004b586  movups  xmmword ptr [rbp+57h+pData+0Ah], xmm0
0x18004b58a  movups  xmmword ptr [rbp+57h+lpNewFileName], xmm0
0x18004b58e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004b596  movdqu  [rbp+57h+var_88], xmm1
0x18004b59b  mov     word ptr [rbp+57h+lpNewFileName], r15w
0x18004b5a0  lea     rdx, aEnter_0; "Enter"
0x18004b5a7  lea     rcx, aPrintconfigCco_10; "PrintConfig::CConfigManager::SaveMerged"...
0x18004b5ae  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004b5b3  lea     rcx, aPpd; ".ppd"
0x18004b5ba  lea     rax, aGpd_0; ".gpd"
0x18004b5c1  cmp     [rdi+18h], r15d
0x18004b5c5  cmovz   rax, rcx
0x18004b5c9  mov     qword ptr [rsp+100h+cbData], rax
0x18004b5ce  mov     r9d, dword ptr [rbp+57h+var_D0]
0x18004b5d2  lea     r8, aXS; "%x%s"
0x18004b5d9  lea     edx, [r15+0Dh]; unsigned __int64
0x18004b5dd  lea     rcx, [rbp+57h+pData]; unsigned __int16 *
0x18004b5e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b5e6  test    eax, eax
0x18004b5e8  js      loc_18004B7EA
0x18004b5ee  xorps   xmm0, xmm0
0x18004b5f1  movups  [rbp+57h+Src], xmm0
0x18004b5f5  xorps   xmm1, xmm1
0x18004b5f8  movdqu  [rbp+57h+var_68], xmm1
0x18004b5fd  lea     rax, [rbp+57h+pData]
0x18004b601  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004b605  mov     r8, rbx
0x18004b608  inc     r8
0x18004b60b  cmp     [rax+r8*2], r15w
0x18004b610  jnz     short loc_18004B608
0x18004b612  lea     rdx, [rbp+57h+pData]
0x18004b616  lea     rcx, [rbp+57h+Src]
0x18004b61a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004b61f  nop
0x18004b620  lea     r8, [rdi+20h]
0x18004b624  mov     r9, [r8+10h]
0x18004b628  cmp     qword ptr [r8+18h], 7
0x18004b62d  jbe     short loc_18004B632
0x18004b62f  mov     r8, [r8]
0x18004b632  lea     rcx, [rbp+57h+Src]; Src
0x18004b636  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18004b63b  movups  xmm0, xmmword ptr [rax]
0x18004b63e  movups  [rbp+57h+pExceptionObject], xmm0
0x18004b642  movups  xmm1, xmmword ptr [rax+10h]
0x18004b646  movups  [rbp+57h+var_A8], xmm1
0x18004b64a  mov     [rax+10h], r15
0x18004b64e  mov     qword ptr [rax+18h], 7
0x18004b656  mov     [rax], r15w
0x18004b65a  lea     rdx, [rbp+57h+pExceptionObject]
0x18004b65e  lea     rcx, [rbp+57h+lpNewFileName]
0x18004b662  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004b667  lea     rcx, [rbp+57h+pExceptionObject]
0x18004b66b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b670  nop
0x18004b671  lea     rcx, [rbp+57h+Src]
0x18004b675  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b67a  lea     rdx, [rbp+57h+lpNewFileName]
0x18004b67e  cmp     qword ptr [rbp+57h+var_88+8], 7
0x18004b683  cmova   rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x18004b688  mov     r8d, 1; dwFlags
0x18004b68e  mov     rcx, r14; lpExistingFileName
0x18004b691  call    cs:__imp_MoveFileExW
0x18004b698  nop     dword ptr [rax+rax+00h]
0x18004b69d  mov     edi, 80070000h
0x18004b6a2  test    eax, eax
0x18004b6a4  jnz     short loc_18004B6E5
0x18004b6a6  call    cs:__imp_GetLastError
0x18004b6ad  nop     dword ptr [rax+rax+00h]
0x18004b6b2  mov     r8d, eax
0x18004b6b5  lea     rdx, aMovefileFailed; "MoveFile failed: error=%d"
0x18004b6bc  lea     rcx, aPrintconfigCco_10; "PrintConfig::CConfigManager::SaveMerged"...
0x18004b6c3  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b6c8  call    cs:__imp_GetLastError
0x18004b6cf  nop     dword ptr [rax+rax+00h]
0x18004b6d4  test    eax, eax
0x18004b6d6  jle     short loc_18004B6DF
0x18004b6d8  movzx   eax, ax
0x18004b6db  or      eax, edi
0x18004b6dd  test    eax, eax
0x18004b6df  js      loc_18004B806
0x18004b6e5  lea     rax, [rbp+57h+pData]
0x18004b6e9  inc     rbx
0x18004b6ec  cmp     [rax+rbx*2], r15w
0x18004b6f1  jnz     short loc_18004B6E9
0x18004b6f3  lea     eax, ds:2[rbx*2]
0x18004b6fa  mov     [rsp+100h+cbData], eax; cbData
0x18004b6fe  lea     r9, [rbp+57h+pData]; pData
0x18004b702  mov     r8d, 1; Type
0x18004b708  lea     rdx, aV4MergedConfig_0; "V4_Merged_ConfigFile_Name"
0x18004b70f  mov     rcx, rsi; hPrinter
0x18004b712  call    cs:__imp_SetPrinterDataW
0x18004b719  nop     dword ptr [rax+rax+00h]
0x18004b71e  mov     ebx, eax
0x18004b720  test    eax, eax
0x18004b722  jz      short loc_18004B75A
0x18004b724  call    cs:__imp_GetLastError
0x18004b72b  nop     dword ptr [rax+rax+00h]
0x18004b730  mov     r9d, eax
0x18004b733  mov     r8d, ebx
0x18004b736  lea     rdx, aSetprinterdata_3; "SetPrinterData failed: dwStatus=%d, err"...
0x18004b73d  lea     rcx, aPrintconfigCco_10; "PrintConfig::CConfigManager::SaveMerged"...
0x18004b744  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b749  test    ebx, ebx
0x18004b74b  jle     short loc_18004B754
0x18004b74d  movzx   ebx, bx
0x18004b750  or      ebx, edi
0x18004b752  test    ebx, ebx
0x18004b754  js      loc_18004B822
0x18004b75a  mov     r8d, 4; Type
0x18004b760  mov     [rsp+100h+cbData], r8d; cbData
0x18004b765  lea     r9, [rbp+57h+var_D0]; pData
0x18004b769  lea     rdx, aV4MergedConfig; "V4_Merged_ConfigFile_CRC"
0x18004b770  mov     rcx, rsi; hPrinter
0x18004b773  call    cs:__imp_SetPrinterDataW
0x18004b77a  nop     dword ptr [rax+rax+00h]
0x18004b77f  mov     ebx, eax
0x18004b781  test    eax, eax
0x18004b783  jz      short loc_18004B7A8
0x18004b785  mov     r8d, eax
0x18004b788  lea     rdx, aSetprinterdata_5; "SetPrinterData failed: dwStatus=%d"
0x18004b78f  lea     rcx, aPrintconfigCco_10; "PrintConfig::CConfigManager::SaveMerged"...
0x18004b796  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b79b  test    ebx, ebx
0x18004b79d  jle     short loc_18004B7A6
0x18004b79f  movzx   ebx, bx
0x18004b7a2  or      ebx, edi
0x18004b7a4  test    ebx, ebx
0x18004b7a6  js      short loc_18004B7CE
0x18004b7a8  lea     rcx, [rbp+57h+lpNewFileName]
0x18004b7ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b7b1  mov     rcx, [rbp+57h+var_38]
0x18004b7b5  xor     rcx, rsp; StackCookie
0x18004b7b8  call    __security_check_cookie
0x18004b7bd  add     rsp, 0D8h
0x18004b7c4  pop     r15
0x18004b7c6  pop     r14
0x18004b7c8  pop     rdi
0x18004b7c9  pop     rsi
0x18004b7ca  pop     rbx
0x18004b7cb  pop     rbp
0x18004b7cc  retn
0x18004b7ce  mov     edx, ebx; int
0x18004b7d0  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004b7d4  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b7d9  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b7e0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004b7e4  call    _CxxThrowException_0
0x18004b7ea  mov     edx, eax; int
0x18004b7ec  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004b7f0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b7f5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b7fc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004b800  call    _CxxThrowException_0
0x18004b806  mov     edx, eax; int
0x18004b808  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004b80c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b811  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b818  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004b81c  call    _CxxThrowException_0
0x18004b822  mov     edx, ebx; int
0x18004b824  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004b828  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b82d  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b834  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004b838  call    _CxxThrowException_0
```
