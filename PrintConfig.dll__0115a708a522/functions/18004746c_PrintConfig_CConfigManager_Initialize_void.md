# PrintConfig::CConfigManager::Initialize(void)

- ea: `0x18004746c`
- end: `0x1800479e1`
- name: `?Initialize@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `1397`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `3`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010abc`
- `0x18001bb3c`
- `0x18001c364`

## callees

- `0x180003400`
- `0x180004408`
- `0x180004564`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x18000fb68`
- `0x1800100a0`
- `0x18001535c`
- `0x180018f58`
- `0x1800192fc`
- `0x1800193b8`
- `0x180019410`
- `0x18001973c`
- `0x18001caf0`
- `0x18001d130`
- `0x18002dbc8`
- `0x180034730`
- `0x18004746c`
- `0x18004939c`
- `0x180157bf0`
- `0x180158644`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800477d2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800477ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004780b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800477d2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800477ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004780b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047826`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047826`
- `KERNEL32!GetLastError` at `0x180047991`
- `KERNEL32!GetLastError` at `0x180047991`
- `OLEAUT32!__imp_SysFreeString` at `0x1800474b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800474b7`
- `WINSPOOL!GetPrinterDataW` at `0x180047582`
- `WINSPOOL!GetPrinterDataW` at `0x180047582`
- `WINSPOOL!ClosePrinter` at `0x1800476a3`
- `WINSPOOL!ClosePrinter` at `0x1800476a3`
- `WINSPOOL!OpenPrinterW` at `0x1800476bd`
- `WINSPOOL!OpenPrinterW` at `0x1800476bd`

## string_xrefs

- `0x180047577`: `PrintQueueV4DriverDirectory`
- `0x180047528`: `PrintConfig::CConfigManager::Initialize`
- `0x18004786b`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x1800479b3`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x1800479a0`: `OpenPrinter for admin handle failed: %d`
- `0x18004771d`: `application/vnd.ms-PrintDeviceCapabilities+xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrintConfig::CConfigManager::Initialize(BSTR *this)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, BSTR *); // rbx
  BSTR *v4; // r12
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
  BSTR *v17; // rbx
  BSTR v18; // rcx
  __int64 v19; // r8
  BSTR v20; // rdx
  BSTR *v21; // rax
  void **v22; // rbx
  BSTR v23; // rcx
  int LocalPrintConfigData; // eax
  BSTR v25; // rcx
  _QWORD *v26; // r14
  __int64 v27; // rax
  const wchar_t *v28; // rdx
  bool v29; // al
  __int64 v30; // rax
  const wchar_t *v31; // rdx
  bool v32; // al
  __int64 v33; // rax
  const wchar_t *v34; // rdx
  bool v35; // al
  char IsEnabled; // al
  struct _DRIVER_INFO_8W **v37; // r8
  void *v38; // rcx
  int DriverInfo; // ebx
  void *v40; // r15
  __int64 v41; // r14
  wil::details::in1diag3 *v42; // rcx
  unsigned __int64 v43; // r9
  __int64 v44; // rdx
  int IsVirtualPrinterCommon; // eax
  _DWORD *v46; // rax
  Print::Driver::Telemetry::PrintConfigTelemetry *v47; // rcx
  DWORD LastError; // eax
  const char *v49; // r9
  void *Block; // [rsp+30h] [rbp-69h] BYREF
  DWORD pcbNeeded; // [rsp+38h] [rbp-61h] BYREF
  DWORD pType; // [rsp+3Ch] [rbp-5Dh] BYREF
  HANDLE hPrinter; // [rsp+40h] [rbp-59h] BYREF
  LPBYTE pData[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v55; // [rsp+58h] [rbp-41h]
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+60h] [rbp-39h] BYREF
  __int64 v57; // [rsp+78h] [rbp-21h]
  _OWORD pExceptionObject[2]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v57 = -2;
  hPrinter = 0;
  v2 = (__int64)*this;
  v3 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)*this + 64LL);
  v4 = this + 2;
  SysFreeString(this[2]);
  *v4 = 0;
  v5 = v3(v2, v4);
  if ( v5 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v5);
    throw (hr_error *)pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(*(_QWORD *)*this + 56LL))(*this, &hPrinter);
  if ( v6 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v6);
    throw (hr_error *)pExceptionObject;
  }
  v7 = IsDriverGPDBased(hPrinter, (int *)this + 6);
  if ( v7 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v7);
    throw (hr_error *)pExceptionObject;
  }
  *(_OWORD *)pData = 0;
  v55 = 0;
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
      std::vector<unsigned char>::resize((__int64 *)pData, v8);
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
  std::wstring::_Construct<1,unsigned short const *>(pExceptionObject, pData[0], v16);
  v17 = this + 4;
  std::wstring::operator=((char **)this + 4, (__int64)pExceptionObject);
  std::wstring::~wstring((char **)pExceptionObject);
  v18 = this[6];
  v19 = (__int64)v18 - 1;
  if ( !v18 )
    std::_String_val<std::_Simple_types<char>>::_Xran();
  v20 = this[7];
  if ( (unsigned __int64)v20 <= 7 )
    v21 = this + 4;
  else
    v21 = (BSTR *)*v17;
  if ( *((_WORD *)v21 + v19) != 92 )
  {
    if ( v18 >= v20 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(
        (void **)this + 4,
        (__int64)v20,
        v19,
        92);
    }
    else
    {
      this[6] = (BSTR)((char *)v18 + 1);
      if ( (unsigned __int64)v20 > 7 )
        v17 = (BSTR *)*v17;
      *(_DWORD *)((char *)v17 + 2 * (_QWORD)v18) = 92;
    }
  }
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v22 = (void **)(this + 8);
  v23 = this[8];
  if ( v23 )
  {
    ClosePrinter(v23);
    *v22 = 0;
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
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
      v49);
  }
  Block = 0;
  LocalPrintConfigData = LocalPrintConfigData::CreateLocalPrintConfigData(*v22, (struct LocalPrintConfigData **)&Block);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl'::`2'::impl);
  v38 = *v22;
  if ( IsEnabled )
  {
    *((_DWORD *)this + 31) = 0;
    Block = 0;
    DriverInfo = PrintCore::GetDriverInfo(v38, (BYTE **)&Block, v37);
    if ( DriverInfo >= 0 )
    {
      v40 = Block;
      v41 = *((_QWORD *)Block + 15);
      if ( (unsigned int)_o__wcsicmp(v41, L"{B71661F4-A4DC-43DF-BC16-39D337D15A95}") )
      {
        if ( (unsigned int)_o__wcsicmp(v41, L"{6D170653-5280-44C2-BA44-2C04BC9D46DA}") )
          v10 = (unsigned int)_o__wcsicmp(v41, L"{C1F56D94-A46F-492E-A129-7F54D1EE2356}") == 0 ? 3 : 0;
        else
          v10 = 2;
      }
      *((_DWORD *)this + 31) = v10;
      free(v40);
    }
    v42 = retaddr;
    if ( DriverInfo < 0 )
    {
      v43 = (unsigned int)DriverInfo;
      v44 = 171;
LABEL_59:
      wil::details::in1diag3::_Log_Hr(
        v42,
        (void *)v44,
        (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v43);
    }
  }
  else
  {
    LODWORD(Block) = 0;
    IsVirtualPrinterCommon = PrintCore::IsVirtualPrinterCommon((PrintCore *)v38, &Block, v37);
    *((_BYTE *)this + 120) = (_DWORD)Block != 0;
    v42 = retaddr;
    if ( IsVirtualPrinterCommon < 0 )
    {
      v43 = (unsigned int)IsVirtualPrinterCommon;
      v44 = 176;
      goto LABEL_59;
    }
  }
  v46 = (_DWORD *)*((_QWORD *)Print::Driver::Telemetry::PrintConfigTelemetry::Instance() + 1);
  if ( v46 && *v46 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::Instance();
    Print::Driver::Telemetry::PrintConfigTelemetry::PrinterPDCUse_(
      v47,
      *v4,
      *((unsigned __int8 *)this + 28),
      *((unsigned __int8 *)this + 29));
  }
  std::vector<char>::~vector<char>((char **)pData);
}

