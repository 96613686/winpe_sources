# DeclaredConfigurationStore_GetDocResultInterval(DeclaredConfigurationScopeData *,ushort const *,tagVARIANT *,bool)

- ea: `0x18006e430`
- end: `0x180070d28`
- name: `?DeclaredConfigurationStore_GetDocResultInterval@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAUtagVARIANT@@_N@Z`
- size: `10488`
- prototype: `int(struct DeclaredConfigurationScopeData *, const unsigned __int16 *, struct tagVARIANT *, bool)`
- caller_count: `4`
- callee_count: `44`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180060dec`
- `0x180061a38`
- `0x18006e410`
- `0x18006e420`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x1800117dc`
- `0x180014348`
- `0x18001438c`
- `0x1800143c8`
- `0x18001449c`
- `0x180018768`
- `0x180018a20`
- `0x180018ac0`
- `0x180018b30`
- `0x18001924c`
- `0x180019d38`
- `0x18001c32c`
- `0x18001ca40`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d020`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18001d13c`
- `0x18001d37c`
- `0x18001dea8`
- `0x180055ef0`
- `0x180057630`
- `0x180058148`
- `0x180059cb4`
- `0x18005f464`
- `0x18006e430`
- `0x1800725e0`
- `0x180072f9c`
- `0x180086c10`
- `0x18008e7e4`
- `0x18008ea9c`
- `0x18008f6b0`
- `0x18009888c`
- `0x1800a02dc`
- `0x1800b7b20`
- `0x1800c9f38`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180100ad8`
- `0x18012d59c`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180070acb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180070acb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070408`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070408`
- `OLEAUT32!__imp_SysAllocString` at `0x1800707c4`
- `OLEAUT32!__imp_SysAllocString` at `0x180070a00`
- `OLEAUT32!__imp_SysAllocString` at `0x1800707c4`
- `OLEAUT32!__imp_SysAllocString` at `0x180070a00`
- `OLEAUT32!__imp_VariantInit` at `0x18006e490`
- `OLEAUT32!__imp_VariantInit` at `0x18006e490`
- `OLEAUT32!__imp_VariantClear` at `0x180070a13`
- `OLEAUT32!__imp_VariantClear` at `0x180070a8b`
- `OLEAUT32!__imp_VariantClear` at `0x180070b11`
- `OLEAUT32!__imp_VariantClear` at `0x180070a13`
- `OLEAUT32!__imp_VariantClear` at `0x180070a8b`
- `OLEAUT32!__imp_VariantClear` at `0x180070b11`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006e608`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006e608`
- `XmlLite!CreateXmlWriter` at `0x18006e638`
- `XmlLite!CreateXmlWriter` at `0x18006e638`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18006e68f`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18006e68f`

## string_xrefs

- `0x18006ef32`: `Delete`
- `0x18006eb5f`: `BulkTemplateVersion`
- `0x18006f241`: `BulkTemplateVersion`
- `0x18006f2e1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18006f2bf`: `DeclaredConfigurationStore_GetDocResult`
- `0x18006e85d`: `DeclaredConfigurationResult`
- `0x18006f2b8`: `Cound not get the raw key for the bulk template version`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall DeclaredConfigurationStore_GetDocResultInterval(
        struct DeclaredConfigurationScopeData *a1,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  int EnrollmentIdSidStateDocIdKey; // ebx
  __int64 v8; // rbx
  __int64 v9; // r8
  _WORD *v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  char **v14; // rdx
  _QWORD *v15; // rdx
  int RegistryString; // ebx
  __int64 (__fastcall *v17)(void *, _QWORD, const wchar_t *, _QWORD, char **); // rax
  char **v18; // rdx
  __int64 (__fastcall *v19)(void *, _QWORD, const wchar_t *, _QWORD, const wchar_t *); // rax
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  const wchar_t *v22; // rdx
  __int64 v23; // r8
  char **v24; // rdx
  _QWORD *v25; // rdx
  int v26; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  _QWORD *v28; // rbx
  _QWORD *v29; // rsi
  int v30; // edi
  __int64 v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // rdi
  _QWORD *v34; // rsi
  int v35; // ebx
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rax
  unsigned int v42; // ecx
  int v43; // edi
  __int64 v44; // rbx
  int v45; // esi
  int v46; // edi
  BSTR v47; // rax
  char *v48; // rdi
  char *v49; // rcx
  OLECHAR i; // ax
  __int64 v51; // r8
  __int64 v52; // rbx
  __int64 v53; // rax
  __int64 v54; // rax
  BSTR v55; // rax
  const unsigned __int16 *v56; // rax
  const unsigned __int16 *v57; // r8
  __int16 v58; // ax
  OLECHAR *v59; // rbx
  OLECHAR *j; // rax
  int v61; // [rsp+20h] [rbp-578h]
  int v62; // [rsp+20h] [rbp-578h]
  void *ppvObject; // [rsp+40h] [rbp-558h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-550h] BYREF
  void *Block; // [rsp+50h] [rbp-548h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+58h] [rbp-540h] BYREF
  unsigned __int16 *v67; // [rsp+60h] [rbp-538h] BYREF
  HKEY v68; // [rsp+68h] [rbp-530h] BYREF
  __int64 v69; // [rsp+70h] [rbp-528h] BYREF
  HKEY v70[2]; // [rsp+78h] [rbp-520h] BYREF
  __int64 v71; // [rsp+88h] [rbp-510h]
  __int128 v72; // [rsp+90h] [rbp-508h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-4F8h]
  unsigned int v74; // [rsp+A8h] [rbp-4F0h] BYREF
  OLECHAR *v75; // [rsp+B0h] [rbp-4E8h] BYREF
  LPSTREAM *p_ppstm; // [rsp+B8h] [rbp-4E0h] BYREF
  char v77; // [rsp+C0h] [rbp-4D8h]
  IXmlWriterOutput **p_ppOutput; // [rsp+C8h] [rbp-4D0h] BYREF
  char v79; // [rsp+D0h] [rbp-4C8h]
  void **p_ppvObject; // [rsp+D8h] [rbp-4C0h] BYREF
  char v81; // [rsp+E0h] [rbp-4B8h]
  OLECHAR **p_psz; // [rsp+E8h] [rbp-4B0h] BYREF
  char v83; // [rsp+F0h] [rbp-4A8h]
  void **p_Block; // [rsp+F8h] [rbp-4A0h] BYREF
  char v85; // [rsp+100h] [rbp-498h]
  OLECHAR *psz; // [rsp+108h] [rbp-490h] BYREF
  SIZE_T uBytes; // [rsp+110h] [rbp-488h] BYREF
  __int64 v88; // [rsp+118h] [rbp-480h] BYREF
  __int64 v89; // [rsp+120h] [rbp-478h]
  VARIANTARG pvarg; // [rsp+128h] [rbp-470h] BYREF
  _QWORD v91[4]; // [rsp+140h] [rbp-458h] BYREF
  char *v92[4]; // [rsp+160h] [rbp-438h] BYREF
  _BYTE v93[32]; // [rsp+180h] [rbp-418h] BYREF
  _BYTE v94[32]; // [rsp+1A0h] [rbp-3F8h] BYREF
  _BYTE v95[32]; // [rsp+1C0h] [rbp-3D8h] BYREF
  OLECHAR **v96; // [rsp+1E0h] [rbp-3B8h] BYREF
  unsigned __int16 *v97; // [rsp+1E8h] [rbp-3B0h] BYREF
  char v98; // [rsp+1F0h] [rbp-3A8h]
  char *v99[4]; // [rsp+200h] [rbp-398h] BYREF
  _QWORD v100[4]; // [rsp+220h] [rbp-378h] BYREF
  char *v101; // [rsp+240h] [rbp-358h] BYREF
  char *v102[4]; // [rsp+260h] [rbp-338h] BYREF
  _QWORD v103[18]; // [rsp+280h] [rbp-318h] BYREF
  int v104; // [rsp+310h] [rbp-288h]
  unsigned int v105; // [rsp+318h] [rbp-280h]
  _QWORD v106[28]; // [rsp+320h] [rbp-278h] BYREF
  _QWORD v107[12]; // [rsp+400h] [rbp-198h] BYREF
  _QWORD v108[8]; // [rsp+460h] [rbp-138h] BYREF
  char v109; // [rsp+4A0h] [rbp-F8h]
  _BYTE v110[32]; // [rsp+4F0h] [rbp-A8h] BYREF
  _BYTE v111[32]; // [rsp+510h] [rbp-88h] BYREF
  _BYTE v112[32]; // [rsp+530h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+598h] [rbp+0h]

  Block = 0;
  psz = 0;
  v67 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v67);
    return 2147942487LL;
  }
  VariantInit(a3);
  v68 = 0;
  v70[0] = (HKEY)&v68;
  v70[1] = 0;
  LOBYTE(v71) = 1;
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(a1, a2, &v70[1], 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v70);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_5;
  EnrollmentIdSidStateDocIdKey = DCCDNUtil_GetRegistryString(v68, 0, L"MostRecentVersion", (unsigned __int16 **)&Block);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_5;
  p_Block = &Block;
  v85 = 1;
  DCDocument::DCDocument((DCDocument *)v99);
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  std::wstring::_Assign<unsigned short>(v99, a2, (char *)v9);
  v10 = (_WORD *)*((_QWORD *)a1 + 1);
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  std::wstring::_Assign<unsigned short>(&v101, v10, (char *)v11);
  do
    ++v8;
  while ( *((_WORD *)Block + v8) );
  std::wstring::_Assign<unsigned short>(v102, Block, (char *)v8);
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetMergedResultDocument(
                                   (const unsigned __int16 **)a1,
                                   (struct DCDocument *)v99);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_14;
  ppvObject = 0;
  ppOutput = 0;
  v74 = 0;
  ppstm = 0;
  v89 = 0;
  v88 = 0;
  LODWORD(uBytes) = 0;
  EnrollmentIdSidStateDocIdKey = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    goto LABEL_14;
  p_ppstm = &ppstm;
  v77 = 1;
  EnrollmentIdSidStateDocIdKey = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  p_ppvObject = &ppvObject;
  v81 = 1;
  EnrollmentIdSidStateDocIdKey = CreateXmlWriterOutputWithEncodingName((IUnknown *)ppstm, 0, L"UTF-16", &ppOutput);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  p_ppOutput = &ppOutput;
  v79 = 1;
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(
                                   ppvObject,
                                   ppOutput);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(
                                   ppvObject,
                                   2);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(
                                   ppvObject,
                                   3,
                                   1);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
                                   ppvObject,
                                   0,
                                   L"DeclaredConfigurationResult",
                                   0);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  v12 = v100;
  if ( v100[3] > 7u )
    v12 = (_QWORD *)v100[0];
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD, _QWORD *))(*(_QWORD *)ppvObject + 56LL))(
                                   ppvObject,
                                   0,
                                   L"context",
                                   0,
                                   v12);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  v13 = v103;
  if ( v103[3] > 7u )
    v13 = (_QWORD *)v103[0];
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD, _QWORD *))(*(_QWORD *)ppvObject + 56LL))(
                                   ppvObject,
                                   0,
                                   L"schema",
                                   0,
                                   v13);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  v14 = v99;
  if ( v99[3] > (char *)7 )
    v14 = (char **)v99[0];
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const unsigned __int16 *, _QWORD, char **))(*(_QWORD *)ppvObject + 56LL))(
                                   ppvObject,
                                   0,
                                   L"id",
                                   0,
                                   v14);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  v15 = v107;
  if ( v107[3] > 7u )
    v15 = (_QWORD *)v107[0];
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD, _QWORD *))(*(_QWORD *)ppvObject + 56LL))(
                                   ppvObject,
                                   0,
                                   L"osdefinedscenario",
                                   0,
                                   v15);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  v70[0] = (HKEY)&v67;
  v70[1] = 0;
  LOBYTE(v71) = 1;
  RegistryString = DCCDNUtil_GetRegistryString(v68, 0, L"BulkTemplateVersion", (unsigned __int16 **)&v70[1]);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(v70);
  v17 = *(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, char **))(*(_QWORD *)ppvObject + 56LL);
  if ( RegistryString < 0 )
  {
    v18 = v102;
    if ( v102[3] > (char *)7 )
      v18 = (char **)v102[0];
    EnrollmentIdSidStateDocIdKey = v17(ppvObject, 0, L"checksum", 0, v18);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      if ( ppOutput )
        ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
      if ( ppvObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      ppstm = 0;
      goto LABEL_14;
    }
  }
  else
  {
    EnrollmentIdSidStateDocIdKey = v17(ppvObject, 0, L"checksum", 0, (char **)v67);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      if ( ppOutput )
        ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
      if ( ppvObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      ppstm = 0;
      goto LABEL_14;
    }
  }
  v19 = *(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, const wchar_t *))(*(_QWORD *)ppvObject + 56LL);
  if ( v109 != 1 )
  {
    EnrollmentIdSidStateDocIdKey = v19(
                                     ppvObject,
                                     0,
                                     L"result_checksum",
                                     0,
                                     L"30D5F0FFBEC3B6108ABC170B425E54E523EB20C0F492D735A85A0B7BBC9F9874");
    if ( EnrollmentIdSidStateDocIdKey >= 0 )
      goto LABEL_137;
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
LABEL_14:
    DCDocument::~DCDocument((DCDocument *)v99);
    operator delete(Block);
LABEL_15:
    Block = 0;
LABEL_5:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v68);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v67);
    return (unsigned int)EnrollmentIdSidStateDocIdKey;
  }
  EnrollmentIdSidStateDocIdKey = v19(ppvObject, 0, L"result_checksum", 0, &word_180142E98);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  v20 = v106;
  if ( v106[3] > 7u )
    v20 = (_QWORD *)v106[0];
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, _QWORD *))(*(_QWORD *)ppvObject + 56LL))(
                                   ppvObject,
                                   0,
                                   L"url",
                                   0,
                                   v20);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
LABEL_137:
  v21 = v108;
  if ( v108[3] > 7u )
    v21 = (_QWORD *)v108[0];
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, _QWORD *))(*(_QWORD *)ppvObject + 56LL))(
                                   ppvObject,
                                   0,
                                   L"result_timestamp",
                                   0,
                                   v21);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  std::wstring::wstring((__int64)v92);
  switch ( v104 )
  {
    case 1:
      v22 = L"Set";
      goto LABEL_164;
    case 2:
      v22 = L"Delete";
      v23 = 6;
      goto LABEL_165;
    case 3:
      v22 = L"Download";
      v23 = 8;
      goto LABEL_165;
    case 4:
      v22 = L"Get";
LABEL_164:
      v23 = 3;
      goto LABEL_165;
  }
  v22 = L"NotDefined";
  v23 = 10;
LABEL_165:
  std::wstring::_Assign<unsigned short>(v92, v22, (char *)v23);
  v24 = v92;
  if ( v92[3] > (char *)7 )
    v24 = (char **)v92[0];
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD, char **))(*(_QWORD *)ppvObject + 56LL))(
                                   ppvObject,
                                   0,
                                   L"operation",
                                   0,
                                   v24);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    std::wstring::_Tidy_deallocate(v92);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  std::wstring::wstring((__int64)v91);
  EnrollmentIdSidStateDocIdKey = GetDeclaredConfigurationDocumentState(v105, v91);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  v25 = v91;
  if ( v91[3] > 7u )
    v25 = (_QWORD *)v91[0];
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD, _QWORD *))(*(_QWORD *)ppvObject + 56LL))(
                                   ppvObject,
                                   0,
                                   L"state",
                                   0,
                                   v25);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  v69 = 0;
  v70[0] = (HKEY)&v69;
  v70[1] = 0;
  LOBYTE(v71) = 1;
  EnrollmentIdSidStateDocIdKey = GetEnrollmentIdSidStateDocIdVersionRawKey(
                                   (_DWORD)a1,
                                   (_DWORD)a2,
                                   (_DWORD)Block,
                                   (unsigned int)&v70[1],
                                   0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v70);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    v79 = 0;
    lambda_d5ff8c9817e5a9116541095c6031f66c_::operator()(&p_ppOutput);
    v81 = 0;
    lambda_d5ff8c9817e5a9116541095c6031f66c_::operator()(&p_ppvObject);
    v77 = 0;
    lambda_d5ff8c9817e5a9116541095c6031f66c_::operator()(&p_ppstm);
    goto LABEL_14;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PfximportProperties>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PfximportProperties>::GetImpl'::`2'::impl) )
  {
    v70[0] = (HKEY)&v67;
    v70[1] = 0;
    LOBYTE(v71) = 1;
    v26 = DCCDNUtil_GetRegistryString(v68, 0, L"BulkTemplateVersion", (unsigned __int16 **)&v70[1]);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(v70);
    if ( v26 >= 0 )
    {
      v70[0] = (HKEY)&v69;
      v70[1] = 0;
      LOBYTE(v71) = 1;
      EnrollmentIdSidStateDocIdKey = GetEnrollmentIdSidStateDocIdVersionRawKey(
                                       (_DWORD)a1,
                                       (_DWORD)a2,
                                       (_DWORD)v67,
                                       (unsigned int)&v70[1],
                                       0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v70);
      Logger = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        Logger,
        L"DeclaredConfigurationStore_GetDocResult",
        L"Cound not get the raw key for the bulk template version",
        v67,
        EnrollmentIdSidStateDocIdKey);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4320,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
          v62);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
        std::wstring::_Tidy_deallocate(v91);
        std::wstring::_Tidy_deallocate(v92);
        if ( ppOutput )
          ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
        ppOutput = 0;
        if ( ppvObject )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        ppvObject = 0;
        if ( ppstm )
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        ppstm = 0;
        goto LABEL_14;
      }
    }
  }
  v72 = 0;
  v73 = 0;
  EnrollmentIdSidStateDocIdKey = DCGetReflectedProperties(v69, &v72);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  if ( *((_QWORD *)&v72 + 1) != (_QWORD)v72 )
  {
    EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *, _QWORD, const WCHAR *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
                                     ppvObject,
                                     0,
                                     L"ReflectedProperties",
                                     0);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
      std::wstring::_Tidy_deallocate(v91);
      std::wstring::_Tidy_deallocate(v92);
      if ( ppOutput )
        ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
      if ( ppvObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      ppstm = 0;
      goto LABEL_14;
    }
    v28 = **(_QWORD ***)v72;
    v29 = *(_QWORD **)(*(_QWORD *)v72 + 8LL);
    while ( v28 != v29 )
    {
      if ( *(_DWORD *)(*v28 + 64LL) == 1 )
      {
        v30 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
                ppvObject,
                0,
                L"Property",
                0);
        if ( v30 < 0 )
        {
          std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
          std::wstring::_Tidy_deallocate(v91);
          std::wstring::_Tidy_deallocate(v92);
          if ( ppOutput )
            ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
          ppOutput = 0;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          ppvObject = 0;
          if ( ppstm )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
          ppstm = 0;
          goto LABEL_274;
        }
        v31 = std::wstring::c_str(*v28);
        v30 = (*(__int64 (__fastcall **)(void *, _QWORD, const unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)ppvObject + 56LL))(
                ppvObject,
                0,
                L"name",
                0,
                v31);
        if ( v30 < 0 )
        {
          std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
          std::wstring::_Tidy_deallocate(v91);
          std::wstring::_Tidy_deallocate(v92);
          if ( ppOutput )
            ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
          ppOutput = 0;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          ppvObject = 0;
          if ( ppstm )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
          ppstm = 0;
          goto LABEL_274;
        }
        v30 = (*(__int64 (__fastcall **)(void *, _QWORD, const unsigned __int16 *, _QWORD, const char *))(*(_QWORD *)ppvObject + 56LL))(
                ppvObject,
                0,
                L"type",
                0,
                L"chr");
        if ( v30 < 0 )
        {
          std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
          std::wstring::_Tidy_deallocate(v91);
          std::wstring::_Tidy_deallocate(v92);
          if ( ppOutput )
            ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
          ppOutput = 0;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          ppvObject = 0;
          if ( ppstm )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
          ppstm = 0;
          goto LABEL_274;
        }
        v32 = std::wstring::c_str(*v28 + 32LL);
        v30 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 224LL))(ppvObject, v32);
        if ( v30 < 0 )
        {
          std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
          std::wstring::_Tidy_deallocate(v91);
          std::wstring::_Tidy_deallocate(v92);
          if ( ppOutput )
            ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
          ppOutput = 0;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          ppvObject = 0;
          if ( ppstm )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
          ppstm = 0;
          goto LABEL_274;
        }
        v30 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
        if ( v30 < 0 )
        {
          std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
          std::wstring::_Tidy_deallocate(v91);
          std::wstring::_Tidy_deallocate(v92);
          if ( ppOutput )
            ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
          ppOutput = 0;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          ppvObject = 0;
          if ( ppstm )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
          ppstm = 0;
LABEL_274:
          DCDocument::~DCDocument((DCDocument *)v99);
          operator delete(Block);
          Block = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v68);
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v67);
          return (unsigned int)v30;
        }
      }
      v28 += 2;
    }
    EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
    if ( EnrollmentIdSidStateDocIdKey < 0 )
    {
      std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
      std::wstring::_Tidy_deallocate(v91);
      std::wstring::_Tidy_deallocate(v92);
      if ( ppOutput )
        ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
      ppOutput = 0;
      if ( ppvObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      ppvObject = 0;
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      ppstm = 0;
      goto LABEL_14;
    }
  }
  std::wstring::wstring((__int64)v95);
  std::wstring::wstring((__int64)v94);
  std::wstring::wstring((__int64)v93);
  *(_OWORD *)v70 = 0;
  v71 = 0;
  v33 = (_QWORD *)v103[4];
  v34 = (_QWORD *)v103[5];
  while ( v33 != v34 )
  {
    v35 = (**(__int64 (__fastcall ***)(_QWORD))*v33)(*v33);
    if ( v35 == 1 )
    {
      v36 = _RTDynamicCast_0(*v33, 0, &DCProvider `RTTI Type Descriptor', &DCCSP `RTTI Type Descriptor', 0);
      if ( !v36 )
      {
        std::wstring::_Tidy_deallocate(v93);
        std::wstring::_Tidy_deallocate(v94);
        std::wstring::_Tidy_deallocate(v95);
        std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
        std::wstring::_Tidy_deallocate(v91);
        std::wstring::_Tidy_deallocate(v92);
        if ( ppOutput )
          ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
        ppOutput = 0;
        if ( ppvObject )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        ppvObject = 0;
        if ( ppstm )
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        ppstm = 0;
LABEL_310:
        DCDocument::~DCDocument((DCDocument *)v99);
        operator delete(Block);
        EnrollmentIdSidStateDocIdKey = -2147418113;
        goto LABEL_15;
      }
      v37 = std::wstring::wstring((__int64)&v96, v91);
      EnrollmentIdSidStateDocIdKey = CSPProviderWriteCSPResults(ppvObject, v36, v37);
      if ( EnrollmentIdSidStateDocIdKey < 0 )
      {
        std::wstring::_Tidy_deallocate(v93);
        std::wstring::_Tidy_deallocate(v94);
        std::wstring::_Tidy_deallocate(v95);
        std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
        std::wstring::_Tidy_deallocate(v91);
        std::wstring::_Tidy_deallocate(v92);
        if ( ppOutput )
          ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
        ppOutput = 0;
        if ( ppvObject )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        ppvObject = 0;
        if ( ppstm )
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        ppstm = 0;
        goto LABEL_14;
      }
    }
    else if ( v35 == 2 )
    {
      v38 = _RTDynamicCast_0(*v33, 0, &DCProvider `RTTI Type Descriptor', &DCDSCNative `RTTI Type Descriptor', 0);
      if ( !v38 )
      {
        std::wstring::_Tidy_deallocate(v93);
        std::wstring::_Tidy_deallocate(v94);
        std::wstring::_Tidy_deallocate(v95);
        std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
        std::wstring::_Tidy_deallocate(v91);
        std::wstring::_Tidy_deallocate(v92);
        if ( ppOutput )
          ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
        ppOutput = 0;
        if ( ppvObject )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        ppvObject = 0;
        if ( ppstm )
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        ppstm = 0;
        goto LABEL_310;
      }
      v39 = std::wstring::wstring((__int64)&v96, v91);
      DSCNativeProviderWriteDSCResults(ppvObject, v38, v39);
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        std::wstring::_Tidy_deallocate(v93);
        std::wstring::_Tidy_deallocate(v94);
        std::wstring::_Tidy_deallocate(v95);
        std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
        std::wstring::_Tidy_deallocate(v91);
        std::wstring::_Tidy_deallocate(v92);
        if ( ppOutput )
          ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
        ppOutput = 0;
        if ( ppvObject )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
        ppvObject = 0;
        if ( ppstm )
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        ppstm = 0;
        goto LABEL_310;
      }
      if ( v35 == 3 )
      {
        v40 = _RTDynamicCast_0(*v33, 0, &DCProvider `RTTI Type Descriptor', &DCCSP `RTTI Type Descriptor', 0);
        if ( !v40 )
        {
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v94);
          std::wstring::_Tidy_deallocate(v95);
          std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
          std::wstring::_Tidy_deallocate(v91);
          std::wstring::_Tidy_deallocate(v92);
          if ( ppOutput )
            ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
          ppOutput = 0;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          ppvObject = 0;
          if ( ppstm )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
          ppstm = 0;
          goto LABEL_310;
        }
        v41 = std::wstring::wstring((__int64)&v96, v91);
        EnrollmentIdSidStateDocIdKey = RegistryProviderWriteRegistryResults(ppvObject, v40, v41);
        if ( EnrollmentIdSidStateDocIdKey < 0 )
        {
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v94);
          std::wstring::_Tidy_deallocate(v95);
          std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
          std::wstring::_Tidy_deallocate(v91);
          std::wstring::_Tidy_deallocate(v92);
          if ( ppOutput )
            ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
          ppOutput = 0;
          if ( ppvObject )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
          ppvObject = 0;
          if ( ppstm )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
          ppstm = 0;
          goto LABEL_14;
        }
      }
    }
    v33 += 2;
  }
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 120LL))(ppvObject);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  EnrollmentIdSidStateDocIdKey = (*(__int64 (__fastcall **)(LPSTREAM, __int64, __int64, __int64 *))(*(_QWORD *)ppstm
                                                                                                  + 40LL))(
                                   ppstm,
                                   v89,
                                   1,
                                   &v88);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    goto LABEL_14;
  }
  if ( HIDWORD(v88) )
  {
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
    DCDocument::~DCDocument((DCDocument *)v99);
    operator delete(Block);
    EnrollmentIdSidStateDocIdKey = 122;
    goto LABEL_15;
  }
  v42 = ((unsigned int)v88 >> 1) + 1;
  if ( v42 < (unsigned int)v88 >> 1 )
  {
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    if ( ppOutput )
      ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
    ppOutput = 0;
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppstm);
    DCDocument::~DCDocument((DCDocument *)v99);
    wil::details::ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___::_ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___(&p_Block);
    EnrollmentIdSidStateDocIdKey = -2147024362;
    goto LABEL_5;
  }
  EnrollmentIdSidStateDocIdKey = ULongMult(v42, 2u, (unsigned int *)&uBytes);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
