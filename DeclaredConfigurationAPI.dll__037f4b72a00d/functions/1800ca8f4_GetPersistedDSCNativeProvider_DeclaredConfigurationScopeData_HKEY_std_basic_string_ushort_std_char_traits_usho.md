# GetPersistedDSCNativeProvider(DeclaredConfigurationScopeData *,HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort const *,DCDocument *,DCPersistedDocType)

- ea: `0x1800ca8f4`
- end: `0x1800cba62`
- name: `?GetPersistedDSCNativeProvider@@YAJPEAUDeclaredConfigurationScopeData@@PEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAVDCDocument@@W4DCPersistedDocType@@@Z`
- size: `4462`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, int)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180076c10`
- `0x180078e2c`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x1800117bc`
- `0x1800117dc`
- `0x180011fe0`
- `0x18001438c`
- `0x1800143c8`
- `0x180018ac0`
- `0x180019208`
- `0x18001924c`
- `0x180019d38`
- `0x18001a048`
- `0x18001b3d4`
- `0x18001b488`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18001df78`
- `0x18004abf8`
- `0x18004cf10`
- `0x18004eb5c`
- `0x180058630`
- `0x1800a1878`
- `0x1800ca3c4`
- `0x1800ca8f4`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x1801006c8`
- `0x180100ad8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb5e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb66e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb5e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cb66e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cb47c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cb47c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cb46a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cb5db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cb660`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cb46a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cb5db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cb660`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cae81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cae81`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800cb578`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800cb578`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cb3f6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cb3f6`
- `OLEAUT32!__imp_VariantInit` at `0x1800ca952`
- `OLEAUT32!__imp_VariantInit` at `0x1800ca961`
- `OLEAUT32!__imp_VariantInit` at `0x1800cb208`
- `OLEAUT32!__imp_VariantInit` at `0x1800ca952`
- `OLEAUT32!__imp_VariantInit` at `0x1800ca961`
- `OLEAUT32!__imp_VariantInit` at `0x1800cb208`
- `OLEAUT32!__imp_VariantClear` at `0x1800caa00`
- `OLEAUT32!__imp_VariantClear` at `0x1800caa0f`
- `OLEAUT32!__imp_VariantClear` at `0x1800caa7b`
- `OLEAUT32!__imp_VariantClear` at `0x1800caa8a`
- `OLEAUT32!__imp_VariantClear` at `0x1800caba9`
- `OLEAUT32!__imp_VariantClear` at `0x1800cac24`
- `OLEAUT32!__imp_VariantClear` at `0x1800cac93`
- `OLEAUT32!__imp_VariantClear` at `0x1800cad1b`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf68`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf77`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb2a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb9b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb9bf`
- `OLEAUT32!__imp_VariantClear` at `0x1800cba17`
- `OLEAUT32!__imp_VariantClear` at `0x1800cba26`
- `OLEAUT32!__imp_VariantClear` at `0x1800caa00`
- `OLEAUT32!__imp_VariantClear` at `0x1800caa0f`
- `OLEAUT32!__imp_VariantClear` at `0x1800caa7b`
- `OLEAUT32!__imp_VariantClear` at `0x1800caa8a`
- `OLEAUT32!__imp_VariantClear` at `0x1800caba9`
- `OLEAUT32!__imp_VariantClear` at `0x1800cac24`
- `OLEAUT32!__imp_VariantClear` at `0x1800cac93`
- `OLEAUT32!__imp_VariantClear` at `0x1800cad1b`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf68`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf77`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb2a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb9b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb9bf`
- `OLEAUT32!__imp_VariantClear` at `0x1800cba17`
- `OLEAUT32!__imp_VariantClear` at `0x1800cba26`

## string_xrefs

- `0x1800cb42d`: `fileHandle.reset(CreateFile: failed to open file`
- `0x1800cb599`: `ReadFile`
- `0x1800cb617`: `ReadFile: read size is different than expected`
- `0x1800ca9d3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providerdscnative.cpp`
- `0x1800caeee`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providerdscnative.cpp`
- `0x1800cb374`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providerdscnative.cpp`
- `0x1800cb44b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providerdscnative.cpp`
- `0x1800cb5b7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providerdscnative.cpp`
- `0x1800cb6fa`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providerdscnative.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall GetPersistedDSCNativeProvider(__int64 a1, HKEY a2, __int64 a3, __int64 a4, __int64 *a5, int a6)
{
  __int64 v6; // r14
  int v8; // r12d
  __int64 v9; // rax
  std::_Ref_count_base *v10; // rsi
  __int64 result; // rax
  const unsigned __int16 *v12; // rdx
  int RegistryString; // ebx
  __int64 v14; // r8
  const unsigned __int16 *v15; // rdx
  __int64 v16; // r8
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rdx
  int v19; // r9d
  __int64 *v20; // r15
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rbx
  int v24; // r9d
  __int64 v25; // r8
  __int64 v26; // rdx
  int v27; // r9d
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned int v31; // eax
  unsigned int i; // r12d
  __int64 v33; // rbx
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rax
  const WCHAR *v37; // rdx
  LSTATUS v38; // ebx
  __int64 v39; // rax
  char *v40; // rsi
  __int64 v41; // r8
  __int64 v42; // r8
  int v43; // eax
  int v44; // r9d
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r8
  int RegistryDWORD; // r12d
  DWORD v49; // r15d
  __int64 v50; // r8
  char *v51; // rcx
  HANDLE FileW; // rax
  CDeclaredConfigurationLogger *Logger; // rax
  const char *v54; // r9
  HANDLE ProcessHeap; // rax
  void *v56; // rax
  CDeclaredConfigurationLogger *v57; // rax
  const char *v58; // r9
  void *v59; // rsi
  HANDLE v60; // rax
  CDeclaredConfigurationLogger *v61; // rax
  char *v62; // r9
  __int64 v63; // r8
  void *v64; // rbx
  HANDLE v65; // rax
  __int64 v66; // r8
  _QWORD *v67; // rcx
  __int64 v68; // r9
  int phkResult; // [rsp+20h] [rbp-238h]
  int phkResulta; // [rsp+20h] [rbp-238h]
  int phkResultb; // [rsp+20h] [rbp-238h]
  int phkResultc; // [rsp+20h] [rbp-238h]
  int phkResultd; // [rsp+20h] [rbp-238h]
  int phkResulte; // [rsp+20h] [rbp-238h]
  int phkResultf; // [rsp+20h] [rbp-238h]
  HKEY v76; // [rsp+40h] [rbp-218h] BYREF
  void *Block; // [rsp+48h] [rbp-210h] BYREF
  unsigned __int16 *v78; // [rsp+50h] [rbp-208h] BYREF
  void *v79; // [rsp+58h] [rbp-200h] BYREF
  unsigned __int16 *v80; // [rsp+60h] [rbp-1F8h] BYREF
  unsigned __int16 *v81; // [rsp+68h] [rbp-1F0h] BYREF
  unsigned int v82; // [rsp+70h] [rbp-1E8h] BYREF
  __int64 v83; // [rsp+78h] [rbp-1E0h] BYREF
  std::_Ref_count_base *v84[2]; // [rsp+80h] [rbp-1D8h] BYREF
  unsigned __int16 *v85; // [rsp+90h] [rbp-1C8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+98h] [rbp-1C0h] BYREF
  _WORD *v87; // [rsp+A8h] [rbp-1B0h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-1A8h] BYREF
  unsigned int v89; // [rsp+C8h] [rbp-190h] BYREF
  DWORD NumberOfBytesRead; // [rsp+CCh] [rbp-18Ch] BYREF
  unsigned int v91; // [rsp+D0h] [rbp-188h]
  LPVOID lpMem; // [rsp+D8h] [rbp-180h] BYREF
  VARIANTARG v93; // [rsp+E0h] [rbp-178h] BYREF
  LPVOID *p_lpMem; // [rsp+F8h] [rbp-160h] BYREF
  std::_Ref_count_base *v95; // [rsp+100h] [rbp-158h]
  __int64 v96; // [rsp+108h] [rbp-150h]
  HKEY hKey; // [rsp+110h] [rbp-148h]
  int v98[2]; // [rsp+118h] [rbp-140h]
  _BYTE v99[8]; // [rsp+120h] [rbp-138h] BYREF
  std::_Ref_count_base *v100; // [rsp+128h] [rbp-130h]
  void **p_Block; // [rsp+130h] [rbp-128h]
  void **v102; // [rsp+138h] [rbp-120h]
  unsigned __int16 **v103; // [rsp+140h] [rbp-118h]
  char v104; // [rsp+148h] [rbp-110h]
  __int64 v105; // [rsp+150h] [rbp-108h]
  VARIANTARG v106; // [rsp+158h] [rbp-100h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+178h] [rbp-E0h] BYREF
  unsigned __int16 **v108; // [rsp+198h] [rbp-C0h] BYREF
  unsigned __int16 *v109; // [rsp+1A0h] [rbp-B8h] BYREF
  char v110; // [rsp+1A8h] [rbp-B0h]
  _BYTE v111[32]; // [rsp+1B8h] [rbp-A0h] BYREF
  _BYTE v112[32]; // [rsp+1D8h] [rbp-80h] BYREF
  unsigned __int16 v113[16]; // [rsp+1F8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v96 = a4;
  v6 = a3;
  hKey = a2;
  v8 = a1;
  *(_QWORD *)v98 = a1;
  v105 = a3;
  VariantInit(&pvarg);
  VariantInit(&v93);
  try
  {
    *(_OWORD *)v84 = 0;
    *(_OWORD *)lpFileName = 0;
    v113[0] = 0;
    v9 = std::make_shared<DCDSCNative,>(&p_lpMem);
    std::shared_ptr<DCURI>::operator=(v84, v9);
    if ( v95 )
      std::_Ref_count_base::_Decref(v95);
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
      (const char *)0x8007000ELL,
      phkResultd);
    goto LABEL_174;
  }
  v10 = v84[0];
  if ( !v84[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
      (const char *)0x8007000ELL,
      phkResulte);
    if ( v84[1] )
      std::_Ref_count_base::_Decref(v84[1]);
    VariantClear(&v93);
    VariantClear(&pvarg);
    std::wstring::_Tidy_deallocate(v6);
    return 2147942414LL;
  }
  *((_DWORD *)v84[0] + 10) = 2;
  v85 = 0;
  if ( *(_QWORD *)(v6 + 24) <= 7u )
    v12 = (const unsigned __int16 *)v6;
  else
    v12 = *(const unsigned __int16 **)v6;
  RegistryString = DCCDNUtil_GetRegistryString(a2, v12, L"namespace", &v85);
  if ( RegistryString < 0 )
    goto LABEL_12;
  v80 = v85;
  v14 = -1;
  do
    ++v14;
  while ( v85[v14] );
  std::wstring::_Assign<unsigned short>((char **)v10 + 6, v85, (char *)v14);
  v85 = 0;
  if ( *(_QWORD *)(v6 + 24) <= 7u )
    v15 = (const unsigned __int16 *)v6;
  else
    v15 = *(const unsigned __int16 **)v6;
  RegistryString = DCCDNUtil_GetRegistryString(a2, v15, L"className", &v85);
  if ( RegistryString < 0 )
    goto LABEL_21;
  v81 = v85;
  v16 = -1;
  do
    ++v16;
  while ( v85[v16] );
  std::wstring::_Assign<unsigned short>((char **)v10 + 10, v85, (char *)v16);
  v82 = 0;
  if ( *(_QWORD *)(v6 + 24) <= 7u )
    v17 = (const unsigned __int16 *)v6;
  else
    v17 = *(const unsigned __int16 **)v6;
  RegistryString = DCCDNUtil_GetRegistryDWORD(a2, v17, L"operation", &v82);
  if ( RegistryString < 0
    || ((*((_DWORD *)v10 + 39) = v82, v89 = 0, *(_QWORD *)(v6 + 24) <= 7u)
      ? (v18 = (const unsigned __int16 *)v6)
      : (v18 = *(const unsigned __int16 **)v6),
        RegistryString = DCCDNUtil_GetRegistryDWORD(a2, v18, L"KeyValueCount", &v89),
        RegistryString < 0) )
  {
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v81);
LABEL_21:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v80);
    goto LABEL_12;
  }
  VariantClear(&pvarg);
  pvarg.vt = 3;
  v20 = a5 + 12;
  if ( (unsigned __int64)a5[15] <= 7 )
    LODWORD(v21) = (_DWORD)a5 + 96;
  else
    v21 = *v20;
  if ( (unsigned __int64)a5[3] <= 7 )
    LODWORD(v22) = (_DWORD)a5;
  else
    v22 = *a5;
  v23 = v96;
  DeclaredConfigurationStore_ReadResultData_2(v8, v22, v21, v19, v96, 0, L"state", (DWORD)&pvarg);
  *((_DWORD *)v10 + 3) = pvarg.lVal;
  VariantClear(&pvarg);
  pvarg.vt = 3;
  if ( (unsigned __int64)a5[15] <= 7 )
    LODWORD(v25) = (_DWORD)a5 + 96;
  else
    v25 = *v20;
  if ( (unsigned __int64)a5[3] <= 7 )
    LODWORD(v26) = (_DWORD)a5;
  else
    v26 = *a5;
  DeclaredConfigurationStore_ReadResultData_2(v8, v26, v25, v24, v23, 0, L"hresult", (DWORD)&pvarg);
  *((_DWORD *)v10 + 28) = pvarg.lVal;
  VariantClear(&pvarg);
  v93.vt = 8;
  if ( (unsigned __int64)a5[15] <= 7 )
    LODWORD(v28) = (_DWORD)a5 + 96;
  else
    v28 = *v20;
  if ( (unsigned __int64)a5[3] <= 7 )
    LODWORD(v29) = (_DWORD)a5;
  else
    v29 = *a5;
  if ( (int)DeclaredConfigurationStore_ReadResultData_2(v8, v29, v28, v27, v23, 0, L"errorMessage", (DWORD)&v93) >= 0 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(v93.llVal + 2 * v30) );
    std::wstring::_Assign<unsigned short>((char **)v10 + 15, v93.bstrVal, (char *)v30);
  }
  VariantClear(&v93);
  v31 = 1;
  for ( i = 0; ; ++i )
  {
    v82 = i;
    v91 = v31;
    if ( i >= v89 )
      break;
    v83 = 0;
    v76 = 0;
    v79 = 0;
    Block = 0;
    v78 = 0;
    RegistryString = StringCchPrintfW(v113, 0xFu, L"KeyValue%d", v31);
    if ( RegistryString < 0 )
      goto LABEL_147;
    std::wstring::wstring((__int64)lpSubKey);
    try
    {
      v33 = std::wstring::wstring((__int64)v112, (__int64)v113);
      v34 = std::wstring::wstring((__int64)v111, (__int64)L"\\");
      v35 = std::operator+<unsigned short>(&v106, v6, v34);
      v36 = std::operator+<unsigned short>(&v108, v35, v33);
      std::wstring::operator=(lpSubKey, v36);
      std::wstring::_Tidy_deallocate(&v108);
      std::wstring::_Tidy_deallocate(&v106);
      std::wstring::_Tidy_deallocate(v111);
      std::wstring::_Tidy_deallocate(v112);
      *(_QWORD *)&v106.vt = &v76;
      v106.llVal = 0;
      *((_BYTE *)&v106.decVal + 16) = 1;
      v37 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v37 = lpSubKey[0];
      v38 = RegOpenKeyExW(hKey, v37, 0, 0x20119u, (PHKEY)&v106.llVal);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v106);
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
        (const char *)0x8007000ELL,
        phkResultc);
      goto LABEL_159;
    }
    if ( v38 )
      goto LABEL_84;
    try
    {
      v39 = std::make_shared<DCDSCNativeKeyValue,>(v99);
      std::shared_ptr<DCURI>::operator=(lpFileName, v39);
      if ( v100 )
        std::_Ref_count_base::_Decref(v100);
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
        (const char *)0x8007000ELL,
        phkResultb);
      goto LABEL_159;
    }
    v40 = (char *)lpFileName[0];
    if ( !lpFileName[0] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B8,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
        (const char *)0x8007000ELL,
        phkResultf);
      std::wstring::_Tidy_deallocate(lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v83);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v81);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v80);
      if ( lpFileName[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpFileName[1]);
      if ( v84[1] )
        std::_Ref_count_base::_Decref(v84[1]);
      VariantClear(&v93);
      VariantClear(&pvarg);
      std::wstring::_Tidy_deallocate(v6);
      return 2147942414LL;
    }
    *(_DWORD *)&v106.vt = 0;
    if ( DCCDNUtil_GetRegistryDWORD(v76, 0, L"typeStored", (unsigned int *)&v106.vt) < 0 )
      goto LABEL_84;
    *((_DWORD *)v40 + 26) = *(_DWORD *)&v106.vt;
    *(_DWORD *)&v106.vt = 0;
    if ( DCCDNUtil_GetRegistryDWORD(v76, 0, L"Key", (unsigned int *)&v106.vt) < 0 )
      goto LABEL_84;
    v40[68] = *(_DWORD *)&v106.vt != 0;
    if ( a6 == 2 )
    {
      *(_DWORD *)&v106.vt = 0;
      DCCDNUtil_GetRegistryDWORD(v76, 0, L"instanceDataAllowed", (unsigned int *)&v106.vt);
      v40[109] = *(_DWORD *)&v106.vt != 0;
    }
    p_Block = &Block;
    v102 = &v79;
    v103 = &v78;
    v104 = 1;
    if ( v40[109] )
    {
      if ( (*((_BYTE *)a5 + 676) & 3) != 0 )
      {
        DCCDNUtil_GetRegistryString(v76, 0, L"instanceDataVariable", &v78);
        if ( v78 )
        {
          v41 = -1;
          do
            ++v41;
          while ( v78[v41] );
          std::wstring::_Assign<unsigned short>((char **)v40 + 14, v78, (char *)v41);
        }
      }
    }
    if ( DCCDNUtil_GetRegistryString(v76, 0, L"Name", (unsigned __int16 **)&Block) < 0 )
    {
      operator delete(Block);
      Block = 0;
      operator delete(v79);
      v79 = 0;
      operator delete(v78);
      v78 = 0;
LABEL_84:
      std::wstring::_Tidy_deallocate(lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
      goto LABEL_85;
    }
    v42 = -1;
    do
      ++v42;
    while ( *((_WORD *)Block + v42) );
    std::wstring::_Assign<unsigned short>((char **)v40 + 4, Block, (char *)v42);
    v43 = *((_DWORD *)a5 + 68);
    if ( v43 == 4 )
    {
      if ( a6 != 3 )
        goto LABEL_108;
      if ( *((_DWORD *)v40 + 26) != 1 )
      {
        operator delete(Block);
        Block = 0;
        operator delete(v79);
        v79 = 0;
        operator delete(v78);
        v78 = 0;
        std::wstring::_Tidy_deallocate(lpSubKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v83);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v81);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v80);
        if ( lpFileName[1] )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpFileName[1]);
        if ( v84[1] )
          std::_Ref_count_base::_Decref(v84[1]);
        RegistryString = -2147418113;
        goto LABEL_14;
      }
      VariantInit(&v106);
      v106.vt = 8;
      if ( (unsigned __int64)a5[15] <= 7 )
        LODWORD(v45) = (_DWORD)v20;
      else
        v45 = *v20;
      if ( (unsigned __int64)a5[3] <= 7 )
        LODWORD(v46) = (_DWORD)a5;
      else
        v46 = *a5;
      if ( (int)DeclaredConfigurationStore_ReadResultData_2(
                  v98[0],
                  v46,
                  v45,
                  v44,
                  v96,
                  (__int64)v113,
                  L"value",
                  (DWORD)&v106) >= 0 )
      {
        v47 = -1;
        do
          ++v47;
        while ( *(_WORD *)(v106.llVal + 2 * v47) );
        std::wstring::_Assign<unsigned short>((char **)v40, v106.bstrVal, (char *)v47);
        v40[108] = 1;
      }
      VariantClear(&v106);
    }
    else if ( (unsigned int)(v43 - 1) <= 1 )
    {
LABEL_108:
      if ( *((_DWORD *)v40 + 26) == 1 )
      {
        *(_DWORD *)&v106.vt = 0;
        RegistryDWORD = DCCDNUtil_GetRegistryDWORD(v76, 0, L"valueSize", (unsigned int *)&v106.vt);
        if ( RegistryDWORD >= 0 && (v49 = *(_DWORD *)&v106.vt) != 0 )
        {
          *(_QWORD *)&v106.vt = -1;
          v87 = 0;
          v108 = &v87;
          v109 = 0;
          v110 = 1;
          RegistryString = DCCDNUtil_GetRegistryString(v76, 0, L"value", &v109);
          wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v108);
          if ( RegistryString < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x346,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
              (const char *)(unsigned int)RegistryString,
              phkResultf);
            goto LABEL_113;
          }
          v50 = -1;
          do
            ++v50;
          while ( v87[v50] );
          std::wstring::_Assign<unsigned short>((char **)v40, v87, (char *)v50);
          if ( *((_QWORD *)v40 + 3) <= 7u )
            v51 = v40;
          else
            v51 = *(char **)v40;
          FileW = CreateFileW((LPCWSTR)v51, 0x80000000, 0, 0, 3u, 0x80u, 0);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &v106,
            FileW);
          if ( *(_QWORD *)&v106.vt == -1 )
          {
            Logger = CDeclaredConfigurationLogger::GetLogger();
            if ( *((_QWORD *)v40 + 3) > 7u )
              v40 = *(char **)v40;
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              Logger,
              L"GetPersistedDSCNativeProvider",
              L"fileHandle.reset(CreateFile: failed to open file",
              (const unsigned __int16 *)v40,
              RegistryDWORD);
            RegistryString = wil::details::in1diag3::Return_GetLastError(
                               retaddr,
                               (void *)0x359,
                               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\"
                                             "providerdscnative.cpp",
                               v54);
            goto LABEL_113;
          }
          NumberOfBytesRead = 0;
          ProcessHeap = GetProcessHeap();
          v56 = HeapAlloc(ProcessHeap, 8u, v49 + 2);
          lpMem = v56;
          if ( !v56 )
          {
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v87);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v106);
            operator delete(Block);
            Block = 0;
            operator delete(v79);
            v79 = 0;
            operator delete(v78);
            v78 = 0;
            std::wstring::_Tidy_deallocate(lpSubKey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v83);
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v81);
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v80);
            if ( lpFileName[1] )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpFileName[1]);
            if ( v84[1] )
              std::_Ref_count_base::_Decref(v84[1]);
            RegistryString = -2147024882;
LABEL_14:
            VariantClear(&v93);
            VariantClear(&pvarg);
            std::wstring::_Tidy_deallocate(v6);
            return (unsigned int)RegistryString;
          }
          p_lpMem = &lpMem;
          LOBYTE(v95) = 1;
          if ( !ReadFile(*(HANDLE *)&v106.vt, v56, v49, &NumberOfBytesRead, 0) )
          {
            v57 = CDeclaredConfigurationLogger::GetLogger();
            if ( *((_QWORD *)v40 + 3) > 7u )
              v40 = *(char **)v40;
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v57,
              L"GetPersistedDSCNativeProvider",
              L"ReadFile",
              (const unsigned __int16 *)v40,
              RegistryDWORD);
            RegistryString = wil::details::in1diag3::Return_GetLastError(
                               retaddr,
                               (void *)0x375,
                               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\"
                                             "providerdscnative.cpp",
                               v58);
            v59 = lpMem;
            if ( lpMem )
            {
              v60 = GetProcessHeap();
              HeapFree(v60, 0, v59);
            }
LABEL_113:
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v87);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v106);
LABEL_146:
            operator delete(Block);
            Block = 0;
            operator delete(v79);
            v79 = 0;
            operator delete(v78);
            v78 = 0;
            std::wstring::_Tidy_deallocate(lpSubKey);
LABEL_147:
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v83);
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v81);
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v80);
            if ( lpFileName[1] )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpFileName[1]);
LABEL_12:
            if ( v84[1] )
              std::_Ref_count_base::_Decref(v84[1]);
            goto LABEL_14;
          }
          if ( NumberOfBytesRead != v49 )
          {
            v61 = CDeclaredConfigurationLogger::GetLogger();
            if ( *((_QWORD *)v40 + 3) <= 7u )
              v62 = v40;
            else
              v62 = *(char **)v40;
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v61,
              L"GetPersistedDSCNativeProvider",
              L"ReadFile: read size is different than expected",
              (const unsigned __int16 *)v62,
              RegistryDWORD);
          }
          v63 = -1;
          do
            ++v63;
          while ( *((_WORD *)lpMem + v63) );
          std::wstring::_Assign<unsigned short>((char **)v40, lpMem, (char *)v63);
          LOBYTE(v95) = 0;
          v64 = lpMem;
          if ( lpMem )
          {
            v65 = GetProcessHeap();
            HeapFree(v65, 0, v64);
          }
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v87);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v106);
        }
        else
        {
          v85 = 0;
          v108 = &v85;
          v109 = 0;
          v110 = 1;
          RegistryString = DCCDNUtil_GetRegistryString(v76, 0, L"value", &v109);
          wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v108);
          if ( RegistryString < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x384,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
              (const char *)(unsigned int)RegistryString,
              phkResultf);
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v85);
            goto LABEL_146;
          }
          v66 = -1;
          do
            ++v66;
          while ( v85[v66] );
          std::wstring::_Assign<unsigned short>((char **)v40, v85, (char *)v66);
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v85);
        }
        i = v82;
      }
    }
    try
    {
      v67 = (_QWORD *)*((_QWORD *)v84[0] + 3);
      if ( v67 == *((_QWORD **)v84[0] + 4) )
      {
        std::vector<std::shared_ptr<DCDSCNativeKeyValue>>::_Emplace_reallocate<std::shared_ptr<DCDSCNativeKeyValue> const &>(
          (char *)v84[0] + 16,
          *((_QWORD *)v84[0] + 3),
          lpFileName);
      }
      else
      {
        std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(v67, lpFileName);
        *(_QWORD *)(v68 + 24) += 16LL;
      }
      *(_OWORD *)&v106.vt = 0;
      std::shared_ptr<DCURI>::operator=(lpFileName, &v106);
      if ( v106.llVal )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v106.llVal);
      operator delete(Block);
      Block = 0;
      operator delete(v79);
      v79 = 0;
      operator delete(v78);
      v78 = 0;
      std::wstring::_Tidy_deallocate(lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
      v20 = a5 + 12;
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A8,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
        (const char *)0x8007000ELL,
        phkResulta);
      operator delete(Block);
      Block = 0;
      operator delete(v79);
      v79 = 0;
      operator delete(v78);
      v78 = 0;
LABEL_159:
      std::wstring::_Tidy_deallocate(lpSubKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v76);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v83);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v81);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v80);
      if ( lpFileName[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpFileName[1]);
      if ( v84[1] )
        std::_Ref_count_base::_Decref(v84[1]);
      RegistryString = -2147024882;
      v6 = v105;
      goto LABEL_14;
    }
LABEL_85:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v83);
    v31 = v91 + 1;
  }
  std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(&p_lpMem, v84);
  try
  {
    std::vector<std::shared_ptr<DCProviderOrchestration>>::push_back(a5 + 20, &p_lpMem);
    if ( v95 )
      std::_Ref_count_base::_Decref(v95);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v81);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v80);
    if ( lpFileName[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpFileName[1]);
    if ( v84[1] )
      std::_Ref_count_base::_Decref(v84[1]);
    VariantClear(&v93);
    VariantClear(&pvarg);
    std::wstring::_Tidy_deallocate(v6);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providerdscnative.cpp",
      (const char *)0x8007000ELL,
      phkResult);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v81);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v80);
    if ( lpFileName[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpFileName[1]);
LABEL_174:
    if ( v84[1] )
      std::_Ref_count_base::_Decref(v84[1]);
    VariantClear(&v93);
    VariantClear(&pvarg);
    std::wstring::_Tidy_deallocate(v105);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800ca8f4  push    rbx
0x1800ca8f6  push    rsi
0x1800ca8f7  push    rdi
0x1800ca8f8  push    r12
0x1800ca8fa  push    r13
0x1800ca8fc  push    r14
0x1800ca8fe  push    r15
0x1800ca900  sub     rsp, 220h
0x1800ca907  mov     rax, cs:__security_cookie
0x1800ca90e  xor     rax, rsp
0x1800ca911  mov     [rsp+258h+var_40], rax
0x1800ca919  mov     [rsp+258h+var_150], r9
0x1800ca921  mov     r14, r8
0x1800ca924  mov     r15, rdx
0x1800ca927  mov     [rsp+258h+hKey], rdx
0x1800ca92f  mov     r12, rcx
0x1800ca932  mov     qword ptr [rsp+258h+var_140], rcx
0x1800ca93a  mov     r13, [rsp+258h+arg_20]
0x1800ca942  mov     [rsp+258h+var_108], r8
0x1800ca94a  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1800ca952  call    cs:__imp_VariantInit
0x1800ca958  nop
0x1800ca959  lea     rcx, [rsp+258h+var_178]; pvarg
0x1800ca961  call    cs:__imp_VariantInit
0x1800ca967  nop
0x1800ca968  xorps   xmm0, xmm0
0x1800ca96b  movdqu  xmmword ptr [rsp+258h+var_1D8], xmm0
0x1800ca974  movdqu  xmmword ptr [rsp+258h+lpFileName], xmm0
0x1800ca97d  xor     edi, edi
0x1800ca97f  mov     [rsp+258h+var_60], di
0x1800ca987  lea     rcx, [rsp+258h+var_160]
0x1800ca98f  call    ??$make_shared@VDCDSCNative@@$$V@std@@YA?AV?$shared_ptr@VDCDSCNative@@@0@XZ; std::make_shared<DCDSCNative,>(void)
0x1800ca994  mov     rdx, rax
0x1800ca997  lea     rcx, [rsp+258h+var_1D8]
0x1800ca99f  call    ??4?$shared_ptr@VDCURI@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<DCURI>::operator=(std::shared_ptr<DCURI> &&)
0x1800ca9a4  mov     rcx, [rsp+258h+var_158]; this
0x1800ca9ac  test    rcx, rcx
0x1800ca9af  jz      short loc_1800CA9B6
0x1800ca9b1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ca9b6  mov     rsi, [rsp+258h+var_1D8]
0x1800ca9be  test    rsi, rsi
0x1800ca9c1  jnz     short loc_1800CAA25
0x1800ca9c3  mov     rcx, [rsp+258h]; this
0x1800ca9cb  mov     ebx, 8007000Eh
0x1800ca9d0  mov     r9d, ebx; char *
0x1800ca9d3  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ca9da  mov     edx, 1E3h; void *
0x1800ca9df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca9e4  nop
0x1800ca9e5  mov     rcx, [rsp+258h+var_1D8+8]; this
0x1800ca9ed  test    rcx, rcx
0x1800ca9f0  jz      short loc_1800CA9F8
0x1800ca9f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ca9f7  nop
0x1800ca9f8  lea     rcx, [rsp+258h+var_178]; pvarg
0x1800caa00  call    cs:__imp_VariantClear
0x1800caa06  nop
0x1800caa07  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1800caa0f  call    cs:__imp_VariantClear
0x1800caa15  nop
0x1800caa16  mov     rcx, r14
0x1800caa19  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caa1e  mov     eax, ebx
0x1800caa20  jmp     loc_1800CBA3F
0x1800caa25  mov     dword ptr [rsi+28h], 2
0x1800caa2c  mov     [rsp+258h+var_1C8], rdi
0x1800caa34  cmp     qword ptr [r14+18h], 7
0x1800caa39  jbe     short loc_1800CAA40
0x1800caa3b  mov     rdx, [r14]
0x1800caa3e  jmp     short loc_1800CAA43
0x1800caa40  mov     rdx, r14; unsigned __int16 *
0x1800caa43  lea     r9, [rsp+258h+var_1C8]; unsigned __int16 **
0x1800caa4b  lea     r8, aNamespace; "namespace"
0x1800caa52  mov     rcx, r15; HKEY
0x1800caa55  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800caa5a  mov     ebx, eax
0x1800caa5c  test    eax, eax
0x1800caa5e  jns     short loc_1800CAAA0
0x1800caa60  mov     rcx, [rsp+258h+var_1D8+8]; this
0x1800caa68  test    rcx, rcx
0x1800caa6b  jz      short loc_1800CAA73
0x1800caa6d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800caa72  nop
0x1800caa73  lea     rcx, [rsp+258h+var_178]; pvarg
0x1800caa7b  call    cs:__imp_VariantClear
0x1800caa81  nop
0x1800caa82  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1800caa8a  call    cs:__imp_VariantClear
0x1800caa90  nop
0x1800caa91  mov     rcx, r14
0x1800caa94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caa99  mov     eax, ebx
0x1800caa9b  jmp     loc_1800CBA3F
0x1800caaa0  mov     rdx, [rsp+258h+var_1C8]
0x1800caaa8  mov     [rsp+258h+var_1F8], rdx
0x1800caaad  lea     rcx, [rsi+30h]
0x1800caab1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800caab5  inc     r8
0x1800caab8  cmp     [rdx+r8*2], di
0x1800caabd  jnz     short loc_1800CAAB5
0x1800caabf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800caac4  mov     [rsp+258h+var_1C8], rdi
0x1800caacc  cmp     qword ptr [r14+18h], 7
0x1800caad1  jbe     short loc_1800CAAD8
0x1800caad3  mov     rdx, [r14]
0x1800caad6  jmp     short loc_1800CAADB
0x1800caad8  mov     rdx, r14; unsigned __int16 *
0x1800caadb  lea     r9, [rsp+258h+var_1C8]; unsigned __int16 **
0x1800caae3  lea     r8, aClassname; "className"
0x1800caaea  mov     rcx, r15; HKEY
0x1800caaed  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800caaf2  mov     ebx, eax
0x1800caaf4  test    eax, eax
0x1800caaf6  jns     short loc_1800CAB07
0x1800caaf8  lea     rcx, [rsp+258h+var_1F8]
0x1800caafd  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800cab02  jmp     loc_1800CAA60
0x1800cab07  mov     rdx, [rsp+258h+var_1C8]
0x1800cab0f  mov     [rsp+258h+var_1F0], rdx
0x1800cab14  lea     rcx, [rsi+50h]
0x1800cab18  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800cab1c  inc     r8
0x1800cab1f  cmp     [rdx+r8*2], di
0x1800cab24  jnz     short loc_1800CAB1C
0x1800cab26  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800cab2b  mov     [rsp+258h+var_1E8], edi
0x1800cab2f  cmp     qword ptr [r14+18h], 7
0x1800cab34  jbe     short loc_1800CAB3B
0x1800cab36  mov     rdx, [r14]
0x1800cab39  jmp     short loc_1800CAB3E
0x1800cab3b  mov     rdx, r14; unsigned __int16 *
0x1800cab3e  lea     r9, [rsp+258h+var_1E8]; unsigned int *
0x1800cab43  lea     r8, aOperation; "operation"
0x1800cab4a  mov     rcx, r15; HKEY
0x1800cab4d  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800cab52  mov     ebx, eax
0x1800cab54  test    eax, eax
0x1800cab56  jns     short loc_1800CAB64
0x1800cab58  lea     rcx, [rsp+258h+var_1F0]
0x1800cab5d  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800cab62  jmp     short loc_1800CAAF8
0x1800cab64  mov     eax, [rsp+258h+var_1E8]
0x1800cab68  mov     [rsi+9Ch], eax
0x1800cab6e  mov     [rsp+258h+var_190], edi
0x1800cab75  cmp     qword ptr [r14+18h], 7
0x1800cab7a  jbe     short loc_1800CAB81
0x1800cab7c  mov     rdx, [r14]
0x1800cab7f  jmp     short loc_1800CAB84
0x1800cab81  mov     rdx, r14; unsigned __int16 *
0x1800cab84  lea     r9, [rsp+258h+var_190]; unsigned int *
0x1800cab8c  lea     r8, aKeyvaluecount; "KeyValueCount"
0x1800cab93  mov     rcx, r15; HKEY
0x1800cab96  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800cab9b  mov     ebx, eax
0x1800cab9d  test    eax, eax
0x1800cab9f  js      short loc_1800CAB58
0x1800caba1  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1800caba9  call    cs:__imp_VariantClear
0x1800cabaf  mov     eax, 3
0x1800cabb4  mov     word ptr [rsp+258h+pvarg], ax
0x1800cabbc  lea     r15, [r13+60h]
0x1800cabc0  cmp     qword ptr [r15+18h], 7
0x1800cabc5  jbe     short loc_1800CABCC
0x1800cabc7  mov     r8, [r15]
0x1800cabca  jmp     short loc_1800CABCF
0x1800cabcc  mov     r8, r15; int
0x1800cabcf  cmp     qword ptr [r13+18h], 7
0x1800cabd4  jbe     short loc_1800CABDC
0x1800cabd6  mov     rdx, [r13+0]
0x1800cabda  jmp     short loc_1800CABDF
0x1800cabdc  mov     rdx, r13; int
0x1800cabdf  lea     rax, [rsp+258h+pvarg]
0x1800cabe7  mov     qword ptr [rsp+258h+Type], rax; Type
0x1800cabec  lea     rax, ValueName; "state"
0x1800cabf3  mov     [rsp+258h+hTemplateFile], rax; lpValueName
0x1800cabf8  mov     qword ptr [rsp+258h+dwFlagsAndAttributes], rdi; __int64
0x1800cabfd  mov     rbx, [rsp+258h+var_150]
0x1800cac05  mov     [rsp+258h+phkResult], rbx; __int64
0x1800cac0a  mov     rcx, r12; int
0x1800cac0d  call    DeclaredConfigurationStore_ReadResultData_2
0x1800cac12  mov     eax, dword ptr [rsp+258h+pvarg+8]
0x1800cac19  mov     [rsi+0Ch], eax
0x1800cac1c  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1800cac24  call    cs:__imp_VariantClear
0x1800cac2a  mov     eax, 3
0x1800cac2f  mov     word ptr [rsp+258h+pvarg], ax
0x1800cac37  cmp     qword ptr [r15+18h], 7
0x1800cac3c  jbe     short loc_1800CAC43
0x1800cac3e  mov     r8, [r15]
0x1800cac41  jmp     short loc_1800CAC46
0x1800cac43  mov     r8, r15; int
0x1800cac46  cmp     qword ptr [r13+18h], 7
0x1800cac4b  jbe     short loc_1800CAC53
0x1800cac4d  mov     rdx, [r13+0]
0x1800cac51  jmp     short loc_1800CAC56
0x1800cac53  mov     rdx, r13; int
0x1800cac56  lea     rax, [rsp+258h+pvarg]
0x1800cac5e  mov     qword ptr [rsp+258h+Type], rax; Type
0x1800cac63  lea     rax, aHresult_0; "hresult"
0x1800cac6a  mov     [rsp+258h+hTemplateFile], rax; lpValueName
0x1800cac6f  mov     qword ptr [rsp+258h+dwFlagsAndAttributes], rdi; __int64
0x1800cac74  mov     [rsp+258h+phkResult], rbx; __int64
0x1800cac79  mov     rcx, r12; int
0x1800cac7c  call    DeclaredConfigurationStore_ReadResultData_2
0x1800cac81  mov     eax, dword ptr [rsp+258h+pvarg+8]
0x1800cac88  mov     [rsi+70h], eax
0x1800cac8b  lea     rcx, [rsp+258h+pvarg]; pvarg
0x1800cac93  call    cs:__imp_VariantClear
0x1800cac99  mov     eax, 8
0x1800cac9e  mov     word ptr [rsp+258h+var_178], ax
0x1800caca6  cmp     qword ptr [r15+18h], 7
0x1800cacab  jbe     short loc_1800CACB2
0x1800cacad  mov     r8, [r15]
0x1800cacb0  jmp     short loc_1800CACB5
0x1800cacb2  mov     r8, r15; int
0x1800cacb5  cmp     qword ptr [r13+18h], 7
0x1800cacba  jbe     short loc_1800CACC2
0x1800cacbc  mov     rdx, [r13+0]
0x1800cacc0  jmp     short loc_1800CACC5
0x1800cacc2  mov     rdx, r13; int
0x1800cacc5  lea     rax, [rsp+258h+var_178]
0x1800caccd  mov     qword ptr [rsp+258h+Type], rax; Type
0x1800cacd2  lea     rax, aErrormessage; "errorMessage"
0x1800cacd9  mov     [rsp+258h+hTemplateFile], rax; lpValueName
0x1800cacde  mov     qword ptr [rsp+258h+dwFlagsAndAttributes], rdi; __int64
0x1800cace3  mov     [rsp+258h+phkResult], rbx; __int64
0x1800cace8  mov     rcx, r12; int
0x1800caceb  call    DeclaredConfigurationStore_ReadResultData_2
0x1800cacf0  test    eax, eax
0x1800cacf2  js      short loc_1800CAD13
0x1800cacf4  mov     rdx, qword ptr [rsp+258h+var_178+8]
0x1800cacfc  lea     rcx, [rsi+78h]
0x1800cad00  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800cad04  inc     r8
0x1800cad07  cmp     [rdx+r8*2], di
0x1800cad0c  jnz     short loc_1800CAD04
0x1800cad0e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800cad13  lea     rcx, [rsp+258h+var_178]; pvarg
0x1800cad1b  call    cs:__imp_VariantClear
0x1800cad21  mov     eax, 1
0x1800cad26  mov     r12d, edi
0x1800cad29  mov     [rsp+258h+var_1E8], r12d
0x1800cad2e  mov     [rsp+258h+var_188], eax
0x1800cad35  cmp     r12d, [rsp+258h+var_190]
0x1800cad3d  jnb     loc_1800CB92E
0x1800cad43  mov     [rsp+258h+var_1E0], rdi
0x1800cad48  mov     [rsp+258h+var_218], rdi
0x1800cad4d  mov     [rsp+258h+var_200], rdi
0x1800cad52  mov     [rsp+258h+Block], rdi
0x1800cad57  mov     [rsp+258h+var_208], rdi
0x1800cad5c  mov     r9d, eax
0x1800cad5f  lea     r8, aKeyvalueD; "KeyValue%d"
0x1800cad66  mov     edx, 0Fh; unsigned __int64
0x1800cad6b  lea     rcx, [rsp+258h+var_60]; unsigned __int16 *
0x1800cad73  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cad78  mov     ebx, eax
0x1800cad7a  test    eax, eax
0x1800cad7c  js      loc_1800CB755
0x1800cad82  lea     rcx, [rsp+258h+lpSubKey]
0x1800cad8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cad8f  nop
0x1800cad90  lea     rdx, [rsp+258h+var_60]
0x1800cad98  lea     rcx, [rsp+258h+var_80]
0x1800cada0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cada5  mov     rbx, rax
0x1800cada8  lea     rdx, StringValue; "\\"
0x1800cadaf  lea     rcx, [rsp+258h+var_A0]
0x1800cadb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cadbc  nop
0x1800cadbd  mov     r8, rax
0x1800cadc0  mov     rdx, r14
0x1800cadc3  lea     rcx, [rsp+258h+var_100]
0x1800cadcb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x1800cadd0  nop
0x1800cadd1  mov     r8, rbx
0x1800cadd4  mov     rdx, rax
0x1800cadd7  lea     rcx, [rsp+258h+var_C0]
0x1800caddf  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800cade4  mov     rdx, rax
0x1800cade7  lea     rcx, [rsp+258h+lpSubKey]
0x1800cadef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cadf4  lea     rcx, [rsp+258h+var_C0]
0x1800cadfc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cae01  nop
0x1800cae02  lea     rcx, [rsp+258h+var_100]
0x1800cae0a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cae0f  nop
0x1800cae10  lea     rcx, [rsp+258h+var_A0]
0x1800cae18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cae1d  nop
0x1800cae1e  lea     rcx, [rsp+258h+var_80]
0x1800cae26  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cae2b  nop
0x1800cae2c  lea     rax, [rsp+258h+var_218]
0x1800cae31  mov     [rsp+258h+var_100], rax
0x1800cae39  mov     [rsp+258h+var_100+8], rdi
0x1800cae41  mov     [rsp+258h+var_F0], 1
0x1800cae49  lea     rdx, [rsp+258h+lpSubKey]
0x1800cae51  cmp     [rsp+258h+var_C8], 7
0x1800cae5a  cmova   rdx, [rsp+258h+lpSubKey]; lpSubKey
  ... truncated ...
```
