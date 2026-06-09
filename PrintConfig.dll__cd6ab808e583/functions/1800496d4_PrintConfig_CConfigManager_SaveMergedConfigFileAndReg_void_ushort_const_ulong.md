# PrintConfig::CConfigManager::SaveMergedConfigFileAndReg(void *,ushort const *,ulong)

- ea: `0x1800496d4`
- end: `0x1800499a9`
- name: `?SaveMergedConfigFileAndReg@CConfigManager@PrintConfig@@AEAAXPEAXPEBGK@Z`
- size: `725`
- prototype: `void(PrintConfig::CConfigManager *__hidden this, void *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18004b448`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000bed0`
- `0x18000da28`
- `0x18000f380`
- `0x18000f590`
- `0x18000fb88`
- `0x1800183a0`
- `0x1800183f8`
- `0x18003b314`
- `0x1800496d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180049830`
- `KERNEL32!GetLastError` at `0x18004984c`
- `KERNEL32!GetLastError` at `0x18004989c`
- `KERNEL32!GetLastError` at `0x180049830`
- `KERNEL32!GetLastError` at `0x18004984c`
- `KERNEL32!GetLastError` at `0x18004989c`
- `KERNEL32!MoveFileExW` at `0x180049821`
- `KERNEL32!MoveFileExW` at `0x180049821`
- `WINSPOOL!SetPrinterDataW` at `0x180049890`
- `WINSPOOL!SetPrinterDataW` at `0x1800498e5`
- `WINSPOOL!SetPrinterDataW` at `0x180049890`
- `WINSPOOL!SetPrinterDataW` at `0x1800498e5`

## string_xrefs

- `0x180049737`: `PrintConfig::CConfigManager::SaveMergedConfigFileAndReg`
- `0x180049840`: `PrintConfig::CConfigManager::SaveMergedConfigFileAndReg`
- `0x1800498af`: `PrintConfig::CConfigManager::SaveMergedConfigFileAndReg`
- `0x1800498fb`: `PrintConfig::CConfigManager::SaveMergedConfigFileAndReg`
- `0x1800498db`: `V4_Merged_ConfigFile_CRC`
- `0x180049886`: `V4_Merged_ConfigFile_Name`
- `0x180049839`: `MoveFile failed: error=%d`

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
  __int64 v11; // rax
  const WCHAR *v12; // rdx
  DWORD LastError; // eax
  signed int v14; // eax
  bool v15; // sf
  signed int v16; // ebx
  DWORD v17; // eax
  bool v18; // sf
  DWORD v19; // eax
  signed int v20; // ebx
  bool v21; // sf
  BYTE v22[4]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v23; // [rsp+40h] [rbp-69h]
  _OWORD pExceptionObject[2]; // [rsp+48h] [rbp-61h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+68h] [rbp-41h] BYREF
  __m128i si128; // [rsp+78h] [rbp-31h]
  _OWORD Src[2]; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int16 pData[16]; // [rsp+A8h] [rbp-1h] BYREF

  v23 = -2;
  *(_DWORD *)v22 = a4;
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
  v8 = StringCchPrintfW(pData, 0xDu, L"%x%s", *(unsigned int *)v22, v7);
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
  std::wstring::_Construct<1,unsigned short const *>((char **)Src, pData, v10);
  v11 = std::wstring::_Insert<unsigned short>(Src);
  pExceptionObject[0] = *(_OWORD *)v11;
  pExceptionObject[1] = *(_OWORD *)(v11 + 16);
  *(_QWORD *)(v11 + 16) = 0;
  *(_QWORD *)(v11 + 24) = 7;
  *(_WORD *)v11 = 0;
  std::wstring::operator=(lpNewFileName, pExceptionObject);
  std::wstring::~wstring(pExceptionObject);
  std::wstring::~wstring(Src);
  v12 = (const WCHAR *)lpNewFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v12 = lpNewFileName[0];
  if ( !MoveFileExW(a3, v12, 1u) )
  {
    LastError = GetLastError();
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::SaveMergedConfigFileAndReg",
      L"MoveFile failed: error=%d",
      LastError);
    v14 = GetLastError();
    v15 = v14 < 0;
    if ( v14 > 0 )
    {
      v14 = (unsigned __int16)v14 | 0x80070000;
      v15 = v14 < 0;
    }
    if ( v15 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v14);
      throw (hr_error *)pExceptionObject;
    }
  }
  do
    ++v9;
  while ( pData[v9] );
  v16 = SetPrinterDataW(a2, (LPWSTR)L"V4_Merged_ConfigFile_Name", 1u, (LPBYTE)pData, 2 * v9 + 2);
  if ( v16 )
  {
    v17 = GetLastError();
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::SaveMergedConfigFileAndReg",
      L"SetPrinterData failed: dwStatus=%d, error=%d",
      (unsigned int)v16,
      v17);
    v18 = v16 < 0;
    if ( v16 > 0 )
    {
      v16 = (unsigned __int16)v16 | 0x80070000;
      v18 = v16 < 0;
    }
    if ( v18 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v16);
      throw (hr_error *)pExceptionObject;
    }
  }
  v19 = SetPrinterDataW(a2, (LPWSTR)L"V4_Merged_ConfigFile_CRC", 4u, v22, 4u);
  v20 = v19;
  if ( v19 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::SaveMergedConfigFileAndReg",
      L"SetPrinterData failed: dwStatus=%d",
      v19);
    v21 = v20 < 0;
    if ( v20 > 0 )
    {
      v20 = (unsigned __int16)v20 | 0x80070000;
      v21 = v20 < 0;
    }
    if ( v21 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v20);
      throw (hr_error *)pExceptionObject;
    }
  }
  std::wstring::~wstring(lpNewFileName);
}

```