LABEL_365:
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(v70);
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppOutput);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppvObject);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppstm);
    DCDocument::~DCDocument((DCDocument *)v99);
    wil::details::ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___::_ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___(&p_Block);
    goto LABEL_5;
  }
  v43 = uBytes;
  v44 = (unsigned int)uBytes;
  psz = (OLECHAR *)LocalAlloc(0x40u, (unsigned int)uBytes);
  if ( !psz )
  {
LABEL_367:
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(v70);
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppOutput);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppvObject);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppstm);
    DCDocument::~DCDocument((DCDocument *)v99);
    wil::details::ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___::_ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___(&p_Block);
    EnrollmentIdSidStateDocIdKey = -2147024882;
    goto LABEL_5;
  }
  p_psz = &psz;
  v83 = 1;
  v45 = (*(__int64 (__fastcall **)(LPSTREAM, __int64, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, v89, 0, 0);
  if ( v45 < 0 )
  {
    wil::details::ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___::_ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___(&p_psz);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(v70);
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppOutput);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppvObject);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppstm);
    DCDocument::~DCDocument((DCDocument *)v99);
    wil::details::ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___::_ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___(&p_Block);
    EnrollmentIdSidStateDocIdKey = v45;
    goto LABEL_5;
  }
  v46 = (*(__int64 (__fastcall **)(LPSTREAM, OLECHAR *, _QWORD, unsigned int *))(*(_QWORD *)ppstm + 24LL))(
          ppstm,
          psz,
          (unsigned int)(v43 - 2),
          &v74);
  if ( v46 < 0 )
  {
    wil::details::ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___::_ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___(&p_psz);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(v70);
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppOutput);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppvObject);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppstm);
    DCDocument::~DCDocument((DCDocument *)v99);
    wil::details::ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___::_ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___(&p_Block);
    EnrollmentIdSidStateDocIdKey = v46;
    goto LABEL_5;
  }
  if ( v44 - 2 != v74 )
  {
    wil::details::ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___::_ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___(&p_psz);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(v70);
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppOutput);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppvObject);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppstm);
    DCDocument::~DCDocument((DCDocument *)v99);
    wil::details::ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___::_ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___(&p_Block);
    EnrollmentIdSidStateDocIdKey = 122;
    goto LABEL_5;
  }
  psz[(unsigned __int64)v74 >> 1] = 0;
  v47 = SysAllocString(psz);
  v48 = (char *)v47;
  if ( !v47 )
  {
LABEL_375:
    wil::details::ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___::_ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___(&p_psz);
    goto LABEL_367;
  }
  v49 = (char *)v47;
  for ( i = *v47; i && i != 62; i = *(_WORD *)v49 )
    v49 += 2;
  if ( !*(_WORD *)v49 )
  {
    wil::details::ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___::_ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___(&p_psz);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(v70);
    std::wstring::_Tidy_deallocate(v93);
    std::wstring::_Tidy_deallocate(v94);
    std::wstring::_Tidy_deallocate(v95);
    std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppOutput);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppvObject);
    wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppstm);
    DCDocument::~DCDocument((DCDocument *)v99);
    wil::details::ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___::_ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___(&p_Block);
    EnrollmentIdSidStateDocIdKey = -2147418113;
    goto LABEL_5;
  }
  v51 = (unsigned int)((v49 - v48 + 2) >> 1);
  v74 -= 2 * v51;
  v75 = 0;
  v96 = &v75;
  v97 = 0;
  v98 = 1;
  EnrollmentIdSidStateDocIdKey = GetResultChecksum((unsigned __int8 *)&psz[v51], v74, &v97);
  wil::details::out_param_t<std::unique_ptr<unsigned char [0]>>::~out_param_t<std::unique_ptr<unsigned char [0]>>(&v96);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
