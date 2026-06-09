# Win32Adapters::Envelope::RemoveEnvelope(ushort *,ushort * *,_GUID *,ushort * *,ushort * *,_GUID *,bool *,HWND__ * *)

- ea: `0x180036d30`
- end: `0x180037446`
- name: `?RemoveEnvelope@Envelope@Win32Adapters@@YAXPEAGPEAPEAGPEAU_GUID@@112PEA_NPEAPEAUHWND__@@@Z`
- size: `1814`
- prototype: `void(Win32Adapters::Envelope *__hidden this, unsigned __int16 *, unsigned __int16 **, struct _GUID *, unsigned __int16 **, unsigned __int16 **, struct _GUID *, bool *, HWND *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032130`
- `0x1800b16e0`

## callees

- `0x180004424`
- `0x18000f380`
- `0x18001047c`
- `0x1800183f8`
- `0x180035cdc`
- `0x180036d30`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180036fca`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180037014`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180036fca`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180037014`
- `OLEAUT32!__imp_SysAllocString` at `0x180036eab`
- `OLEAUT32!__imp_SysAllocString` at `0x180036f73`
- `OLEAUT32!__imp_SysAllocString` at `0x18003704d`
- `OLEAUT32!__imp_SysAllocString` at `0x180036eab`
- `OLEAUT32!__imp_SysAllocString` at `0x180036f73`
- `OLEAUT32!__imp_SysAllocString` at `0x18003704d`
- `OLEAUT32!__imp_SysFreeString` at `0x180036ebf`
- `OLEAUT32!__imp_SysFreeString` at `0x180036f87`
- `OLEAUT32!__imp_SysFreeString` at `0x180037061`
- `OLEAUT32!__imp_SysFreeString` at `0x180037141`
- `OLEAUT32!__imp_SysFreeString` at `0x180036ebf`
- `OLEAUT32!__imp_SysFreeString` at `0x180036f87`
- `OLEAUT32!__imp_SysFreeString` at `0x180037061`
- `OLEAUT32!__imp_SysFreeString` at `0x180037141`
- `OLEAUT32!__imp_VariantInit` at `0x180036e60`
- `OLEAUT32!__imp_VariantInit` at `0x180036e60`
- `OLEAUT32!__imp_VariantClear` at `0x180036ec9`
- `OLEAUT32!__imp_VariantClear` at `0x180036f2f`
- `OLEAUT32!__imp_VariantClear` at `0x180036f9a`
- `OLEAUT32!__imp_VariantClear` at `0x180036fe4`
- `OLEAUT32!__imp_VariantClear` at `0x180037090`
- `OLEAUT32!__imp_VariantClear` at `0x180037136`
- `OLEAUT32!__imp_VariantClear` at `0x180036ec9`
- `OLEAUT32!__imp_VariantClear` at `0x180036f2f`
- `OLEAUT32!__imp_VariantClear` at `0x180036f9a`
- `OLEAUT32!__imp_VariantClear` at `0x180036fe4`
- `OLEAUT32!__imp_VariantClear` at `0x180037090`
- `OLEAUT32!__imp_VariantClear` at `0x180037136`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180036e30`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180036e30`
- `ole32!CoCreateInstance` at `0x180036d7e`
- `ole32!CoCreateInstance` at `0x180036d7e`

## string_xrefs

