# PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180041c4c`
- end: `0x1800421eb`
- name: `?ExtractPrintDeviceCapabilitiesChangeID@CConfigManager@PrintConfig@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1439`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180049274`

## callees

- `0x180004424`
- `0x18000f380`
- `0x18001047c`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018aa8`
- `0x180021e84`
- `0x180025380`
- `0x180026860`
- `0x180041c4c`
- `0x1801c3010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180041d55`
- `OLEAUT32!__imp_SysAllocString` at `0x180041e04`
- `OLEAUT32!__imp_SysAllocString` at `0x180041e30`
- `OLEAUT32!__imp_SysAllocString` at `0x180041e99`
- `OLEAUT32!__imp_SysAllocString` at `0x180041ff6`
- `OLEAUT32!__imp_SysAllocString` at `0x180041d55`
- `OLEAUT32!__imp_SysAllocString` at `0x180041e04`
- `OLEAUT32!__imp_SysAllocString` at `0x180041e30`
- `OLEAUT32!__imp_SysAllocString` at `0x180041e99`
- `OLEAUT32!__imp_SysAllocString` at `0x180041ff6`
- `OLEAUT32!__imp_SysFreeString` at `0x180041e6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180041eca`
- `OLEAUT32!__imp_SysFreeString` at `0x180041f6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180041fed`
- `OLEAUT32!__imp_SysFreeString` at `0x180041e6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180041eca`
- `OLEAUT32!__imp_SysFreeString` at `0x180041f6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180041fed`
- `OLEAUT32!__imp_SysStringLen` at `0x180041f26`
- `OLEAUT32!__imp_SysStringLen` at `0x180041f26`
- `OLEAUT32!__imp_VariantClear` at `0x180041d41`
- `OLEAUT32!__imp_VariantClear` at `0x180041da5`
- `OLEAUT32!__imp_VariantClear` at `0x180041df2`
- `OLEAUT32!__imp_VariantClear` at `0x180041e75`
- `OLEAUT32!__imp_VariantClear` at `0x180041d41`
- `OLEAUT32!__imp_VariantClear` at `0x180041da5`
- `OLEAUT32!__imp_VariantClear` at `0x180041df2`
- `OLEAUT32!__imp_VariantClear` at `0x180041e75`
- `ole32!CoCreateInstance` at `0x180041cb8`
- `ole32!CoCreateInstance` at `0x180041cb8`
- `WINSPOOL!SetPrinterDataW` at `0x180041f4c`
- `WINSPOOL!SetPrinterDataW` at `0x180041f4c`

## string_xrefs