LABEL_383:
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v75);
    wil::details::ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___::_ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___(&p_psz);
    goto LABEL_365;
  }
  std::wstring::wstring((__int64)&v96);
  try
  {
    v52 = std::wstring::wstring((__int64)v112, (__int64)L"\\raw");
    v53 = std::wstring::wstring((__int64)v111, (__int64)Block);
    v54 = std::operator+<unsigned short>(v110, v53, v52);
    std::wstring::operator=(&v96, v54);
    std::wstring::_Tidy_deallocate(v110);
    std::wstring::_Tidy_deallocate(v111);
    std::wstring::_Tidy_deallocate(v112);
    ATL::CComVariant::CComVariant(&pvarg);
    v55 = SysAllocString(v75);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4421,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      v61);
    goto LABEL_400;
  }
  if ( !v55 )
  {
    VariantClear(&pvarg);
LABEL_400:
    std::wstring::_Tidy_deallocate(&v96);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v75);
    goto LABEL_375;
  }
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)v55;
  std::wstring::c_str(v102);
  v56 = (const unsigned __int16 *)std::wstring::c_str(v99);
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_WriteResultData(
                                   a1,
                                   v56,
                                   v57,
                                   0,
                                   0,
                                   0,
                                   L"resultchecksum",
                                   &pvarg);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
  {
    VariantClear(&pvarg);
    std::wstring::_Tidy_deallocate(&v96);
    goto LABEL_383;
  }
  if ( !v109 )
  {
    v58 = *(_WORD *)v48;
    if ( *(_WORD *)v48 )
    {
      v59 = (OLECHAR *)v48;
      while ( v58 != 62 )
      {
        if ( !(unsigned int)_o__wcsnicmp(v59, L"30D5F0FFBEC3B6108ABC170B425E54E523EB20C0F492D735A85A0B7BBC9F9874", 64) )
        {
          for ( j = v75; *j; ++j )
            *v59++ = *j;
          break;
        }
        v58 = *++v59;
        if ( !*v59 )
          break;
      }
    }
  }
  a3->vt = 8;
  a3->llVal = (LONGLONG)v48;
  VariantClear(&pvarg);
  std::wstring::_Tidy_deallocate(&v96);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v75);
  wil::details::ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___::_ScopeExitFn__lambda_4b4b83bc48aacbb9d4e61734a52bcf4a___(&p_psz);
  std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(v70);
  std::wstring::_Tidy_deallocate(v93);
  std::wstring::_Tidy_deallocate(v94);
  std::wstring::_Tidy_deallocate(v95);
  std::vector<std::shared_ptr<SCDScenarioInfo>>::~vector<std::shared_ptr<SCDScenarioInfo>>(&v72);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
  std::wstring::_Tidy_deallocate(v91);
  std::wstring::_Tidy_deallocate(v92);
  wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppOutput);
  wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppvObject);
  wil::details::ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___::_ScopeExitFn__lambda_d5ff8c9817e5a9116541095c6031f66c___(&p_ppstm);
  DCDocument::~DCDocument((DCDocument *)v99);
  wil::details::ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___::_ScopeExitFn__lambda_6fafa08fdcce94e67b46979a522bcd38___(&p_Block);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v68);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v67);
  return 0;
}