- `0x180036e36`: `Win32Adapters::Envelope::RemoveEnvelope`
- `0x18003724b`: `Win32Adapters::Envelope::RemoveEnvelope`
- `0x18003729e`: `Win32Adapters::Envelope::RemoveEnvelope`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Win32Adapters::Envelope::RemoveEnvelope(
        Win32Adapters::Envelope *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct _GUID *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        struct _GUID *a7,
        bool *a8)
{
  HRESULT v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  BSTR v17; // rax
  int v18; // eax
  struct _GUID *v19; // r8
  int v20; // eax
  unsigned __int16 *v21; // rax
  int v22; // eax
  int v23; // eax
  unsigned __int16 *v24; // rax
  int v25; // eax
  struct _GUID *v26; // r8
  int v27; // eax
  int v28; // eax
  __int16 v29; // [rsp+30h] [rbp-69h] BYREF
  __int64 v30; // [rsp+38h] [rbp-61h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+40h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-39h] BYREF
  BSTR bstrLeft; // [rsp+78h] [rbp-21h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v35[9]; // [rsp+88h] [rbp-11h] BYREF

  v35[1] = -2;
  ppv = 0;
  v12 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( v12 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v12);
    throw (hr_error *)pExceptionObject;
  }
  v29 = 0;
  v13 = (*(__int64 (__fastcall **)(LPVOID, Win32Adapters::Envelope *, __int16 *))(*(_QWORD *)ppv + 520LL))(
          ppv,
          this,
          &v29);
  if ( v13 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v13);
    throw (hr_error *)pExceptionObject;
  }
  if ( !v29 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024809);
    throw (hr_error *)pExceptionObject;
  }
  v30 = 0;
  v14 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 360LL))(ppv, &v30);
  if ( v14 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v14);
    throw (hr_error *)pExceptionObject;
  }
  if ( !v30 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Win32Adapters::Envelope::RemoveEnvelope",
      L"Unable to get document element throwing 0x%x.",
      2147500037LL);
    hr_error::hr_error((hr_error *)pExceptionObject, -2147467259);
    throw (hr_error *)pExceptionObject;
  }
  bstrLeft = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v30 + 344LL))(v30, &bstrLeft);
  if ( v15 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v15);
    throw (hr_error *)pExceptionObject;
  }
  if ( !bstrLeft )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Win32Adapters::Envelope::RemoveEnvelope",
      L"Unable to get tag name throwing 0x%x.",
      2147500037LL);
    hr_error::hr_error((hr_error *)pExceptionObject, -2147467259);
    throw (hr_error *)pExceptionObject;
  }
  if ( VarBstrCmp(bstrLeft, bstrRight, 0x400u, 0) != 1 )
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Win32Adapters::Envelope::RemoveEnvelope",
      L"Root tag is %ws not %ws; we may fail later.",
      bstrLeft,
      bstrRight);
  VariantInit(&pvarg);
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v30 + 352LL))(
          v30,
          qword_18029E8B8,
          &pvarg);
  if ( v16 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v16);
    throw (hr_error *)pExceptionObject;
  }
  if ( pvarg.vt != 8 || !pvarg.llVal )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Win32Adapters::Envelope::RemoveEnvelope",
      L"Unable to get attribute %ws as a BSTR throwing 0x%x.",
      qword_18029E8B8,
      2147500037LL);
    hr_error::hr_error((hr_error *)pExceptionObject, -2147467259);
    throw (hr_error *)pExceptionObject;
  }
  v17 = SysAllocString(pvarg.bstrVal);
  if ( !v17 )
    goto LABEL_51;
  *(_QWORD *)a2 = v17;
  SysFreeString(0);
  VariantClear(&pvarg);
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v30 + 352LL))(
          v30,
          qword_18029E8C0,
          &pvarg);
  if ( v18 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v18);
    throw (hr_error *)pExceptionObject;
  }
  Win32Adapters::Guid::GuidFromString((Win32Adapters::Guid *)pvarg.llVal, (const unsigned __int16 *)a3, v19);
  if ( PRINTER_EXTENSION_REASON_PRINT_PREFERENCES == *(_OWORD *)a3 )
  {
    if ( !a5 )
    {
LABEL_22:
      if ( a7 )
      {
        VariantClear(&pvarg);
        v22 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v30 + 352LL))(
                v30,
                qword_18029E8D8,
                &pvarg);
        if ( v22 < 0 )
        {
          hr_error::hr_error((hr_error *)pExceptionObject, v22);
          throw (hr_error *)pExceptionObject;
        }
        LOBYTE(a7->Data1) = (unsigned int)_o__wtol(pvarg.llVal) != 0;
      }
      if ( a8 )
      {
        VariantClear(&pvarg);
        v23 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v30 + 352LL))(
                v30,
                qword_18029E8E0,
                &pvarg);
        if ( v23 < 0 )
        {
          hr_error::hr_error((hr_error *)pExceptionObject, v23);
          throw (hr_error *)pExceptionObject;
        }
        *(_QWORD *)a8 = (int)_o__wtol(pvarg.llVal);
      }
      if ( a6 )
        *(GUID *)a6 = GUID_NULL;
      goto LABEL_40;
    }
    VariantClear(&pvarg);
    v20 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v30 + 352LL))(
            v30,
            qword_18029E8C8,
            &pvarg);
    if ( v20 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v20);
      throw (hr_error *)pExceptionObject;
    }
    if ( pvarg.vt != 8 || !pvarg.llVal )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Win32Adapters::Envelope::RemoveEnvelope",
        L"Unable to get attribute %ws as a BSTR throwing 0x%x.",
        qword_18029E8C8,
        2147500037LL);
      hr_error::hr_error((hr_error *)pExceptionObject, -2147467259);
      throw (hr_error *)pExceptionObject;
    }
    v21 = SysAllocString(pvarg.bstrVal);
    if ( v21 )
    {
      *a5 = v21;
      SysFreeString(0);
      goto LABEL_22;
    }
