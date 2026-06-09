# StorageWriter::CreateFeatureKey(_RTL_FEATURE_CONFIGURATION_PRIORITY,uint,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *)

- ea: `0x180118d90`
- end: `0x1801192d1`
- name: `?CreateFeatureKey@StorageWriter@@CAJW4_RTL_FEATURE_CONFIGURATION_PRIORITY@@IAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `1345`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180119dc8`

## callees

- `0x180004bd0`
- `0x18000da88`
- `0x180118ac0`
- `0x180118b64`
- `0x180118d90`
- `0x180119ad4`
- `0x18011a2e4`
- `0x18011b8a0`
- `0x18011b938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180118ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011913a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180118ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011913a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119019`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119019`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119159`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011900b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119081`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011914b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801191ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119257`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011900b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119081`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011914b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801191ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119257`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801191a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801191a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801190ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801191e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011926b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801190ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801191e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011926b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119281`

## string_xrefs

- `0x180118e21`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x180118e79`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x180119063`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x1801190ff`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x1801191cd`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18011929d`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
__int64 __fastcall StorageWriter::CreateFeatureKey(unsigned int a1, int a2, HKEY *a3, const unsigned __int16 *a4)
{
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // ebx
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  struct RegPersistedKey *v16; // rax
  __int64 v17; // r8
  _OWORD *v18; // rcx
  __int64 v19; // r9
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  WCHAR *v34; // rcx
  _OWORD *v35; // rax
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  HKEY v43; // rdi
  DWORD LastError; // ebx
  WCHAR *v45; // rbx
  int v46; // eax
  unsigned int v47; // edi
  int v49; // eax
  HKEY v50; // rsi
  DWORD v51; // edi
  WCHAR *v52; // rdi
  HKEY v53; // rcx
  const WCHAR *v54; // rdx
  LSTATUS v55; // eax
  unsigned int v56; // esi
  struct _SECURITY_ATTRIBUTES *dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v64[528]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v65[528]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR SubKey[264]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+5D8h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterCreateImmutable>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterCreateImmutable>::GetImpl'::`2'::impl) )
  {
    if ( a1 > 0xF )
    {
      v8 = 44;
LABEL_59:
      v13 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
        (const char *)0x80070057LL,
        (int)dwOptions);
      return v13;
    }
  }
  else if ( a1 > 0xF || (v9 = 33291, _bittest(&v9, a1)) )
  {
    v8 = 49;
    goto LABEL_59;
  }
  pv = 0;
  v10 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          L"%u",
          a1);
  v13 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)(unsigned int)v10,
      (int)dwOptions);