## disassembly

```asm
0x1800496d4  push    rbp
0x1800496d6  push    rbx
0x1800496d7  push    rsi
0x1800496d8  push    rdi
0x1800496d9  push    r14
0x1800496db  push    r15
0x1800496dd  lea     rbp, [rsp-2Fh]
0x1800496e2  sub     rsp, 0D8h
0x1800496e9  mov     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFEh
0x1800496f1  mov     rax, cs:__security_cookie
0x1800496f8  xor     rax, rsp
0x1800496fb  mov     [rbp+57h+var_38], rax
0x1800496ff  mov     r14, r8
0x180049702  mov     rsi, rdx
0x180049705  mov     rdi, rcx
0x180049708  mov     dword ptr [rbp+57h+var_D0], r9d
0x18004970c  xor     r15d, r15d
0x18004970f  xorps   xmm0, xmm0
0x180049712  movups  xmmword ptr [rbp+57h+pData], xmm0
0x180049716  movups  xmmword ptr [rbp+57h+pData+0Ah], xmm0
0x18004971a  movups  xmmword ptr [rbp+57h+lpNewFileName], xmm0
0x18004971e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180049726  movdqu  [rbp+57h+var_88], xmm1
0x18004972b  mov     word ptr [rbp+57h+lpNewFileName], r15w
0x180049730  lea     rdx, aEnter_0; "Enter"
0x180049737  lea     rcx, aPrintconfigCco_10; "PrintConfig::CConfigManager::SaveMerged"...
0x18004973e  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180049743  lea     rcx, aPpd; ".ppd"
0x18004974a  lea     rax, aGpd_0; ".gpd"
0x180049751  cmp     [rdi+18h], r15d
0x180049755  cmovz   rax, rcx
0x180049759  mov     qword ptr [rsp+100h+cbData], rax
0x18004975e  mov     r9d, dword ptr [rbp+57h+var_D0]
0x180049762  lea     r8, aXS; "%x%s"
0x180049769  lea     edx, [r15+0Dh]; unsigned __int64
0x18004976d  lea     rcx, [rbp+57h+pData]; unsigned __int16 *
0x180049771  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180049776  test    eax, eax
0x180049778  js      loc_180049955
0x18004977e  xorps   xmm0, xmm0
0x180049781  movups  [rbp+57h+Src], xmm0
0x180049785  xorps   xmm1, xmm1
0x180049788  movdqu  [rbp+57h+var_68], xmm1
0x18004978d  lea     rax, [rbp+57h+pData]
0x180049791  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180049795  mov     r8, rbx
0x180049798  inc     r8
0x18004979b  cmp     [rax+r8*2], r15w
0x1800497a0  jnz     short loc_180049798
0x1800497a2  lea     rdx, [rbp+57h+pData]
0x1800497a6  lea     rcx, [rbp+57h+Src]
0x1800497aa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800497af  nop
0x1800497b0  lea     r8, [rdi+20h]
0x1800497b4  mov     r9, [r8+10h]
0x1800497b8  cmp     qword ptr [r8+18h], 7
0x1800497bd  jbe     short loc_1800497C2
0x1800497bf  mov     r8, [r8]
0x1800497c2  lea     rcx, [rbp+57h+Src]; Src
0x1800497c6  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x1800497cb  movups  xmm0, xmmword ptr [rax]
0x1800497ce  movups  [rbp+57h+pExceptionObject], xmm0
0x1800497d2  movups  xmm1, xmmword ptr [rax+10h]
0x1800497d6  movups  [rbp+57h+var_A8], xmm1
0x1800497da  mov     [rax+10h], r15
0x1800497de  mov     qword ptr [rax+18h], 7
0x1800497e6  mov     [rax], r15w
0x1800497ea  lea     rdx, [rbp+57h+pExceptionObject]
0x1800497ee  lea     rcx, [rbp+57h+lpNewFileName]
0x1800497f2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800497f7  lea     rcx, [rbp+57h+pExceptionObject]
0x1800497fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049800  nop
0x180049801  lea     rcx, [rbp+57h+Src]
0x180049805  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004980a  lea     rdx, [rbp+57h+lpNewFileName]
0x18004980e  cmp     qword ptr [rbp+57h+var_88+8], 7
0x180049813  cmova   rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x180049818  mov     r8d, 1; dwFlags
0x18004981e  mov     rcx, r14; lpExistingFileName
0x180049821  call    cs:__imp_MoveFileExW
0x180049827  mov     edi, 80070000h
0x18004982c  test    eax, eax
0x18004982e  jnz     short loc_180049863
0x180049830  call    cs:__imp_GetLastError
0x180049836  mov     r8d, eax
0x180049839  lea     rdx, aMovefileFailed; "MoveFile failed: error=%d"
0x180049840  lea     rcx, aPrintconfigCco_10; "PrintConfig::CConfigManager::SaveMerged"...
0x180049847  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004984c  call    cs:__imp_GetLastError
0x180049852  test    eax, eax
0x180049854  jle     short loc_18004985D
0x180049856  movzx   eax, ax
0x180049859  or      eax, edi
0x18004985b  test    eax, eax
0x18004985d  js      loc_180049971
0x180049863  lea     rax, [rbp+57h+pData]
0x180049867  inc     rbx
0x18004986a  cmp     [rax+rbx*2], r15w
0x18004986f  jnz     short loc_180049867
0x180049871  lea     eax, ds:2[rbx*2]
0x180049878  mov     [rsp+100h+cbData], eax; cbData
0x18004987c  lea     r9, [rbp+57h+pData]; pData
0x180049880  mov     r8d, 1; Type
0x180049886  lea     rdx, aV4MergedConfig_0; "V4_Merged_ConfigFile_Name"
0x18004988d  mov     rcx, rsi; hPrinter
0x180049890  call    cs:__imp_SetPrinterDataW
0x180049896  mov     ebx, eax
0x180049898  test    eax, eax
0x18004989a  jz      short loc_1800498CC
0x18004989c  call    cs:__imp_GetLastError
0x1800498a2  mov     r9d, eax
0x1800498a5  mov     r8d, ebx
0x1800498a8  lea     rdx, aSetprinterdata_3; "SetPrinterData failed: dwStatus=%d, err"...
0x1800498af  lea     rcx, aPrintconfigCco_10; "PrintConfig::CConfigManager::SaveMerged"...
0x1800498b6  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800498bb  test    ebx, ebx
0x1800498bd  jle     short loc_1800498C6
0x1800498bf  movzx   ebx, bx
0x1800498c2  or      ebx, edi
0x1800498c4  test    ebx, ebx
0x1800498c6  js      loc_18004998D
0x1800498cc  mov     r8d, 4; Type
0x1800498d2  mov     [rsp+100h+cbData], r8d; cbData
0x1800498d7  lea     r9, [rbp+57h+var_D0]; pData
0x1800498db  lea     rdx, aV4MergedConfig; "V4_Merged_ConfigFile_CRC"
0x1800498e2  mov     rcx, rsi; hPrinter
0x1800498e5  call    cs:__imp_SetPrinterDataW
0x1800498eb  mov     ebx, eax
0x1800498ed  test    eax, eax
0x1800498ef  jz      short loc_180049914
0x1800498f1  mov     r8d, eax
0x1800498f4  lea     rdx, aSetprinterdata_5; "SetPrinterData failed: dwStatus=%d"
0x1800498fb  lea     rcx, aPrintconfigCco_10; "PrintConfig::CConfigManager::SaveMerged"...
0x180049902  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180049907  test    ebx, ebx
0x180049909  jle     short loc_180049912
0x18004990b  movzx   ebx, bx
0x18004990e  or      ebx, edi
0x180049910  test    ebx, ebx
0x180049912  js      short loc_180049939
0x180049914  lea     rcx, [rbp+57h+lpNewFileName]
0x180049918  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004991d  mov     rcx, [rbp+57h+var_38]
0x180049921  xor     rcx, rsp; StackCookie
0x180049924  call    __security_check_cookie
0x180049929  add     rsp, 0D8h
0x180049930  pop     r15
0x180049932  pop     r14
0x180049934  pop     rdi
0x180049935  pop     rsi
0x180049936  pop     rbx
0x180049937  pop     rbp
0x180049938  retn
0x180049939  mov     edx, ebx; int
0x18004993b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004993f  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180049944  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004994b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004994f  call    _CxxThrowException_0
0x180049955  mov     edx, eax; int
0x180049957  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004995b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180049960  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180049967  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004996b  call    _CxxThrowException_0
0x180049971  mov     edx, eax; int
0x180049973  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180049977  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004997c  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180049983  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180049987  call    _CxxThrowException_0
0x18004998d  mov     edx, ebx; int
0x18004998f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180049993  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180049998  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004999f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800499a3  call    _CxxThrowException_0
```
