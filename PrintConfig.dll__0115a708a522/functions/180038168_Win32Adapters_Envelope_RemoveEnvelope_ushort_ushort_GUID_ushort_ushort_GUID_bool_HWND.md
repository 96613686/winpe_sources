# Win32Adapters::Envelope::RemoveEnvelope(ushort *,ushort * *,_GUID *,ushort * *,ushort * *,_GUID *,bool *,HWND__ * *)

- ea: `0x180038168`
- end: `0x1800388eb`
- name: `?RemoveEnvelope@Envelope@Win32Adapters@@YAXPEAGPEAPEAGPEAU_GUID@@112PEA_NPEAPEAUHWND__@@@Z`
- size: `1923`
- prototype: `void __fastcall(Win32Adapters::Envelope *this, unsigned __int16 *, UUID *, struct _GUID *, unsigned __int16 **, UUID *, struct _GUID *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800330e0`
- `0x1800b5260`

## callees

- `0x180004564`
- `0x18000f830`
- `0x1800109e8`
- `0x180018f58`
- `0x180036f2c`
- `0x180038168`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003843e`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180038494`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003843e`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180038494`
- `OLEAUT32!__imp_SysAllocString` at `0x1800382f5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800383d5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800384d3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800382f5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800383d5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800384d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003830f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800383ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800384ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800385df`
- `OLEAUT32!__imp_SysFreeString` at `0x18003830f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800383ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800384ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800385df`
- `OLEAUT32!__imp_VariantInit` at `0x1800382a4`
- `OLEAUT32!__imp_VariantInit` at `0x1800382a4`
- `OLEAUT32!__imp_VariantClear` at `0x18003831f`
- `OLEAUT32!__imp_VariantClear` at `0x18003838b`
- `OLEAUT32!__imp_VariantClear` at `0x180038408`
- `OLEAUT32!__imp_VariantClear` at `0x18003845e`
- `OLEAUT32!__imp_VariantClear` at `0x180038522`
- `OLEAUT32!__imp_VariantClear` at `0x1800385ce`
- `OLEAUT32!__imp_VariantClear` at `0x18003831f`
- `OLEAUT32!__imp_VariantClear` at `0x18003838b`
- `OLEAUT32!__imp_VariantClear` at `0x180038408`
- `OLEAUT32!__imp_VariantClear` at `0x18003845e`
- `OLEAUT32!__imp_VariantClear` at `0x180038522`
- `OLEAUT32!__imp_VariantClear` at `0x1800385ce`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18003826e`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18003826e`
- `ole32!CoCreateInstance` at `0x1800381b6`
- `ole32!CoCreateInstance` at `0x1800381b6`

## string_xrefs