LABEL_8:
    if ( pv )
      CoTaskMemFree(pv);
    return v13;
  }
  lpSubKey = 0;
  v14 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [10],unsigned short [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &lpSubKey,
          v11,
          v12,
          &pv);
  v13 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)(unsigned int)v14,
      (int)dwOptions);
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
    goto LABEL_8;
  }
  dwDisposition = 0;
  hKey = 0;
  if ( a4 )
  {
    RegPersistedKey::RegPersistedKey((RegPersistedKey *)v65, v15, a4);
    v17 = 4;
    v18 = v64;
    v16 = (struct RegPersistedKey *)v65;
    v19 = 4;
    do
    {
      v27 = *((_OWORD *)v16 + 1);
      *v18 = *(_OWORD *)v16;
      v28 = *((_OWORD *)v16 + 2);
      v18[1] = v27;
      v29 = *((_OWORD *)v16 + 3);
      v18[2] = v28;
      v30 = *((_OWORD *)v16 + 4);
      v18[3] = v29;
      v31 = *((_OWORD *)v16 + 5);
      v18[4] = v30;
      v32 = *((_OWORD *)v16 + 6);
      v18[5] = v31;
      v33 = *((_OWORD *)v16 + 7);
      v16 = (struct RegPersistedKey *)((char *)v16 + 128);
      v18[6] = v32;
      v18[7] = v33;
      v18 += 8;
      --v19;
    }
    while ( v19 );
  }
  else
  {
    v16 = RegPersistedKeySingleton::KeyFeatureManagement();
    v17 = 4;
    v18 = v64;
    v19 = 4;
    do
    {
      v20 = *((_OWORD *)v16 + 1);
      *v18 = *(_OWORD *)v16;
      v21 = *((_OWORD *)v16 + 2);
      v18[1] = v20;
      v22 = *((_OWORD *)v16 + 3);
      v18[2] = v21;
      v23 = *((_OWORD *)v16 + 4);
      v18[3] = v22;
      v24 = *((_OWORD *)v16 + 5);
      v18[4] = v23;
      v25 = *((_OWORD *)v16 + 6);
      v18[5] = v24;
      v26 = *((_OWORD *)v16 + 7);
      v16 = (struct RegPersistedKey *)((char *)v16 + 128);
      v18[6] = v25;
      v18[7] = v26;
      v18 += 8;
      --v19;
    }
    while ( v19 );
  }
  *(_QWORD *)v18 = *(_QWORD *)v16;
  v34 = SubKey;
  v35 = v64;
  do
  {
    v36 = v35[1];
    *(_OWORD *)v34 = *v35;
    v37 = v35[2];
    *((_OWORD *)v34 + 1) = v36;
    v38 = v35[3];
    *((_OWORD *)v34 + 2) = v37;
    v39 = v35[4];
    *((_OWORD *)v34 + 3) = v38;
    v40 = v35[5];
    *((_OWORD *)v34 + 4) = v39;
    v41 = v35[6];
    *((_OWORD *)v34 + 5) = v40;
    v42 = v35[7];
    v35 += 8;
    *((_OWORD *)v34 + 6) = v41;
    *((_OWORD *)v34 + 7) = v42;
    v34 += 64;
    --v17;
  }
  while ( v17 );
  v43 = hKey;
  *(_QWORD *)v34 = *(_QWORD *)v35;
  if ( v43 )
  {
    LastError = GetLastError();
    RegCloseKey(v43);
    SetLastError(LastError);
  }
  v45 = (WCHAR *)lpSubKey;
  hKey = 0;
  v46 = RegPersistedKey::RegCreateKeyExW(SubKey, lpSubKey, v17, v19, dwOptions, &hKey, &dwDisposition);
  v47 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)(unsigned int)v46,
      dwOptionsa);
LABEL_25:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v45 )
      CoTaskMemFree(v45);
    if ( pv )
      CoTaskMemFree(pv);
    return v47;
  }
  lpSubKey = 0;
  v49 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &lpSubKey,
          L"%lu",
          __ROR4__(_byteswap_ulong(a2 ^ 0x74161A4E) ^ 0x8FB23D4F, 255) ^ 0x833EA8FF);
  v47 = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)(unsigned int)v49,
      dwOptionsa);
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
    goto LABEL_25;
  }
  v50 = *a3;
  if ( *a3 )
  {
    v51 = GetLastError();
    RegCloseKey(v50);
    SetLastError(v51);
  }
  v52 = (WCHAR *)lpSubKey;
  v53 = hKey;
  v54 = lpSubKey;
  *a3 = 0;
  v55 = RegCreateKeyExW(v53, v54, 0, 0, 0, 0xF013Fu, 0, a3, &dwDisposition);
  v56 = v55;
  if ( v55 > 0 )
    v56 = (unsigned __int16)v55 | 0x80070000;
  if ( (v56 & 0x80000000) == 0 )
  {
    if ( v52 )
      CoTaskMemFree(v52);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v45 )
      CoTaskMemFree(v45);
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)v56,
      dwOptionsb);
    if ( v52 )
      CoTaskMemFree(v52);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v45 )
      CoTaskMemFree(v45);
    if ( pv )
      CoTaskMemFree(pv);
    return v56;
  }
}