```

## disassembly

```asm
0x18004746c  push    rbp
0x18004746e  push    rbx
0x18004746f  push    rsi
0x180047470  push    rdi
0x180047471  push    r12
0x180047473  push    r13
0x180047475  push    r14
0x180047477  push    r15
0x180047479  lea     rbp, [rsp-1Fh]
0x18004747e  sub     rsp, 0B8h
0x180047485  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x18004748d  mov     rax, cs:__security_cookie
0x180047494  xor     rax, rsp
0x180047497  mov     [rbp+57h+var_50], rax
0x18004749b  mov     rsi, rcx
0x18004749e  xor     r13d, r13d
0x1800474a1  mov     [rbp+57h+hPrinter], r13
0x1800474a5  mov     rdi, [rcx]
0x1800474a8  mov     rax, [rdi]
0x1800474ab  mov     rbx, [rax+40h]
0x1800474af  lea     r12, [rcx+10h]
0x1800474b3  mov     rcx, [r12]; bstrString
0x1800474b7  call    cs:__imp_SysFreeString
0x1800474be  nop     dword ptr [rax+rax+00h]
0x1800474c3  mov     [r12], r13
0x1800474c7  mov     rdx, r12
0x1800474ca  mov     rcx, rdi
0x1800474cd  mov     rax, rbx
0x1800474d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474d5  test    eax, eax
0x1800474d7  js      loc_18004791B
0x1800474dd  mov     rcx, [rsi]
0x1800474e0  mov     rax, [rcx]
0x1800474e3  lea     rdx, [rbp+57h+hPrinter]
0x1800474e7  mov     rax, [rax+38h]
0x1800474eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474f0  test    eax, eax
0x1800474f2  js      loc_180047937
0x1800474f8  lea     rdx, [rsi+18h]
0x1800474fc  mov     rcx, [rbp+57h+hPrinter]
0x180047500  call    IsDriverGPDBased
0x180047505  test    eax, eax
0x180047507  js      loc_180047953
0x18004750d  xorps   xmm0, xmm0
0x180047510  movdqu  xmmword ptr [rbp+57h+pData], xmm0
0x180047515  mov     [rbp+57h+var_98], r13
0x180047519  mov     [rbp+57h+pType], r13d
0x18004751d  mov     eax, 208h
0x180047522  mov     [rbp+57h+var_B8], eax
0x180047525  mov     r14d, r13d
0x180047528  lea     r15, aPrintconfigCco_9; "PrintConfig::CConfigManager::Initialize"
0x18004752f  lea     edi, [r13+1]
0x180047533  cmp     r14d, 2
0x180047537  jz      loc_1800478FC
0x18004753d  mov     edx, eax
0x18004753f  mov     rcx, [rbp+57h+pData+8]
0x180047543  mov     rax, rcx
0x180047546  mov     r9, [rbp+57h+pData]
0x18004754a  sub     rax, r9
0x18004754d  cmp     rax, rdx
0x180047550  jnb     short loc_180047563
0x180047552  lea     rcx, [rbp+57h+pData]
0x180047556  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18004755b  mov     rcx, [rbp+57h+pData+8]
0x18004755f  mov     r9, [rbp+57h+pData]; pData
0x180047563  sub     ecx, r9d
0x180047566  lea     rax, [rbp+57h+var_B8]
0x18004756a  mov     [rsp+0F0h+pcbNeeded], rax; pcbNeeded
0x18004756f  mov     [rsp+0F0h+nSize], ecx; int
0x180047573  lea     r8, [rbp+57h+pType]; pType
0x180047577  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x18004757e  mov     rcx, [rbp+57h+hPrinter]; hPrinter
0x180047582  call    cs:__imp_GetPrinterDataW
0x180047589  nop     dword ptr [rax+rax+00h]
0x18004758e  mov     ebx, eax
0x180047590  test    eax, eax
0x180047592  jz      short loc_1800475D3
0x180047594  cmp     eax, 0EAh
0x180047599  jz      short loc_1800475C2
0x18004759b  mov     r8d, eax
0x18004759e  lea     rdx, aGetprinterdata_6; "GetPrinterData failed: dwRet=%d"
0x1800475a5  mov     rcx, r15; char *
0x1800475a8  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800475ad  test    ebx, ebx
0x1800475af  jle     short loc_1800475BC
0x1800475b1  movzx   ebx, bx
0x1800475b4  or      ebx, 80070000h
0x1800475ba  test    ebx, ebx
0x1800475bc  js      loc_18004796F
0x1800475c2  add     r14d, edi
0x1800475c5  cmp     r14d, 2
0x1800475c9  jg      short loc_1800475F0
0x1800475cb  mov     eax, [rbp+57h+var_B8]
0x1800475ce  jmp     loc_180047533
0x1800475d3  cmp     [rbp+57h+pType], edi
0x1800475d6  jnz     loc_1800478CE
0x1800475dc  mov     eax, [rbp+57h+var_B8]
0x1800475df  test    eax, eax
0x1800475e1  jz      loc_1800478CE
0x1800475e7  test    dil, al
0x1800475ea  jnz     loc_1800478CE
0x1800475f0  mov     rdx, [rbp+57h+pData]
0x1800475f4  xorps   xmm0, xmm0
0x1800475f7  movups  [rbp+57h+pExceptionObject], xmm0
0x1800475fb  xorps   xmm1, xmm1
0x1800475fe  movdqu  [rbp+57h+var_60], xmm1
0x180047603  or      r8, 0FFFFFFFFFFFFFFFFh
0x180047607  inc     r8
0x18004760a  cmp     [rdx+r8*2], r13w
0x18004760f  jnz     short loc_180047607
0x180047611  lea     rcx, [rbp+57h+pExceptionObject]
0x180047615  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004761a  lea     rbx, [rsi+20h]
0x18004761e  lea     rdx, [rbp+57h+pExceptionObject]
0x180047622  mov     rcx, rbx
0x180047625  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004762a  lea     rcx, [rbp+57h+pExceptionObject]
0x18004762e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180047633  mov     rcx, [rsi+30h]
0x180047637  lea     r8, [rcx-1]
0x18004763b  cmp     rcx, r8
0x18004763e  jbe     loc_18004798B
0x180047644  mov     rdx, [rbx+18h]
0x180047648  cmp     rdx, 7
0x18004764c  jbe     short loc_180047653
0x18004764e  mov     rax, [rbx]
0x180047651  jmp     short loc_180047656
0x180047653  mov     rax, rbx
0x180047656  mov     r9d, 5Ch ; '\'
0x18004765c  cmp     [rax+r8*2], r9w
0x180047661  jz      short loc_180047687
0x180047663  cmp     rcx, rdx
0x180047666  jnb     short loc_18004767F
0x180047668  lea     rax, [rcx+1]
0x18004766c  mov     [rbx+10h], rax
0x180047670  cmp     rdx, 7
0x180047674  jbe     short loc_180047679
0x180047676  mov     rbx, [rbx]
0x180047679  mov     [rbx+rcx*2], r9d
0x18004767d  jmp     short loc_180047687
0x18004767f  mov     rcx, rbx; Src
0x180047682  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180047687  xorps   xmm0, xmm0
0x18004768a  movdqu  xmmword ptr [rbp+57h+pDefault.pDatatype], xmm0
0x18004768f  mov     qword ptr [rbp+57h+pDefault.DesiredAccess], 0F000Ch
0x180047697  lea     rbx, [rsi+40h]
0x18004769b  mov     rcx, [rbx]; hPrinter
0x18004769e  test    rcx, rcx
0x1800476a1  jz      short loc_1800476B2
0x1800476a3  call    cs:__imp_ClosePrinter
0x1800476aa  nop     dword ptr [rax+rax+00h]
0x1800476af  mov     [rbx], r13
0x1800476b2  lea     r8, [rbp+57h+pDefault]; pDefault
0x1800476b6  mov     rdx, rbx; phPrinter
0x1800476b9  mov     rcx, [r12]; pPrinterName
0x1800476bd  call    cs:__imp_OpenPrinterW
0x1800476c4  nop     dword ptr [rax+rax+00h]
0x1800476c9  test    eax, eax
0x1800476cb  jz      loc_180047991
0x1800476d1  mov     [rbp+57h+Block], r13
0x1800476d5  lea     rdx, [rbp+57h+Block]; struct LocalPrintConfigData **
0x1800476d9  mov     rcx, [rbx]; void *
0x1800476dc  call    ?CreateLocalPrintConfigData@LocalPrintConfigData@@SAJPEAXPEAPEAV1@@Z; LocalPrintConfigData::CreateLocalPrintConfigData(void *,LocalPrintConfigData * *)
0x1800476e1  test    eax, eax
0x1800476e3  js      loc_1800479C5
0x1800476e9  mov     rcx, [rsi+48h]
0x1800476ed  mov     r14, [rbp+57h+Block]
0x1800476f1  mov     [rsi+48h], r14
0x1800476f5  test    rcx, rcx
0x1800476f8  jz      short loc_180047708
0x1800476fa  mov     rax, [rcx]
0x1800476fd  mov     edx, edi
0x1800476ff  mov     rax, [rax+20h]
0x180047703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047708  mov     rax, [r14+60h]
0x18004770c  test    rax, rax
0x18004770f  jz      short loc_180047730
0x180047711  mov     rdx, [rax+88h]; String2
0x180047718  test    rdx, rdx
0x18004771b  jz      short loc_180047730
0x18004771d  lea     rcx, aApplicationVnd; "application/vnd.ms-PrintDeviceCapabilit"...
0x180047724  call    _wcsicmp
0x180047729  test    eax, eax
0x18004772b  setz    al
0x18004772e  jmp     short loc_180047733
0x180047730  mov     al, r13b
0x180047733  mov     [rsi+1Ch], al
0x180047736  mov     rax, [r14+60h]
0x18004773a  test    rax, rax
0x18004773d  jz      short loc_18004775E
0x18004773f  mov     rdx, [rax+90h]; String2
0x180047746  test    rdx, rdx
0x180047749  jz      short loc_18004775E
0x18004774b  lea     rcx, aTrue; "true"
0x180047752  call    _wcsicmp
0x180047757  test    eax, eax
0x180047759  setz    al
0x18004775c  jmp     short loc_180047761
0x18004775e  mov     al, r13b
0x180047761  mov     [rsi+1Dh], al
0x180047764  mov     rax, [r14+60h]
0x180047768  test    rax, rax
0x18004776b  jz      short loc_18004778C
0x18004776d  mov     rdx, [rax+98h]; String2
0x180047774  test    rdx, rdx
0x180047777  jz      short loc_18004778C
0x180047779  lea     rcx, aTrue; "true"
0x180047780  call    _wcsicmp
0x180047785  test    eax, eax
0x180047787  setz    al
0x18004778a  jmp     short loc_18004778F
0x18004778c  mov     al, r13b
0x18004778f  mov     [rsi+1Eh], al
0x180047792  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505> `wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl(void)'::`2'::impl
0x180047799  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled(void)
0x18004779e  mov     rcx, [rbx]; this
0x1800477a1  test    al, al
0x1800477a3  jz      loc_180047844
0x1800477a9  mov     [rsi+7Ch], r13d
0x1800477ad  mov     [rbp+57h+Block], r13
0x1800477b1  lea     rdx, [rbp+57h+Block]; void *
0x1800477b5  call    ?GetDriverInfo@PrintCore@@YAJPEAXPEAPEAU_DRIVER_INFO_8W@@@Z; PrintCore::GetDriverInfo(void *,_DRIVER_INFO_8W * *)
0x1800477ba  mov     ebx, eax
0x1800477bc  test    eax, eax
0x1800477be  js      short loc_180047832
0x1800477c0  mov     r15, [rbp+57h+Block]
0x1800477c4  mov     r14, [r15+78h]
0x1800477c8  lea     rdx, aB71661f4A4dc43; "{B71661F4-A4DC-43DF-BC16-39D337D15A95}"
0x1800477cf  mov     rcx, r14
0x1800477d2  call    cs:__imp__o__wcsicmp
0x1800477d9  nop     dword ptr [rax+rax+00h]
0x1800477de  test    eax, eax
0x1800477e0  jz      short loc_180047820
0x1800477e2  lea     rdx, a6d170653528044; "{6D170653-5280-44C2-BA44-2C04BC9D46DA}"
0x1800477e9  mov     rcx, r14
0x1800477ec  call    cs:__imp__o__wcsicmp
0x1800477f3  nop     dword ptr [rax+rax+00h]
0x1800477f8  test    eax, eax
0x1800477fa  jnz     short loc_180047801
0x1800477fc  lea     edi, [rax+2]
0x1800477ff  jmp     short loc_180047820
0x180047801  lea     rdx, aC1f56d94A46f49; "{C1F56D94-A46F-492E-A129-7F54D1EE2356}"
0x180047808  mov     rcx, r14
0x18004780b  call    cs:__imp__o__wcsicmp
0x180047812  nop     dword ptr [rax+rax+00h]
0x180047817  neg     eax
0x180047819  sbb     edi, edi
0x18004781b  not     edi
0x18004781d  and     edi, 3
0x180047820  mov     [rsi+7Ch], edi
0x180047823  mov     rcx, r15; Block
0x180047826  call    cs:__imp_free
0x18004782d  nop     dword ptr [rax+rax+00h]
0x180047832  mov     rcx, [rbp+5Fh]
0x180047836  test    ebx, ebx
0x180047838  jns     short loc_180047877
0x18004783a  mov     r9d, ebx
0x18004783d  mov     edx, 0ABh
0x180047842  jmp     short loc_18004786B
0x180047844  mov     dword ptr [rbp+57h+Block], r13d
0x180047848  lea     rdx, [rbp+57h+Block]; void *
0x18004784c  call    ?IsVirtualPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsVirtualPrinterCommon(void *,int *)
0x180047851  cmp     dword ptr [rbp+57h+Block], r13d
0x180047855  setnz   cl
0x180047858  mov     [rsi+78h], cl
0x18004785b  mov     rcx, [rbp+5Fh]; this
0x18004785f  test    eax, eax
0x180047861  jns     short loc_180047877
0x180047863  mov     r9d, eax; char *
0x180047866  mov     edx, 0B0h; void *
0x18004786b  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x180047872  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047877  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x18004787c  mov     rax, [rax+8]
0x180047880  test    rax, rax
0x180047883  jz      short loc_1800478A4
0x180047885  mov     eax, [rax]
0x180047887  test    eax, eax
0x180047889  jz      short loc_1800478A4
0x18004788b  call    ?Instance@PrintConfigTelemetry@Telemetry@Driver@Print@@KAPEAV1234@XZ; Print::Driver::Telemetry::PrintConfigTelemetry::Instance(void)
0x180047890  movzx   r9d, byte ptr [rsi+1Dh]; int
0x180047895  movzx   r8d, byte ptr [rsi+1Ch]; int
0x18004789a  mov     rdx, [r12]; unsigned __int16 *
0x18004789e  call    ?PrinterPDCUse_@PrintConfigTelemetry@Telemetry@Driver@Print@@QEAAXQEBGHH@Z; Print::Driver::Telemetry::PrintConfigTelemetry::PrinterPDCUse_(ushort const * const,int,int)
0x1800478a3  nop
0x1800478a4  lea     rcx, [rbp+57h+pData]
0x1800478a8  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800478ad  mov     rcx, [rbp+57h+var_50]
0x1800478b1  xor     rcx, rsp; StackCookie
0x1800478b4  call    __security_check_cookie
0x1800478b9  add     rsp, 0B8h
0x1800478c0  pop     r15
0x1800478c2  pop     r14
0x1800478c4  pop     r13
0x1800478c6  pop     r12
0x1800478c8  pop     rdi
0x1800478c9  pop     rsi
0x1800478ca  pop     rbx
0x1800478cb  pop     rbp
0x1800478cc  retn
  ... truncated ...
```
