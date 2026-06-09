# DCConfigManagerWrap::GetCurrentNodeXML(ushort const *,ushort const *,ConfigDataType,int,ushort * *)

- ea: `0x1800170a8`
- end: `0x180018072`
- name: `?GetCurrentNodeXML@DCConfigManagerWrap@@AEAAJPEBG0W4ConfigDataType@@HPEAPEAG@Z`
- size: `4042`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015dc8`

## callees

- `0x1800117dc`
- `0x1800170a8`
- `0x180018744`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017fe1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017fe1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017dac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017dac`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017117`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017117`
- `XmlLite!CreateXmlWriter` at `0x180017147`
- `XmlLite!CreateXmlWriter` at `0x180017147`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x1800171a4`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x1800171a4`

## string_xrefs

- `0x1800174b1`: `LocURI`
- `0x18001715a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x1800171b7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x18001722a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x1800172ad`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017332`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x1800173bd`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017448`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x1800174d3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017555`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x1800175d1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x18001764d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x1800176d8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017767`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x1800177fe`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x18001787a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x1800178f6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017994`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017a16`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017a92`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017b0e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017b8d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017c17`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017ccb`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017d43`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017dc7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017e59`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180017eef`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`
- `0x180018044`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcconfigmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DCConfigManagerWrap::GetCurrentNodeXML(
        SIZE_T a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        HLOCAL *a6)
{
  __int64 v6; // rsi
  HLOCAL *v9; // r15
  unsigned int v10; // ebx
  __int64 v11; // rdx
  HRESULT v12; // eax
  HRESULT v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  const unsigned __int16 * near *v25; // rdx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rsi
  int v38; // eax
  int v39; // eax
  int v41; // [rsp+28h] [rbp-59h]
  void *ppvObject; // [rsp+38h] [rbp-49h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+40h] [rbp-41h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-31h] BYREF
  __int64 v46; // [rsp+58h] [rbp-29h] BYREF
  __int64 v47; // [rsp+60h] [rbp-21h]
  LPSTREAM *p_ppstm; // [rsp+68h] [rbp-19h]
  char v49; // [rsp+70h] [rbp-11h]
  void **p_ppvObject; // [rsp+78h] [rbp-9h]
  char v51; // [rsp+80h] [rbp-1h]
  IXmlWriterOutput **p_ppOutput; // [rsp+88h] [rbp+7h]
  char v53; // [rsp+90h] [rbp+Fh]
  HLOCAL *p_hMem; // [rsp+98h] [rbp+17h]
  char v55; // [rsp+A0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+4Fh]
  SIZE_T uBytes; // [rsp+D8h] [rbp+57h] BYREF
  unsigned int v58; // [rsp+E0h] [rbp+5Fh] BYREF

  uBytes = a1;
  v6 = a4;
  hMem = 0;
  if ( !a2 || (v9 = a6) == 0 )
  {
    v10 = -2147024809;
    v11 = 2085;
    goto LABEL_242;
  }
  ppvObject = 0;
  ppOutput = 0;
  v58 = 0;
  ppstm = 0;
  v47 = 0;
  v46 = 0;
  LODWORD(uBytes) = 0;
  v10 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( (v10 & 0x80000000) != 0 )
  {
    v11 = 2098;
LABEL_242:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)v10,
      v41);
    return v10;
  }
  p_ppstm = &ppstm;
  v49 = 1;
  v12 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v10 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v12,
      v41);
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  p_ppvObject = &ppvObject;
  v51 = 1;
  v13 = CreateXmlWriterOutputWithEncodingName((IUnknown *)ppstm, 0, L"UTF-16", &ppOutput);
  v10 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v13,
      v41);
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  p_ppOutput = &ppOutput;
  v53 = 1;
  v14 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppOutput);
  v10 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x856,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v14,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v15 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2);
  v10 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v15,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v16 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 3, 1);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v16,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v17 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
          ppvObject,
          0,
          L"Item",
          0);
  v10 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x860,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v17,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v18 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
          ppvObject,
          0,
          L"Source",
          0);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x867,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v18,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v19 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
          ppvObject,
          0,
          L"LocURI",
          0);
  v10 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v19,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v20 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 224LL))(ppvObject, a2);
  v10 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v20,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v21 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
  v10 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x870,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v21,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v22 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
  v10 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x873,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v22,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v23 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
          ppvObject,
          0,
          L"Meta",
          0);
  v10 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v23,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v24 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)ppvObject + 216LL))(
          ppvObject,
          0,
          L"Format",
          L"syncml:metinf");
  v10 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x87E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v24,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  if ( (unsigned int)v6 > 0xD )
    v25 = 0;
  else
    v25 = (&c_rgszCfgNodeDataType)[v6];
  v26 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 * near *))(*(_QWORD *)ppvObject + 224LL))(
          ppvObject,
          v25);
  v10 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x881,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v26,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v27 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
  v10 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x884,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v27,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v28 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
  v10 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x887,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v28,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  if ( a5 && a3 )
  {
    v29 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
            ppvObject,
            0,
            L"Data",
            0);
    v10 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
        (const char *)(unsigned int)v29,
        v41);
      if ( ppOutput )
      {
        ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
        ppOutput = 0;
      }
      if ( ppvObject )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        ppvObject = 0;
      }
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return v10;
    }
    v30 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 224LL))(ppvObject, a3);
    v10 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
        (const char *)(unsigned int)v30,
        v41);
      if ( ppOutput )
      {
        ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
        ppOutput = 0;
      }
      if ( ppvObject )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        ppvObject = 0;
      }
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return v10;
    }
    v31 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
    v10 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x891,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
        (const char *)(unsigned int)v31,
        v41);
      if ( ppOutput )
      {
        ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
        ppOutput = 0;
      }
      if ( ppvObject )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        ppvObject = 0;
      }
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      return v10;
    }
  }
  v32 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
  v10 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x895,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v32,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v33 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
  v10 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x898,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v33,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v34 = (*(__int64 (__fastcall **)(LPSTREAM, __int64, __int64, __int64 *))(*(_QWORD *)ppstm + 40LL))(
          ppstm,
          v47,
          1,
          &v46);
  v10 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v34,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  if ( HIDWORD(v46) )
  {
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
LABEL_231:
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return 122;
  }
  v35 = ((unsigned int)v46 >> 1) + 1;
  if ( (unsigned int)v35 < (unsigned int)v46 >> 1 )
  {
    v10 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)0x80070216LL,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v36 = ULongLongToULong(2 * v35, (unsigned int *)&uBytes);
  v10 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8AA,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v36,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v37 = (unsigned int)uBytes;
  hMem = LocalAlloc(0x40u, (unsigned int)uBytes);
  if ( !hMem )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)0x8007000ELL,
      v41);
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  p_hMem = &hMem;
  v55 = 1;
  v38 = (*(__int64 (__fastcall **)(LPSTREAM, __int64, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, v47, 0, 0);
  v10 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8BA,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v38,
      v41);
    LocalFree(hMem);
    hMem = 0;
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  v39 = (*(__int64 (__fastcall **)(LPSTREAM, HLOCAL, _QWORD, unsigned int *))(*(_QWORD *)ppstm + 24LL))(
          ppstm,
          hMem,
          (unsigned int)(v37 - 2),
          &v58);
  v10 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8BE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcconfigmanager.cpp",
      (const char *)(unsigned int)v39,
      v41);
    LocalFree(hMem);
    hMem = 0;
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    return v10;
  }
  if ( v37 - 2 != v58 )
  {
    LocalFree(hMem);
    hMem = 0;
    if ( ppOutput )
    {
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
    }
    if ( ppvObject )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
    }
    goto LABEL_231;
  }
  *((_WORD *)hMem + ((unsigned __int64)v58 >> 1)) = 0;
  *v9 = hMem;
  hMem = 0;
  LocalFree(0);
  hMem = 0;
  if ( ppOutput )
  {
    ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
  }
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
  }
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  return 0;
}

```