- `0x180041fc3`: `Missing change ID in device-resident PrintDeviceCapabilities file.`
- `0x180041dfd`: `xmlns:psf2='http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2'`
- `0x180041c87`: `PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID`
- `0x180041f16`: `PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID`
- `0x180041fca`: `PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID`
- `0x18004213b`: `PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID(__int64 a1, __int64 a2)
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
  _QWORD *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rax
  BSTR pbstr[2]; // [rsp+38h] [rbp-59h] BYREF
  VARIANTARG pExceptionObject; // [rsp+48h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-29h] BYREF
  BSTR v39; // [rsp+80h] [rbp-11h] BYREF
  __int64 v40; // [rsp+88h] [rbp-9h] BYREF
  _QWORD v41[7]; // [rsp+90h] [rbp-1h] BYREF
  __int16 v42; // [rsp+108h] [rbp+77h] BYREF
  LPVOID ppv; // [rsp+110h] [rbp+7Fh] BYREF

  v41[1] = -2;
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
  v42 = 0;
  v8 = ppv;
  v9 = *(_QWORD *)ppv;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v10 = (const OLECHAR *)a2;
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
  v11 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v9 + 464))(v8, &pExceptionObject, &v42);
  VariantClear(&pvarg);
  if ( v11 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v11);
    throw (hr_error *)&pExceptionObject;
  }
  if ( !v42 )
  {
    v41[0] = 0;
    v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 480LL))(ppv, v41);
    if ( v12 >= 0 )
    {
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v39);
      v30 = (_QWORD *)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Get(v41);
      v32 = std::streambuf::setbuf(&v39, v31, *v30, v30);
      (*(void (__fastcall **)(__int64, __int64))(v33 + 72))(v34, v32);
      v35 = std::wstring::c_str(a2);
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID",
        L"Failed to parse PrintDeviceCapabilities bidi file ('%ws'). Reason: %ws",
        v35,
        v39);
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
  v39 = v17;
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
  v40 = 0;
  v20 = ppv;
  v21 = *(_QWORD *)ppv;
  v22 = SysAllocString(L"/psf2:PrintDeviceCapabilities/psf2:CapabilitiesChangeID");
  v23 = v22;
  v39 = v22;
  if ( !v22 )
    ATL::AtlThrowImpl(-2147024882);
  v24 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(v21 + 296))(v20, v22, &v40);
  SysFreeString(v23);
  if ( v24 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v24);
    throw (hr_error *)&pExceptionObject;
  }
  pbstr[0] = 0;
  if ( v40 )
  {
    v25 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v40 + 208LL))(v40, pbstr);
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
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x180041c4c  mov     rax, rsp
0x180041c4f  push    rbp
0x180041c50  push    rdi
0x180041c51  push    r13
0x180041c53  push    r14
0x180041c55  push    r15
0x180041c57  lea     rbp, [rax-5Fh]
0x180041c5b  sub     rsp, 0C0h
0x180041c62  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x180041c6a  mov     [rax+8], rbx
0x180041c6e  mov     [rax+10h], rsi
0x180041c72  movaps  xmmword ptr [rax-38h], xmm6
0x180041c76  movaps  xmmword ptr [rax-48h], xmm7
0x180041c7a  mov     rdi, rdx
0x180041c7d  mov     r15, rcx
0x180041c80  lea     rdx, aParsingChangei; "Parsing ChangeID from the bidi PrintDev"...
0x180041c87  lea     rcx, aPrintconfigCco_20; "PrintConfig::CConfigManager::ExtractPri"...
0x180041c8e  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180041c93  mov     [rbp+57h+arg_18], 0
0x180041c9b  lea     rax, [rbp+57h+arg_18]
0x180041c9f  mov     [rsp+0E0h+ppv], rax; ppv
0x180041ca4  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180041cab  xor     edx, edx; pUnkOuter
0x180041cad  lea     r8d, [rdx+1]; dwClsContext
0x180041cb1  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180041cb8  call    cs:__imp_CoCreateInstance
0x180041cbe  test    eax, eax
0x180041cc0  js      loc_18004204D
0x180041cc6  mov     rcx, [rbp+57h+arg_18]
0x180041cca  mov     rax, [rcx]
0x180041ccd  xor     edx, edx
0x180041ccf  mov     rax, [rax+220h]
0x180041cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cdb  test    eax, eax
0x180041cdd  js      loc_180042069
0x180041ce3  mov     rcx, [rbp+57h+arg_18]
0x180041ce7  mov     rax, [rcx]
0x180041cea  xor     edx, edx
0x180041cec  mov     rax, [rax+1F8h]
0x180041cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cf8  test    eax, eax
0x180041cfa  js      loc_180042085
0x180041d00  mov     rcx, [rbp+57h+arg_18]
0x180041d04  mov     rax, [rcx]
0x180041d07  xor     edx, edx
0x180041d09  mov     rax, [rax+230h]
0x180041d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d15  test    eax, eax
0x180041d17  js      loc_1800420A1
0x180041d1d  xor     eax, eax
0x180041d1f  mov     [rbp+57h+arg_10], ax
0x180041d23  mov     rsi, [rbp+57h+arg_18]
0x180041d27  mov     r14, [rsi]
0x180041d2a  cmp     qword ptr [rdi+18h], 7
0x180041d2f  jbe     short loc_180041D36
0x180041d31  mov     rbx, [rdi]
0x180041d34  jmp     short loc_180041D39
0x180041d36  mov     rbx, rdi
0x180041d39  mov     word ptr [rbp+57h+pvarg], ax
0x180041d3d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180041d41  call    cs:__imp_VariantClear
0x180041d47  mov     r13d, 8
0x180041d4d  mov     word ptr [rbp+57h+pvarg], r13w
0x180041d52  mov     rcx, rbx; psz
0x180041d55  call    cs:__imp_SysAllocString
0x180041d5b  mov     dword ptr [rbp+57h+pvarg+8], eax
0x180041d5e  mov     rcx, rax
0x180041d61  sar     rcx, 20h
0x180041d65  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x180041d68  test    rax, rax
0x180041d6b  jnz     short loc_180041D76
0x180041d6d  test    rbx, rbx
0x180041d70  jnz     loc_1800420BD
0x180041d76  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180041d7a  movaps  [rbp+57h+pExceptionObject], xmm0
0x180041d7e  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180041d83  movsd   [rbp+57h+var_90], xmm1
0x180041d88  lea     r8, [rbp+57h+arg_10]
0x180041d8c  lea     rdx, [rbp+57h+pExceptionObject]
0x180041d90  mov     rcx, rsi
0x180041d93  mov     rax, [r14+1D0h]
0x180041d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d9f  mov     ebx, eax
0x180041da1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180041da5  call    cs:__imp_VariantClear
0x180041dab  test    ebx, ebx
0x180041dad  js      loc_1800420D8
0x180041db3  xor     eax, eax
0x180041db5  cmp     ax, [rbp+57h+arg_10]
0x180041db9  jnz     short loc_180041DE3
0x180041dbb  mov     [rbp+57h+var_58], rax
0x180041dbf  mov     rcx, [rbp+57h+arg_18]
0x180041dc3  mov     rax, [rcx]
0x180041dc6  lea     rdx, [rbp+57h+var_58]
0x180041dca  mov     rax, [rax+1E0h]
0x180041dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041dd6  test    eax, eax
0x180041dd8  js      loc_180042026
0x180041dde  jmp     loc_1800420F4
0x180041de3  mov     rdi, [rbp+57h+arg_18]
0x180041de7  mov     rsi, [rdi]
0x180041dea  mov     word ptr [rbp+57h+pvarg], ax
0x180041dee  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180041df2  call    cs:__imp_VariantClear
0x180041df8  mov     word ptr [rbp+57h+pvarg], r13w
0x180041dfd  lea     rcx, aXmlnsPsf2HttpS; "xmlns:psf2='http://schemas.microsoft.co"...
0x180041e04  call    cs:__imp_SysAllocString
0x180041e0a  mov     dword ptr [rbp+57h+pvarg+8], eax
0x180041e0d  mov     rcx, rax
0x180041e10  sar     rcx, 20h
0x180041e14  mov     dword ptr [rbp+57h+pvarg+0Ch], ecx
0x180041e17  test    rax, rax
0x180041e1a  jz      loc_180042166
0x180041e20  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x180041e24  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x180041e29  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x180041e30  call    cs:__imp_SysAllocString
0x180041e36  mov     rbx, rax
0x180041e39  mov     [rbp+57h+var_68], rax
0x180041e3d  test    rax, rax
0x180041e40  jz      loc_180042181
0x180041e46  movaps  [rbp+57h+pExceptionObject], xmm6
0x180041e4a  movsd   [rbp+57h+var_90], xmm7
0x180041e4f  lea     r8, [rbp+57h+pExceptionObject]
0x180041e53  mov     rdx, rax
0x180041e56  mov     rcx, rdi
0x180041e59  mov     rax, [rsi+280h]
0x180041e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e65  mov     edi, eax
0x180041e67  mov     rcx, rbx; bstrString
0x180041e6a  call    cs:__imp_SysFreeString
0x180041e70  nop
0x180041e71  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180041e75  call    cs:__imp_VariantClear
0x180041e7b  test    edi, edi
0x180041e7d  js      loc_18004218C
0x180041e83  mov     [rbp+57h+var_60], 0
0x180041e8b  mov     rdi, [rbp+57h+arg_18]
0x180041e8f  mov     rsi, [rdi]
0x180041e92  lea     rcx, aPsf2Printdevic_0; "/psf2:PrintDeviceCapabilities/psf2:Capa"...
0x180041e99  call    cs:__imp_SysAllocString
0x180041e9f  mov     rbx, rax
0x180041ea2  mov     [rbp+57h+var_68], rax
0x180041ea6  test    rax, rax
0x180041ea9  jz      loc_1800421A8
0x180041eaf  lea     r8, [rbp+57h+var_60]
0x180041eb3  mov     rdx, rax
0x180041eb6  mov     rcx, rdi
0x180041eb9  mov     rax, [rsi+128h]
0x180041ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ec5  mov     edi, eax
0x180041ec7  mov     rcx, rbx; bstrString
0x180041eca  call    cs:__imp_SysFreeString
0x180041ed0  test    edi, edi
0x180041ed2  js      loc_1800421B3
0x180041ed8  mov     [rbp+57h+pbstr], 0
0x180041ee0  mov     rcx, [rbp+57h+var_60]
0x180041ee4  test    rcx, rcx
0x180041ee7  jz      loc_180041FC3
0x180041eed  mov     rax, [rcx]
0x180041ef0  lea     rdx, [rbp+57h+pbstr]
0x180041ef4  mov     rax, [rax+0D0h]
0x180041efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f00  test    eax, eax
0x180041f02  js      loc_1800421CF
0x180041f08  mov     rax, [rbp+57h+pbstr]
0x180041f0c  mov     r8, rax
0x180041f0f  lea     rdx, aBidiPrintdevic; "Bidi PrintDeviceCapabilities file chang"...
0x180041f16  lea     rcx, aPrintconfigCco_20; "PrintConfig::CConfigManager::ExtractPri"...
0x180041f1d  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180041f22  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180041f26  call    cs:__imp_SysStringLen
0x180041f2c  lea     eax, ds:2[rax*2]
0x180041f33  mov     dword ptr [rsp+0E0h+ppv], eax; cbData
0x180041f37  mov     r9, [rbp+57h+pbstr]; pData
0x180041f3b  mov     r8d, 1; Type
0x180041f41  lea     rdx, aV4PdcChangeid; "V4_PDC_ChangeID"
0x180041f48  mov     rcx, [r15+40h]; hPrinter
0x180041f4c  call    cs:__imp_SetPrinterDataW
0x180041f52  test    eax, eax
0x180041f54  jle     short loc_180041F60
0x180041f56  movzx   eax, ax
0x180041f59  or      eax, 80070000h
0x180041f5e  test    eax, eax
0x180041f60  js      loc_18004200A
0x180041f66  mov     rcx, [rbp+57h+pbstr]; bstrString
0x180041f6a  call    cs:__imp_SysFreeString
0x180041f70  nop
0x180041f71  mov     rcx, [rbp+57h+var_60]
0x180041f75  test    rcx, rcx
0x180041f78  jz      short loc_180041F87
0x180041f7a  mov     rax, [rcx]
0x180041f7d  mov     rax, [rax+10h]
0x180041f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f86  nop
0x180041f87  mov     rcx, [rbp+57h+arg_18]
0x180041f8b  test    rcx, rcx
0x180041f8e  jz      short loc_180041F9D
0x180041f90  mov     rax, [rcx]
0x180041f93  mov     rax, [rax+10h]
0x180041f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f9c  nop
0x180041f9d  lea     r11, [rsp+0E0h+var_20]
0x180041fa5  mov     rbx, [r11+30h]
0x180041fa9  mov     rsi, [r11+38h]
0x180041fad  movaps  xmm6, xmmword ptr [r11-10h]
0x180041fb2  movaps  xmm7, xmmword ptr [r11-20h]
0x180041fb7  mov     rsp, r11
0x180041fba  pop     r15
0x180041fbc  pop     r14
0x180041fbe  pop     r13
0x180041fc0  pop     rdi
0x180041fc1  pop     rbp
0x180041fc2  retn
0x180041fc3  lea     rdx, aMissingChangeI; "Missing change ID in device-resident Pr"...
0x180041fca  lea     rcx, aPrintconfigCco_20; "PrintConfig::CConfigManager::ExtractPri"...
0x180041fd1  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180041fd6  lea     rbx, aV4NoChangeidPr; "V4_No_ChangeID_Present"
0x180041fdd  mov     rax, [rbp+57h+pbstr]
0x180041fe1  cmp     rbx, rax
0x180041fe4  jz      loc_180041F0C
0x180041fea  mov     rcx, rax; bstrString
0x180041fed  call    cs:__imp_SysFreeString
0x180041ff3  mov     rcx, rbx; psz
0x180041ff6  call    cs:__imp_SysAllocString
0x180041ffc  mov     [rbp+57h+pbstr], rax
0x180042000  test    rax, rax
0x180042003  jz      short loc_180042042
0x180042005  jmp     loc_180041F0C
0x18004200a  mov     edx, eax; int
0x18004200c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180042010  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180042015  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004201c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180042020  call    _CxxThrowException_0
0x180042026  mov     edx, eax; int
0x180042028  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004202c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180042031  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180042038  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004203c  call    _CxxThrowException_0
0x180042042  mov     ecx, 8007000Eh; int
0x180042047  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18004204d  mov     edx, eax; int
0x18004204f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180042053  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180042058  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004205f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180042063  call    _CxxThrowException_0
0x180042069  mov     edx, eax; int
0x18004206b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004206f  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180042074  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004207b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004207f  call    _CxxThrowException_0
0x180042085  mov     edx, eax; int
0x180042087  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004208b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180042090  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180042097  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004209b  call    _CxxThrowException_0
0x1800420a1  mov     edx, eax; int
0x1800420a3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800420a7  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800420ac  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800420b3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800420b7  call    _CxxThrowException_0
0x1800420bd  mov     eax, 0Ah
0x1800420c2  mov     word ptr [rbp+57h+pvarg], ax
0x1800420c6  mov     dword ptr [rbp+57h+pvarg+8], 8007000Eh
0x1800420cd  mov     ecx, 8007000Eh; int
0x1800420d2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800420d8  mov     edx, ebx; int
0x1800420da  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800420de  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800420e3  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800420ea  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800420ee  call    _CxxThrowException_0
0x1800420f4  lea     rcx, [rbp+57h+var_68]; this
0x1800420f8  call    ??0CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::CComBSTR(void)
0x1800420fd  nop
0x1800420fe  lea     rcx, [rbp+57h+var_58]
0x180042102  call    ?Get@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAPEBGXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Get(void)
0x180042107  mov     r9, rax
0x18004210a  mov     r8, [rax]
0x18004210d  lea     rcx, [rbp+57h+var_68]
0x180042111  call    ?setbuf@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAAPEAV12@PEAD_J@Z; std::streambuf::setbuf(char *,__int64)
0x180042116  mov     rdx, rax
0x180042119  mov     rcx, r9
0x18004211c  mov     rax, [r8+48h]
0x180042120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042125  mov     rcx, rdi
0x180042128  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004212d  mov     r9, [rbp+57h+var_68]
0x180042131  mov     r8, rax
0x180042134  lea     rdx, aFailedToParseP; "Failed to parse PrintDeviceCapabilities"...
0x18004213b  lea     rcx, aPrintconfigCco_20; "PrintConfig::CConfigManager::ExtractPri"...
0x180042142  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180042147  mov     edx, 80004005h; int
0x18004214c  lea     rcx, [rbp+57h+pExceptionObject]; this
  ... truncated ...
```
