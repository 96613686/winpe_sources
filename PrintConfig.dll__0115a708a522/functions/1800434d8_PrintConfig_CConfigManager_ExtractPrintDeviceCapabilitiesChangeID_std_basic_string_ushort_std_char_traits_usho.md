# PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800434d8`
- end: `0x180043ad8`
- name: `?ExtractPrintDeviceCapabilitiesChangeID@CConfigManager@PrintConfig@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1536`
- prototype: `void __fastcall(__int64, OLECHAR *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004b124`

## callees

- `0x180004564`
- `0x18000f830`
- `0x1800109e8`
- `0x180018f00`
- `0x180018f58`
- `0x180019698`
- `0x180022928`
- `0x180026010`
- `0x180027550`
- `0x1800434d8`
- `0x1801cb010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800435ed`
- `OLEAUT32!__imp_SysAllocString` at `0x1800436ae`
- `OLEAUT32!__imp_SysAllocString` at `0x1800436e0`
- `OLEAUT32!__imp_SysAllocString` at `0x18004375b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800438dd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800435ed`
- `OLEAUT32!__imp_SysAllocString` at `0x1800436ae`
- `OLEAUT32!__imp_SysAllocString` at `0x1800436e0`
- `OLEAUT32!__imp_SysAllocString` at `0x18004375b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800438dd`
- `OLEAUT32!__imp_SysFreeString` at `0x180043720`
- `OLEAUT32!__imp_SysFreeString` at `0x180043792`
- `OLEAUT32!__imp_SysFreeString` at `0x180043844`
- `OLEAUT32!__imp_SysFreeString` at `0x1800438ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180043720`
- `OLEAUT32!__imp_SysFreeString` at `0x180043792`
- `OLEAUT32!__imp_SysFreeString` at `0x180043844`
- `OLEAUT32!__imp_SysFreeString` at `0x1800438ce`
- `OLEAUT32!__imp_SysStringLen` at `0x1800437f4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800437f4`
- `OLEAUT32!__imp_VariantClear` at `0x1800435d3`
- `OLEAUT32!__imp_VariantClear` at `0x180043643`
- `OLEAUT32!__imp_VariantClear` at `0x180043696`
- `OLEAUT32!__imp_VariantClear` at `0x180043731`
- `OLEAUT32!__imp_VariantClear` at `0x1800435d3`
- `OLEAUT32!__imp_VariantClear` at `0x180043643`
- `OLEAUT32!__imp_VariantClear` at `0x180043696`
- `OLEAUT32!__imp_VariantClear` at `0x180043731`
- `ole32!CoCreateInstance` at `0x180043544`
- `ole32!CoCreateInstance` at `0x180043544`
- `WINSPOOL!SetPrinterDataW` at `0x180043820`
- `WINSPOOL!SetPrinterDataW` at `0x180043820`

## string_xrefs

