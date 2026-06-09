# PrintConfig::CConfigManager::Initialize(void)

- ea: `0x180045828`
- end: `0x180045d2b`
- name: `?Initialize@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `1283`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this)`
- caller_count: `3`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x18001053c`
- `0x18001aecc`
- `0x18001b6d0`

## callees

- `0x1800032e0`
- `0x1800042c8`
- `0x180004424`
- `0x18000da28`
- `0x18000f380`
- `0x18000f590`
- `0x18000f6a0`
- `0x18000fb88`
- `0x180014a48`
- `0x1800183f8`
- `0x18001878c`
- `0x180018848`
- `0x180018b44`
- `0x18001be3c`
- `0x18002c8b4`
- `0x180033670`
- `0x180045828`
- `0x18004759c`
- `0x180150b80`
- `0x180151584`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b77`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b90`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b77`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045b90`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180045ba5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180045ba5`
- `KERNEL32!GetLastError` at `0x180045ce1`
- `KERNEL32!GetLastError` at `0x180045ce1`
- `OLEAUT32!__imp_SysFreeString` at `0x180045873`
- `OLEAUT32!__imp_SysFreeString` at `0x180045873`
- `WINSPOOL!GetPrinterDataW` at `0x180045938`
- `WINSPOOL!GetPrinterDataW` at `0x180045938`
- `WINSPOOL!ClosePrinter` at `0x180045a53`
- `WINSPOOL!ClosePrinter` at `0x180045a53`
- `WINSPOOL!OpenPrinterW` at `0x180045a67`
- `WINSPOOL!OpenPrinterW` at `0x180045a67`

## string_xrefs