LABEL_51:
    ATL::AtlThrowImpl(-2147024882);
  }
  if ( a5 )
  {
    v24 = SysAllocString(&Filename);
    if ( !v24 )
      goto LABEL_51;
    *a5 = v24;
    SysFreeString(0);
  }
  if ( a7 )
    LOBYTE(a7->Data1) = 0;
  if ( a8 )
    *(_QWORD *)a8 = 0;
  if ( a6 )
  {
    VariantClear(&pvarg);
    v25 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v30 + 352LL))(
            v30,
            qword_18029E8D0,
            &pvarg);
    if ( v25 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v25);
      throw (hr_error *)pExceptionObject;
    }
    Win32Adapters::Guid::GuidFromString((Win32Adapters::Guid *)pvarg.llVal, (const unsigned __int16 *)a6, v26);
  }
LABEL_40:
  v35[0] = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v30 + 104LL))(v30, v35);
  if ( v27 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v27);
    throw (hr_error *)pExceptionObject;
  }
  if ( !v35[0] )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Win32Adapters::Envelope::RemoveEnvelope",
      L"Unable to get first child throwing 0x%x.",
      2147500037LL);
    hr_error::hr_error((hr_error *)pExceptionObject, -2147467259);
    throw (hr_error *)pExceptionObject;
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(*(_QWORD *)v35[0] + 208LL))(v35[0], a4);
  if ( v28 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v28);
    throw (hr_error *)pExceptionObject;
  }
  if ( !a4 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "Win32Adapters::Envelope::RemoveEnvelope",
      L"Unable to get text throwing 0x%x.",
      2147500037LL);
    hr_error::hr_error((hr_error *)pExceptionObject, -2147467259);
    throw (hr_error *)pExceptionObject;
  }
  if ( v35[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v35[0] + 16LL))(v35[0]);
  VariantClear(&pvarg);
  SysFreeString(bstrLeft);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x180036d30  push    rbp