- `0x18003827a`: `Win32Adapters::Envelope::RemoveEnvelope`
- `0x1800386f0`: `Win32Adapters::Envelope::RemoveEnvelope`
- `0x180038743`: `Win32Adapters::Envelope::RemoveEnvelope`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Win32Adapters::Envelope::RemoveEnvelope(
        Win32Adapters::Envelope *this,
        unsigned __int16 *a2,
        UUID *a3,
        struct _GUID *a4,
        unsigned __int16 **a5,
        UUID *a6,
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
          qword_1802A5A78,
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
      qword_1802A5A78,
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
          qword_1802A5A80,
          &pvarg);
  if ( v18 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v18);
    throw (hr_error *)pExceptionObject;
  }
  Win32Adapters::Guid::GuidFromString((Win32Adapters::Guid *)pvarg.llVal, a3, v19);
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
                qword_1802A5A98,
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
                qword_1802A5AA0,
                &pvarg);
        if ( v23 < 0 )
        {
          hr_error::hr_error((hr_error *)pExceptionObject, v23);
          throw (hr_error *)pExceptionObject;
        }
        *(_QWORD *)a8 = (int)_o__wtol(pvarg.llVal);
      }
      if ( a6 )
        *a6 = GUID_NULL;
      goto LABEL_40;
    }
    VariantClear(&pvarg);
    v20 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v30 + 352LL))(
            v30,
            qword_1802A5A88,
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
        qword_1802A5A88,
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
            qword_1802A5A90,
            &pvarg);
    if ( v25 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v25);
      throw (hr_error *)pExceptionObject;
    }
    Win32Adapters::Guid::GuidFromString((Win32Adapters::Guid *)pvarg.llVal, a6, v26);
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
0x180038168  push    rbp
0x18003816a  push    rbx
0x18003816b  push    rsi
0x18003816c  push    rdi
0x18003816d  push    r12
0x18003816f  push    r14
0x180038171  lea     rbp, [rsp-0Fh]
0x180038176  sub     rsp, 0A8h
0x18003817d  mov     [rbp+37h+var_40], 0FFFFFFFFFFFFFFFEh
0x180038185  mov     r14, r9
0x180038188  mov     rbx, r8
0x18003818b  mov     rsi, rdx
0x18003818e  mov     rdi, rcx
0x180038191  mov     [rbp+37h+var_50], 0
0x180038199  lea     rax, [rbp+37h+var_50]
0x18003819d  mov     [rsp+0D0h+ppv], rax; ppv
0x1800381a2  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x1800381a9  xor     edx, edx; pUnkOuter
0x1800381ab  lea     r8d, [rdx+17h]; dwClsContext
0x1800381af  lea     rcx, rclsid; rclsid
0x1800381b6  call    cs:__imp_CoCreateInstance
0x1800381bd  nop     dword ptr [rax+rax+00h]
0x1800381c2  test    eax, eax
0x1800381c4  js      loc_18003866E
0x1800381ca  xor     eax, eax
0x1800381cc  mov     [rbp+37h+var_A0], ax
0x1800381d0  mov     rcx, [rbp+37h+var_50]
0x1800381d4  mov     rax, [rcx]
0x1800381d7  lea     r8, [rbp+37h+var_A0]
0x1800381db  mov     rdx, rdi
0x1800381de  mov     rax, [rax+208h]
0x1800381e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381ea  test    eax, eax
0x1800381ec  js      loc_18003868A
0x1800381f2  xor     eax, eax
0x1800381f4  cmp     ax, [rbp+37h+var_A0]
0x1800381f8  jz      loc_1800386A6
0x1800381fe  mov     [rbp+37h+var_98], rax
0x180038202  mov     rcx, [rbp+37h+var_50]
0x180038206  mov     rax, [rcx]
0x180038209  lea     rdx, [rbp+37h+var_98]
0x18003820d  mov     rax, [rax+168h]
0x180038214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038219  test    eax, eax
0x18003821b  js      loc_1800386C5
0x180038221  mov     rcx, [rbp+37h+var_98]
0x180038225  test    rcx, rcx
0x180038228  jz      loc_1800386E1
0x18003822e  mov     [rbp+37h+bstrLeft], 0
0x180038236  mov     rax, [rcx]
0x180038239  lea     rdx, [rbp+37h+bstrLeft]
0x18003823d  mov     rax, [rax+158h]
0x180038244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038249  test    eax, eax
0x18003824b  js      loc_180038718
0x180038251  mov     rcx, [rbp+37h+bstrLeft]; bstrLeft
0x180038255  test    rcx, rcx
0x180038258  jz      loc_180038734
0x18003825e  xor     r9d, r9d; dwFlags
0x180038261  mov     r8d, 400h; lcid
0x180038267  mov     rdx, cs:bstrRight; bstrRight
0x18003826e  call    cs:__imp_VarBstrCmp
0x180038275  nop     dword ptr [rax+rax+00h]
0x18003827a  lea     rdi, aWin32adaptersE; "Win32Adapters::Envelope::RemoveEnvelope"
0x180038281  cmp     eax, 1
0x180038284  jz      short loc_1800382A0
0x180038286  mov     r9, cs:bstrRight
0x18003828d  mov     r8, [rbp+37h+bstrLeft]
0x180038291  lea     rdx, aRootTagIsWsNot; "Root tag is %ws not %ws; we may fail la"...
0x180038298  mov     rcx, rdi; char *
0x18003829b  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800382a0  lea     rcx, [rbp+37h+pvarg]; pvarg
0x1800382a4  call    cs:__imp_VariantInit
0x1800382ab  nop     dword ptr [rax+rax+00h]
0x1800382b0  nop
0x1800382b1  mov     rcx, [rbp+37h+var_98]
0x1800382b5  mov     rax, [rcx]
0x1800382b8  lea     r8, [rbp+37h+pvarg]
0x1800382bc  mov     rdx, cs:qword_1802A5A78
0x1800382c3  mov     rax, [rax+160h]
0x1800382ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382cf  test    eax, eax
0x1800382d1  js      loc_18003876B
0x1800382d7  mov     r12d, 8
0x1800382dd  cmp     r12w, word ptr [rbp+37h+pvarg]
0x1800382e2  jnz     loc_180038634
0x1800382e8  mov     rcx, qword ptr [rbp+37h+pvarg+8]; psz
0x1800382ec  test    rcx, rcx
0x1800382ef  jz      loc_180038634
0x1800382f5  call    cs:__imp_SysAllocString
0x1800382fc  nop     dword ptr [rax+rax+00h]
0x180038301  test    rax, rax
0x180038304  jz      loc_180038629
0x18003830a  mov     [rsi], rax
0x18003830d  xor     ecx, ecx; bstrString
0x18003830f  call    cs:__imp_SysFreeString
0x180038316  nop     dword ptr [rax+rax+00h]
0x18003831b  lea     rcx, [rbp+37h+pvarg]; pvarg
0x18003831f  call    cs:__imp_VariantClear
0x180038326  nop     dword ptr [rax+rax+00h]
0x18003832b  mov     rcx, [rbp+37h+var_98]
0x18003832f  mov     rax, [rcx]
0x180038332  lea     r8, [rbp+37h+pvarg]
0x180038336  mov     rdx, cs:qword_1802A5A80
0x18003833d  mov     rax, [rax+160h]
0x180038344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038349  test    eax, eax
0x18003834b  js      loc_180038787
0x180038351  mov     rdx, rbx; unsigned __int16 *
0x180038354  mov     rcx, qword ptr [rbp+37h+pvarg+8]; this
0x180038358  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x18003835d  mov     rax, qword ptr cs:PRINTER_EXTENSION_REASON_PRINT_PREFERENCES
0x180038364  cmp     rax, [rbx]
0x180038367  jnz     loc_1800384C3
0x18003836d  mov     rax, qword ptr cs:PRINTER_EXTENSION_REASON_PRINT_PREFERENCES+8
0x180038374  cmp     rax, [rbx+8]
0x180038378  jnz     loc_1800384C3
0x18003837e  mov     rbx, [rbp+37h+arg_20]
0x180038382  test    rbx, rbx
0x180038385  jz      short loc_1800383FB
0x180038387  lea     rcx, [rbp+37h+pvarg]; pvarg
0x18003838b  call    cs:__imp_VariantClear
0x180038392  nop     dword ptr [rax+rax+00h]
0x180038397  mov     rcx, [rbp+37h+var_98]
0x18003839b  mov     rax, [rcx]
0x18003839e  lea     r8, [rbp+37h+pvarg]
0x1800383a2  mov     rdx, cs:qword_1802A5A88
0x1800383a9  mov     rax, [rax+160h]
0x1800383b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383b5  test    eax, eax
0x1800383b7  js      loc_1800387A3
0x1800383bd  cmp     r12w, word ptr [rbp+37h+pvarg]
0x1800383c2  jnz     loc_1800387DB
0x1800383c8  mov     rcx, qword ptr [rbp+37h+pvarg+8]; psz
0x1800383cc  test    rcx, rcx
0x1800383cf  jz      loc_1800387DB
0x1800383d5  call    cs:__imp_SysAllocString
0x1800383dc  nop     dword ptr [rax+rax+00h]
0x1800383e1  test    rax, rax
0x1800383e4  jz      loc_180038629
0x1800383ea  mov     [rbx], rax
0x1800383ed  xor     ecx, ecx; bstrString
0x1800383ef  call    cs:__imp_SysFreeString
0x1800383f6  nop     dword ptr [rax+rax+00h]
0x1800383fb  mov     rbx, [rbp+37h+arg_30]
0x1800383ff  test    rbx, rbx
0x180038402  jz      short loc_180038451
0x180038404  lea     rcx, [rbp+37h+pvarg]; pvarg
0x180038408  call    cs:__imp_VariantClear
0x18003840f  nop     dword ptr [rax+rax+00h]
0x180038414  mov     rcx, [rbp+37h+var_98]
0x180038418  mov     rax, [rcx]
0x18003841b  lea     r8, [rbp+37h+pvarg]
0x18003841f  mov     rdx, cs:qword_1802A5A98
0x180038426  mov     rax, [rax+160h]
0x18003842d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038432  test    eax, eax
0x180038434  js      loc_1800387BF
0x18003843a  mov     rcx, qword ptr [rbp+37h+pvarg+8]
0x18003843e  call    cs:__imp__o__wtol
0x180038445  nop     dword ptr [rax+rax+00h]
0x18003844a  test    eax, eax
0x18003844c  setnz   al
0x18003844f  mov     [rbx], al
0x180038451  mov     rbx, [rbp+37h+arg_38]
0x180038455  test    rbx, rbx
0x180038458  jz      short loc_1800384A6
0x18003845a  lea     rcx, [rbp+37h+pvarg]; pvarg
0x18003845e  call    cs:__imp_VariantClear
0x180038465  nop     dword ptr [rax+rax+00h]
0x18003846a  mov     rcx, [rbp+37h+var_98]
0x18003846e  mov     rax, [rcx]
0x180038471  lea     r8, [rbp+37h+pvarg]
0x180038475  mov     rdx, cs:qword_1802A5AA0
0x18003847c  mov     rax, [rax+160h]
0x180038483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038488  test    eax, eax
0x18003848a  js      loc_180038815
0x180038490  mov     rcx, qword ptr [rbp+37h+pvarg+8]
0x180038494  call    cs:__imp__o__wtol
0x18003849b  nop     dword ptr [rax+rax+00h]
0x1800384a0  movsxd  rcx, eax
0x1800384a3  mov     [rbx], rcx
0x1800384a6  mov     rax, [rbp+37h+arg_28]
0x1800384aa  test    rax, rax
0x1800384ad  jz      loc_180038560
0x1800384b3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800384ba  movdqu  xmmword ptr [rax], xmm0
0x1800384be  jmp     loc_180038560
0x1800384c3  mov     rbx, [rbp+37h+arg_20]
0x1800384c7  test    rbx, rbx
0x1800384ca  jz      short loc_1800384F9
0x1800384cc  lea     rcx, Filename; psz
0x1800384d3  call    cs:__imp_SysAllocString
0x1800384da  nop     dword ptr [rax+rax+00h]
0x1800384df  test    rax, rax
0x1800384e2  jz      loc_180038629
0x1800384e8  mov     [rbx], rax
0x1800384eb  xor     ecx, ecx; bstrString
0x1800384ed  call    cs:__imp_SysFreeString
0x1800384f4  nop     dword ptr [rax+rax+00h]
0x1800384f9  mov     rax, [rbp+37h+arg_30]
0x1800384fd  test    rax, rax
0x180038500  jz      short loc_180038505
0x180038502  mov     byte ptr [rax], 0
0x180038505  mov     rax, [rbp+37h+arg_38]
0x180038509  test    rax, rax
0x18003850c  jz      short loc_180038515
0x18003850e  mov     qword ptr [rax], 0
0x180038515  mov     rbx, [rbp+37h+arg_28]
0x180038519  test    rbx, rbx
0x18003851c  jz      short loc_180038560
0x18003851e  lea     rcx, [rbp+37h+pvarg]; pvarg
0x180038522  call    cs:__imp_VariantClear
0x180038529  nop     dword ptr [rax+rax+00h]
0x18003852e  mov     rcx, [rbp+37h+var_98]
0x180038532  mov     rax, [rcx]
0x180038535  lea     r8, [rbp+37h+pvarg]
0x180038539  mov     rdx, cs:qword_1802A5A90
0x180038540  mov     rax, [rax+160h]
0x180038547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003854c  test    eax, eax
0x18003854e  js      loc_180038831
0x180038554  mov     rdx, rbx; unsigned __int16 *
0x180038557  mov     rcx, qword ptr [rbp+37h+pvarg+8]; this
0x18003855b  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x180038560  mov     [rbp+37h+var_48], 0
0x180038568  mov     rcx, [rbp+37h+var_98]
0x18003856c  mov     rax, [rcx]
0x18003856f  lea     rdx, [rbp+37h+var_48]
0x180038573  mov     rax, [rax+68h]
0x180038577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003857c  test    eax, eax
0x18003857e  js      loc_18003884D
0x180038584  mov     rcx, [rbp+37h+var_48]
0x180038588  test    rcx, rcx
0x18003858b  jz      loc_180038869
0x180038591  mov     rax, [rcx]
0x180038594  mov     rdx, r14
0x180038597  mov     rax, [rax+0D0h]
0x18003859e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385a3  test    eax, eax
0x1800385a5  js      loc_18003889C
0x1800385ab  test    r14, r14
0x1800385ae  jz      loc_1800388B8
0x1800385b4  mov     rcx, [rbp+37h+var_48]
0x1800385b8  test    rcx, rcx
0x1800385bb  jz      short loc_1800385CA
0x1800385bd  mov     rax, [rcx]
0x1800385c0  mov     rax, [rax+10h]
0x1800385c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385c9  nop
0x1800385ca  lea     rcx, [rbp+37h+pvarg]; pvarg
0x1800385ce  call    cs:__imp_VariantClear
0x1800385d5  nop     dword ptr [rax+rax+00h]
0x1800385da  nop
0x1800385db  mov     rcx, [rbp+37h+bstrLeft]; bstrString
0x1800385df  call    cs:__imp_SysFreeString
0x1800385e6  nop     dword ptr [rax+rax+00h]
0x1800385eb  nop
0x1800385ec  mov     rcx, [rbp+37h+var_98]
0x1800385f0  test    rcx, rcx
0x1800385f3  jz      short loc_180038602
0x1800385f5  mov     rax, [rcx]
0x1800385f8  mov     rax, [rax+10h]
0x1800385fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038601  nop
0x180038602  mov     rcx, [rbp+37h+var_50]
0x180038606  test    rcx, rcx
0x180038609  jz      short loc_180038618
0x18003860b  mov     rax, [rcx]
0x18003860e  mov     rax, [rax+10h]
0x180038612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038617  nop
0x180038618  add     rsp, 0A8h
0x18003861f  pop     r14
0x180038621  pop     r12
0x180038623  pop     rdi
0x180038624  pop     rsi
0x180038625  pop     rbx
0x180038626  pop     rbp
0x180038627  retn
0x180038629  mov     ecx, 8007000Eh; int
0x18003862e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180038634  mov     ebx, 80004005h
0x180038639  mov     r9d, ebx
0x18003863c  mov     r8, cs:qword_1802A5A78
0x180038643  lea     rdx, aUnableToGetAtt; "Unable to get attribute %ws as a BSTR t"...
0x18003864a  mov     rcx, rdi; char *
0x18003864d  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180038652  mov     edx, ebx; int
0x180038654  lea     rcx, [rbp+37h+pExceptionObject]; this
0x180038658  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18003865d  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180038664  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x180038668  call    _CxxThrowException_0
0x18003866e  mov     edx, eax; int
0x180038670  lea     rcx, [rbp+37h+pExceptionObject]; this
0x180038674  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180038679  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
  ... truncated ...
```