- `0x18004592d`: `PrintQueueV4DriverDirectory`
- `0x1800458de`: `PrintConfig::CConfigManager::Initialize`
- `0x180045bb7`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x180045cfd`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x180045cea`: `OpenPrinter for admin handle failed: %d`
- `0x180045ac1`: `application/vnd.ms-PrintDeviceCapabilities+xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrintConfig::CConfigManager::Initialize(BSTR *this)
{
  BSTR v2; // rdi
  __int64 (__fastcall *v3)(BSTR, LPWSTR *); // rbx
  LPWSTR *v4; // r12
  int v5; // eax
  int v6; // eax
  int v7; // eax
  DWORD v8; // eax
  int v9; // r14d
  int v10; // edi
  int v11; // ecx
  BYTE *v12; // r9
  DWORD PrinterDataW; // eax
  signed int v14; // ebx
  bool v15; // sf
  unsigned __int64 v16; // r8
  char *v17; // rbx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  char *v20; // rax
  void **v21; // r14
  BSTR v22; // rcx
  int LocalPrintConfigData; // eax
  struct _DRIVER_INFO_8W **v24; // r8
  BSTR v25; // rcx
  _QWORD *v26; // rbx
  __int64 v27; // rax
  const wchar_t *v28; // rdx
  bool v29; // al
  __int64 v30; // rax
  const wchar_t *v31; // rdx
  bool v32; // al
  __int64 v33; // rax
  const wchar_t *v34; // rdx
  bool v35; // al
  void *v36; // rcx
  int DriverInfo; // r14d
  void *v38; // r15
  __int64 v39; // rbx
  _DWORD *v40; // rax
  Print::Driver::Telemetry::PrintConfigTelemetry *v41; // rcx
  DWORD LastError; // eax
  const char *v43; // r9
  DWORD nSize; // [rsp+20h] [rbp-79h]
  DWORD pcbNeeded; // [rsp+30h] [rbp-69h] BYREF
  DWORD pType; // [rsp+34h] [rbp-65h] BYREF
  void *Block; // [rsp+38h] [rbp-61h] BYREF
  HANDLE hPrinter; // [rsp+40h] [rbp-59h] BYREF
  LPBYTE pData[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v50; // [rsp+58h] [rbp-41h]
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+60h] [rbp-39h] BYREF
  __int64 v52; // [rsp+78h] [rbp-21h]
  _OWORD pExceptionObject[2]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v52 = -2;
  hPrinter = 0;
  v2 = *this;
  v3 = *(__int64 (__fastcall **)(BSTR, LPWSTR *))(*(_QWORD *)*this + 64LL);
  v4 = this + 2;
  SysFreeString(this[2]);
  *v4 = 0;
  v5 = v3(v2, v4);
  if ( v5 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v5);
    throw (hr_error *)pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(BSTR, HANDLE *))(*(_QWORD *)*this + 56LL))(*this, &hPrinter);
  if ( v6 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v6);
    throw (hr_error *)pExceptionObject;
  }
  v7 = IsDriverGPDBased(hPrinter, this + 3);
  if ( v7 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v7);
    throw (hr_error *)pExceptionObject;
  }
  *(_OWORD *)pData = 0;
  v50 = 0;
  pType = 0;
  v8 = 520;
  pcbNeeded = 520;
  v9 = 0;
  v10 = 1;
  while ( 1 )
  {
    if ( v9 == 2 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, -2147418113);
      throw (hr_error *)pExceptionObject;
    }
    v11 = (int)pData[1];
    v12 = pData[0];
    if ( (LPBYTE)(pData[1] - pData[0]) < (LPBYTE)v8 )
    {
      std::vector<unsigned char>::resize(pData, v8);
      v11 = (int)pData[1];
      v12 = pData[0];
    }
    PrinterDataW = GetPrinterDataW(
                     hPrinter,
                     (LPWSTR)L"PrintQueueV4DriverDirectory",
                     &pType,
                     v12,
                     v11 - (_DWORD)v12,
                     &pcbNeeded);
    v14 = PrinterDataW;
    if ( !PrinterDataW )
      break;
    if ( PrinterDataW != 234 )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "PrintConfig::CConfigManager::Initialize",
        L"GetPrinterData failed: dwRet=%d",
        PrinterDataW);
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
    if ( ++v9 > 2 )
      goto LABEL_18;
    v8 = pcbNeeded;
  }
  if ( pType != 1 || !pcbNeeded || (pcbNeeded & 1) != 0 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::Initialize",
      L"GetPrinterData result data unexpected");
    hr_error::hr_error((hr_error *)pExceptionObject, -2147418113);
    throw (hr_error *)pExceptionObject;
  }
LABEL_18:
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)&pData[0][2 * v16] );
  std::wstring::_Construct<1,unsigned short const *>((char **)pExceptionObject, pData[0], v16);
  v17 = (char *)(this + 4);
  std::wstring::operator=(this + 4, pExceptionObject);
  std::wstring::~wstring(pExceptionObject);
  v18 = (unsigned __int64)this[6];
  if ( !v18 )
    std::_String_val<std::_Simple_types<char>>::_Xran();
  v19 = (unsigned __int64)this[7];
  if ( v19 <= 7 )
    v20 = (char *)(this + 4);
  else
    v20 = *(char **)v17;
  if ( *(_WORD *)&v20[2 * v18 - 2] != 92 )
  {
    if ( v18 >= v19 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(this + 4);
    }
    else
    {
      this[6] = (BSTR)(v18 + 1);
      if ( v19 > 7 )
        v17 = *(char **)v17;
      *(_DWORD *)&v17[2 * v18] = 92;
    }
  }
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v21 = (void **)(this + 8);
  v22 = this[8];
  if ( v22 )
  {
    ClosePrinter(v22);
    *v21 = 0;
  }
  if ( !OpenPrinterW(*v4, (LPHANDLE)this + 8, &pDefault) )
  {
    LastError = GetLastError();
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::Initialize",
      L"OpenPrinter for admin handle failed: %d",
      LastError);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x9D,
      (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
      v43);
  }
  Block = 0;
  LocalPrintConfigData = LocalPrintConfigData::CreateLocalPrintConfigData(*v21, (struct LocalPrintConfigData **)&Block);
  if ( LocalPrintConfigData < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, LocalPrintConfigData);
    throw (hr_error *)pExceptionObject;
  }
  v25 = this[9];
  v26 = Block;
  this[9] = (BSTR)Block;
  if ( v25 )
    (*(void (__fastcall **)(BSTR, __int64))(*(_QWORD *)v25 + 32LL))(v25, 1);
  v27 = v26[12];
  v29 = v27
     && (v28 = *(const wchar_t **)(v27 + 136)) != 0
     && wcsicmp(L"application/vnd.ms-PrintDeviceCapabilities+xml", v28) == 0;
  *((_BYTE *)this + 28) = v29;
  v30 = v26[12];
  v32 = v30 && (v31 = *(const wchar_t **)(v30 + 144)) != 0 && wcsicmp(L"true", v31) == 0;
  *((_BYTE *)this + 29) = v32;
  v33 = v26[12];
  v35 = v33 && (v34 = *(const wchar_t **)(v33 + 152)) != 0 && wcsicmp(L"true", v34) == 0;
  *((_BYTE *)this + 30) = v35;
  v36 = *v21;
  *((_DWORD *)this + 30) = 0;
  Block = 0;
  DriverInfo = PrintCore::GetDriverInfo(v36, &Block, v24);
  if ( DriverInfo >= 0 )
  {
    v38 = Block;
    v39 = *((_QWORD *)Block + 15);
    if ( (unsigned int)_o__wcsicmp(v39, L"{B71661F4-A4DC-43DF-BC16-39D337D15A95}") )
    {
      if ( (unsigned int)_o__wcsicmp(v39, L"{6D170653-5280-44C2-BA44-2C04BC9D46DA}") )
        v10 = (unsigned int)_o__wcsicmp(v39, L"{C1F56D94-A46F-492E-A129-7F54D1EE2356}") == 0 ? 3 : 0;
      else
        v10 = 2;
    }
    *((_DWORD *)this + 30) = v10;
    free(v38);
  }
  if ( DriverInfo < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
      (const char *)(unsigned int)DriverInfo,
      nSize);
  v40 = (_DWORD *)*((_QWORD *)Print::Driver::Telemetry::PrintConfigTelemetry::Instance() + 1);
  if ( v40 && *v40 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::Instance();
    Print::Driver::Telemetry::PrintConfigTelemetry::PrinterPDCUse_(
      v41,
      *v4,
      *((unsigned __int8 *)this + 28),
      *((unsigned __int8 *)this + 29));
  }
  std::vector<char>::~vector<char>(pData);
}

```