```

## disassembly

```asm
0x180118d90  push    rbp
0x180118d92  push    rbx
0x180118d93  push    rsi
0x180118d94  push    rdi
0x180118d95  push    r14
0x180118d97  lea     rbp, [rsp-5B0h]
0x180118d9f  sub     rsp, 6B0h
0x180118da6  mov     rax, cs:__security_cookie
0x180118dad  xor     rax, rsp
0x180118db0  mov     [rbp+5D0h+var_30], rax
0x180118db7  mov     rdi, r9
0x180118dba  mov     r14, r8
0x180118dbd  mov     esi, edx
0x180118dbf  mov     ebx, ecx
0x180118dc1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterCreateImmutable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterCreateImmutable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterCreateImmutable> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterCreateImmutable>::GetImpl(void)'::`2'::impl
0x180118dc8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterCreateImmutable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_StorageWriterCreateImmutable>::__private_IsEnabled(void)
0x180118dcd  test    al, al
0x180118dcf  jz      short loc_180118DE0
0x180118dd1  cmp     ebx, 0Fh
0x180118dd4  jbe     short loc_180118DF7
0x180118dd6  mov     edx, 2Ch ; ','
0x180118ddb  jmp     loc_180119296
0x180118de0  cmp     ebx, 0Fh
0x180118de3  ja      loc_180119291
0x180118de9  mov     eax, 820Bh
0x180118dee  bt      eax, ebx
0x180118df1  jb      loc_180119291
0x180118df7  mov     r8d, ebx
0x180118dfa  mov     [rsp+6D0h+pv], 0
0x180118e03  lea     rdx, aU; "%u"
0x180118e0a  lea     rcx, [rsp+6D0h+pv]
0x180118e0f  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180118e14  mov     ebx, eax
0x180118e16  test    eax, eax
0x180118e18  jns     short loc_180118E54
0x180118e1a  mov     rcx, [rbp+5D8h]; this
0x180118e21  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x180118e28  mov     r9d, eax; char *
0x180118e2b  mov     edx, 35h ; '5'; void *
0x180118e30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118e35  mov     rcx, [rsp+6D0h+pv]; pv
0x180118e3a  test    rcx, rcx
0x180118e3d  jz      loc_1801192B1
0x180118e43  call    cs:__imp_CoTaskMemFree
0x180118e4a  nop     dword ptr [rax+rax+00h]
0x180118e4f  jmp     loc_1801192B1
0x180118e54  lea     r9, [rsp+6D0h+pv]
0x180118e59  mov     [rsp+6D0h+lpSubKey], 0
0x180118e62  lea     rcx, [rsp+6D0h+lpSubKey]
0x180118e67  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY09G$$BY01GV12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY09$$CBGAEAY01$$CBGAEBV10@@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [10],ushort [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[10],ushort const (&)[2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x180118e6c  mov     ebx, eax
0x180118e6e  test    eax, eax
0x180118e70  jns     short loc_180118EA5
0x180118e72  mov     rcx, [rbp+5D8h]; this
0x180118e79  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x180118e80  mov     r9d, eax; char *
0x180118e83  mov     edx, 39h ; '9'; void *
0x180118e88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118e8d  mov     rcx, [rsp+6D0h+lpSubKey]; pv
0x180118e92  test    rcx, rcx
0x180118e95  jz      short loc_180118E35
0x180118e97  call    cs:__imp_CoTaskMemFree
0x180118e9e  nop     dword ptr [rax+rax+00h]
0x180118ea3  jmp     short loc_180118E35
0x180118ea5  mov     [rsp+6D0h+dwDisposition], 0
0x180118ead  mov     [rsp+6D0h+hKey], 0
0x180118eb6  test    rdi, rdi
0x180118eb9  jnz     short loc_180118F1C
0x180118ebb  call    ?KeyFeatureManagement@RegPersistedKeySingleton@@SAAEAVRegPersistedKey@@XZ; RegPersistedKeySingleton::KeyFeatureManagement(void)
0x180118ec0  lea     r8d, [rdi+4]
0x180118ec4  lea     rcx, [rsp+6D0h+var_660]
0x180118ec9  mov     r9d, r8d
0x180118ecc  lea     edx, [r8+7Ch]
0x180118ed0  movups  xmm0, xmmword ptr [rax]
0x180118ed3  movups  xmm1, xmmword ptr [rax+10h]
0x180118ed7  movups  xmmword ptr [rcx], xmm0
0x180118eda  movups  xmm0, xmmword ptr [rax+20h]
0x180118ede  movups  xmmword ptr [rcx+10h], xmm1
0x180118ee2  movups  xmm1, xmmword ptr [rax+30h]
0x180118ee6  movups  xmmword ptr [rcx+20h], xmm0
0x180118eea  movups  xmm0, xmmword ptr [rax+40h]
0x180118eee  movups  xmmword ptr [rcx+30h], xmm1
0x180118ef2  movups  xmm1, xmmword ptr [rax+50h]
0x180118ef6  movups  xmmword ptr [rcx+40h], xmm0
0x180118efa  movups  xmm0, xmmword ptr [rax+60h]
0x180118efe  movups  xmmword ptr [rcx+50h], xmm1
0x180118f02  movups  xmm1, xmmword ptr [rax+70h]
0x180118f06  add     rax, rdx
0x180118f09  movups  xmmword ptr [rcx+60h], xmm0
0x180118f0d  movups  xmmword ptr [rcx+70h], xmm1
0x180118f11  add     rcx, rdx
0x180118f14  sub     r9, 1
0x180118f18  jnz     short loc_180118ED0
0x180118f1a  jmp     short loc_180118F8E
0x180118f1c  mov     r8, rdi; unsigned __int16 *
0x180118f1f  lea     rcx, [rbp+5D0h+var_450]; this
0x180118f26  call    ??0RegPersistedKey@@QEAA@PEBG0@Z; RegPersistedKey::RegPersistedKey(ushort const *,ushort const *)
0x180118f2b  mov     r8d, 4
0x180118f31  lea     rcx, [rsp+6D0h+var_660]
0x180118f36  lea     rax, [rbp+5D0h+var_450]
0x180118f3d  mov     r9d, r8d
0x180118f40  lea     edx, [r8+7Ch]
0x180118f44  movups  xmm0, xmmword ptr [rax]
0x180118f47  movups  xmm1, xmmword ptr [rax+10h]
0x180118f4b  movups  xmmword ptr [rcx], xmm0
0x180118f4e  movups  xmm0, xmmword ptr [rax+20h]
0x180118f52  movups  xmmword ptr [rcx+10h], xmm1
0x180118f56  movups  xmm1, xmmword ptr [rax+30h]
0x180118f5a  movups  xmmword ptr [rcx+20h], xmm0
0x180118f5e  movups  xmm0, xmmword ptr [rax+40h]
0x180118f62  movups  xmmword ptr [rcx+30h], xmm1
0x180118f66  movups  xmm1, xmmword ptr [rax+50h]
0x180118f6a  movups  xmmword ptr [rcx+40h], xmm0
0x180118f6e  movups  xmm0, xmmword ptr [rax+60h]
0x180118f72  movups  xmmword ptr [rcx+50h], xmm1
0x180118f76  movups  xmm1, xmmword ptr [rax+70h]
0x180118f7a  add     rax, rdx
0x180118f7d  movups  xmmword ptr [rcx+60h], xmm0
0x180118f81  movups  xmmword ptr [rcx+70h], xmm1
0x180118f85  add     rcx, rdx
0x180118f88  sub     r9, 1
0x180118f8c  jnz     short loc_180118F44
0x180118f8e  mov     rax, [rax]
0x180118f91  mov     [rcx], rax
0x180118f94  lea     rcx, [rbp+5D0h+SubKey]
0x180118f9b  lea     rax, [rsp+6D0h+var_660]
0x180118fa0  movups  xmm0, xmmword ptr [rax]
0x180118fa3  movups  xmm1, xmmword ptr [rax+10h]
0x180118fa7  movups  xmmword ptr [rcx], xmm0
0x180118faa  movups  xmm0, xmmword ptr [rax+20h]
0x180118fae  movups  xmmword ptr [rcx+10h], xmm1
0x180118fb2  movups  xmm1, xmmword ptr [rax+30h]
0x180118fb6  movups  xmmword ptr [rcx+20h], xmm0
0x180118fba  movups  xmm0, xmmword ptr [rax+40h]
0x180118fbe  movups  xmmword ptr [rcx+30h], xmm1
0x180118fc2  movups  xmm1, xmmword ptr [rax+50h]
0x180118fc6  movups  xmmword ptr [rcx+40h], xmm0
0x180118fca  movups  xmm0, xmmword ptr [rax+60h]
0x180118fce  movups  xmmword ptr [rcx+50h], xmm1
0x180118fd2  movups  xmm1, xmmword ptr [rax+70h]
0x180118fd6  add     rax, rdx
0x180118fd9  movups  xmmword ptr [rcx+60h], xmm0
0x180118fdd  movups  xmmword ptr [rcx+70h], xmm1
0x180118fe1  add     rcx, rdx
0x180118fe4  sub     r8, 1
0x180118fe8  jnz     short loc_180118FA0
0x180118fea  mov     rdi, [rsp+6D0h+hKey]
0x180118fef  mov     rax, [rax]
0x180118ff2  mov     [rcx], rax
0x180118ff5  test    rdi, rdi
0x180118ff8  jz      short loc_180119025
0x180118ffa  call    cs:__imp_GetLastError
0x180119001  nop     dword ptr [rax+rax+00h]
0x180119006  mov     rcx, rdi; hKey
0x180119009  mov     ebx, eax
0x18011900b  call    cs:__imp_RegCloseKey
0x180119012  nop     dword ptr [rax+rax+00h]
0x180119017  mov     ecx, ebx; dwErrCode
0x180119019  call    cs:__imp_SetLastError
0x180119020  nop     dword ptr [rax+rax+00h]
0x180119025  mov     rbx, [rsp+6D0h+lpSubKey]
0x18011902a  lea     rax, [rsp+6D0h+dwDisposition]
0x18011902f  mov     [rsp+6D0h+lpSecurityAttributes], rax; unsigned int *
0x180119034  lea     rcx, [rbp+5D0h+SubKey]; lpSubKey
0x18011903b  lea     rax, [rsp+6D0h+hKey]
0x180119040  mov     [rsp+6D0h+hKey], 0
0x180119049  mov     rdx, rbx; LPCWSTR
0x18011904c  mov     qword ptr [rsp+6D0h+samDesired], rax; HKEY *
0x180119051  call    ?RegCreateKeyExW@RegPersistedKey@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAUHKEY__@@PEAK@Z; RegPersistedKey::RegCreateKeyExW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180119056  mov     edi, eax
0x180119058  test    eax, eax
0x18011905a  jns     short loc_1801190BE
0x18011905c  mov     rcx, [rbp+5D8h]; this
0x180119063  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x18011906a  mov     r9d, eax; char *
0x18011906d  mov     edx, 43h ; 'C'; void *
0x180119072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119077  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18011907c  test    rcx, rcx
0x18011907f  jz      short loc_18011908D
0x180119081  call    cs:__imp_RegCloseKey
0x180119088  nop     dword ptr [rax+rax+00h]
0x18011908d  test    rbx, rbx
0x180119090  jz      short loc_1801190A1
0x180119092  mov     rcx, rbx; pv
0x180119095  call    cs:__imp_CoTaskMemFree
0x18011909c  nop     dword ptr [rax+rax+00h]
0x1801190a1  mov     rcx, [rsp+6D0h+pv]; pv
0x1801190a6  test    rcx, rcx
0x1801190a9  jz      short loc_1801190B7
0x1801190ab  call    cs:__imp_CoTaskMemFree
0x1801190b2  nop     dword ptr [rax+rax+00h]
0x1801190b7  mov     eax, edi
0x1801190b9  jmp     loc_1801192B3
0x1801190be  xor     esi, 74161A4Eh
0x1801190c4  mov     [rsp+6D0h+lpSubKey], 0
0x1801190cd  bswap   esi
0x1801190cf  xor     esi, 8FB23D4Fh
0x1801190d5  lea     rdx, aLu; "%lu"
0x1801190dc  ror     esi, 0FFh
0x1801190df  lea     rcx, [rsp+6D0h+lpSubKey]
0x1801190e4  xor     esi, 833EA8FFh
0x1801190ea  mov     r8d, esi
0x1801190ed  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1801190f2  mov     edi, eax
0x1801190f4  test    eax, eax
0x1801190f6  jns     short loc_180119132
0x1801190f8  mov     rcx, [rbp+5D8h]; this
0x1801190ff  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x180119106  mov     r9d, eax; char *
0x180119109  mov     edx, 47h ; 'G'; void *
0x18011910e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119113  mov     rcx, [rsp+6D0h+lpSubKey]; pv
0x180119118  test    rcx, rcx
0x18011911b  jz      loc_180119077
0x180119121  call    cs:__imp_CoTaskMemFree
0x180119128  nop     dword ptr [rax+rax+00h]
0x18011912d  jmp     loc_180119077
0x180119132  mov     rsi, [r14]
0x180119135  test    rsi, rsi
0x180119138  jz      short loc_180119165
0x18011913a  call    cs:__imp_GetLastError
0x180119141  nop     dword ptr [rax+rax+00h]
0x180119146  mov     rcx, rsi; hKey
0x180119149  mov     edi, eax
0x18011914b  call    cs:__imp_RegCloseKey
0x180119152  nop     dword ptr [rax+rax+00h]
0x180119157  mov     ecx, edi; dwErrCode
0x180119159  call    cs:__imp_SetLastError
0x180119160  nop     dword ptr [rax+rax+00h]
0x180119165  mov     rdi, [rsp+6D0h+lpSubKey]
0x18011916a  lea     rax, [rsp+6D0h+dwDisposition]
0x18011916f  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180119174  xor     r9d, r9d; lpClass
0x180119177  mov     [rsp+6D0h+lpdwDisposition], rax; lpdwDisposition
0x18011917c  xor     r8d, r8d; Reserved
0x18011917f  mov     [rsp+6D0h+phkResult], r14; phkResult
0x180119184  mov     rdx, rdi; lpSubKey
0x180119187  mov     [rsp+6D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180119190  mov     [rsp+6D0h+samDesired], 0F013Fh; samDesired
0x180119198  mov     dword ptr [rsp+6D0h+dwOptions], 0; int
0x1801191a0  mov     qword ptr [r14], 0
0x1801191a7  call    cs:__imp_RegCreateKeyExW
0x1801191ae  nop     dword ptr [rax+rax+00h]
0x1801191b3  mov     esi, eax
0x1801191b5  test    eax, eax
0x1801191b7  jle     short loc_1801191C2
0x1801191b9  movzx   esi, ax
0x1801191bc  or      esi, 80070000h
0x1801191c2  test    esi, esi
0x1801191c4  jns     short loc_180119239
0x1801191c6  mov     rcx, [rbp+5D8h]; this
0x1801191cd  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x1801191d4  mov     r9d, esi; char *
0x1801191d7  mov     edx, 4Fh ; 'O'; void *
0x1801191dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801191e1  test    rdi, rdi
0x1801191e4  jz      short loc_1801191F5
0x1801191e6  mov     rcx, rdi; pv
0x1801191e9  call    cs:__imp_CoTaskMemFree
0x1801191f0  nop     dword ptr [rax+rax+00h]
0x1801191f5  mov     rcx, [rsp+6D0h+hKey]; hKey
0x1801191fa  test    rcx, rcx
0x1801191fd  jz      short loc_18011920B
0x1801191ff  call    cs:__imp_RegCloseKey
0x180119206  nop     dword ptr [rax+rax+00h]
0x18011920b  test    rbx, rbx
0x18011920e  jz      short loc_18011921F
0x180119210  mov     rcx, rbx; pv
0x180119213  call    cs:__imp_CoTaskMemFree
0x18011921a  nop     dword ptr [rax+rax+00h]
0x18011921f  mov     rcx, [rsp+6D0h+pv]; pv
0x180119224  test    rcx, rcx
0x180119227  jz      short loc_180119235
0x180119229  call    cs:__imp_CoTaskMemFree
0x180119230  nop     dword ptr [rax+rax+00h]
0x180119235  mov     eax, esi
0x180119237  jmp     short loc_1801192B3
0x180119239  test    rdi, rdi
0x18011923c  jz      short loc_18011924D
0x18011923e  mov     rcx, rdi; pv
0x180119241  call    cs:__imp_CoTaskMemFree
0x180119248  nop     dword ptr [rax+rax+00h]
0x18011924d  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180119252  test    rcx, rcx
0x180119255  jz      short loc_180119263
0x180119257  call    cs:__imp_RegCloseKey
0x18011925e  nop     dword ptr [rax+rax+00h]
0x180119263  test    rbx, rbx
0x180119266  jz      short loc_180119277
0x180119268  mov     rcx, rbx; pv
0x18011926b  call    cs:__imp_CoTaskMemFree
0x180119272  nop     dword ptr [rax+rax+00h]
0x180119277  mov     rcx, [rsp+6D0h+pv]; pv
0x18011927c  test    rcx, rcx
0x18011927f  jz      short loc_18011928D
0x180119281  call    cs:__imp_CoTaskMemFree
0x180119288  nop     dword ptr [rax+rax+00h]
0x18011928d  xor     eax, eax
0x18011928f  jmp     short loc_1801192B3
  ... truncated ...
```