## disassembly

```asm
0x1800170a8  mov     rax, rsp
0x1800170ab  mov     [rax+18h], rbx
0x1800170af  mov     [rax+20h], rsi
0x1800170b3  mov     [rax+8], rcx
0x1800170b7  push    rbp
0x1800170b8  push    rdi
0x1800170b9  push    r12
0x1800170bb  push    r14
0x1800170bd  push    r15
0x1800170bf  lea     rbp, [rax-4Fh]
0x1800170c3  sub     rsp, 0A0h
0x1800170ca  movsxd  rsi, r9d
0x1800170cd  mov     r14, r8
0x1800170d0  mov     rdi, rdx
0x1800170d3  xor     r12d, r12d
0x1800170d6  mov     [rbp+47h+hMem], r12
0x1800170da  test    rdx, rdx
0x1800170dd  jz      loc_180018037
0x1800170e3  mov     r15, [rbp+47h+arg_28]
0x1800170e7  test    r15, r15
0x1800170ea  jz      loc_180018037
0x1800170f0  mov     [rbp+47h+ppvObject], r12
0x1800170f4  mov     [rbp+47h+ppOutput], r12
0x1800170f8  mov     [rbp+47h+arg_8], r12d
0x1800170fc  mov     [rbp+47h+ppstm], r12
0x180017100  mov     [rbp+47h+var_68], r12
0x180017104  mov     [rbp+47h+var_70], r12
0x180017108  mov     dword ptr [rbp+47h+uBytes], r12d
0x18001710c  lea     r8, [rbp+47h+ppstm]; ppstm
0x180017110  lea     edx, [r12+1]; fDeleteOnRelease
0x180017115  xor     ecx, ecx; hGlobal
0x180017117  call    cs:__imp_CreateStreamOnHGlobal
0x18001711d  mov     ebx, eax
0x18001711f  test    eax, eax
0x180017121  jns     short loc_18001712D
0x180017123  mov     edx, 832h
0x180017128  jmp     loc_180018041
0x18001712d  lea     rax, [rbp+47h+ppstm]
0x180017131  mov     [rbp+47h+var_60], rax
0x180017135  mov     [rbp+47h+var_58], 1
0x180017139  xor     r8d, r8d; pMalloc
0x18001713c  lea     rdx, [rbp+47h+ppvObject]; ppvObject
0x180017140  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180017147  call    cs:__imp_CreateXmlWriter
0x18001714d  mov     ebx, eax
0x18001714f  test    eax, eax
0x180017151  jns     short loc_180017187
0x180017153  mov     rcx, [rbp+4Fh]; this
0x180017157  mov     r9d, eax; char *
0x18001715a  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180017161  mov     edx, 83Eh; void *
0x180017166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001716b  nop
0x18001716c  mov     rcx, [rbp+47h+ppstm]
0x180017170  test    rcx, rcx
0x180017173  jz      short loc_180017182
0x180017175  mov     rax, [rcx]
0x180017178  mov     rax, [rax+10h]
0x18001717c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017181  nop
0x180017182  jmp     loc_180018054
0x180017187  lea     rax, [rbp+47h+ppvObject]
0x18001718b  mov     [rbp+47h+var_50], rax
0x18001718f  mov     [rbp+47h+var_48], 1
0x180017193  lea     r9, [rbp+47h+ppOutput]; ppOutput
0x180017197  lea     r8, pwszEncodingName; "UTF-16"
0x18001719e  xor     edx, edx; pMalloc
0x1800171a0  mov     rcx, [rbp+47h+ppstm]; pOutputStream
0x1800171a4  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x1800171aa  mov     ebx, eax
0x1800171ac  test    eax, eax
0x1800171ae  jns     short loc_1800171FD
0x1800171b0  mov     rcx, [rbp+4Fh]; this
0x1800171b4  mov     r9d, eax; char *
0x1800171b7  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800171be  mov     edx, 84Ah; void *
0x1800171c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800171c8  nop
0x1800171c9  mov     rcx, [rbp+47h+ppvObject]
0x1800171cd  test    rcx, rcx
0x1800171d0  jz      short loc_1800171E2
0x1800171d2  mov     rax, [rcx]
0x1800171d5  mov     rax, [rax+10h]
0x1800171d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171de  mov     [rbp+47h+ppvObject], r12
0x1800171e2  mov     rcx, [rbp+47h+ppstm]
0x1800171e6  test    rcx, rcx
0x1800171e9  jz      short loc_1800171F8
0x1800171eb  mov     rax, [rcx]
0x1800171ee  mov     rax, [rax+10h]
0x1800171f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171f7  nop
0x1800171f8  jmp     loc_180018054
0x1800171fd  lea     rax, [rbp+47h+ppOutput]
0x180017201  mov     [rbp+47h+var_40], rax
0x180017205  mov     [rbp+47h+var_38], 1
0x180017209  mov     rcx, [rbp+47h+ppvObject]
0x18001720d  mov     rax, [rcx]
0x180017210  mov     rdx, [rbp+47h+ppOutput]
0x180017214  mov     rax, [rax+18h]
0x180017218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001721d  mov     ebx, eax
0x18001721f  test    eax, eax
0x180017221  jns     short loc_180017289
0x180017223  mov     rcx, [rbp+4Fh]; this
0x180017227  mov     r9d, eax; char *
0x18001722a  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180017231  mov     edx, 856h; void *
0x180017236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001723b  nop
0x18001723c  mov     rcx, [rbp+47h+ppOutput]
0x180017240  test    rcx, rcx
0x180017243  jz      short loc_180017255
0x180017245  mov     rax, [rcx]
0x180017248  mov     rax, [rax+10h]
0x18001724c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017251  mov     [rbp+47h+ppOutput], r12
0x180017255  mov     rcx, [rbp+47h+ppvObject]
0x180017259  test    rcx, rcx
0x18001725c  jz      short loc_18001726E
0x18001725e  mov     rax, [rcx]
0x180017261  mov     rax, [rax+10h]
0x180017265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001726a  mov     [rbp+47h+ppvObject], r12
0x18001726e  mov     rcx, [rbp+47h+ppstm]
0x180017272  test    rcx, rcx
0x180017275  jz      short loc_180017284
0x180017277  mov     rax, [rcx]
0x18001727a  mov     rax, [rax+10h]
0x18001727e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017283  nop
0x180017284  jmp     loc_180018054
0x180017289  mov     rcx, [rbp+47h+ppvObject]
0x18001728d  mov     rax, [rcx]
0x180017290  xor     r8d, r8d
0x180017293  lea     edx, [r8+2]
0x180017297  mov     rax, [rax+28h]
0x18001729b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172a0  mov     ebx, eax
0x1800172a2  test    eax, eax
0x1800172a4  jns     short loc_18001730C
0x1800172a6  mov     rcx, [rbp+4Fh]; this
0x1800172aa  mov     r9d, eax; char *
0x1800172ad  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800172b4  mov     edx, 85Ah; void *
0x1800172b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800172be  nop
0x1800172bf  mov     rcx, [rbp+47h+ppOutput]
0x1800172c3  test    rcx, rcx
0x1800172c6  jz      short loc_1800172D8
0x1800172c8  mov     rax, [rcx]
0x1800172cb  mov     rax, [rax+10h]
0x1800172cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172d4  mov     [rbp+47h+ppOutput], r12
0x1800172d8  mov     rcx, [rbp+47h+ppvObject]
0x1800172dc  test    rcx, rcx
0x1800172df  jz      short loc_1800172F1
0x1800172e1  mov     rax, [rcx]
0x1800172e4  mov     rax, [rax+10h]
0x1800172e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172ed  mov     [rbp+47h+ppvObject], r12
0x1800172f1  mov     rcx, [rbp+47h+ppstm]
0x1800172f5  test    rcx, rcx
0x1800172f8  jz      short loc_180017307
0x1800172fa  mov     rax, [rcx]
0x1800172fd  mov     rax, [rax+10h]
0x180017301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017306  nop
0x180017307  jmp     loc_180018054
0x18001730c  mov     rcx, [rbp+47h+ppvObject]
0x180017310  mov     rax, [rcx]
0x180017313  mov     edx, 3
0x180017318  lea     r8d, [rdx-2]
0x18001731c  mov     rax, [rax+28h]
0x180017320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017325  mov     ebx, eax
0x180017327  test    eax, eax
0x180017329  jns     short loc_180017391
0x18001732b  mov     rcx, [rbp+4Fh]; this
0x18001732f  mov     r9d, eax; char *
0x180017332  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180017339  mov     edx, 85Dh; void *
0x18001733e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017343  nop
0x180017344  mov     rcx, [rbp+47h+ppOutput]
0x180017348  test    rcx, rcx
0x18001734b  jz      short loc_18001735D
0x18001734d  mov     rax, [rcx]
0x180017350  mov     rax, [rax+10h]
0x180017354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017359  mov     [rbp+47h+ppOutput], r12
0x18001735d  mov     rcx, [rbp+47h+ppvObject]
0x180017361  test    rcx, rcx
0x180017364  jz      short loc_180017376
0x180017366  mov     rax, [rcx]
0x180017369  mov     rax, [rax+10h]
0x18001736d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017372  mov     [rbp+47h+ppvObject], r12
0x180017376  mov     rcx, [rbp+47h+ppstm]
0x18001737a  test    rcx, rcx
0x18001737d  jz      short loc_18001738C
0x18001737f  mov     rax, [rcx]
0x180017382  mov     rax, [rax+10h]
0x180017386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001738b  nop
0x18001738c  jmp     loc_180018054
0x180017391  mov     rcx, [rbp+47h+ppvObject]
0x180017395  mov     rax, [rcx]
0x180017398  xor     r9d, r9d
0x18001739b  lea     r8, aItem; "Item"
0x1800173a2  xor     edx, edx
0x1800173a4  mov     rax, [rax+0D8h]
0x1800173ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173b0  mov     ebx, eax
0x1800173b2  test    eax, eax
0x1800173b4  jns     short loc_18001741C
0x1800173b6  mov     rcx, [rbp+4Fh]; this
0x1800173ba  mov     r9d, eax; char *
0x1800173bd  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800173c4  mov     edx, 860h; void *
0x1800173c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800173ce  nop
0x1800173cf  mov     rcx, [rbp+47h+ppOutput]
0x1800173d3  test    rcx, rcx
0x1800173d6  jz      short loc_1800173E8
0x1800173d8  mov     rax, [rcx]
0x1800173db  mov     rax, [rax+10h]
0x1800173df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173e4  mov     [rbp+47h+ppOutput], r12
0x1800173e8  mov     rcx, [rbp+47h+ppvObject]
0x1800173ec  test    rcx, rcx
0x1800173ef  jz      short loc_180017401
0x1800173f1  mov     rax, [rcx]
0x1800173f4  mov     rax, [rax+10h]
0x1800173f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173fd  mov     [rbp+47h+ppvObject], r12
0x180017401  mov     rcx, [rbp+47h+ppstm]
0x180017405  test    rcx, rcx
0x180017408  jz      short loc_180017417
0x18001740a  mov     rax, [rcx]
0x18001740d  mov     rax, [rax+10h]
0x180017411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017416  nop
0x180017417  jmp     loc_180018054
0x18001741c  mov     rcx, [rbp+47h+ppvObject]
0x180017420  mov     rax, [rcx]
0x180017423  xor     r9d, r9d
0x180017426  lea     r8, aSource; "Source"
0x18001742d  xor     edx, edx
0x18001742f  mov     rax, [rax+0D8h]
0x180017436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001743b  mov     ebx, eax
0x18001743d  test    eax, eax
0x18001743f  jns     short loc_1800174A7
0x180017441  mov     rcx, [rbp+4Fh]; this
0x180017445  mov     r9d, eax; char *
0x180017448  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18001744f  mov     edx, 867h; void *
0x180017454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017459  nop
0x18001745a  mov     rcx, [rbp+47h+ppOutput]
0x18001745e  test    rcx, rcx
0x180017461  jz      short loc_180017473
0x180017463  mov     rax, [rcx]
0x180017466  mov     rax, [rax+10h]
0x18001746a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001746f  mov     [rbp+47h+ppOutput], r12
0x180017473  mov     rcx, [rbp+47h+ppvObject]
0x180017477  test    rcx, rcx
0x18001747a  jz      short loc_18001748C
0x18001747c  mov     rax, [rcx]
0x18001747f  mov     rax, [rax+10h]
0x180017483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017488  mov     [rbp+47h+ppvObject], r12
0x18001748c  mov     rcx, [rbp+47h+ppstm]
0x180017490  test    rcx, rcx
0x180017493  jz      short loc_1800174A2
0x180017495  mov     rax, [rcx]
0x180017498  mov     rax, [rax+10h]
0x18001749c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174a1  nop
0x1800174a2  jmp     loc_180018054
0x1800174a7  mov     rcx, [rbp+47h+ppvObject]
0x1800174ab  mov     rax, [rcx]
0x1800174ae  xor     r9d, r9d
0x1800174b1  lea     r8, aLocuri; "LocURI"
0x1800174b8  xor     edx, edx
0x1800174ba  mov     rax, [rax+0D8h]
0x1800174c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174c6  mov     ebx, eax
0x1800174c8  test    eax, eax
0x1800174ca  jns     short loc_180017532
0x1800174cc  mov     rcx, [rbp+4Fh]; this
0x1800174d0  mov     r9d, eax; char *
0x1800174d3  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800174da  mov     edx, 86Ah; void *
0x1800174df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174e4  nop
0x1800174e5  mov     rcx, [rbp+47h+ppOutput]
0x1800174e9  test    rcx, rcx
  ... truncated ...
```
