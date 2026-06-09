# ConstructDSCNativeProvider(DeclaredConfigurationScopeData *,DCDocument *,DCPersistedDocType,DCDSCNative *,HKEY__ *,ushort const *,int,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *)

- ea: `0x1800c7600`
- end: `0x1800c7d9b`
- name: `?ConstructDSCNativeProvider@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@W4DCPersistedDocType@@PEAVDCDSCNative@@PEAUHKEY__@@PEBGHPEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1947`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180067160`
- `0x1800c7da4`

## callees

- `0x18000b9e0`
- `0x180011fe0`
- `0x180018744`
- `0x180018ac0`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001cec8`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18004a5d4`
- `0x18004a630`
- `0x18004cb4c`
- `0x18004dc70`
- `0x18004e324`
- `0x180072788`
- `0x1800869b0`
- `0x180086c10`
- `0x1800a0de4`
- `0x1800a17cc`
- `0x1800c5fd0`
- `0x1800c7600`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x1801006c8`
- `0x180100e3c`
- `0x18010136c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c779f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c779f`
- `OLEAUT32!__imp_VariantInit` at `0x1800c7cd5`
- `OLEAUT32!__imp_VariantInit` at `0x1800c7cd5`
- `OLEAUT32!__imp_VariantClear` at `0x1800c7d70`
- `OLEAUT32!__imp_VariantClear` at `0x1800c7d70`

## string_xrefs

