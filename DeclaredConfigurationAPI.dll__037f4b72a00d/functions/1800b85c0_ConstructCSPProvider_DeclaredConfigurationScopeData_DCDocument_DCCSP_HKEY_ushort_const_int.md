# ConstructCSPProvider(DeclaredConfigurationScopeData *,DCDocument *,DCCSP *,HKEY__ *,ushort const *,int)

- ea: `0x1800b85c0`
- end: `0x1800b8fa6`
- name: `?ConstructCSPProvider@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEAVDCCSP@@PEAUHKEY__@@PEBGH@Z`
- size: `2534`
- prototype: `__int64 __usercall@<rax>(struct DeclaredConfigurationScopeData *@<rcx>, struct DCDocument *@<rdx>, struct DCCSP *@<r8>, HKEY@<r9>, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005e76c`
- `0x180067160`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x180018744`
- `0x180018ac0`
- `0x180018b30`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x180049100`
- `0x18004a5d4`
- `0x18004a630`
- `0x18004b7f4`
- `0x18005ff88`
- `0x180072788`
- `0x1800869b0`
- `0x180086c10`
- `0x180098e10`
- `0x1800b85c0`
- `0x1800baca4`
- `0x1800c5fd0`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x180100c90`
- `0x180100e3c`
- `0x180100fd8`
- `0x1801011cc`
- `0x18010136c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b86d5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b86d5`
- `OLEAUT32!__imp_VariantInit` at `0x1800b87a2`
- `OLEAUT32!__imp_VariantInit` at `0x1800b8d87`
- `OLEAUT32!__imp_VariantInit` at `0x1800b87a2`
- `OLEAUT32!__imp_VariantInit` at `0x1800b8d87`
- `OLEAUT32!__imp_VariantClear` at `0x1800b8976`
- `OLEAUT32!__imp_VariantClear` at `0x1800b8d3a`
- `OLEAUT32!__imp_VariantClear` at `0x1800b8e09`
- `OLEAUT32!__imp_VariantClear` at `0x1800b8e86`
- `OLEAUT32!__imp_VariantClear` at `0x1800b8976`
- `OLEAUT32!__imp_VariantClear` at `0x1800b8d3a`
- `OLEAUT32!__imp_VariantClear` at `0x1800b8e09`
- `OLEAUT32!__imp_VariantClear` at `0x1800b8e86`

## string_xrefs

- `0x1800b8d18`: `typeConfig`
- `0x1800b8c36`: `valueConfigured`
- `0x1800b8dbf`: `UriCount`
- `0x1800b8961`: `DeclaredConfigurationStore_ConstructURIStorage`
- `0x1800b8f03`: `DeclaredConfigurationStore_ConstructURIStorage`
- `0x1800b894f`: `DCCDNUtil_SetRegistryString`
- `0x1800b8ee3`: `DCCDNUtil_SetRegistryString`
- `0x1800b8674`: `URI%d`
- `0x1800b8f2e`: `DCCDNUtil_SetRegistryDWORD`
- `0x1800b8e6a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800b8f27`: `Failed to set the string size for URI value`
- `0x1800b8ef8`: `DeclaredConfigurationStore_GetFilePathForUriValue`
- `0x1800b8edc`: `Failed to set the file path for the URI value`
- `0x1800b8ece`: `DeclaredConfigurationStore_WriteFileForUriValue`
- `0x1800b8956`: `Failed to write URI value to registry`
- `0x1800b8a09`: `DCCDNUtil_SetRegistryMultiString`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int __fastcall ConstructCSPProvider(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2,
        struct DCCSP *a3,
        HKEY a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  unsigned __int16 *v10; // rbx
  int result; // eax
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r14d
  struct DCURI **v14; // rdi
  int FilePathForUriValue; // ebx
  const unsigned __int16 *v16; // r9
  int v17; // eax
  const unsigned __int16 *v18; // r9
  const unsigned __int16 *v19; // r9
  unsigned __int64 v20; // rcx
  __int64 v21; // rax
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // rdx
  struct DCURI *v24; // rdx
  int v25; // eax
  unsigned int v26; // r9d
  const unsigned __int16 *v27; // r9
  int v28; // eax
  CDeclaredConfigurationLogger *Logger; // rax
  const unsigned __int16 *v30; // r8
  const wchar_t *v31; // r9
  int v32; // eax
  const unsigned __int16 *v33; // r9
  int v34; // eax
  const unsigned __int16 *v35; // r9
  const unsigned __int16 *v36; // rcx
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // r11
  DWORD v39; // r11d
  __int64 v40; // rax
  const unsigned __int16 *v41; // rbx
  __int64 v42; // rax
  _QWORD *v43; // r8
  __int64 v44; // rdx
  void *v45; // r9
  unsigned int v46; // edi
  const unsigned __int16 *v47; // r8
  int v48; // edi
  __int64 v49; // rdx
  CDeclaredConfigurationLogger *v50; // rax
  const unsigned __int16 *v51; // r9
  const unsigned __int16 *v52; // r8
  int dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v55; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp-88h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+80h] [rbp-80h] BYREF
  void *p_hKey; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  char v61; // [rsp+98h] [rbp-68h]
  unsigned __int64 v62; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v63; // [rsp+A8h] [rbp-58h]
  struct DCURI **v64; // [rsp+B0h] [rbp-50h]
  VARIANTARG v65; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v66[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v67[32]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SubKey[16]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v10 = a5;
  v63 = a5;
  v55 = a6;
  SubKey[0] = 0;
  result = DCCDNUtil_SetRegistryDWORD(a4, 0, L"ProviderType", 1u);
  if ( result >= 0 )
  {
    v12 = (const unsigned __int16 *)((char *)a3 + 88);
    if ( *((_QWORD *)a3 + 14) > 7u )
      v12 = *(const unsigned __int16 **)v12;
    result = DCCDNUtil_SetRegistryString(a4, 0, L"csp", v12, 0);
    if ( result >= 0 )
    {
      v13 = 1;
      v14 = (struct DCURI **)*((_QWORD *)a3 + 2);
      v64 = (struct DCURI **)*((_QWORD *)a3 + 3);
      if ( v14 != v64 )
      {
        while ( 1 )
        {
          result = StringCchPrintfW(SubKey, 0xFu, L"URI%d", v13);
          if ( result < 0 )
            return result;
          hKey = 0;
          p_hKey = &hKey;
          phkResult = 0;
          v61 = 1;
          FilePathForUriValue = RegCreateKeyExW(a4, SubKey, 0, 0, 0, 0x2011Fu, 0, &phkResult, 0);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
          if ( FilePathForUriValue )
          {
            if ( FilePathForUriValue > 0 )
              FilePathForUriValue = (unsigned __int16)FilePathForUriValue | 0x80070000;
            goto LABEL_127;
          }
          v16 = (const unsigned __int16 *)*v14;
          if ( *((_QWORD *)*v14 + 3) > 7u )
            v16 = *(const unsigned __int16 **)v16;
          v17 = DCCDNUtil_SetRegistryString(hKey, 0, L"uri", v16, 0);
          if ( v17 < 0 )
            goto LABEL_124;
          v18 = (const unsigned __int16 *)((char *)*v14 + 264);
          if ( *((_QWORD *)*v14 + 36) > 7u )
            v18 = *(const unsigned __int16 **)v18;
          v17 = DCCDNUtil_SetRegistryString(hKey, 0, L"alias", v18, 0);
          if ( v17 < 0 )
          {
LABEL_124:
            FilePathForUriValue = v17;
            goto LABEL_127;
          }
          v19 = (const unsigned __int16 *)((char *)*v14 + 296);
          v20 = *((_QWORD *)*v14 + 40);
          if ( v20 <= 7 )
            v21 = (__int64)*v14 + 296;
          else
            v21 = *(_QWORD *)v19;
          if ( v21 )
          {
            if ( v20 > 7 )
              v19 = *(const unsigned __int16 **)v19;
            FilePathForUriValue = DCCDNUtil_SetRegistryString(hKey, 0, L"reserved", v19, 0);
            if ( FilePathForUriValue < 0 )
              goto LABEL_127;
          }
          VariantInit(&pvarg);
          pvarg.vt = 3;
          pvarg.lVal = *((_DWORD *)*v14 + 44);
          v22 = (const unsigned __int16 *)((char *)a2 + 96);
          if ( *((_QWORD *)a2 + 15) > 7u )
            v22 = *(const unsigned __int16 **)v22;
          if ( *((_QWORD *)a2 + 3) <= 7u )
            v23 = (const unsigned __int16 *)a2;
          else
            v23 = *(const unsigned __int16 **)a2;
          FilePathForUriValue = DeclaredConfigurationStore_WriteResultData(
                                  a1,
                                  v23,
                                  v22,
                                  0,
                                  v63,
                                  SubKey,
                                  L"state",
                                  &pvarg);
          if ( FilePathForUriValue < 0 )
            goto LABEL_50;
          FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"state", *((_DWORD *)*v14 + 44));
          if ( FilePathForUriValue < 0 )
            goto LABEL_50;
          FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"typeStored", *((_DWORD *)*v14 + 96));
          if ( FilePathForUriValue < 0 )
            goto LABEL_50;
          v25 = *((_DWORD *)*v14 + 49);
          if ( v25 == 1 )
          {
            v26 = 1;
          }
          else
          {
            if ( v25 != 2 )
              goto LABEL_34;
            v26 = 2;
          }
          FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"RecursiveQueryLevel", v26);
          if ( FilePathForUriValue < 0 )
            goto LABEL_50;
LABEL_34:
          ++v13;
          if ( *((_DWORD *)a2 + 68) != 1 )
            goto LABEL_83;
          v24 = *v14;
          if ( *((_DWORD *)*v14 + 96) != 1 )
          {
            switch ( *((_DWORD *)*v14 + 96) )
            {
              case 3:
                v32 = DCSetRegistryBinary(hKey, 0, L"value", *((BYTE **)v24 + 49), *((_DWORD *)v24 + 100));
                goto LABEL_61;
              case 4:
                v32 = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"value", *((_DWORD *)v24 + 98));
                goto LABEL_61;
              case 5:
                goto LABEL_82;
            }
            if ( *((_DWORD *)*v14 + 96) != 6 )
            {
              if ( *((_DWORD *)*v14 + 96) != 7 )
              {
                if ( *((_DWORD *)*v14 + 96) != 8 )
                {
                  FilePathForUriValue = -2147418113;
                  goto LABEL_50;
                }
LABEL_42:
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                {
                  v27 = (const unsigned __int16 *)((char *)*v14 + 32);
                  if ( *((_QWORD *)*v14 + 7) > 7u )
                    v27 = *(const unsigned __int16 **)v27;
                  v28 = DCCDNUtil_SetRegistryString(hKey, 0, L"value", v27, 1);
                  FilePathForUriValue = v28;
                  if ( v28 == -2147023446 )
                  {
                    v48 = DCSetRegistryLargeString(*v14, hKey, a1, a2, v55, v13);
                    if ( v48 >= 0 )
                      goto LABEL_50;
                    v49 = 1688;
LABEL_111:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v49,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                      (const char *)(unsigned int)v48,
                      dwOptions);
                    VariantClear(&pvarg);
                    FilePathForUriValue = v48;
                    goto LABEL_127;
                  }
                  if ( v28 < 0 )
                    goto LABEL_47;
                  goto LABEL_83;
                }
              }
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                goto LABEL_82;
              v33 = (const unsigned __int16 *)((char *)*v14 + 32);
              if ( *((_QWORD *)*v14 + 7) > 7u )
                v33 = *(const unsigned __int16 **)v33;
              v34 = DCCDNUtil_SetRegistryMultiString(hKey, 0, L"value", v33);
              FilePathForUriValue = v34;
              if ( v34 == -2147023446 )
              {
                v48 = DCSetRegistryLargeString(*v14, hKey, a1, a2, v55, v13);
                if ( v48 >= 0 )
                  goto LABEL_50;
                v49 = 1715;
                goto LABEL_111;
              }
              if ( v34 < 0 )
              {
                Logger = CDeclaredConfigurationLogger::GetLogger();
                v30 = L"DCCDNUtil_SetRegistryMultiString";
                goto LABEL_48;
              }
              goto LABEL_83;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
            {
              v32 = DCCDNUtil_SetRegistryQWORD(hKey, 0, L"value", *((_QWORD *)*v14 + 49));
LABEL_61:
              FilePathForUriValue = v32;
LABEL_82:
              if ( FilePathForUriValue < 0 )
                goto LABEL_50;
              goto LABEL_83;
            }
            goto LABEL_42;
          }
          v35 = (const unsigned __int16 *)((char *)v24 + 32);
          if ( *((_QWORD *)v24 + 7) > 7u )
            v35 = *(const unsigned __int16 **)v35;
          FilePathForUriValue = DCCDNUtil_SetRegistryString(hKey, 0, L"value", v35, 0);
          if ( FilePathForUriValue != -2147023446 )
          {
            if ( FilePathForUriValue < 0 )
            {
LABEL_47:
              Logger = CDeclaredConfigurationLogger::GetLogger();
              v30 = L"DCCDNUtil_SetRegistryString";
LABEL_48:
              v31 = L"Failed to write URI value to registry";
              goto LABEL_49;
            }
            goto LABEL_82;
          }
          *(_QWORD *)nNumberOfBytesToWrite = 0;
          v36 = (const unsigned __int16 *)((char *)*v14 + 32);
          if ( *((_QWORD *)*v14 + 7) > 7u )
            v36 = *(const unsigned __int16 **)v36;
          FilePathForUriValue = StringCchLengthW(v36, 0x7FFFFFFFu, (unsigned __int64 *)nNumberOfBytesToWrite);
          if ( FilePathForUriValue < 0 )
          {
            Logger = CDeclaredConfigurationLogger::GetLogger();
            v31 = (const wchar_t *)*v14;
            if ( *((_QWORD *)*v14 + 3) > 7u )
              v31 = *(const wchar_t **)v31;
            v30 = L"StringCchLengthW: failed to get string size";
            goto LABEL_49;
          }
          v62 = v38;
          FilePathForUriValue = ULongLongMult(*(unsigned __int64 *)nNumberOfBytesToWrite, v37, &v62);
          if ( FilePathForUriValue < 0 )
          {
            Logger = CDeclaredConfigurationLogger::GetLogger();
            v31 = L"failed to calculate size";
            v30 = L"SizeTMult";
            goto LABEL_49;
          }
          nNumberOfBytesToWrite[0] = v39;
          FilePathForUriValue = ULongLongToULong(v62, nNumberOfBytesToWrite);
          if ( FilePathForUriValue < 0 )
          {
            Logger = CDeclaredConfigurationLogger::GetLogger();
            v31 = L"failed to convert size to DWORD";
            v30 = L"SIZETToDWord";
LABEL_49:
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              Logger,
              L"DeclaredConfigurationStore_ConstructURIStorage",
              v30,
              v31,
              FilePathForUriValue);
            goto LABEL_50;
          }
          FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"valueSize", nNumberOfBytesToWrite[0]);
          if ( FilePathForUriValue < 0 )
          {
            Logger = CDeclaredConfigurationLogger::GetLogger();
            v31 = L"Failed to set the string size for URI value";
            v30 = L"DCCDNUtil_SetRegistryDWORD";
            goto LABEL_49;
          }
          lpFileName = 0;
          p_hKey = &lpFileName;
          phkResult = 0;
          v61 = 1;
          v40 = std::to_wstring(v67, v13);
          v41 = (const unsigned __int16 *)v40;
          if ( *(_QWORD *)(v40 + 24) > 7u )
            v41 = *(const unsigned __int16 **)v40;
          v42 = std::to_wstring(v66, v55);
          if ( *(_QWORD *)(v42 + 24) > 7u )
            v42 = *(_QWORD *)v42;
          FilePathForUriValue = DeclaredConfigurationStore_GetFilePathForUriValue(
                                  a1,
                                  a2,
                                  (const unsigned __int16 *)v42,
                                  v41,
                                  (unsigned __int16 **)&phkResult);
          std::wstring::_Tidy_deallocate(v66);
          std::wstring::_Tidy_deallocate(v67);
          wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_hKey);
          if ( FilePathForUriValue < 0 )
          {
            v50 = CDeclaredConfigurationLogger::GetLogger();
            v51 = &word_180142E98;
            v52 = L"DeclaredConfigurationStore_GetFilePathForUriValue";
LABEL_117:
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v50,
              L"DeclaredConfigurationStore_ConstructURIStorage",
              v52,
              v51,
              FilePathForUriValue);
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpFileName);
LABEL_50:
            VariantClear(&pvarg);
LABEL_127:
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            return FilePathForUriValue;
          }
          FilePathForUriValue = DCCDNUtil_SetRegistryString(hKey, 0, L"value", lpFileName, 0);
          if ( FilePathForUriValue < 0 )
          {
            v50 = CDeclaredConfigurationLogger::GetLogger();
            v51 = L"Failed to set the file path for the URI value";
            v52 = L"DCCDNUtil_SetRegistryString";
            goto LABEL_117;
          }
          v43 = (_QWORD *)((char *)*v14 + 32);
          if ( *((_QWORD *)*v14 + 7) > 7u )
            v43 = (_QWORD *)*v43;
          FilePathForUriValue = DeclaredConfigurationStore_WriteFileForUriValue(
                                  lpFileName,
                                  nNumberOfBytesToWrite[0],
                                  v43);
          if ( FilePathForUriValue < 0 )
          {
            v50 = CDeclaredConfigurationLogger::GetLogger();
            v51 = lpFileName;
            v52 = L"DeclaredConfigurationStore_WriteFileForUriValue";
            goto LABEL_117;
          }
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpFileName);
LABEL_83:
          LOBYTE(v24) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_SupportNotConfigured>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_SupportNotConfigured>::GetImpl'::`2'::impl,
            v24);
          if ( *((_BYTE *)*v14 + 408) == 1 && *((_DWORD *)a2 + 69) == 2 )
          {
            FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"valueConfigured", 0);
            if ( FilePathForUriValue < 0 )
              goto LABEL_50;
          }
          LOBYTE(v44) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_DriftControl>::GetImpl'::`2'::impl,
            v44);
          if ( *((_DWORD *)a2 + 68) == 1 )
          {
            v45 = (void *)*((_QWORD *)*v14 + 41);
            if ( v45 )
            {
              FilePathForUriValue = DCCDNUtil_SetRegistryBinary(hKey, 0, L"hashValue", v45, 0x10u);
              if ( FilePathForUriValue < 0 )
                goto LABEL_50;
            }
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
          {
            if ( *((_DWORD *)a2 + 69) == 2 && *((_DWORD *)a2 + 68) == 1 )
            {
              FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"behavior", *((_DWORD *)*v14 + 84));
              if ( FilePathForUriValue < 0 )
                goto LABEL_50;
            }
          }
          FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"typeStored", *((_DWORD *)*v14 + 96));
          if ( FilePathForUriValue < 0 )
            goto LABEL_50;
          FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"typeConfig", *((_DWORD *)*v14 + 41));
          if ( FilePathForUriValue < 0 )
            goto LABEL_50;
          VariantClear(&pvarg);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          v14 += 2;
          if ( v14 == v64 )
          {
            v10 = v63;
            break;
          }
        }
      }
      v55 = 0;
      result = ULongLongToULong((__int64)(*((_QWORD *)a3 + 3) - *((_QWORD *)a3 + 2)) >> 4, &v55);
      if ( result >= 0 )
      {
        VariantInit(&v65);
        v65.vt = 3;
        v46 = v55;
        v65.lVal = v55;
        v47 = (const unsigned __int16 *)((char *)a2 + 96);
        if ( *((_QWORD *)a2 + 15) > 7u )
          v47 = *(const unsigned __int16 **)v47;
        if ( *((_QWORD *)a2 + 3) > 7u )
          a2 = *(struct DCDocument **)a2;
        FilePathForUriValue = DeclaredConfigurationStore_WriteResultData(
                                a1,
                                (const unsigned __int16 *)a2,
                                v47,
                                0,
                                v10,
                                0,
                                L"UriCount",
                                &v65);
        if ( FilePathForUriValue >= 0 )
        {
          FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(a4, 0, L"UriCount", v46);
          if ( FilePathForUriValue >= 0 )
            FilePathForUriValue = 0;
        }
        VariantClear(&v65);
        return FilePathForUriValue;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b85c0  push    rbp
0x1800b85c2  push    rbx
0x1800b85c3  push    rsi
0x1800b85c4  push    rdi
0x1800b85c5  push    r12
0x1800b85c7  push    r13
0x1800b85c9  push    r14
0x1800b85cb  push    r15
0x1800b85cd  lea     rbp, [rsp-48h]
0x1800b85d2  sub     rsp, 148h
0x1800b85d9  mov     rax, cs:__security_cookie
0x1800b85e0  xor     rax, rsp
0x1800b85e3  mov     [rbp+80h+var_50], rax
0x1800b85e7  mov     r13, r9
0x1800b85ea  mov     r15, r8
0x1800b85ed  mov     rsi, rdx
0x1800b85f0  mov     r12, rcx
0x1800b85f3  mov     rbx, [rbp+80h+arg_20]
0x1800b85fa  mov     [rbp+80h+var_D8], rbx
0x1800b85fe  mov     eax, [rbp+80h+arg_28]
0x1800b8604  mov     [rsp+180h+var_128], eax
0x1800b8608  xor     eax, eax
0x1800b860a  mov     [rbp+80h+SubKey], ax
0x1800b860e  lea     edi, [rax+1]
0x1800b8611  mov     r9d, edi; unsigned int
0x1800b8614  lea     r8, aProvidertype_0; "ProviderType"
0x1800b861b  xor     edx, edx; unsigned __int16 *
0x1800b861d  mov     rcx, r13; HKEY
0x1800b8620  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800b8625  test    eax, eax
0x1800b8627  js      loc_1800B8E11
0x1800b862d  lea     r9, [r15+58h]
0x1800b8631  cmp     qword ptr [r9+18h], 7
0x1800b8636  jbe     short loc_1800B863B
0x1800b8638  mov     r9, [r9]; unsigned __int16 *
0x1800b863b  mov     byte ptr [rsp+180h+dwOptions], 0; bool
0x1800b8640  lea     r8, aCsp_0; "csp"
0x1800b8647  xor     edx, edx; unsigned __int16 *
0x1800b8649  mov     rcx, r13; HKEY
0x1800b864c  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800b8651  test    eax, eax
0x1800b8653  js      loc_1800B8E11
0x1800b8659  mov     r14d, edi
0x1800b865c  mov     rdi, [r15+10h]
0x1800b8660  mov     rax, [r15+18h]
0x1800b8664  mov     [rbp+80h+var_D0], rax
0x1800b8668  cmp     rdi, rax
0x1800b866b  jz      loc_1800B8D5D
0x1800b8671  mov     r9d, r14d
0x1800b8674  lea     r8, aUriD_0; "URI%d"
0x1800b867b  mov     edx, 0Fh; unsigned __int64
0x1800b8680  lea     rcx, [rbp+80h+SubKey]; unsigned __int16 *
0x1800b8684  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b8689  xor     ecx, ecx
0x1800b868b  test    eax, eax
0x1800b868d  js      loc_1800B8E11
0x1800b8693  mov     [rsp+180h+hKey], rcx
0x1800b8698  lea     rax, [rsp+180h+hKey]
0x1800b869d  mov     [rbp+80h+var_F8], rax
0x1800b86a1  mov     [rbp+80h+var_F0], rcx
0x1800b86a5  mov     [rbp+80h+var_E8], 1
0x1800b86a9  mov     [rsp+180h+lpdwDisposition], rcx; lpdwDisposition
0x1800b86ae  lea     rax, [rbp+80h+var_F0]
0x1800b86b2  mov     [rsp+180h+phkResult], rax; phkResult
0x1800b86b7  mov     [rsp+180h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1800b86bc  mov     [rsp+180h+samDesired], 2011Fh; samDesired
0x1800b86c4  mov     [rsp+180h+dwOptions], ecx; dwOptions
0x1800b86c8  xor     r9d, r9d; lpClass
0x1800b86cb  xor     r8d, r8d; Reserved
0x1800b86ce  lea     rdx, [rbp+80h+SubKey]; lpSubKey
0x1800b86d2  mov     rcx, r13; hKey
0x1800b86d5  call    cs:__imp_RegCreateKeyExW
0x1800b86db  mov     ebx, eax
0x1800b86dd  lea     rcx, [rbp+80h+var_F8]
0x1800b86e1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800b86e6  test    ebx, ebx
0x1800b86e8  jnz     loc_1800B8F8C
0x1800b86ee  mov     r9, [rdi]
0x1800b86f1  cmp     qword ptr [r9+18h], 7
0x1800b86f6  jbe     short loc_1800B86FB
0x1800b86f8  mov     r9, [r9]; unsigned __int16 *
0x1800b86fb  xor     ebx, ebx
0x1800b86fd  mov     byte ptr [rsp+180h+dwOptions], bl; bool
0x1800b8701  lea     r8, aUri_1; "uri"
0x1800b8708  xor     edx, edx; unsigned __int16 *
0x1800b870a  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b870f  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800b8714  test    eax, eax
0x1800b8716  js      loc_1800B8F88
0x1800b871c  mov     r9, [rdi]
0x1800b871f  add     r9, 108h
0x1800b8726  cmp     qword ptr [r9+18h], 7
0x1800b872b  jbe     short loc_1800B8730
0x1800b872d  mov     r9, [r9]; unsigned __int16 *
0x1800b8730  mov     byte ptr [rsp+180h+dwOptions], bl; bool
0x1800b8734  lea     r8, aAlias; "alias"
0x1800b873b  xor     edx, edx; unsigned __int16 *
0x1800b873d  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b8742  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800b8747  test    eax, eax
0x1800b8749  js      loc_1800B8F88
0x1800b874f  mov     rax, [rdi]
0x1800b8752  lea     r9, [rax+128h]
0x1800b8759  mov     rcx, [rax+140h]
0x1800b8760  cmp     rcx, 7
0x1800b8764  jbe     short loc_1800B876B
0x1800b8766  mov     rax, [r9]
0x1800b8769  jmp     short loc_1800B876E
0x1800b876b  mov     rax, r9
0x1800b876e  test    rax, rax
0x1800b8771  jz      short loc_1800B879D
0x1800b8773  cmp     rcx, 7
0x1800b8777  jbe     short loc_1800B877C
0x1800b8779  mov     r9, [r9]; unsigned __int16 *
0x1800b877c  mov     byte ptr [rsp+180h+dwOptions], bl; bool
0x1800b8780  lea     r8, aReserved_0; "reserved"
0x1800b8787  xor     edx, edx; unsigned __int16 *
0x1800b8789  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b878e  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800b8793  mov     ebx, eax
0x1800b8795  test    eax, eax
0x1800b8797  js      loc_1800B8F97
0x1800b879d  lea     rcx, [rsp+180h+pvarg]; pvarg
0x1800b87a2  call    cs:__imp_VariantInit
0x1800b87a8  nop
0x1800b87a9  mov     eax, 3
0x1800b87ae  mov     word ptr [rsp+180h+pvarg], ax
0x1800b87b3  mov     rax, [rdi]
0x1800b87b6  mov     ecx, [rax+0B0h]
0x1800b87bc  mov     dword ptr [rsp+180h+pvarg+8], ecx
0x1800b87c0  lea     r8, [rsi+60h]
0x1800b87c4  cmp     qword ptr [rsi+78h], 7
0x1800b87c9  jbe     short loc_1800B87CE
0x1800b87cb  mov     r8, [r8]; unsigned __int16 *
0x1800b87ce  cmp     qword ptr [rsi+18h], 7
0x1800b87d3  jbe     short loc_1800B87DA
0x1800b87d5  mov     rdx, [rsi]
0x1800b87d8  jmp     short loc_1800B87DD
0x1800b87da  mov     rdx, rsi; unsigned __int16 *
0x1800b87dd  lea     rax, [rsp+180h+pvarg]
0x1800b87e2  mov     [rsp+180h+phkResult], rax; struct tagVARIANT *
0x1800b87e7  lea     rax, ValueName; "state"
0x1800b87ee  mov     [rsp+180h+lpSecurityAttributes], rax; lpValueName
0x1800b87f3  lea     rax, [rbp+80h+SubKey]
0x1800b87f7  mov     qword ptr [rsp+180h+samDesired], rax; unsigned __int16 *
0x1800b87fc  mov     rax, [rbp+80h+var_D8]
0x1800b8800  mov     qword ptr [rsp+180h+dwOptions], rax; unsigned __int16 *
0x1800b8805  xor     r9d, r9d; unsigned __int16 *
0x1800b8808  mov     rcx, r12; struct DeclaredConfigurationScopeData *
0x1800b880b  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x1800b8810  mov     ebx, eax
0x1800b8812  test    eax, eax
0x1800b8814  js      loc_1800B8971
0x1800b881a  mov     r9, [rdi]
0x1800b881d  mov     r9d, [r9+0B0h]; unsigned int
0x1800b8824  lea     r8, ValueName; "state"
0x1800b882b  xor     edx, edx; unsigned __int16 *
0x1800b882d  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b8832  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800b8837  mov     ebx, eax
0x1800b8839  test    eax, eax
0x1800b883b  js      loc_1800B8971
0x1800b8841  mov     r9, [rdi]
0x1800b8844  mov     r9d, [r9+180h]; unsigned int
0x1800b884b  lea     r8, aTypestored; "typeStored"
0x1800b8852  xor     edx, edx; unsigned __int16 *
0x1800b8854  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b8859  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800b885e  mov     ebx, eax
0x1800b8860  test    eax, eax
0x1800b8862  js      loc_1800B8971
0x1800b8868  mov     rcx, [rdi]
0x1800b886b  mov     eax, [rcx+0C4h]
0x1800b8871  cmp     eax, 1
0x1800b8874  jnz     short loc_1800B887B
0x1800b8876  mov     r9d, eax
0x1800b8879  jmp     short loc_1800B8883
0x1800b887b  cmp     eax, 2
0x1800b887e  jnz     short loc_1800B88A0
0x1800b8880  mov     r9d, eax; unsigned int
0x1800b8883  lea     r8, aRecursivequery; "RecursiveQueryLevel"
0x1800b888a  xor     edx, edx; unsigned __int16 *
0x1800b888c  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b8891  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800b8896  test    eax, eax
0x1800b8898  mov     ebx, eax
0x1800b889a  js      loc_1800B8971
0x1800b88a0  inc     r14d
0x1800b88a3  cmp     dword ptr [rsi+110h], 1
0x1800b88aa  jnz     loc_1800B8C10
0x1800b88b0  mov     rdx, [rdi]
0x1800b88b3  mov     ecx, [rdx+180h]
0x1800b88b9  sub     ecx, 1
0x1800b88bc  jz      loc_1800B8A5C
0x1800b88c2  sub     ecx, 2
0x1800b88c5  jz      loc_1800B8A31
0x1800b88cb  sub     ecx, 1
0x1800b88ce  jz      loc_1800B8A15
0x1800b88d4  sub     ecx, 1
0x1800b88d7  jz      loc_1800B8C08
0x1800b88dd  sub     ecx, 1
0x1800b88e0  jz      loc_1800B8981
0x1800b88e6  sub     ecx, 1
0x1800b88e9  jz      loc_1800B89B7
0x1800b88ef  cmp     ecx, 1
0x1800b88f2  jnz     loc_1800B8E31
0x1800b88f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800b88ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800b8904  test    al, al
0x1800b8906  jz      loc_1800B89B7
0x1800b890c  mov     r9, [rdi]
0x1800b890f  add     r9, 20h ; ' '
0x1800b8913  cmp     qword ptr [r9+18h], 7
0x1800b8918  jbe     short loc_1800B891D
0x1800b891a  mov     r9, [r9]; unsigned __int16 *
0x1800b891d  mov     byte ptr [rsp+180h+dwOptions], 1; bool
0x1800b8922  lea     r8, aValue_0; "value"
0x1800b8929  xor     edx, edx; unsigned __int16 *
0x1800b892b  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b8930  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800b8935  mov     ebx, eax
0x1800b8937  cmp     eax, 800705AAh
0x1800b893c  jz      loc_1800B8E3B
0x1800b8942  test    eax, eax
0x1800b8944  jns     loc_1800B8C10
0x1800b894a  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800b894f  lea     r8, aDccdnutilSetre; "DCCDNUtil_SetRegistryString"
0x1800b8956  lea     r9, aFailedToWriteU; "Failed to write URI value to registry"
0x1800b895d  mov     [rsp+180h+dwOptions], ebx; int
0x1800b8961  lea     rdx, aDeclaredconfig_180; "DeclaredConfigurationStore_ConstructURI"...
0x1800b8968  mov     rcx, rax; this
0x1800b896b  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800b8970  nop
0x1800b8971  lea     rcx, [rsp+180h+pvarg]; pvarg
0x1800b8976  call    cs:__imp_VariantClear
0x1800b897c  jmp     loc_1800B8F97
0x1800b8981  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800b8988  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800b898d  test    al, al
0x1800b898f  jz      loc_1800B88F8
0x1800b8995  mov     r9, [rdi]
0x1800b8998  mov     r9, [r9+188h]; unsigned __int64
0x1800b899f  lea     r8, aValue_0; "value"
0x1800b89a6  xor     edx, edx; unsigned __int16 *
0x1800b89a8  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b89ad  call    ?DCCDNUtil_SetRegistryQWORD@@YAJPEAUHKEY__@@PEBG1_K@Z; DCCDNUtil_SetRegistryQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)
0x1800b89b2  jmp     loc_1800B8A55
0x1800b89b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800b89be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800b89c3  test    al, al
0x1800b89c5  jz      loc_1800B8C08
0x1800b89cb  mov     r9, [rdi]
0x1800b89ce  add     r9, 20h ; ' '
0x1800b89d2  cmp     qword ptr [r9+18h], 7
0x1800b89d7  jbe     short loc_1800B89DC
0x1800b89d9  mov     r9, [r9]; unsigned __int16 *
0x1800b89dc  lea     r8, aValue_0; "value"
0x1800b89e3  xor     edx, edx; unsigned __int16 *
0x1800b89e5  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b89ea  call    ?DCCDNUtil_SetRegistryMultiString@@YAJPEAUHKEY__@@PEBG11@Z; DCCDNUtil_SetRegistryMultiString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800b89ef  mov     ebx, eax
0x1800b89f1  cmp     eax, 800705AAh
0x1800b89f6  jz      loc_1800B8E93
0x1800b89fc  test    eax, eax
0x1800b89fe  jns     loc_1800B8C10
0x1800b8a04  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800b8a09  lea     r8, aDccdnutilSetre_1; "DCCDNUtil_SetRegistryMultiString"
0x1800b8a10  jmp     loc_1800B8956
0x1800b8a15  mov     r9d, [rdx+188h]; unsigned int
0x1800b8a1c  lea     r8, aValue_0; "value"
0x1800b8a23  xor     edx, edx; unsigned __int16 *
0x1800b8a25  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b8a2a  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800b8a2f  jmp     short loc_1800B8A55
0x1800b8a31  mov     eax, [rdx+190h]
0x1800b8a37  mov     [rsp+180h+dwOptions], eax; cbData
0x1800b8a3b  mov     r9, [rdx+188h]; lpData
0x1800b8a42  lea     r8, aValue_0; "value"
0x1800b8a49  xor     edx, edx; lpSubKey
0x1800b8a4b  mov     rcx, [rsp+180h+hKey]; hKey
0x1800b8a50  call    ?DCSetRegistryBinary@@YAJPEAUHKEY__@@PEBG1PEAXK@Z; DCSetRegistryBinary(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x1800b8a55  mov     ebx, eax
0x1800b8a57  jmp     loc_1800B8C08
0x1800b8a5c  lea     r9, [rdx+20h]
0x1800b8a60  cmp     qword ptr [rdx+38h], 7
0x1800b8a65  jbe     short loc_1800B8A6A
0x1800b8a67  mov     r9, [r9]; unsigned __int16 *
0x1800b8a6a  mov     byte ptr [rsp+180h+dwOptions], 0; bool
0x1800b8a6f  lea     r8, aValue_0; "value"
0x1800b8a76  xor     edx, edx; unsigned __int16 *
0x1800b8a78  mov     rcx, [rsp+180h+hKey]; HKEY
0x1800b8a7d  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800b8a82  mov     ebx, eax
0x1800b8a84  cmp     eax, 800705AAh
0x1800b8a89  jnz     loc_1800B8C00
0x1800b8a8f  xor     r11d, r11d
0x1800b8a92  mov     qword ptr [rbp+80h+nNumberOfBytesToWrite], r11
0x1800b8a96  mov     rcx, [rdi]
0x1800b8a99  add     rcx, 20h ; ' '
0x1800b8a9d  cmp     qword ptr [rcx+18h], 7
  ... truncated ...
```