## disassembly

```asm
0x180045828  push    rbp
0x18004582a  push    rbx
0x18004582b  push    rsi
0x18004582c  push    rdi
0x18004582d  push    r12
0x18004582f  push    r13
0x180045831  push    r14
0x180045833  push    r15
0x180045835  lea     rbp, [rsp-1Fh]
0x18004583a  sub     rsp, 0B8h
0x180045841  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x180045849  mov     rax, cs:__security_cookie
0x180045850  xor     rax, rsp
0x180045853  mov     [rbp+57h+var_50], rax
0x180045857  mov     rsi, rcx
0x18004585a  xor     r13d, r13d
0x18004585d  mov     [rbp+57h+hPrinter], r13
0x180045861  mov     rdi, [rcx]
0x180045864  mov     rax, [rdi]
0x180045867  mov     rbx, [rax+40h]
0x18004586b  lea     r12, [rcx+10h]
0x18004586f  mov     rcx, [r12]; bstrString
0x180045873  call    cs:__imp_SysFreeString
0x180045879  mov     [r12], r13
0x18004587d  mov     rdx, r12
0x180045880  mov     rcx, rdi
0x180045883  mov     rax, rbx
0x180045886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004588b  test    eax, eax
0x18004588d  js      loc_180045C6B
0x180045893  mov     rcx, [rsi]
0x180045896  mov     rax, [rcx]
0x180045899  lea     rdx, [rbp+57h+hPrinter]
0x18004589d  mov     rax, [rax+38h]
0x1800458a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458a6  test    eax, eax
0x1800458a8  js      loc_180045C87
0x1800458ae  lea     rdx, [rsi+18h]
0x1800458b2  mov     rcx, [rbp+57h+hPrinter]
0x1800458b6  call    IsDriverGPDBased
0x1800458bb  test    eax, eax
0x1800458bd  js      loc_180045CA3
0x1800458c3  xorps   xmm0, xmm0
0x1800458c6  movdqu  xmmword ptr [rbp+57h+pData], xmm0
0x1800458cb  mov     [rbp+57h+var_98], r13
0x1800458cf  mov     [rbp+57h+pType], r13d
0x1800458d3  mov     eax, 208h
0x1800458d8  mov     [rbp+57h+var_C0], eax
0x1800458db  mov     r14d, r13d
0x1800458de  lea     r15, aPrintconfigCco_9; "PrintConfig::CConfigManager::Initialize"
0x1800458e5  lea     edi, [r13+1]
0x1800458e9  cmp     r14d, 2
0x1800458ed  jz      loc_180045C4C
0x1800458f3  mov     edx, eax
0x1800458f5  mov     rcx, [rbp+57h+pData+8]
0x1800458f9  mov     rax, rcx
0x1800458fc  mov     r9, [rbp+57h+pData]
0x180045900  sub     rax, r9
0x180045903  cmp     rax, rdx
0x180045906  jnb     short loc_180045919
0x180045908  lea     rcx, [rbp+57h+pData]
0x18004590c  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180045911  mov     rcx, [rbp+57h+pData+8]
0x180045915  mov     r9, [rbp+57h+pData]; pData
0x180045919  sub     ecx, r9d
0x18004591c  lea     rax, [rbp+57h+var_C0]
0x180045920  mov     [rsp+0F0h+pcbNeeded], rax; pcbNeeded
0x180045925  mov     [rsp+0F0h+nSize], ecx; int
0x180045929  lea     r8, [rbp+57h+pType]; pType
0x18004592d  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x180045934  mov     rcx, [rbp+57h+hPrinter]; hPrinter
0x180045938  call    cs:__imp_GetPrinterDataW
0x18004593e  mov     ebx, eax
0x180045940  test    eax, eax
0x180045942  jz      short loc_180045983
0x180045944  cmp     eax, 0EAh
0x180045949  jz      short loc_180045972
0x18004594b  mov     r8d, eax
0x18004594e  lea     rdx, aGetprinterdata_6; "GetPrinterData failed: dwRet=%d"
0x180045955  mov     rcx, r15; char *
0x180045958  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004595d  test    ebx, ebx
0x18004595f  jle     short loc_18004596C
0x180045961  movzx   ebx, bx
0x180045964  or      ebx, 80070000h
0x18004596a  test    ebx, ebx
0x18004596c  js      loc_180045CBF
0x180045972  add     r14d, edi
0x180045975  cmp     r14d, 2
0x180045979  jg      short loc_1800459A0
0x18004597b  mov     eax, [rbp+57h+var_C0]
0x18004597e  jmp     loc_1800458E9
0x180045983  cmp     [rbp+57h+pType], edi
0x180045986  jnz     loc_180045C1E
0x18004598c  mov     eax, [rbp+57h+var_C0]
0x18004598f  test    eax, eax
0x180045991  jz      loc_180045C1E
0x180045997  test    dil, al
0x18004599a  jnz     loc_180045C1E
0x1800459a0  mov     rdx, [rbp+57h+pData]
0x1800459a4  xorps   xmm0, xmm0
0x1800459a7  movups  [rbp+57h+pExceptionObject], xmm0
0x1800459ab  xorps   xmm1, xmm1
0x1800459ae  movdqu  [rbp+57h+var_60], xmm1
0x1800459b3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800459b7  inc     r8
0x1800459ba  cmp     [rdx+r8*2], r13w
0x1800459bf  jnz     short loc_1800459B7
0x1800459c1  lea     rcx, [rbp+57h+pExceptionObject]
0x1800459c5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800459ca  lea     rbx, [rsi+20h]
0x1800459ce  lea     rdx, [rbp+57h+pExceptionObject]
0x1800459d2  mov     rcx, rbx
0x1800459d5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800459da  lea     rcx, [rbp+57h+pExceptionObject]
0x1800459de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800459e3  mov     rcx, [rsi+30h]
0x1800459e7  lea     r8, [rcx-1]
0x1800459eb  cmp     rcx, r8
0x1800459ee  jbe     loc_180045CDB
0x1800459f4  mov     rdx, [rbx+18h]
0x1800459f8  cmp     rdx, 7
0x1800459fc  jbe     short loc_180045A03
0x1800459fe  mov     rax, [rbx]
0x180045a01  jmp     short loc_180045A06
0x180045a03  mov     rax, rbx
0x180045a06  mov     r9d, 5Ch ; '\'
0x180045a0c  cmp     [rax+r8*2], r9w
0x180045a11  jz      short loc_180045A37
0x180045a13  cmp     rcx, rdx
0x180045a16  jnb     short loc_180045A2F
0x180045a18  lea     rax, [rcx+1]
0x180045a1c  mov     [rbx+10h], rax
0x180045a20  cmp     rdx, 7
0x180045a24  jbe     short loc_180045A29
0x180045a26  mov     rbx, [rbx]
0x180045a29  mov     [rbx+rcx*2], r9d
0x180045a2d  jmp     short loc_180045A37
0x180045a2f  mov     rcx, rbx; Src
0x180045a32  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180045a37  xorps   xmm0, xmm0
0x180045a3a  movdqu  xmmword ptr [rbp+57h+pDefault.pDatatype], xmm0
0x180045a3f  mov     qword ptr [rbp+57h+pDefault.DesiredAccess], 0F000Ch
0x180045a47  lea     r14, [rsi+40h]
0x180045a4b  mov     rcx, [r14]; hPrinter
0x180045a4e  test    rcx, rcx
0x180045a51  jz      short loc_180045A5C
0x180045a53  call    cs:__imp_ClosePrinter
0x180045a59  mov     [r14], r13
0x180045a5c  lea     r8, [rbp+57h+pDefault]; pDefault
0x180045a60  mov     rdx, r14; phPrinter
0x180045a63  mov     rcx, [r12]; pPrinterName
0x180045a67  call    cs:__imp_OpenPrinterW
0x180045a6d  test    eax, eax
0x180045a6f  jz      loc_180045CE1
0x180045a75  mov     [rbp+57h+Block], r13
0x180045a79  lea     rdx, [rbp+57h+Block]; struct LocalPrintConfigData **
0x180045a7d  mov     rcx, [r14]; void *
0x180045a80  call    ?CreateLocalPrintConfigData@LocalPrintConfigData@@SAJPEAXPEAPEAV1@@Z; LocalPrintConfigData::CreateLocalPrintConfigData(void *,LocalPrintConfigData * *)
0x180045a85  test    eax, eax
0x180045a87  js      loc_180045D0F
0x180045a8d  mov     rcx, [rsi+48h]
0x180045a91  mov     rbx, [rbp+57h+Block]
0x180045a95  mov     [rsi+48h], rbx
0x180045a99  test    rcx, rcx
0x180045a9c  jz      short loc_180045AAC
0x180045a9e  mov     rax, [rcx]
0x180045aa1  mov     edx, edi
0x180045aa3  mov     rax, [rax+20h]
0x180045aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045aac  mov     rax, [rbx+60h]
0x180045ab0  test    rax, rax
0x180045ab3  jz      short loc_180045AD4
0x180045ab5  mov     rdx, [rax+88h]; String2
0x180045abc  test    rdx, rdx
0x180045abf  jz      short loc_180045AD4
0x180045ac1  lea     rcx, aApplicationVnd; "application/vnd.ms-PrintDeviceCapabilit"...
0x180045ac8  call    _wcsicmp
0x180045acd  test    eax, eax
0x180045acf  setz    al
0x180045ad2  jmp     short loc_180045AD7
0x180045ad4  mov     al, r13b
0x180045ad7  mov     [rsi+1Ch], al
0x180045ada  mov     rax, [rbx+60h]
0x180045ade  test    rax, rax
0x180045ae1  jz      short loc_180045B02
0x180045ae3  mov     rdx, [rax+90h]; String2
0x180045aea  test    rdx, rdx
0x180045aed  jz      short loc_180045B02
0x180045aef  lea     rcx, aTrue; "true"
0x180045af6  call    _wcsicmp
0x180045afb  test    eax, eax
0x180045afd  setz    al
0x180045b00  jmp     short loc_180045B05
0x180045b02  mov     al, r13b
0x180045b05  mov     [rsi+1Dh], al
0x180045b08  mov     rax, [rbx+60h]
0x180045b0c  test    rax, rax
0x180045b0f  jz      short loc_180045B30
0x180045b11  mov     rdx, [rax+98h]; String2
0x180045b18  test    rdx, rdx
0x180045b1b  jz      short loc_180045B30
0x180045b1d  lea     rcx, aTrue; "true"
0x180045b24  call    _wcsicmp
0x180045b29  test    eax, eax
0x180045b2b  setz    al
0x180045b2e  jmp     short loc_180045B33
0x180045b30  mov     al, r13b
0x180045b33  mov     [rsi+1Eh], al
0x180045b36  mov     rcx, [r14]; hPrinter
0x180045b39  mov     [rsi+78h], r13d
0x180045b3d  mov     [rbp+57h+Block], r13
0x180045b41  lea     rdx, [rbp+57h+Block]; void *
0x180045b45  call    ?GetDriverInfo@PrintCore@@YAJPEAXPEAPEAU_DRIVER_INFO_8W@@@Z; PrintCore::GetDriverInfo(void *,_DRIVER_INFO_8W * *)
0x180045b4a  mov     r14d, eax
0x180045b4d  test    eax, eax
0x180045b4f  js      short loc_180045BAB
0x180045b51  mov     r15, [rbp+57h+Block]
0x180045b55  mov     rbx, [r15+78h]
0x180045b59  lea     rdx, aB71661f4A4dc43; "{B71661F4-A4DC-43DF-BC16-39D337D15A95}"
0x180045b60  mov     rcx, rbx
0x180045b63  call    cs:__imp__o__wcsicmp
0x180045b69  test    eax, eax
0x180045b6b  jz      short loc_180045B9F
0x180045b6d  lea     rdx, a6d170653528044; "{6D170653-5280-44C2-BA44-2C04BC9D46DA}"
0x180045b74  mov     rcx, rbx
0x180045b77  call    cs:__imp__o__wcsicmp
0x180045b7d  test    eax, eax
0x180045b7f  jnz     short loc_180045B86
0x180045b81  lea     edi, [rax+2]
0x180045b84  jmp     short loc_180045B9F
0x180045b86  lea     rdx, aC1f56d94A46f49; "{C1F56D94-A46F-492E-A129-7F54D1EE2356}"
0x180045b8d  mov     rcx, rbx
0x180045b90  call    cs:__imp__o__wcsicmp
0x180045b96  neg     eax
0x180045b98  sbb     edi, edi
0x180045b9a  not     edi
0x180045b9c  and     edi, 3
0x180045b9f  mov     [rsi+78h], edi
0x180045ba2  mov     rcx, r15; Block
0x180045ba5  call    cs:__imp_free
0x180045bab  mov     rcx, [rbp+5Fh]; this
0x180045baf  test    r14d, r14d
0x180045bb2  jns     short loc_180045BC8
0x180045bb4  mov     r9d, r14d; char *
0x180045bb7  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x180045bbe  mov     edx, 0A9h; void *
0x180045bc3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045bc8  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x180045bcd  mov     rax, [rax+8]
0x180045bd1  test    rax, rax
0x180045bd4  jz      short loc_180045BF5
0x180045bd6  mov     eax, [rax]
0x180045bd8  test    eax, eax
0x180045bda  jz      short loc_180045BF5
0x180045bdc  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x180045be1  movzx   r9d, byte ptr [rsi+1Dh]; int
0x180045be6  movzx   r8d, byte ptr [rsi+1Ch]; int
0x180045beb  mov     rdx, [r12]; unsigned __int16 *
0x180045bef  call    ?PrinterPDCUse_@PrintConfigTelemetry@Telemetry@Driver@Print@@QEAAXQEBGHH@Z; Print::Driver::Telemetry::PrintConfigTelemetry::PrinterPDCUse_(ushort const * const,int,int)
0x180045bf4  nop
0x180045bf5  lea     rcx, [rbp+57h+pData]
0x180045bf9  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180045bfe  mov     rcx, [rbp+57h+var_50]
0x180045c02  xor     rcx, rsp; StackCookie
0x180045c05  call    __security_check_cookie
0x180045c0a  add     rsp, 0B8h
0x180045c11  pop     r15
0x180045c13  pop     r14
0x180045c15  pop     r13
0x180045c17  pop     r12
0x180045c19  pop     rdi
0x180045c1a  pop     rsi
0x180045c1b  pop     rbx
0x180045c1c  pop     rbp
0x180045c1d  retn
0x180045c1e  lea     rdx, aGetprinterdata_1; "GetPrinterData result data unexpected"
0x180045c25  mov     rcx, r15; char *
0x180045c28  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180045c2d  mov     edx, 8000FFFFh; int
0x180045c32  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180045c36  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180045c3b  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180045c42  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180045c46  call    _CxxThrowException_0
0x180045c4c  mov     edx, 8000FFFFh; int
0x180045c51  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180045c55  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180045c5a  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180045c61  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180045c65  call    _CxxThrowException_0
0x180045c6b  mov     edx, eax; int
0x180045c6d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180045c71  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180045c76  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180045c7d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180045c81  call    _CxxThrowException_0
0x180045c87  mov     edx, eax; int
0x180045c89  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180045c8d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
  ... truncated ...
```