- `0x1800438a4`: `Missing change ID in device-resident PrintDeviceCapabilities file.`
- `0x1800436a7`: `xmlns:psf2='http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2'`
- `0x180043513`: `PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID`
- `0x1800437e4`: `PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID`
- `0x1800438ab`: `PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID`
- `0x180043a28`: `PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID(__int64 a1, OLECHAR *a2)
{
  HRESULT v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  LPVOID v8; // rsi
  __int64 v9; // r14
  const OLECHAR *v10; // rbx
  int v11; // ebx
  int v12; // eax
  LPVOID v13; // rdi
  __int64 v14; // rsi
  __int128 v15; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  BSTR v17; // rax
  OLECHAR *v18; // rbx
  int v19; // edi
  LPVOID v20; // rdi
  __int64 v21; // rsi
  BSTR v22; // rax
  OLECHAR *v23; // rbx
  int v24; // edi
  int v25; // eax
  OLECHAR *v26; // rax
  UINT v27; // eax
  signed int v28; // eax
  bool v29; // sf
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  _QWORD *v33; // rax
  BSTR pbstr[2]; // [rsp+38h] [rbp-59h] BYREF
  VARIANTARG pExceptionObject; // [rsp+48h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-29h] BYREF
  BSTR v37; // [rsp+80h] [rbp-11h] BYREF
  __int64 v38; // [rsp+88h] [rbp-9h] BYREF
  _QWORD v39[7]; // [rsp+90h] [rbp-1h] BYREF
  __int16 v40; // [rsp+108h] [rbp+77h] BYREF
  LPVOID ppv; // [rsp+110h] [rbp+7Fh] BYREF

  v39[1] = -2;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID",
    L"Parsing ChangeID from the bidi PrintDeviceCapabilities file.");
  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
         &ppv);
  if ( v4 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v4);
    throw (hr_error *)&pExceptionObject;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
  if ( v5 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v5);
    throw (hr_error *)&pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  if ( v6 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v6);
    throw (hr_error *)&pExceptionObject;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
  if ( v7 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v7);
    throw (hr_error *)&pExceptionObject;
  }
  v40 = 0;
  v8 = ppv;
  v9 = *(_QWORD *)ppv;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v10 = a2;
  else
    v10 = *(const OLECHAR **)a2;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v10);
  if ( !pvarg.llVal && v10 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  pExceptionObject = pvarg;
  v11 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v9 + 464))(v8, &pExceptionObject, &v40);
  VariantClear(&pvarg);
  if ( v11 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v11);
    throw (hr_error *)&pExceptionObject;
  }
  if ( !v40 )
  {
    v39[0] = 0;
    v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 480LL))(ppv, v39);
    if ( v12 >= 0 )
    {
      Microsoft::WRL::ComPtr<IXMLDOMParseError>::ComPtr<IXMLDOMParseError>(&v37);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Get((__int64)v39);
      v30 = std::streambuf::setbuf((__int64)&v37);
      (*(void (__fastcall **)(__int64, __int64))(v31 + 72))(v32, v30);
      v33 = std::wstring::c_str(a2);
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID",
        L"Failed to parse PrintDeviceCapabilities bidi file ('%ws'). Reason: %ws",
        v33,
        v37);
      hr_error::hr_error((hr_error *)&pExceptionObject, -2147467259);
      throw (hr_error *)&pExceptionObject;
    }
    hr_error::hr_error((hr_error *)&pExceptionObject, v12);
    throw (hr_error *)&pExceptionObject;
  }
  v13 = ppv;
  v14 = *(_QWORD *)ppv;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"xmlns:psf2='http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2'");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v15 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  v17 = SysAllocString(L"SelectionNamespaces");
  v18 = v17;
  v37 = v17;
  if ( !v17 )
    ATL::AtlThrowImpl(-2147024882);
  *(_OWORD *)&pExceptionObject.vt = v15;
  pExceptionObject.pRecInfo = pRecInfo;
  v19 = (*(__int64 (__fastcall **)(LPVOID, BSTR, VARIANTARG *))(v14 + 640))(v13, v17, &pExceptionObject);
  SysFreeString(v18);
  VariantClear(&pvarg);
  if ( v19 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v19);
    throw (hr_error *)&pExceptionObject;
  }
  v38 = 0;
  v20 = ppv;
  v21 = *(_QWORD *)ppv;
  v22 = SysAllocString(L"/psf2:PrintDeviceCapabilities/psf2:CapabilitiesChangeID");
  v23 = v22;
  v37 = v22;
  if ( !v22 )
    ATL::AtlThrowImpl(-2147024882);
  v24 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(v21 + 296))(v20, v22, &v38);
  SysFreeString(v23);
  if ( v24 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v24);
    throw (hr_error *)&pExceptionObject;
  }
  pbstr[0] = 0;
  if ( v38 )
  {
    v25 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v38 + 208LL))(v38, pbstr);
    if ( v25 < 0 )
    {
      hr_error::hr_error((hr_error *)&pExceptionObject, v25);
      throw (hr_error *)&pExceptionObject;
    }
    v26 = pbstr[0];
  }
  else
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID",
      L"Missing change ID in device-resident PrintDeviceCapabilities file.");
    v26 = pbstr[0];
    if ( L"V4_No_ChangeID_Present" != pbstr[0] )
    {
      SysFreeString(pbstr[0]);
      v26 = SysAllocString(L"V4_No_ChangeID_Present");
      pbstr[0] = v26;
      if ( !v26 )
        ATL::AtlThrowImpl(-2147024882);
    }
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID",
    L"Bidi PrintDeviceCapabilities file changeid: %ws",
    v26);
  v27 = SysStringLen(pbstr[0]);
  v28 = SetPrinterDataW(*(HANDLE *)(a1 + 64), (LPWSTR)L"V4_PDC_ChangeID", 1u, (LPBYTE)pbstr[0], 2 * v27 + 2);
  v29 = v28 < 0;
  if ( v28 > 0 )
  {
    v28 = (unsigned __int16)v28 | 0x80070000;
    v29 = v28 < 0;
  }
  if ( v29 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v28);
    throw (hr_error *)&pExceptionObject;
  }
  SysFreeString(pbstr[0]);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x1800434d8  mov     rax, rsp
0x1800434db  push    rbp
0x1800434dc  push    rdi
0x1800434dd  push    r13
0x1800434df  push    r14
0x1800434e1  push    r15
0x1800434e3  lea     rbp, [rax-5Fh]
0x1800434e7  sub     rsp, 0C0h
0x1800434ee  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1800434f6  mov     [rax+8], rbx
0x1800434fa  mov     [rax+10h], rsi
0x1800434fe  movaps  xmmword ptr [rax-38h], xmm6
0x180043502  movaps  xmmword ptr [rax-48h], xmm7
0x180043506  mov     rdi, rdx
0x180043509  mov     r15, rcx
0x18004350c  lea     rdx, aParsingChangei; "Parsing ChangeID from the bidi PrintDev"...
0x180043513  lea     rcx, aPrintconfigCco_20; "PrintConfig::CConfigManager::ExtractPri"...
0x18004351a  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004351f  mov     [rbp+57h+arg_18], 0
0x180043527  lea     rax, [rbp+57h+arg_18]
0x18004352b  mov     [rsp+0E0h+ppv], rax; ppv
0x180043530  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180043537  xor     edx, edx; pUnkOuter
0x180043539  lea     r8d, [rdx+1]; dwClsContext
0x18004353d  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180043544  call    cs:__imp_CoCreateInstance
0x18004354b  nop     dword ptr [rax+rax+00h]
0x180043550  test    eax, eax
0x180043552  js      loc_18004393A
0x180043558  mov     rcx, [rbp+57h+arg_18]
0x18004355c  mov     rax, [rcx]
0x18004355f  xor     edx, edx
0x180043561  mov     rax, [rax+220h]
0x180043568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004356d  test    eax, eax
0x18004356f  js      loc_180043956
0x180043575  mov     rcx, [rbp+57h+arg_18]
0x180043579  mov     rax, [rcx]
0x18004357c  xor     edx, edx
0x18004357e  mov     rax, [rax+1F8h]
0x180043585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004358a  test    eax, eax
0x18004358c  js      loc_180043972
0x180043592  mov     rcx, [rbp+57h+arg_18]
0x180043596  mov     rax, [rcx]
0x180043599  xor     edx, edx
0x18004359b  mov     rax, [rax+230h]
0x1800435a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435a7  test    eax, eax
0x1800435a9  js      loc_18004398E
0x1800435af  xor     eax, eax
0x1800435b1  mov     [rbp+57h+arg_10], ax
0x1800435b5  mov     rsi, [rbp+57h+arg_18]
0x1800435b9  mov     r14, [rsi]
0x1800435bc  cmp     qword ptr [rdi+18h], 7
0x1800435c1  jbe     short loc_1800435C8
0x1800435c3  mov     rbx, [rdi]
0x1800435c6  jmp     short loc_1800435CB
0x1800435c8  mov     rbx, rdi
0x1800435cb  mov     word ptr [rbp+57h+pvarg], ax
0x1800435cf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800435d3  call    cs:__imp_VariantClear
0x1800435da  nop     dword ptr [rax+rax+00h]
0x1800435df  mov     r13d, 8
0x1800435e5  mov     word ptr [rbp+57h+pvarg], r13w
0x1800435ea  mov     rcx, rbx; psz
0x1800435ed  call    cs:__imp_SysAllocString
0x1800435f4  nop     dword ptr [rax+rax+00h]
0x1800435f9  mov     dword ptr [rbp+57h+pvarg+8], eax
0x1800435fc  mov     rcx, rax
0x1800435ff  sar     rcx, 20h
0x180043603  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x180043606  test    rax, rax
0x180043609  jnz     short loc_180043614
0x18004360b  test    rbx, rbx
0x18004360e  jnz     loc_1800439AA
0x180043614  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180043618  movaps  [rbp+57h+pExceptionObject], xmm0
0x18004361c  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180043621  movsd   [rbp+57h+var_90], xmm1
0x180043626  lea     r8, [rbp+57h+arg_10]
0x18004362a  lea     rdx, [rbp+57h+pExceptionObject]
0x18004362e  mov     rcx, rsi
0x180043631  mov     rax, [r14+1D0h]
0x180043638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004363d  mov     ebx, eax
0x18004363f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180043643  call    cs:__imp_VariantClear
0x18004364a  nop     dword ptr [rax+rax+00h]
0x18004364f  test    ebx, ebx
0x180043651  js      loc_1800439C5
0x180043657  xor     eax, eax
0x180043659  cmp     ax, [rbp+57h+arg_10]
0x18004365d  jnz     short loc_180043687
0x18004365f  mov     [rbp+57h+var_58], rax
0x180043663  mov     rcx, [rbp+57h+arg_18]
0x180043667  mov     rax, [rcx]
0x18004366a  lea     rdx, [rbp+57h+var_58]
0x18004366e  mov     rax, [rax+1E0h]
0x180043675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004367a  test    eax, eax
0x18004367c  js      loc_180043913
0x180043682  jmp     loc_1800439E1
0x180043687  mov     rdi, [rbp+57h+arg_18]
0x18004368b  mov     rsi, [rdi]
0x18004368e  mov     word ptr [rbp+57h+pvarg], ax
0x180043692  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180043696  call    cs:__imp_VariantClear
0x18004369d  nop     dword ptr [rax+rax+00h]
0x1800436a2  mov     word ptr [rbp+57h+pvarg], r13w
0x1800436a7  lea     rcx, aXmlnsPsf2HttpS; "xmlns:psf2='http://schemas.microsoft.co"...
0x1800436ae  call    cs:__imp_SysAllocString
0x1800436b5  nop     dword ptr [rax+rax+00h]
0x1800436ba  mov     dword ptr [rbp+57h+pvarg+8], eax
0x1800436bd  mov     rcx, rax
0x1800436c0  sar     rcx, 20h
0x1800436c4  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x1800436c7  test    rax, rax
0x1800436ca  jz      loc_180043A53
0x1800436d0  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x1800436d4  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x1800436d9  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x1800436e0  call    cs:__imp_SysAllocString
0x1800436e7  nop     dword ptr [rax+rax+00h]
0x1800436ec  mov     rbx, rax
0x1800436ef  mov     [rbp+57h+var_68], rax
0x1800436f3  test    rax, rax
0x1800436f6  jz      loc_180043A6E
0x1800436fc  movaps  [rbp+57h+pExceptionObject], xmm6
0x180043700  movsd   [rbp+57h+var_90], xmm7
0x180043705  lea     r8, [rbp+57h+pExceptionObject]
0x180043709  mov     rdx, rax
0x18004370c  mov     rcx, rdi
0x18004370f  mov     rax, [rsi+280h]
0x180043716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004371b  mov     edi, eax
0x18004371d  mov     rcx, rbx; bstrString
0x180043720  call    cs:__imp_SysFreeString
0x180043727  nop     dword ptr [rax+rax+00h]
0x18004372c  nop
0x18004372d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180043731  call    cs:__imp_VariantClear
0x180043738  nop     dword ptr [rax+rax+00h]
0x18004373d  test    edi, edi
0x18004373f  js      loc_180043A79
0x180043745  mov     [rbp+57h+var_60], 0
0x18004374d  mov     rdi, [rbp+57h+arg_18]
0x180043751  mov     rsi, [rdi]
0x180043754  lea     rcx, aPsf2Printdevic_0; "/psf2:PrintDeviceCapabilities/psf2:Capa"...
0x18004375b  call    cs:__imp_SysAllocString
0x180043762  nop     dword ptr [rax+rax+00h]
0x180043767  mov     rbx, rax
0x18004376a  mov     [rbp+57h+var_68], rax
0x18004376e  test    rax, rax
0x180043771  jz      loc_180043A95
0x180043777  lea     r8, [rbp+57h+var_60]
0x18004377b  mov     rdx, rax
0x18004377e  mov     rcx, rdi
0x180043781  mov     rax, [rsi+128h]
0x180043788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004378d  mov     edi, eax
0x18004378f  mov     rcx, rbx; bstrString
0x180043792  call    cs:__imp_SysFreeString
0x180043799  nop     dword ptr [rax+rax+00h]
0x18004379e  test    edi, edi
0x1800437a0  js      loc_180043AA0
0x1800437a6  mov     [rbp+57h+pbstr], 0
0x1800437ae  mov     rcx, [rbp+57h+var_60]
0x1800437b2  test    rcx, rcx
0x1800437b5  jz      loc_1800438A4
0x1800437bb  mov     rax, [rcx]
0x1800437be  lea     rdx, [rbp+57h+pbstr]
0x1800437c2  mov     rax, [rax+0D0h]
0x1800437c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800437ce  test    eax, eax
0x1800437d0  js      loc_180043ABC
0x1800437d6  mov     rax, [rbp+57h+pbstr]
0x1800437da  mov     r8, rax
0x1800437dd  lea     rdx, aBidiPrintdevic; "Bidi PrintDeviceCapabilities file chang"...
0x1800437e4  lea     rcx, aPrintconfigCco_20; "PrintConfig::CConfigManager::ExtractPri"...
0x1800437eb  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800437f0  mov     rcx, [rbp+57h+pbstr]; pbstr
0x1800437f4  call    cs:__imp_SysStringLen
0x1800437fb  nop     dword ptr [rax+rax+00h]
0x180043800  lea     eax, ds:2[rax*2]
0x180043807  mov     dword ptr [rsp+0E0h+ppv], eax; cbData
0x18004380b  mov     r9, [rbp+57h+pbstr]; pData
0x18004380f  mov     r8d, 1; Type
0x180043815  lea     rdx, aV4PdcChangeid; "V4_PDC_ChangeID"
0x18004381c  mov     rcx, [r15+40h]; hPrinter
0x180043820  call    cs:__imp_SetPrinterDataW
0x180043827  nop     dword ptr [rax+rax+00h]
0x18004382c  test    eax, eax
0x18004382e  jle     short loc_18004383A
0x180043830  movzx   eax, ax
0x180043833  or      eax, 80070000h
0x180043838  test    eax, eax
0x18004383a  js      loc_1800438F7
0x180043840  mov     rcx, [rbp+57h+pbstr]; bstrString
0x180043844  call    cs:__imp_SysFreeString
0x18004384b  nop     dword ptr [rax+rax+00h]
0x180043850  nop
0x180043851  mov     rcx, [rbp+57h+var_60]
0x180043855  test    rcx, rcx
0x180043858  jz      short loc_180043867
0x18004385a  mov     rax, [rcx]
0x18004385d  mov     rax, [rax+10h]
0x180043861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043866  nop
0x180043867  mov     rcx, [rbp+57h+arg_18]
0x18004386b  test    rcx, rcx
0x18004386e  jz      short loc_18004387D
0x180043870  mov     rax, [rcx]
0x180043873  mov     rax, [rax+10h]
0x180043877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004387c  nop
0x18004387d  lea     r11, [rsp+0E0h+var_20]
0x180043885  mov     rbx, [r11+30h]
0x180043889  mov     rsi, [r11+38h]
0x18004388d  movaps  xmm6, xmmword ptr [r11-10h]
0x180043892  movaps  xmm7, xmmword ptr [r11-20h]
0x180043897  mov     rsp, r11
0x18004389a  pop     r15
0x18004389c  pop     r14
0x18004389e  pop     r13
0x1800438a0  pop     rdi
0x1800438a1  pop     rbp
0x1800438a2  retn
0x1800438a4  lea     rdx, aMissingChangeI; "Missing change ID in device-resident Pr"...
0x1800438ab  lea     rcx, aPrintconfigCco_20; "PrintConfig::CConfigManager::ExtractPri"...
0x1800438b2  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800438b7  lea     rbx, aV4NoChangeidPr; "V4_No_ChangeID_Present"
0x1800438be  mov     rax, [rbp+57h+pbstr]
0x1800438c2  cmp     rbx, rax
0x1800438c5  jz      loc_1800437DA
0x1800438cb  mov     rcx, rax; bstrString
0x1800438ce  call    cs:__imp_SysFreeString
0x1800438d5  nop     dword ptr [rax+rax+00h]
0x1800438da  mov     rcx, rbx; psz
0x1800438dd  call    cs:__imp_SysAllocString
0x1800438e4  nop     dword ptr [rax+rax+00h]
0x1800438e9  mov     [rbp+57h+pbstr], rax
0x1800438ed  test    rax, rax
0x1800438f0  jz      short loc_18004392F
0x1800438f2  jmp     loc_1800437DA
0x1800438f7  mov     edx, eax; int
0x1800438f9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800438fd  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180043902  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043909  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004390d  call    _CxxThrowException_0
0x180043913  mov     edx, eax; int
0x180043915  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043919  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004391e  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043925  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043929  call    _CxxThrowException_0
0x18004392f  mov     ecx, 8007000Eh; int
0x180043934  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18004393a  mov     edx, eax; int
0x18004393c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043940  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180043945  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004394c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043950  call    _CxxThrowException_0
0x180043956  mov     edx, eax; int
0x180043958  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004395c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180043961  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043968  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004396c  call    _CxxThrowException_0
0x180043972  mov     edx, eax; int
0x180043974  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043978  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004397d  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180043984  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180043988  call    _CxxThrowException_0
0x18004398e  mov     edx, eax; int
0x180043990  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180043994  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180043999  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800439a0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800439a4  call    _CxxThrowException_0
0x1800439aa  mov     eax, 0Ah
0x1800439af  mov     word ptr [rbp+57h+pvarg], ax
0x1800439b3  mov     dword ptr [rbp+57h+pvarg+8], 8007000Eh
0x1800439ba  mov     ecx, 8007000Eh; int
0x1800439bf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800439c5  mov     edx, ebx; int
0x1800439c7  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800439cb  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800439d0  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800439d7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800439db  call    _CxxThrowException_0
0x1800439e1  lea     rcx, [rbp+57h+var_68]
0x1800439e5  call    ??0?$ComPtr@UIXMLDOMParseError@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IXMLDOMParseError>::ComPtr<IXMLDOMParseError>(void)
0x1800439ea  nop
0x1800439eb  lea     rcx, [rbp+57h+var_58]
0x1800439ef  call    ?Get@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAPEBGXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Get(void)
0x1800439f4  mov     r9, rax
  ... truncated ...
```