- `0x1800c7a0e`: `DCCDNUtil_SetRegistryString`
- `0x1800c7c20`: `DCCDNUtil_SetRegistryString`
- `0x1800c7b07`: `DCCDNUtil_SetRegistryDWORD`
- `0x1800c7b00`: `Failed to set the string size for URI value`
- `0x1800c7bc7`: `DeclaredConfigurationStore_GetFilePathForUriValue`
- `0x1800c7c19`: `Failed to set the file path for the URI value`
- `0x1800c7c54`: `DeclaredConfigurationStore_WriteFileForUriValue`
- `0x1800c7a07`: `Failed to write URI value to registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
int __fastcall ConstructDSCNativeProvider(
        struct DeclaredConfigurationScopeData *a1,
        __int64 *a2,
        int a3,
        _QWORD *a4,
        HKEY hKey,
        unsigned __int16 *a6,
        unsigned int a7,
        __int64 a8)
{
  int v10; // r13d
  int result; // eax
  const unsigned __int16 *v12; // r9
  const unsigned __int16 *v13; // r9
  unsigned int v14; // r12d
  const unsigned __int16 **v15; // rdi
  const unsigned __int16 **v16; // rax
  int FilePathForUriValue; // ebx
  int v18; // eax
  const unsigned __int16 *v19; // r9
  __int64 v20; // rbx
  const unsigned __int16 *v21; // r9
  int v22; // ebx
  const unsigned __int16 *v23; // r9
  int v24; // eax
  CDeclaredConfigurationLogger *Logger; // rax
  const wchar_t *v26; // r9
  const unsigned __int16 *v27; // r8
  const unsigned __int16 *v28; // rcx
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // r11
  DWORD v31; // r11d
  __int64 v32; // rax
  const unsigned __int16 *v33; // rbx
  __int64 v34; // rax
  CDeclaredConfigurationLogger *v35; // rax
  const unsigned __int16 *v36; // r9
  const unsigned __int16 *v37; // r8
  const unsigned __int16 *v38; // r8
  int v39; // edi
  const unsigned __int16 *v40; // r8
  HKEY v41; // [rsp+50h] [rbp-168h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+58h] [rbp-160h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-158h] BYREF
  int v44; // [rsp+68h] [rbp-150h]
  unsigned int v45; // [rsp+6Ch] [rbp-14Ch]
  void *p_lpFileName; // [rsp+70h] [rbp-148h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-140h] BYREF
  char v48; // [rsp+80h] [rbp-138h]
  __int64 v49; // [rsp+88h] [rbp-130h]
  unsigned __int64 v50; // [rsp+90h] [rbp-128h] BYREF
  struct DeclaredConfigurationScopeData *v51; // [rsp+98h] [rbp-120h]
  const unsigned __int16 **v52; // [rsp+A0h] [rbp-118h]
  unsigned __int16 *v53; // [rsp+A8h] [rbp-110h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-108h] BYREF
  unsigned __int16 *v55[5]; // [rsp+C8h] [rbp-F0h] BYREF
  _BYTE v56[64]; // [rsp+F0h] [rbp-C8h] BYREF
  _BYTE v57[32]; // [rsp+130h] [rbp-88h] BYREF
  WCHAR SubKey[16]; // [rsp+150h] [rbp-68h] BYREF

  v44 = a3;
  v51 = a1;
  v53 = a6;
  v45 = a7;
  v49 = a8;
  v10 = 0;
  nNumberOfBytesToWrite[0] = 0;
  SubKey[0] = 0;
  result = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"ProviderType", 2);
  if ( result >= 0 )
  {
    v12 = (const unsigned __int16 *)(a4 + 6);
    if ( a4[9] > 7u )
      v12 = *(const unsigned __int16 **)v12;
    result = DCCDNUtil_SetRegistryString(hKey, 0, L"namespace", v12, 0);
    if ( result >= 0 )
    {
      v13 = (const unsigned __int16 *)(a4 + 10);
      if ( a4[13] > 7u )
        v13 = *(const unsigned __int16 **)v13;
      result = DCCDNUtil_SetRegistryString(hKey, 0, L"className", v13, 0);
      if ( result >= 0 )
      {
        result = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"operation", *((_DWORD *)a2 + 68));
        if ( result >= 0 )
        {
          v14 = 1;
          v15 = (const unsigned __int16 **)a4[2];
          v16 = (const unsigned __int16 **)a4[3];
          v52 = v16;
          while ( v15 != v16 )
          {
            result = StringCchPrintfW(SubKey, 0xFu, L"KeyValue%d", v14);
            if ( result < 0 )
              return result;
            v41 = 0;
            p_lpFileName = &v41;
            phkResult = 0;
            v48 = 1;
            FilePathForUriValue = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2011Fu, 0, &phkResult, 0);
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpFileName);
            if ( FilePathForUriValue )
            {
              if ( FilePathForUriValue > 0 )
                FilePathForUriValue = (unsigned __int16)FilePathForUriValue | 0x80070000;
              goto LABEL_22;
            }
            v18 = DCCDNUtil_SetRegistryDWORD(v41, 0, L"instanceDataAllowed", 1);
            if ( v18 < 0 )
              goto LABEL_21;
            v18 = DCCDNUtil_SetRegistryDWORD(v41, 0, L"typeStored", *((_DWORD *)*v15 + 26));
            if ( v18 < 0 )
              goto LABEL_21;
            v18 = DCCDNUtil_SetRegistryDWORD(v41, 0, L"Key", *((unsigned __int8 *)*v15 + 68));
            if ( v18 < 0 )
              goto LABEL_21;
            v19 = *v15 + 16;
            if ( *((_QWORD *)*v15 + 7) > 7u )
              v19 = *(const unsigned __int16 **)v19;
            v18 = DCCDNUtil_SetRegistryString(v41, 0, L"Name", v19, 0);
            if ( v18 < 0 )
            {
LABEL_21:
              FilePathForUriValue = v18;
LABEL_22:
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
              return FilePathForUriValue;
            }
            if ( v44 == 2 )
            {
              if ( v49 )
              {
                if ( !std::wstring::find(*v15, L"@#", 0) )
                {
                  v20 = *((_QWORD *)*v15 + 2);
                  if ( v20 - 1 == std::wstring::find_last_of(*v15, L"#") )
                  {
                    std::wstring::substr(*v15, v55, 2, *((_QWORD *)*v15 + 2) - 3LL);
                    v21 = (const unsigned __int16 *)v55;
                    if ( v55[3] > (unsigned __int16 *)7 )
                      v21 = v55[0];
                    v22 = DCCDNUtil_SetRegistryString(v41, 0, L"instanceDataVariable", v21, 0);
                    if ( v22 < 0 )
                    {
                      std::wstring::_Tidy_deallocate(v55);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
                      return v22;
                    }
                    std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v56, *v15 + 16);
                    v10 |= 1u;
                    std::vector<std::pair<std::wstring,std::wstring>>::push_back(v49, v56);
                    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v56);
                    std::wstring::_Tidy_deallocate(v55);
                  }
                }
              }
            }
            if ( *((_DWORD *)*v15 + 26) != 1 )
            {
              FilePathForUriValue = -2147418113;
              goto LABEL_22;
            }
            ++v14;
            nNumberOfBytesToWrite[0] = 0;
            DCCDNUtil_GetRegistryDWORD(
              HKEY_LOCAL_MACHINE,
              c_szDCRegistry,
              L"LargeStringValueSavedToFileTest",
              nNumberOfBytesToWrite);
            v23 = *v15;
            if ( *((_QWORD *)*v15 + 3) > 7u )
              v23 = *(const unsigned __int16 **)v23;
            v24 = DCCDNUtil_SetRegistryString(v41, 0, L"value", v23, 0);
            FilePathForUriValue = v24;
            if ( v24 == -2147023446 || nNumberOfBytesToWrite[0] == 1 )
            {
              *(_QWORD *)nNumberOfBytesToWrite = 0;
              v28 = *v15;
              if ( *((_QWORD *)*v15 + 3) > 7u )
                v28 = *(const unsigned __int16 **)v28;
              FilePathForUriValue = StringCchLengthW(v28, 0x7FFFFFFFu, (unsigned __int64 *)nNumberOfBytesToWrite);
              if ( FilePathForUriValue < 0 )
              {
                Logger = CDeclaredConfigurationLogger::GetLogger();
                v26 = *v15 + 16;
                if ( *((_QWORD *)*v15 + 7) > 7u )
                  v26 = *(const wchar_t **)v26;
                v27 = L"StringCchLengthW: failed to get string size";
                goto LABEL_46;
              }
              v50 = v30;
              FilePathForUriValue = ULongLongMult(*(unsigned __int64 *)nNumberOfBytesToWrite, v29, &v50);
              if ( FilePathForUriValue < 0 )
              {
                Logger = CDeclaredConfigurationLogger::GetLogger();
                v26 = L"failed to calculate size";
                v27 = L"SizeTMult";
                goto LABEL_46;
              }
              nNumberOfBytesToWrite[0] = v31;
              FilePathForUriValue = ULongLongToULong(v50, nNumberOfBytesToWrite);
              if ( FilePathForUriValue < 0 )
              {
                Logger = CDeclaredConfigurationLogger::GetLogger();
                v26 = L"failed to convert size to DWORD";
                v27 = L"SIZETToDWord";
                goto LABEL_46;
              }
              FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(v41, 0, L"valueSize", nNumberOfBytesToWrite[0]);
              if ( FilePathForUriValue < 0 )
              {
                Logger = CDeclaredConfigurationLogger::GetLogger();
                v26 = L"Failed to set the string size for URI value";
                v27 = L"DCCDNUtil_SetRegistryDWORD";
                goto LABEL_46;
              }
              lpFileName = 0;
              p_lpFileName = &lpFileName;
              phkResult = 0;
              v48 = 1;
              v32 = std::to_wstring(v56, v14);
              v33 = (const unsigned __int16 *)v32;
              if ( *(_QWORD *)(v32 + 24) > 7u )
                v33 = *(const unsigned __int16 **)v32;
              v34 = std::to_wstring(v57, v45);
              if ( *(_QWORD *)(v34 + 24) > 7u )
                v34 = *(_QWORD *)v34;
              FilePathForUriValue = DeclaredConfigurationStore_GetFilePathForUriValue(
                                      v51,
                                      (struct DCDocument *)a2,
                                      (const unsigned __int16 *)v34,
                                      v33,
                                      (unsigned __int16 **)&phkResult);
              std::wstring::_Tidy_deallocate(v57);
              std::wstring::_Tidy_deallocate(v56);
              wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpFileName);
              if ( FilePathForUriValue < 0 )
              {
                v35 = CDeclaredConfigurationLogger::GetLogger();
                v36 = &word_180142E98;
                v37 = L"DeclaredConfigurationStore_GetFilePathForUriValue";
LABEL_59:
                CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                  v35,
                  L"ConstructDSCNativeProvider",
                  v37,
                  v36,
                  FilePathForUriValue);
                std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpFileName);
                goto LABEL_22;
              }
              FilePathForUriValue = DCCDNUtil_SetRegistryString(v41, 0, L"value", lpFileName, 0);
              if ( FilePathForUriValue < 0 )
              {
                v35 = CDeclaredConfigurationLogger::GetLogger();
                v36 = L"Failed to set the file path for the URI value";
                v37 = L"DCCDNUtil_SetRegistryString";
                goto LABEL_59;
              }
              v38 = *v15;
              if ( *((_QWORD *)*v15 + 3) > 7u )
                v38 = *(const unsigned __int16 **)v38;
              FilePathForUriValue = DeclaredConfigurationStore_WriteFileForUriValue(
                                      lpFileName,
                                      nNumberOfBytesToWrite[0],
                                      v38);
              if ( FilePathForUriValue < 0 )
              {
                v35 = CDeclaredConfigurationLogger::GetLogger();
                v36 = lpFileName;
                v37 = L"DeclaredConfigurationStore_WriteFileForUriValue";
                goto LABEL_59;
              }
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpFileName);
            }
            else if ( v24 < 0 )
            {
              Logger = CDeclaredConfigurationLogger::GetLogger();
              v26 = L"Failed to write URI value to registry";
              v27 = L"DCCDNUtil_SetRegistryString";
LABEL_46:
              CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
                Logger,
                L"ConstructDSCNativeProvider",
                v27,
                v26,
                FilePathForUriValue);
              goto LABEL_22;
            }
            FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(v41, 0, L"typeStored", *((_DWORD *)*v15 + 26));
            if ( FilePathForUriValue < 0 )
              goto LABEL_22;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v41);
            v15 += 2;
            v16 = v52;
          }
          nNumberOfBytesToWrite[0] = 0;
          result = ULongLongToULong((__int64)(a4[3] - a4[2]) >> 4, nNumberOfBytesToWrite);
          if ( result < 0 )
            return result;
          VariantInit(&pvarg);
          pvarg.vt = 3;
          v39 = nNumberOfBytesToWrite[0];
          pvarg.lVal = nNumberOfBytesToWrite[0];
          v40 = (const unsigned __int16 *)(a2 + 12);
          if ( (unsigned __int64)a2[15] > 7 )
            v40 = *(const unsigned __int16 **)v40;
          if ( (unsigned __int64)a2[3] > 7 )
            a2 = (__int64 *)*a2;
          FilePathForUriValue = DeclaredConfigurationStore_WriteResultData(
                                  v51,
                                  (const unsigned __int16 *)a2,
                                  v40,
                                  0,
                                  v53,
                                  0,
                                  L"KeyValueCount",
                                  &pvarg);
          if ( FilePathForUriValue >= 0 )
          {
            FilePathForUriValue = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"KeyValueCount", v39);
            if ( FilePathForUriValue >= 0 )
              FilePathForUriValue = 0;
          }
          VariantClear(&pvarg);
          return FilePathForUriValue;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c7600  push    rbx
0x1800c7602  push    rsi
0x1800c7603  push    rdi
0x1800c7604  push    r12
0x1800c7606  push    r13
0x1800c7608  push    r14
0x1800c760a  push    r15
0x1800c760c  sub     rsp, 180h
0x1800c7613  mov     rax, cs:__security_cookie
0x1800c761a  xor     rax, rsp
0x1800c761d  mov     [rsp+1B8h+var_48], rax
0x1800c7625  mov     r14, r9
0x1800c7628  mov     [rsp+1B8h+var_150], r8d
0x1800c762d  mov     rsi, rdx
0x1800c7630  mov     [rsp+1B8h+var_120], rcx
0x1800c7638  mov     r15, [rsp+1B8h+hKey]
0x1800c7640  mov     rbx, [rsp+1B8h+arg_28]
0x1800c7648  mov     [rsp+1B8h+var_110], rbx
0x1800c7650  mov     eax, [rsp+1B8h+arg_30]
0x1800c7657  mov     [rsp+1B8h+var_14C], eax
0x1800c765b  mov     rax, [rsp+1B8h+arg_38]
0x1800c7663  mov     [rsp+1B8h+var_130], rax
0x1800c766b  xor     ebx, ebx
0x1800c766d  mov     r13d, ebx
0x1800c7670  mov     [rsp+1B8h+nNumberOfBytesToWrite], ebx
0x1800c7674  mov     [rsp+1B8h+SubKey], bx
0x1800c767c  lea     r9d, [rbx+2]; unsigned int
0x1800c7680  lea     r8, aProvidertype_0; "ProviderType"
0x1800c7687  xor     edx, edx; unsigned __int16 *
0x1800c7689  mov     rcx, r15; HKEY
0x1800c768c  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800c7691  test    eax, eax
0x1800c7693  js      loc_1800C7D78
0x1800c7699  lea     r9, [r14+30h]
0x1800c769d  cmp     qword ptr [r9+18h], 7
0x1800c76a2  jbe     short loc_1800C76A7
0x1800c76a4  mov     r9, [r9]; unsigned __int16 *
0x1800c76a7  mov     byte ptr [rsp+1B8h+dwOptions], bl; bool
0x1800c76ab  lea     r8, aNamespace; "namespace"
0x1800c76b2  xor     edx, edx; unsigned __int16 *
0x1800c76b4  mov     rcx, r15; HKEY
0x1800c76b7  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800c76bc  test    eax, eax
0x1800c76be  js      loc_1800C7D78
0x1800c76c4  lea     r9, [r14+50h]
0x1800c76c8  cmp     qword ptr [r9+18h], 7
0x1800c76cd  jbe     short loc_1800C76D2
0x1800c76cf  mov     r9, [r9]; unsigned __int16 *
0x1800c76d2  mov     byte ptr [rsp+1B8h+dwOptions], bl; bool
0x1800c76d6  lea     r8, aClassname; "className"
0x1800c76dd  xor     edx, edx; unsigned __int16 *
0x1800c76df  mov     rcx, r15; HKEY
0x1800c76e2  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800c76e7  test    eax, eax
0x1800c76e9  js      loc_1800C7D78
0x1800c76ef  mov     r9d, [rsi+110h]; unsigned int
0x1800c76f6  lea     r8, aOperation; "operation"
0x1800c76fd  xor     edx, edx; unsigned __int16 *
0x1800c76ff  mov     rcx, r15; HKEY
0x1800c7702  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800c7707  test    eax, eax
0x1800c7709  js      loc_1800C7D78
0x1800c770f  mov     r12d, 1
0x1800c7715  mov     rdi, [r14+10h]
0x1800c7719  mov     rax, [r14+18h]
0x1800c771d  mov     [rsp+1B8h+var_118], rax
0x1800c7725  cmp     rdi, rax
0x1800c7728  jz      loc_1800C7CAB
0x1800c772e  mov     r9d, r12d
0x1800c7731  lea     r8, aKeyvalueD; "KeyValue%d"
0x1800c7738  mov     edx, 0Fh; unsigned __int64
0x1800c773d  lea     rcx, [rsp+1B8h+SubKey]; unsigned __int16 *
0x1800c7745  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c774a  test    eax, eax
0x1800c774c  js      loc_1800C7D78
0x1800c7752  mov     [rsp+1B8h+var_168], rbx
0x1800c7757  lea     rax, [rsp+1B8h+var_168]
0x1800c775c  mov     [rsp+1B8h+var_148], rax
0x1800c7761  mov     [rsp+1B8h+var_140], rbx
0x1800c7766  mov     [rsp+1B8h+var_138], 1
0x1800c776e  mov     [rsp+1B8h+lpdwDisposition], rbx; lpdwDisposition
0x1800c7773  lea     rax, [rsp+1B8h+var_140]
0x1800c7778  mov     [rsp+1B8h+phkResult], rax; phkResult
0x1800c777d  mov     [rsp+1B8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800c7782  mov     [rsp+1B8h+samDesired], 2011Fh; samDesired
0x1800c778a  mov     [rsp+1B8h+dwOptions], ebx; dwOptions
0x1800c778e  xor     r9d, r9d; lpClass
0x1800c7791  xor     r8d, r8d; Reserved
0x1800c7794  lea     rdx, [rsp+1B8h+SubKey]; lpSubKey
0x1800c779c  mov     rcx, r15; hKey
0x1800c779f  call    cs:__imp_RegCreateKeyExW
0x1800c77a5  mov     ebx, eax
0x1800c77a7  lea     rcx, [rsp+1B8h+var_148]
0x1800c77ac  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800c77b1  test    ebx, ebx
0x1800c77b3  jz      short loc_1800C77C9
0x1800c77b5  jle     loc_1800C7852
0x1800c77bb  movzx   ebx, bx
0x1800c77be  or      ebx, 80070000h
0x1800c77c4  jmp     loc_1800C7852
0x1800c77c9  mov     r9d, 1; unsigned int
0x1800c77cf  lea     r8, aInstancedataal; "instanceDataAllowed"
0x1800c77d6  xor     edx, edx; unsigned __int16 *
0x1800c77d8  mov     rcx, [rsp+1B8h+var_168]; HKEY
0x1800c77dd  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800c77e2  test    eax, eax
0x1800c77e4  js      short loc_1800C7850
0x1800c77e6  mov     r9, [rdi]
0x1800c77e9  mov     r9d, [r9+68h]; unsigned int
0x1800c77ed  lea     r8, aTypestored; "typeStored"
0x1800c77f4  xor     edx, edx; unsigned __int16 *
0x1800c77f6  mov     rcx, [rsp+1B8h+var_168]; HKEY
0x1800c77fb  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800c7800  test    eax, eax
0x1800c7802  js      short loc_1800C7850
0x1800c7804  mov     rax, [rdi]
0x1800c7807  movzx   r9d, byte ptr [rax+44h]; unsigned int
0x1800c780c  lea     r8, aKey; "Key"
0x1800c7813  xor     edx, edx; unsigned __int16 *
0x1800c7815  mov     rcx, [rsp+1B8h+var_168]; HKEY
0x1800c781a  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800c781f  test    eax, eax
0x1800c7821  js      short loc_1800C7850
0x1800c7823  mov     r9, [rdi]
0x1800c7826  add     r9, 20h ; ' '
0x1800c782a  cmp     qword ptr [r9+18h], 7
0x1800c782f  jbe     short loc_1800C7834
0x1800c7831  mov     r9, [r9]; unsigned __int16 *
0x1800c7834  mov     byte ptr [rsp+1B8h+dwOptions], 0; bool
0x1800c7839  lea     r8, aName; "Name"
0x1800c7840  xor     edx, edx; unsigned __int16 *
0x1800c7842  mov     rcx, [rsp+1B8h+var_168]; HKEY
0x1800c7847  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800c784c  test    eax, eax
0x1800c784e  jns     short loc_1800C7861
0x1800c7850  mov     ebx, eax
0x1800c7852  lea     rcx, [rsp+1B8h+var_168]
0x1800c7857  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c785c  jmp     loc_1800C7D76
0x1800c7861  cmp     [rsp+1B8h+var_150], 2
0x1800c7866  jnz     loc_1800C7988
0x1800c786c  cmp     [rsp+1B8h+var_130], 0
0x1800c7875  jz      loc_1800C7988
0x1800c787b  xor     r8d, r8d
0x1800c787e  lea     rdx, asc_180141D8C; "@#"
0x1800c7885  mov     rcx, [rdi]
0x1800c7888  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800c788d  test    rax, rax
0x1800c7890  jnz     loc_1800C797D
0x1800c7896  mov     rcx, [rdi]
0x1800c7899  mov     rbx, [rcx+10h]
0x1800c789d  lea     rdx, asc_180141D94; "#"
0x1800c78a4  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x1800c78a9  lea     rcx, [rbx-1]
0x1800c78ad  cmp     rcx, rax
0x1800c78b0  jnz     loc_1800C797D
0x1800c78b6  mov     rcx, [rdi]
0x1800c78b9  mov     r9, [rcx+10h]
0x1800c78bd  sub     r9, 3
0x1800c78c1  mov     r8d, 2
0x1800c78c7  lea     rdx, [rsp+1B8h+var_F0]
0x1800c78cf  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800c78d4  nop
0x1800c78d5  lea     r9, [rsp+1B8h+var_F0]
0x1800c78dd  cmp     [rsp+1B8h+var_D8], 7
0x1800c78e6  cmova   r9, [rsp+1B8h+var_F0]; unsigned __int16 *
0x1800c78ef  mov     byte ptr [rsp+1B8h+dwOptions], 0; bool
0x1800c78f4  lea     r8, aInstancedatava; "instanceDataVariable"
0x1800c78fb  xor     edx, edx; unsigned __int16 *
0x1800c78fd  mov     rcx, [rsp+1B8h+var_168]; HKEY
0x1800c7902  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800c7907  mov     ebx, eax
0x1800c7909  test    eax, eax
0x1800c790b  jns     short loc_1800C792C
0x1800c790d  lea     rcx, [rsp+1B8h+var_F0]
0x1800c7915  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c791a  nop
0x1800c791b  lea     rcx, [rsp+1B8h+var_168]
0x1800c7920  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c7925  mov     eax, ebx
0x1800c7927  jmp     loc_1800C7D78
0x1800c792c  mov     rdx, [rdi]
0x1800c792f  add     rdx, 20h ; ' '
0x1800c7933  lea     r8, [rsp+1B8h+var_F0]
0x1800c793b  lea     rcx, [rsp+1B8h+var_C8]
0x1800c7943  call    ??$?0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV01@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(std::wstring &,std::wstring &)
0x1800c7948  or      r13d, 1
0x1800c794c  lea     rdx, [rsp+1B8h+var_C8]
0x1800c7954  mov     rcx, [rsp+1B8h+var_130]
0x1800c795c  call    ?push_back@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::vector<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x1800c7961  nop
0x1800c7962  lea     rcx, [rsp+1B8h+var_C8]
0x1800c796a  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1800c796f  nop
0x1800c7970  lea     rcx, [rsp+1B8h+var_F0]
0x1800c7978  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c797d  jmp     short loc_1800C7988
0x1800c797f  mov     ebx, [rsp+1B8h+var_150]
0x1800c7983  jmp     loc_1800C7852
0x1800c7988  mov     rcx, [rdi]
0x1800c798b  cmp     dword ptr [rcx+68h], 1
0x1800c798f  jz      short loc_1800C799B
0x1800c7991  mov     ebx, 8000FFFFh
0x1800c7996  jmp     loc_1800C7852
0x1800c799b  inc     r12d
0x1800c799e  mov     [rsp+1B8h+nNumberOfBytesToWrite], 0
0x1800c79a6  lea     r9, [rsp+1B8h+nNumberOfBytesToWrite]; unsigned int *
0x1800c79ab  lea     r8, aLargestringval; "LargeStringValueSavedToFileTest"
0x1800c79b2  mov     rdx, cs:?c_szDCRegistry@@3PEBGEB; unsigned __int16 *
0x1800c79b9  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800c79c0  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800c79c5  mov     r9, [rdi]
0x1800c79c8  cmp     qword ptr [r9+18h], 7
0x1800c79cd  jbe     short loc_1800C79D2
0x1800c79cf  mov     r9, [r9]; unsigned __int16 *
0x1800c79d2  mov     byte ptr [rsp+1B8h+dwOptions], 0; bool
0x1800c79d7  lea     r8, aValue_0; "value"
0x1800c79de  xor     edx, edx; unsigned __int16 *
0x1800c79e0  mov     rcx, [rsp+1B8h+var_168]; HKEY
0x1800c79e5  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800c79ea  mov     ebx, eax
0x1800c79ec  cmp     eax, 800705AAh
0x1800c79f1  jz      short loc_1800C7A17
0x1800c79f3  cmp     [rsp+1B8h+nNumberOfBytesToWrite], 1
0x1800c79f8  jz      short loc_1800C7A17
0x1800c79fa  test    eax, eax
0x1800c79fc  jns     loc_1800C7C6A
0x1800c7a02  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c7a07  lea     r9, aFailedToWriteU; "Failed to write URI value to registry"
0x1800c7a0e  lea     r8, aDccdnutilSetre; "DCCDNUtil_SetRegistryString"
0x1800c7a15  jmp     short loc_1800C7A5E
0x1800c7a17  xor     r11d, r11d
0x1800c7a1a  mov     qword ptr [rsp+1B8h+nNumberOfBytesToWrite], r11
0x1800c7a1f  mov     rcx, [rdi]
0x1800c7a22  cmp     qword ptr [rcx+18h], 7
0x1800c7a27  jbe     short loc_1800C7A2C
0x1800c7a29  mov     rcx, [rcx]; unsigned __int16 *
0x1800c7a2c  lea     r8, [rsp+1B8h+nNumberOfBytesToWrite]; unsigned __int64 *
0x1800c7a31  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800c7a36  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800c7a3b  mov     ebx, eax
0x1800c7a3d  test    eax, eax
0x1800c7a3f  jns     short loc_1800C7A76
0x1800c7a41  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c7a46  mov     r9, [rdi]
0x1800c7a49  add     r9, 20h ; ' '
0x1800c7a4d  cmp     qword ptr [r9+18h], 7
0x1800c7a52  jbe     short loc_1800C7A57
0x1800c7a54  mov     r9, [r9]; unsigned __int16 *
0x1800c7a57  lea     r8, aStringcchlengt; "StringCchLengthW: failed to get string "...
0x1800c7a5e  mov     [rsp+1B8h+dwOptions], ebx; int
0x1800c7a62  lea     rdx, aConstructdscna; "ConstructDSCNativeProvider"
0x1800c7a69  mov     rcx, rax; this
0x1800c7a6c  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1800c7a71  jmp     loc_1800C7852
0x1800c7a76  mov     [rsp+1B8h+var_128], r11
0x1800c7a7e  lea     r8, [rsp+1B8h+var_128]; unsigned __int64 *
0x1800c7a86  mov     rcx, qword ptr [rsp+1B8h+nNumberOfBytesToWrite]; unsigned __int64
0x1800c7a8b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800c7a90  mov     ebx, eax
0x1800c7a92  test    eax, eax
0x1800c7a94  jns     short loc_1800C7AAB
0x1800c7a96  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c7a9b  lea     r9, aFailedToCalcul; "failed to calculate size"
0x1800c7aa2  lea     r8, aSizetmult; "SizeTMult"
0x1800c7aa9  jmp     short loc_1800C7A5E
0x1800c7aab  mov     [rsp+1B8h+nNumberOfBytesToWrite], r11d
0x1800c7ab0  lea     rdx, [rsp+1B8h+nNumberOfBytesToWrite]; unsigned int *
0x1800c7ab5  mov     rcx, [rsp+1B8h+var_128]; unsigned __int64
0x1800c7abd  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800c7ac2  mov     ebx, eax
0x1800c7ac4  test    eax, eax
0x1800c7ac6  jns     short loc_1800C7ADD
0x1800c7ac8  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c7acd  lea     r9, aFailedToConver_2; "failed to convert size to DWORD"
0x1800c7ad4  lea     r8, aSizettodword; "SIZETToDWord"
0x1800c7adb  jmp     short loc_1800C7A5E
0x1800c7add  mov     r9d, [rsp+1B8h+nNumberOfBytesToWrite]; unsigned int
0x1800c7ae2  lea     r8, aValuesize; "valueSize"
0x1800c7ae9  xor     edx, edx; unsigned __int16 *
0x1800c7aeb  mov     rcx, [rsp+1B8h+var_168]; HKEY
0x1800c7af0  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800c7af5  mov     ebx, eax
0x1800c7af7  test    eax, eax
0x1800c7af9  jns     short loc_1800C7B13
0x1800c7afb  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800c7b00  lea     r9, aFailedToSetThe_0; "Failed to set the string size for URI v"...
0x1800c7b07  lea     r8, aDccdnutilSetre_2; "DCCDNUtil_SetRegistryDWORD"
0x1800c7b0e  jmp     loc_1800C7A5E
0x1800c7b13  mov     [rsp+1B8h+lpFileName], 0
0x1800c7b1c  lea     rax, [rsp+1B8h+lpFileName]
0x1800c7b21  mov     [rsp+1B8h+var_148], rax
0x1800c7b26  mov     [rsp+1B8h+var_140], 0
0x1800c7b2f  mov     [rsp+1B8h+var_138], 1
0x1800c7b37  mov     edx, r12d
0x1800c7b3a  lea     rcx, [rsp+1B8h+var_C8]
0x1800c7b42  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x1800c7b47  mov     rbx, rax
0x1800c7b4a  cmp     qword ptr [rax+18h], 7
0x1800c7b4f  jbe     short loc_1800C7B54
  ... truncated ...
```