```

## disassembly

```asm
0x18006e430  push    rbx
0x18006e432  push    rsi
0x18006e433  push    rdi
0x18006e434  push    r12
0x18006e436  push    r13
0x18006e438  push    r14
0x18006e43a  push    r15
0x18006e43c  sub     rsp, 560h
0x18006e443  mov     rax, cs:__security_cookie
0x18006e44a  xor     rax, rsp
0x18006e44d  mov     [rsp+598h+var_48], rax
0x18006e455  mov     r13, r8
0x18006e458  mov     rdi, rdx
0x18006e45b  mov     r15, rcx
0x18006e45e  xor     esi, esi
0x18006e460  mov     [rsp+598h+Block], rsi
0x18006e465  mov     [rsp+598h+psz], rsi
0x18006e46d  mov     [rsp+598h+var_538], rsi
0x18006e472  test    rcx, rcx
0x18006e475  jz      loc_180070CF6
0x18006e47b  test    rdx, rdx
0x18006e47e  jz      loc_180070CF6
0x18006e484  test    r8, r8
0x18006e487  jz      loc_180070CF6
0x18006e48d  mov     rcx, r8; pvarg
0x18006e490  call    cs:__imp_VariantInit
0x18006e496  mov     [rsp+598h+var_530], rsi
0x18006e49b  lea     rax, [rsp+598h+var_530]
0x18006e4a0  mov     [rsp+598h+var_520], rax
0x18006e4a5  mov     [rsp+598h+var_520+8], rsi
0x18006e4ad  lea     r14d, [rsi+1]
0x18006e4b1  mov     byte ptr [rsp+598h+var_510], r14b
0x18006e4b9  xor     r9d, r9d; int
0x18006e4bc  lea     r8, [rsp+598h+var_520+8]; HKEY *
0x18006e4c4  mov     rdx, rdi; unsigned __int16 *
0x18006e4c7  mov     rcx, r15; struct DeclaredConfigurationScopeData *
0x18006e4ca  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x18006e4cf  mov     ebx, eax
0x18006e4d1  lea     rcx, [rsp+598h+var_520]
0x18006e4d6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18006e4db  test    ebx, ebx
0x18006e4dd  jns     short loc_18006E4FB
0x18006e4df  lea     rcx, [rsp+598h+var_530]
0x18006e4e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006e4e9  nop
0x18006e4ea  lea     rcx, [rsp+598h+var_538]
0x18006e4ef  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18006e4f4  mov     eax, ebx
0x18006e4f6  jmp     loc_180070D05
0x18006e4fb  lea     r9, [rsp+598h+Block]; unsigned __int16 **
0x18006e500  lea     r8, aMostrecentvers; "MostRecentVersion"
0x18006e507  xor     edx, edx; unsigned __int16 *
0x18006e509  mov     rcx, [rsp+598h+var_530]; HKEY
0x18006e50e  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18006e513  mov     ebx, eax
0x18006e515  test    eax, eax
0x18006e517  js      short loc_18006E4DF
0x18006e519  lea     rax, [rsp+598h+Block]
0x18006e51e  mov     [rsp+598h+var_4A0], rax
0x18006e526  mov     [rsp+598h+var_498], r14b
0x18006e52e  lea     rcx, [rsp+598h+var_398]; this
0x18006e536  call    ??0DCDocument@@QEAA@XZ; DCDocument::DCDocument(void)
0x18006e53b  nop
0x18006e53c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006e540  mov     r8, rbx
0x18006e543  inc     r8
0x18006e546  cmp     [rdi+r8*2], si
0x18006e54b  jnz     short loc_18006E543
0x18006e54d  mov     rdx, rdi
0x18006e550  lea     rcx, [rsp+598h+var_398]
0x18006e558  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18006e55d  mov     rdx, [r15+8]
0x18006e561  mov     r8, rbx
0x18006e564  inc     r8
0x18006e567  cmp     [rdx+r8*2], si
0x18006e56c  jnz     short loc_18006E564
0x18006e56e  lea     rcx, [rsp+598h+var_358]
0x18006e576  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18006e57b  mov     rdx, [rsp+598h+Block]
0x18006e580  inc     rbx
0x18006e583  cmp     [rdx+rbx*2], si
0x18006e587  jnz     short loc_18006E580
0x18006e589  mov     r8, rbx
0x18006e58c  lea     rcx, [rsp+598h+var_338]
0x18006e594  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18006e599  lea     rdx, [rsp+598h+var_398]; struct DCDocument *
0x18006e5a1  mov     rcx, r15; struct DeclaredConfigurationScopeData *
0x18006e5a4  call    ?DeclaredConfigurationStore_GetMergedResultDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@@Z; DeclaredConfigurationStore_GetMergedResultDocument(DeclaredConfigurationScopeData *,DCDocument *)
0x18006e5a9  mov     ebx, eax
0x18006e5ab  test    eax, eax
0x18006e5ad  jns     short loc_18006E5D1
0x18006e5af  lea     rcx, [rsp+598h+var_398]; this
0x18006e5b7  call    ??1DCDocument@@QEAA@XZ; DCDocument::~DCDocument(void)
0x18006e5bc  nop
0x18006e5bd  mov     rcx, [rsp+598h+Block]; Block
0x18006e5c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e5c7  mov     [rsp+598h+Block], rsi
0x18006e5cc  jmp     loc_18006E4DF
0x18006e5d1  mov     [rsp+598h+ppvObject], rsi
0x18006e5d6  mov     [rsp+598h+ppOutput], rsi
0x18006e5db  mov     [rsp+598h+var_4F0], esi
0x18006e5e2  mov     [rsp+598h+ppstm], rsi
0x18006e5e7  mov     [rsp+598h+var_478], rsi
0x18006e5ef  mov     [rsp+598h+var_480], rsi
0x18006e5f7  mov     dword ptr [rsp+598h+uBytes], esi
0x18006e5fe  lea     r8, [rsp+598h+ppstm]; ppstm
0x18006e603  mov     edx, r14d; fDeleteOnRelease
0x18006e606  xor     ecx, ecx; hGlobal
0x18006e608  call    cs:__imp_CreateStreamOnHGlobal
0x18006e60e  mov     ebx, eax
0x18006e610  test    eax, eax
0x18006e612  js      short loc_18006E5AF
0x18006e614  lea     rax, [rsp+598h+ppstm]
0x18006e619  mov     [rsp+598h+var_4E0], rax
0x18006e621  mov     [rsp+598h+var_4D8], r14b
0x18006e629  xor     r8d, r8d; pMalloc
0x18006e62c  lea     rdx, [rsp+598h+ppvObject]; ppvObject
0x18006e631  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18006e638  call    cs:__imp_CreateXmlWriter
0x18006e63e  mov     ebx, eax
0x18006e640  test    eax, eax
0x18006e642  jns     short loc_18006E667
0x18006e644  mov     rdx, [rsp+598h+ppstm]
0x18006e649  test    rdx, rdx
0x18006e64c  jz      short loc_18006E65D
0x18006e64e  mov     rcx, [rdx]
0x18006e651  mov     rax, [rcx+10h]
0x18006e655  mov     rcx, rdx
0x18006e658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e65d  mov     [rsp+598h+ppstm], rsi
0x18006e662  jmp     loc_18006E5AF
0x18006e667  lea     rax, [rsp+598h+ppvObject]
0x18006e66c  mov     [rsp+598h+var_4C0], rax
0x18006e674  mov     [rsp+598h+var_4B8], r14b
0x18006e67c  lea     r9, [rsp+598h+ppOutput]; ppOutput
0x18006e681  lea     r8, pwszEncodingName; "UTF-16"
0x18006e688  xor     edx, edx; pMalloc
0x18006e68a  mov     rcx, [rsp+598h+ppstm]; pOutputStream
0x18006e68f  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18006e695  mov     ebx, eax
0x18006e697  test    eax, eax
0x18006e699  jns     short loc_18006E6D9
0x18006e69b  mov     rdx, [rsp+598h+ppvObject]
0x18006e6a0  test    rdx, rdx
0x18006e6a3  jz      short loc_18006E6B4
0x18006e6a5  mov     rcx, [rdx]
0x18006e6a8  mov     rax, [rcx+10h]
0x18006e6ac  mov     rcx, rdx
0x18006e6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e6b4  mov     [rsp+598h+ppvObject], rsi
0x18006e6b9  mov     rcx, [rsp+598h+ppstm]
0x18006e6be  test    rcx, rcx
0x18006e6c1  jz      short loc_18006E6CF
0x18006e6c3  mov     rax, [rcx]
0x18006e6c6  mov     rax, [rax+10h]
0x18006e6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e6cf  mov     [rsp+598h+ppstm], rsi
0x18006e6d4  jmp     loc_18006E5AF
0x18006e6d9  lea     rax, [rsp+598h+ppOutput]
0x18006e6de  mov     [rsp+598h+var_4D0], rax
0x18006e6e6  mov     [rsp+598h+var_4C8], r14b
0x18006e6ee  mov     rcx, [rsp+598h+ppvObject]
0x18006e6f3  mov     rax, [rcx]
0x18006e6f6  mov     rdx, [rsp+598h+ppOutput]
0x18006e6fb  mov     rax, [rax+18h]
0x18006e6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e704  mov     ebx, eax
0x18006e706  test    eax, eax
0x18006e708  jns     short loc_18006E763
0x18006e70a  mov     rdx, [rsp+598h+ppOutput]
0x18006e70f  test    rdx, rdx
0x18006e712  jz      short loc_18006E723
0x18006e714  mov     rcx, [rdx]
0x18006e717  mov     rax, [rcx+10h]
0x18006e71b  mov     rcx, rdx
0x18006e71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e723  mov     [rsp+598h+ppOutput], rsi
0x18006e728  mov     rcx, [rsp+598h+ppvObject]
0x18006e72d  test    rcx, rcx
0x18006e730  jz      short loc_18006E73E
0x18006e732  mov     rax, [rcx]
0x18006e735  mov     rax, [rax+10h]
0x18006e739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e73e  mov     [rsp+598h+ppvObject], rsi
0x18006e743  mov     rcx, [rsp+598h+ppstm]
0x18006e748  test    rcx, rcx
0x18006e74b  jz      short loc_18006E759
0x18006e74d  mov     rax, [rcx]
0x18006e750  mov     rax, [rax+10h]
0x18006e754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e759  mov     [rsp+598h+ppstm], rsi
0x18006e75e  jmp     loc_18006E5AF
0x18006e763  mov     rcx, [rsp+598h+ppvObject]
0x18006e768  mov     rax, [rcx]
0x18006e76b  xor     r8d, r8d
0x18006e76e  lea     edx, [r8+2]
0x18006e772  mov     rax, [rax+28h]
0x18006e776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e77b  mov     ebx, eax
0x18006e77d  test    eax, eax
0x18006e77f  jns     short loc_18006E7DA
0x18006e781  mov     rdx, [rsp+598h+ppOutput]
0x18006e786  test    rdx, rdx
0x18006e789  jz      short loc_18006E79A
0x18006e78b  mov     rcx, [rdx]
0x18006e78e  mov     rax, [rcx+10h]
0x18006e792  mov     rcx, rdx
0x18006e795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e79a  mov     [rsp+598h+ppOutput], rsi
0x18006e79f  mov     rcx, [rsp+598h+ppvObject]
0x18006e7a4  test    rcx, rcx
0x18006e7a7  jz      short loc_18006E7B5
0x18006e7a9  mov     rax, [rcx]
0x18006e7ac  mov     rax, [rax+10h]
0x18006e7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e7b5  mov     [rsp+598h+ppvObject], rsi
0x18006e7ba  mov     rcx, [rsp+598h+ppstm]
0x18006e7bf  test    rcx, rcx
0x18006e7c2  jz      short loc_18006E7D0
0x18006e7c4  mov     rax, [rcx]
0x18006e7c7  mov     rax, [rax+10h]
0x18006e7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e7d0  mov     [rsp+598h+ppstm], rsi
0x18006e7d5  jmp     loc_18006E5AF
0x18006e7da  mov     rcx, [rsp+598h+ppvObject]
0x18006e7df  mov     rax, [rcx]
0x18006e7e2  mov     r8, r14
0x18006e7e5  mov     edx, 3
0x18006e7ea  mov     rax, [rax+28h]
0x18006e7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e7f3  mov     ebx, eax
0x18006e7f5  test    eax, eax
0x18006e7f7  jns     short loc_18006E852
0x18006e7f9  mov     rdx, [rsp+598h+ppOutput]
0x18006e7fe  test    rdx, rdx
0x18006e801  jz      short loc_18006E812
0x18006e803  mov     rcx, [rdx]
0x18006e806  mov     rax, [rcx+10h]
0x18006e80a  mov     rcx, rdx
0x18006e80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e812  mov     [rsp+598h+ppOutput], rsi
0x18006e817  mov     rcx, [rsp+598h+ppvObject]
0x18006e81c  test    rcx, rcx
0x18006e81f  jz      short loc_18006E82D
0x18006e821  mov     rax, [rcx]
0x18006e824  mov     rax, [rax+10h]
0x18006e828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e82d  mov     [rsp+598h+ppvObject], rsi
0x18006e832  mov     rcx, [rsp+598h+ppstm]
0x18006e837  test    rcx, rcx
0x18006e83a  jz      short loc_18006E848
0x18006e83c  mov     rax, [rcx]
0x18006e83f  mov     rax, [rax+10h]
0x18006e843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e848  mov     [rsp+598h+ppstm], rsi
0x18006e84d  jmp     loc_18006E5AF
0x18006e852  mov     rcx, [rsp+598h+ppvObject]
0x18006e857  mov     rax, [rcx]
0x18006e85a  xor     r9d, r9d
0x18006e85d  lea     r8, aDeclaredconfig_133; "DeclaredConfigurationResult"
0x18006e864  xor     edx, edx
0x18006e866  mov     rax, [rax+0D8h]
0x18006e86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e872  mov     ebx, eax
0x18006e874  test    eax, eax
0x18006e876  jns     short loc_18006E8D1
0x18006e878  mov     rdx, [rsp+598h+ppOutput]
0x18006e87d  test    rdx, rdx
0x18006e880  jz      short loc_18006E891
0x18006e882  mov     rcx, [rdx]
0x18006e885  mov     rax, [rcx+10h]
0x18006e889  mov     rcx, rdx
0x18006e88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e891  mov     [rsp+598h+ppOutput], rsi
0x18006e896  mov     rcx, [rsp+598h+ppvObject]
0x18006e89b  test    rcx, rcx
0x18006e89e  jz      short loc_18006E8AC
0x18006e8a0  mov     rax, [rcx]
0x18006e8a3  mov     rax, [rax+10h]
0x18006e8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8ac  mov     [rsp+598h+ppvObject], rsi
0x18006e8b1  mov     rcx, [rsp+598h+ppstm]
0x18006e8b6  test    rcx, rcx
0x18006e8b9  jz      short loc_18006E8C7
0x18006e8bb  mov     rax, [rcx]
0x18006e8be  mov     rax, [rax+10h]
0x18006e8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8c7  mov     [rsp+598h+ppstm], rsi
0x18006e8cc  jmp     loc_18006E5AF
0x18006e8d1  mov     rcx, [rsp+598h+ppvObject]
0x18006e8d6  mov     rax, [rcx]
0x18006e8d9  lea     rdx, [rsp+598h+var_378]
0x18006e8e1  cmp     [rsp+598h+var_360], 7
0x18006e8ea  cmova   rdx, [rsp+598h+var_378]
0x18006e8f3  mov     [rsp+598h+var_578], rdx
0x18006e8f8  xor     r9d, r9d
0x18006e8fb  lea     r8, aContext_1; "context"
0x18006e902  xor     edx, edx
0x18006e904  mov     rax, [rax+38h]
0x18006e908  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