0x180036d32  push    rbx
0x180036d33  push    rsi
0x180036d34  push    rdi
0x180036d35  push    r12
0x180036d37  push    r14
0x180036d39  lea     rbp, [rsp-0Fh]
0x180036d3e  sub     rsp, 0A8h
0x180036d45  mov     [rbp+37h+var_40], 0FFFFFFFFFFFFFFFEh
0x180036d4d  mov     r14, r9
0x180036d50  mov     rbx, r8
0x180036d53  mov     rsi, rdx
0x180036d56  mov     rdi, rcx
0x180036d59  mov     [rbp+37h+var_50], 0
0x180036d61  lea     rax, [rbp+37h+var_50]
0x180036d65  mov     [rsp+0D0h+ppv], rax; ppv
0x180036d6a  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180036d71  xor     edx, edx; pUnkOuter
0x180036d73  lea     r8d, [rdx+17h]; dwClsContext
0x180036d77  lea     rcx, rclsid; rclsid
0x180036d7e  call    cs:__imp_CoCreateInstance
0x180036d84  test    eax, eax
0x180036d86  js      loc_1800371C9
0x180036d8c  xor     eax, eax
0x180036d8e  mov     [rbp+37h+var_A0], ax
0x180036d92  mov     rcx, [rbp+37h+var_50]
0x180036d96  mov     rax, [rcx]
0x180036d99  lea     r8, [rbp+37h+var_A0]
0x180036d9d  mov     rdx, rdi
0x180036da0  mov     rax, [rax+208h]
0x180036da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036dac  test    eax, eax
0x180036dae  js      loc_1800371E5
0x180036db4  xor     eax, eax
0x180036db6  cmp     ax, [rbp+37h+var_A0]
0x180036dba  jz      loc_180037201
0x180036dc0  mov     [rbp+37h+var_98], rax
0x180036dc4  mov     rcx, [rbp+37h+var_50]
0x180036dc8  mov     rax, [rcx]
0x180036dcb  lea     rdx, [rbp+37h+var_98]
0x180036dcf  mov     rax, [rax+168h]
0x180036dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ddb  test    eax, eax
0x180036ddd  js      loc_180037220
0x180036de3  mov     rcx, [rbp+37h+var_98]
0x180036de7  test    rcx, rcx
0x180036dea  jz      loc_18003723C
0x180036df0  mov     [rbp+37h+bstrLeft], 0
0x180036df8  mov     rax, [rcx]
0x180036dfb  lea     rdx, [rbp+37h+bstrLeft]
0x180036dff  mov     rax, [rax+158h]
0x180036e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e0b  test    eax, eax
0x180036e0d  js      loc_180037273
0x180036e13  mov     rcx, [rbp+37h+bstrLeft]; bstrLeft
0x180036e17  test    rcx, rcx
0x180036e1a  jz      loc_18003728F
0x180036e20  xor     r9d, r9d; dwFlags
0x180036e23  mov     r8d, 400h; lcid
0x180036e29  mov     rdx, cs:bstrRight; bstrRight
0x180036e30  call    cs:__imp_VarBstrCmp
0x180036e36  lea     rdi, aWin32adaptersE; "Win32Adapters::Envelope::RemoveEnvelope"
0x180036e3d  cmp     eax, 1
0x180036e40  jz      short loc_180036E5C
0x180036e42  mov     r9, cs:bstrRight
0x180036e49  mov     r8, [rbp+37h+bstrLeft]
0x180036e4d  lea     rdx, aRootTagIsWsNot; "Root tag is %ws not %ws; we may fail la"...
0x180036e54  mov     rcx, rdi; char *
0x180036e57  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180036e5c  lea     rcx, [rbp+37h+pvarg]; pvarg
0x180036e60  call    cs:__imp_VariantInit
0x180036e66  nop
0x180036e67  mov     rcx, [rbp+37h+var_98]
0x180036e6b  mov     rax, [rcx]
0x180036e6e  lea     r8, [rbp+37h+pvarg]
0x180036e72  mov     rdx, cs:qword_18029E8B8
0x180036e79  mov     rax, [rax+160h]
0x180036e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e85  test    eax, eax
0x180036e87  js      loc_1800372C6
0x180036e8d  mov     r12d, 8
0x180036e93  cmp     r12w, word ptr [rbp+37h+pvarg]
0x180036e98  jnz     loc_18003718F
0x180036e9e  mov     rcx, qword ptr [rbp+37h+pvarg+8]; psz
0x180036ea2  test    rcx, rcx
0x180036ea5  jz      loc_18003718F
0x180036eab  call    cs:__imp_SysAllocString
0x180036eb1  test    rax, rax
0x180036eb4  jz      loc_180037184
0x180036eba  mov     [rsi], rax
0x180036ebd  xor     ecx, ecx; bstrString
0x180036ebf  call    cs:__imp_SysFreeString
0x180036ec5  lea     rcx, [rbp+37h+pvarg]; pvarg
0x180036ec9  call    cs:__imp_VariantClear
0x180036ecf  mov     rcx, [rbp+37h+var_98]
0x180036ed3  mov     rax, [rcx]
0x180036ed6  lea     r8, [rbp+37h+pvarg]
0x180036eda  mov     rdx, cs:qword_18029E8C0
0x180036ee1  mov     rax, [rax+160h]
0x180036ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036eed  test    eax, eax
0x180036eef  js      loc_1800372E2
0x180036ef5  mov     rdx, rbx; unsigned __int16 *
0x180036ef8  mov     rcx, qword ptr [rbp+37h+pvarg+8]; this
0x180036efc  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x180036f01  mov     rax, qword ptr cs:PRINTER_EXTENSION_REASON_PRINT_PREFERENCES
0x180036f08  cmp     rax, [rbx]
0x180036f0b  jnz     loc_18003703D
0x180036f11  mov     rax, qword ptr cs:PRINTER_EXTENSION_REASON_PRINT_PREFERENCES+8
0x180036f18  cmp     rax, [rbx+8]
0x180036f1c  jnz     loc_18003703D
0x180036f22  mov     rbx, [rbp+37h+arg_20]
0x180036f26  test    rbx, rbx
0x180036f29  jz      short loc_180036F8D
0x180036f2b  lea     rcx, [rbp+37h+pvarg]; pvarg
0x180036f2f  call    cs:__imp_VariantClear
0x180036f35  mov     rcx, [rbp+37h+var_98]
0x180036f39  mov     rax, [rcx]
0x180036f3c  lea     r8, [rbp+37h+pvarg]
0x180036f40  mov     rdx, cs:qword_18029E8C8
0x180036f47  mov     rax, [rax+160h]
0x180036f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f53  test    eax, eax
0x180036f55  js      loc_1800372FE
0x180036f5b  cmp     r12w, word ptr [rbp+37h+pvarg]
0x180036f60  jnz     loc_180037336
0x180036f66  mov     rcx, qword ptr [rbp+37h+pvarg+8]; psz
0x180036f6a  test    rcx, rcx
0x180036f6d  jz      loc_180037336
0x180036f73  call    cs:__imp_SysAllocString
0x180036f79  test    rax, rax
0x180036f7c  jz      loc_180037184
0x180036f82  mov     [rbx], rax
0x180036f85  xor     ecx, ecx; bstrString
0x180036f87  call    cs:__imp_SysFreeString
0x180036f8d  mov     rbx, [rbp+37h+arg_30]
0x180036f91  test    rbx, rbx
0x180036f94  jz      short loc_180036FD7
0x180036f96  lea     rcx, [rbp+37h+pvarg]; pvarg
0x180036f9a  call    cs:__imp_VariantClear
0x180036fa0  mov     rcx, [rbp+37h+var_98]
0x180036fa4  mov     rax, [rcx]
0x180036fa7  lea     r8, [rbp+37h+pvarg]
0x180036fab  mov     rdx, cs:qword_18029E8D8
0x180036fb2  mov     rax, [rax+160h]
0x180036fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fbe  test    eax, eax
0x180036fc0  js      loc_18003731A
0x180036fc6  mov     rcx, qword ptr [rbp+37h+pvarg+8]
0x180036fca  call    cs:__imp__o__wtol
0x180036fd0  test    eax, eax
0x180036fd2  setnz   al
0x180036fd5  mov     [rbx], al
0x180036fd7  mov     rbx, [rbp+37h+arg_38]
0x180036fdb  test    rbx, rbx
0x180036fde  jz      short loc_180037020
0x180036fe0  lea     rcx, [rbp+37h+pvarg]; pvarg
0x180036fe4  call    cs:__imp_VariantClear
0x180036fea  mov     rcx, [rbp+37h+var_98]
0x180036fee  mov     rax, [rcx]
0x180036ff1  lea     r8, [rbp+37h+pvarg]
0x180036ff5  mov     rdx, cs:qword_18029E8E0
0x180036ffc  mov     rax, [rax+160h]
0x180037003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037008  test    eax, eax
0x18003700a  js      loc_180037370
0x180037010  mov     rcx, qword ptr [rbp+37h+pvarg+8]
0x180037014  call    cs:__imp__o__wtol
0x18003701a  movsxd  rcx, eax
0x18003701d  mov     [rbx], rcx
0x180037020  mov     rax, [rbp+37h+arg_28]
0x180037024  test    rax, rax
0x180037027  jz      loc_1800370C8
0x18003702d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180037034  movdqu  xmmword ptr [rax], xmm0
0x180037038  jmp     loc_1800370C8
0x18003703d  mov     rbx, [rbp+37h+arg_20]
0x180037041  test    rbx, rbx
0x180037044  jz      short loc_180037067
0x180037046  lea     rcx, Filename; psz
0x18003704d  call    cs:__imp_SysAllocString
0x180037053  test    rax, rax
0x180037056  jz      loc_180037184
0x18003705c  mov     [rbx], rax
0x18003705f  xor     ecx, ecx; bstrString
0x180037061  call    cs:__imp_SysFreeString
0x180037067  mov     rax, [rbp+37h+arg_30]
0x18003706b  test    rax, rax
0x18003706e  jz      short loc_180037073
0x180037070  mov     byte ptr [rax], 0
0x180037073  mov     rax, [rbp+37h+arg_38]
0x180037077  test    rax, rax
0x18003707a  jz      short loc_180037083
0x18003707c  mov     qword ptr [rax], 0
0x180037083  mov     rbx, [rbp+37h+arg_28]
0x180037087  test    rbx, rbx
0x18003708a  jz      short loc_1800370C8
0x18003708c  lea     rcx, [rbp+37h+pvarg]; pvarg
0x180037090  call    cs:__imp_VariantClear
0x180037096  mov     rcx, [rbp+37h+var_98]
0x18003709a  mov     rax, [rcx]
0x18003709d  lea     r8, [rbp+37h+pvarg]
0x1800370a1  mov     rdx, cs:qword_18029E8D0
0x1800370a8  mov     rax, [rax+160h]
0x1800370af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370b4  test    eax, eax
0x1800370b6  js      loc_18003738C
0x1800370bc  mov     rdx, rbx; unsigned __int16 *
0x1800370bf  mov     rcx, qword ptr [rbp+37h+pvarg+8]; this
0x1800370c3  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x1800370c8  mov     [rbp+37h+var_48], 0
0x1800370d0  mov     rcx, [rbp+37h+var_98]
0x1800370d4  mov     rax, [rcx]
0x1800370d7  lea     rdx, [rbp+37h+var_48]
0x1800370db  mov     rax, [rax+68h]
0x1800370df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370e4  test    eax, eax
0x1800370e6  js      loc_1800373A8
0x1800370ec  mov     rcx, [rbp+37h+var_48]
0x1800370f0  test    rcx, rcx
0x1800370f3  jz      loc_1800373C4
0x1800370f9  mov     rax, [rcx]
0x1800370fc  mov     rdx, r14
0x1800370ff  mov     rax, [rax+0D0h]
0x180037106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003710b  test    eax, eax
0x18003710d  js      loc_1800373F7
0x180037113  test    r14, r14
0x180037116  jz      loc_180037413
0x18003711c  mov     rcx, [rbp+37h+var_48]
0x180037120  test    rcx, rcx
0x180037123  jz      short loc_180037132
0x180037125  mov     rax, [rcx]
0x180037128  mov     rax, [rax+10h]
0x18003712c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037131  nop
0x180037132  lea     rcx, [rbp+37h+pvarg]; pvarg
0x180037136  call    cs:__imp_VariantClear
0x18003713c  nop
0x18003713d  mov     rcx, [rbp+37h+bstrLeft]; bstrString
0x180037141  call    cs:__imp_SysFreeString
0x180037147  nop
0x180037148  mov     rcx, [rbp+37h+var_98]
0x18003714c  test    rcx, rcx
0x18003714f  jz      short loc_18003715E
0x180037151  mov     rax, [rcx]
0x180037154  mov     rax, [rax+10h]
0x180037158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003715d  nop
0x18003715e  mov     rcx, [rbp+37h+var_50]
0x180037162  test    rcx, rcx
0x180037165  jz      short loc_180037174
0x180037167  mov     rax, [rcx]
0x18003716a  mov     rax, [rax+10h]
0x18003716e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037173  nop
0x180037174  add     rsp, 0A8h
0x18003717b  pop     r14
0x18003717d  pop     r12
0x18003717f  pop     rdi
0x180037180  pop     rsi
0x180037181  pop     rbx
0x180037182  pop     rbp
0x180037183  retn
0x180037184  mov     ecx, 8007000Eh; int
0x180037189  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003718f  mov     ebx, 80004005h
0x180037194  mov     r9d, ebx
0x180037197  mov     r8, cs:qword_18029E8B8
0x18003719e  lea     rdx, aUnableToGetAtt; "Unable to get attribute %ws as a BSTR t"...
0x1800371a5  mov     rcx, rdi; char *
0x1800371a8  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800371ad  mov     edx, ebx; int
0x1800371af  lea     rcx, [rbp+37h+pExceptionObject]; this
0x1800371b3  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800371b8  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800371bf  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1800371c3  call    _CxxThrowException_0
0x1800371c9  mov     edx, eax; int
0x1800371cb  lea     rcx, [rbp+37h+pExceptionObject]; this
0x1800371cf  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800371d4  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800371db  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1800371df  call    _CxxThrowException_0
0x1800371e5  mov     edx, eax; int
0x1800371e7  lea     rcx, [rbp+37h+pExceptionObject]; this
0x1800371eb  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800371f0  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800371f7  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1800371fb  call    _CxxThrowException_0
0x180037201  mov     edx, 80070057h; int
0x180037206  lea     rcx, [rbp+37h+pExceptionObject]; this
0x18003720a  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18003720f  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180037216  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x18003721a  call    _CxxThrowException_0
0x180037220  mov     edx, eax; int
0x180037222  lea     rcx, [rbp+37h+pExceptionObject]; this
0x180037226  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18003722b  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
  ... truncated ...
```
