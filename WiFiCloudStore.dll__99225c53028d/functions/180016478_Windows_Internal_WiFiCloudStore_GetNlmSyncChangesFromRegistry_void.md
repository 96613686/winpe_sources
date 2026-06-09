# Windows::Internal::WiFiCloudStore::GetNlmSyncChangesFromRegistry(void)

- ea: `0x180016478`
- end: `0x18001678b`
- name: `?GetNlmSyncChangesFromRegistry@WiFiCloudStore@Internal@Windows@@YA?AV?$vector@UNlmSyncStruct@WiFiCloudStore@Internal@Windows@@V?$allocator@UNlmSyncStruct@WiFiCloudStore@Internal@Windows@@@std@@@std@@XZ`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800144c0`

## callees

- `0x180006afc`
- `0x18000ac14`
- `0x18000b6a0`
- `0x18000b714`
- `0x18000ba64`
- `0x18000c5d4`
- `0x180016478`
- `0x180025308`
- `0x18002714c`
- `0x18002a030`
- `0x18002e2d0`
- `0x180031ce4`
- `0x18003ccfc`
- `0x18003d360`
- `0x18003d3ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016674`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800164d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001651c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001651c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016764`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016764`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800165d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180016605`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800165d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180016605`

## string_xrefs

- `0x18001652d`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`
- `0x18001660f`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`
- `0x1800166ac`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`
- `0x1800166e6`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`
- `0x1800166ff`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Windows::Internal::WiFiCloudStore::GetNlmSyncChangesFromRegistry(_QWORD *a1, void *a2)
{
  unsigned int v3; // eax
  DWORD v4; // esi
  WCHAR *v5; // r14
  unsigned int v6; // eax
  unsigned int v7; // eax
  HRESULT v8; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-A9h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-A9h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-A9h]
  LPDWORD lpcbMaxClassLen; // [rsp+30h] [rbp-99h]
  DWORD cbData; // [rsp+60h] [rbp-69h] BYREF
  int v15; // [rsp+64h] [rbp-65h]
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-61h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-5Dh] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-49h] BYREF
  void *v21; // [rsp+88h] [rbp-41h] BYREF
  __int128 v22; // [rsp+90h] [rbp-39h]
  void **v23; // [rsp+A0h] [rbp-29h] BYREF
  char v24; // [rsp+A8h] [rbp-21h]
  LPWSTR lpValueName[2]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v26; // [rsp+C0h] [rbp-9h]
  _QWORD *v27; // [rsp+C8h] [rbp-1h]
  GUID pclsid; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v27 = a1;
  Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)&hMem, a2);
  Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(&hKey);
  v15 = 2;
  if ( hMem )
    LocalFree(hMem);
  cValues = 0;
  cbMaxValueNameLen = 0;
  v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
      (const char *)v3,
      lpcSubKeys);
  std::vector<bond::blob>::vector<bond::blob>(&v21);
  v23 = &v21;
  v24 = 1;
  std::vector<bond::blob>::vector<bond::blob>(a1);
  v15 = 3;
  *(_OWORD *)lpValueName = 0;
  v26 = 0;
  std::vector<unsigned short>::_Construct_n<>(lpValueName, cbMaxValueNameLen + 1);
  v4 = 0;
  v5 = lpValueName[0];
  while ( v4 < cValues )
  {
    LODWORD(hMem) = 0;
    cchValueName = lpValueName[1] - v5;
    cbData = 4;
    v6 = RegEnumValueW(hKey, v4, v5, &cchValueName, 0, 0, (LPBYTE)&hMem, &cbData);
    if ( v6 == 234 )
    {
      v7 = RegEnumValueW(hKey, v4, v5, &cchValueName, 0, 0, 0, 0);
      if ( v7 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xDB,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
          (const char *)v7,
          lpcSubKeysb);
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
        (const char *)0xD,
        (unsigned int)"Value name: %ws, Size: %d",
        (const char *)v5);
      *(_QWORD *)&pclsid.Data1 = v5;
      std::vector<std::wstring>::emplace_back<unsigned short *>(&v21, &pclsid);
    }
    else if ( v6 )
    {
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xE1,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
        (const char *)v6,
        lpcSubKeysa);
    }
    if ( cbData == 4 )
    {
      pclsid = 0;
      v8 = CLSIDFromString(v5, &pclsid);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
          (const char *)(unsigned int)v8,
          lpcSubKeysa);
      std::vector<Windows::Internal::WiFiCloudStore::NlmSyncStruct>::emplace_back<_GUID &,enum Windows::Internal::WiFiCloudStore::NlmModificationType &>(
        a1,
        &pclsid,
        &hMem);
    }
    else
    {
      LODWORD(lpcbMaxClassLen) = cbData;
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0xEE,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
        (const char *)0xD,
        (unsigned int)"Value name: %ws, Size: %d",
        (const char *)v5,
        lpcbMaxClassLen);
      *(_QWORD *)&pclsid.Data1 = v5;
      std::vector<std::wstring>::emplace_back<unsigned short *>(&v21, &pclsid);
    }
    ++v4;
  }
  std::vector<unsigned short>::_Tidy(lpValueName);
  v24 = 0;
  lambda_f63bfaa313a45d693bf0c0519913f2b3_::operator()(&v23);
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v21, v22);
    std::_Deallocate<16>(v21, (*((_QWORD *)&v22 + 1) - (_QWORD)v21) & 0xFFFFFFFFFFFFFFE0uLL);
    v21 = 0;
    v22 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x180016478  push    rbp
0x18001647a  push    rsi
0x18001647b  push    rdi
0x18001647c  push    r13
0x18001647e  push    r14
0x180016480  push    r15
0x180016482  lea     rbp, [rsp-2Fh]
0x180016487  sub     rsp, 0F8h
0x18001648e  mov     rax, cs:__security_cookie
0x180016495  xor     rax, rsp
0x180016498  mov     [rbp+57h+var_40], rax
0x18001649c  mov     rdi, rcx
0x18001649f  mov     [rbp+57h+var_58], rcx
0x1800164a3  xor     r15d, r15d
0x1800164a6  mov     [rbp+57h+var_BC], r15d
0x1800164aa  lea     rcx, [rbp+57h+hMem]; StringSid
0x1800164ae  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x1800164b3  nop
0x1800164b4  mov     r8, [rbp+57h+hMem]
0x1800164b8  lea     rcx, [rbp+57h+hKey]; phkResult
0x1800164bc  call    ?OpenNlmSyncRegistryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenNlmSyncRegistryKeyForUser(Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x1800164c1  mov     [rbp+57h+var_BC], 2
0x1800164c8  mov     rcx, [rbp+57h+hMem]; hMem
0x1800164cc  test    rcx, rcx
0x1800164cf  jz      short loc_1800164D8
0x1800164d1  call    cs:__imp_LocalFree
0x1800164d7  nop
0x1800164d8  mov     [rbp+57h+cValues], r15d
0x1800164dc  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x1800164e0  mov     [rsp+120h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800164e5  mov     [rsp+120h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800164ea  mov     [rsp+120h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800164ef  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800164f3  mov     [rsp+120h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800164f8  lea     rax, [rbp+57h+cValues]
0x1800164fc  mov     [rsp+120h+lpcValues], rax; lpcValues
0x180016501  mov     [rsp+120h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180016506  mov     [rsp+120h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18001650b  mov     [rsp+120h+lpcSubKeys], r15; unsigned int
0x180016510  xor     r9d, r9d; lpReserved
0x180016513  xor     r8d, r8d; lpcchClass
0x180016516  xor     edx, edx; lpClass
0x180016518  mov     rcx, [rbp+57h+hKey]; hKey
0x18001651c  call    cs:__imp_RegQueryInfoKeyW
0x180016522  mov     rcx, [rbp+5Fh]; this
0x180016526  test    eax, eax
0x180016528  jz      short loc_18001653F
0x18001652a  mov     r9d, eax; char *
0x18001652d  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180016534  mov     edx, 0B8h; void *
0x180016539  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001653f  lea     rcx, [rbp+57h+var_98]
0x180016543  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x180016548  nop
0x180016549  lea     rax, [rbp+57h+var_98]
0x18001654d  mov     [rbp+57h+var_80], rax
0x180016551  mov     [rbp+57h+var_78], 1
0x180016555  mov     rcx, rdi
0x180016558  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x18001655d  mov     [rbp+57h+var_BC], 3
0x180016564  xorps   xmm0, xmm0
0x180016567  movdqu  xmmword ptr [rbp+57h+lpValueName], xmm0
0x18001656c  mov     [rbp+57h+var_60], r15
0x180016570  mov     edx, [rbp+57h+cbMaxValueNameLen]
0x180016573  inc     edx
0x180016575  lea     rcx, [rbp+57h+lpValueName]
0x180016579  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x18001657e  nop
0x18001657f  mov     esi, r15d
0x180016582  lea     r13, aValueNameWsSiz; "Value name: %ws, Size: %d"
0x180016589  mov     r14, [rbp+57h+lpValueName]
0x18001658d  cmp     esi, [rbp+57h+cValues]
0x180016590  jnb     loc_180016711
0x180016596  mov     dword ptr [rbp+57h+hMem], r15d
0x18001659a  mov     rax, [rbp+57h+lpValueName+8]
0x18001659e  sub     rax, r14
0x1800165a1  sar     rax, 1
0x1800165a4  mov     [rbp+57h+cchValueName], eax
0x1800165a7  mov     [rbp+57h+cbData], 4
0x1800165ae  lea     rax, [rbp+57h+cbData]
0x1800165b2  mov     [rsp+120h+lpcValues], rax; lpcbData
0x1800165b7  lea     rax, [rbp+57h+hMem]
0x1800165bb  mov     [rsp+120h+lpcbMaxClassLen], rax; lpData
0x1800165c0  mov     [rsp+120h+lpcbMaxSubKeyLen], r15; lpType
0x1800165c5  mov     [rsp+120h+lpcSubKeys], r15; unsigned int
0x1800165ca  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800165ce  mov     r8, r14; lpValueName
0x1800165d1  mov     edx, esi; dwIndex
0x1800165d3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800165d7  call    cs:__imp_RegEnumValueW
0x1800165dd  cmp     eax, 0EAh
0x1800165e2  jnz     short loc_180016656
0x1800165e4  mov     [rsp+120h+lpcValues], r15; lpcbData
0x1800165e9  mov     [rsp+120h+lpcbMaxClassLen], r15; lpData
0x1800165ee  mov     [rsp+120h+lpcbMaxSubKeyLen], r15; lpType
0x1800165f3  mov     [rsp+120h+lpcSubKeys], r15; unsigned int
0x1800165f8  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800165fc  mov     r8, r14; lpValueName
0x1800165ff  mov     edx, esi; dwIndex
0x180016601  mov     rcx, [rbp+57h+hKey]; hKey
0x180016605  call    cs:__imp_RegEnumValueW
0x18001660b  mov     rcx, [rbp+5Fh]; this
0x18001660f  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180016616  test    eax, eax
0x180016618  jnz     loc_1800166D5
0x18001661e  mov     rcx, [rbp+5Fh]; this
0x180016622  mov     eax, [rbp+57h+cbData]
0x180016625  mov     dword ptr [rsp+120h+lpcbMaxClassLen], eax
0x180016629  mov     [rsp+120h+lpcbMaxSubKeyLen], r14; char *
0x18001662e  mov     [rsp+120h+lpcSubKeys], r13; unsigned int
0x180016633  mov     r9d, 0Dh; char *
0x180016639  mov     edx, 0DCh; void *
0x18001663e  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180016643  mov     qword ptr [rbp+57h+pclsid.Data1], r14
0x180016647  lea     rdx, [rbp+57h+pclsid]
0x18001664b  lea     rcx, [rbp+57h+var_98]
0x18001664f  call    ??$emplace_back@PEAG@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEAG@Z; std::vector<std::wstring>::emplace_back<ushort *>(ushort * &&)
0x180016654  jmp     short loc_18001665E
0x180016656  test    eax, eax
0x180016658  jnz     loc_1800166F8
0x18001665e  mov     eax, [rbp+57h+cbData]
0x180016661  cmp     eax, 4
0x180016664  jnz     short loc_180016694
0x180016666  xorps   xmm0, xmm0
0x180016669  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18001666d  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180016671  mov     rcx, r14; lpsz
0x180016674  call    cs:__imp_CLSIDFromString
0x18001667a  mov     rcx, [rbp+5Fh]; this
0x18001667e  test    eax, eax
0x180016680  js      short loc_1800166E3
0x180016682  lea     r8, [rbp+57h+hMem]
0x180016686  lea     rdx, [rbp+57h+pclsid]
0x18001668a  mov     rcx, rdi
0x18001668d  call    ??$emplace_back@AEAU_GUID@@AEAW4NlmModificationType@WiFiCloudStore@Internal@Windows@@@?$vector@UNlmSyncStruct@WiFiCloudStore@Internal@Windows@@V?$allocator@UNlmSyncStruct@WiFiCloudStore@Internal@Windows@@@std@@@std@@QEAAAEAUNlmSyncStruct@WiFiCloudStore@Internal@Windows@@AEAU_GUID@@AEAW4NlmModificationType@345@@Z; std::vector<Windows::Internal::WiFiCloudStore::NlmSyncStruct>::emplace_back<_GUID &,Windows::Internal::WiFiCloudStore::NlmModificationType &>(_GUID &,Windows::Internal::WiFiCloudStore::NlmModificationType &)
0x180016692  jmp     short loc_1800166CE
0x180016694  mov     rcx, [rbp+5Fh]; this
0x180016698  mov     dword ptr [rsp+120h+lpcbMaxClassLen], eax
0x18001669c  mov     [rsp+120h+lpcbMaxSubKeyLen], r14; char *
0x1800166a1  mov     [rsp+120h+lpcSubKeys], r13; unsigned int
0x1800166a6  mov     r9d, 0Dh; char *
0x1800166ac  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x1800166b3  mov     edx, 0EEh; void *
0x1800166b8  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800166bd  mov     qword ptr [rbp+57h+pclsid.Data1], r14
0x1800166c1  lea     rdx, [rbp+57h+pclsid]
0x1800166c5  lea     rcx, [rbp+57h+var_98]
0x1800166c9  call    ??$emplace_back@PEAG@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEAG@Z; std::vector<std::wstring>::emplace_back<ushort *>(ushort * &&)
0x1800166ce  inc     esi
0x1800166d0  jmp     loc_18001658D
0x1800166d5  mov     r9d, eax; char *
0x1800166d8  mov     edx, 0DBh; void *
0x1800166dd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800166e3  mov     r9d, eax; char *
0x1800166e6  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x1800166ed  mov     edx, 0E9h; void *
0x1800166f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800166f8  mov     rcx, [rbp+5Fh]; this
0x1800166fc  mov     r9d, eax; char *
0x1800166ff  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180016706  mov     edx, 0E1h; void *
0x18001670b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180016711  lea     rcx, [rbp+57h+lpValueName]
0x180016715  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18001671a  nop
0x18001671b  mov     [rbp+57h+var_78], r15b
0x18001671f  lea     rcx, [rbp+57h+var_80]
0x180016723  call    _lambda_f63bfaa313a45d693bf0c0519913f2b3___operator__
0x180016728  nop
0x180016729  mov     rcx, [rbp+57h+var_98]
0x18001672d  test    rcx, rcx
0x180016730  jz      short loc_18001675B
0x180016732  mov     rdx, qword ptr [rbp+57h+var_90]
0x180016736  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18001673b  mov     rcx, [rbp+57h+var_98]
0x18001673f  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x180016743  sub     rdx, rcx
0x180016746  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001674a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001674f  mov     [rbp+57h+var_98], r15
0x180016753  xorps   xmm0, xmm0
0x180016756  movdqu  [rbp+57h+var_90], xmm0
0x18001675b  mov     rcx, [rbp+57h+hKey]; hKey
0x18001675f  test    rcx, rcx
0x180016762  jz      short loc_18001676A
0x180016764  call    cs:__imp_RegCloseKey
0x18001676a  mov     rax, rdi
0x18001676d  mov     rcx, [rbp+57h+var_40]
0x180016771  xor     rcx, rsp; StackCookie
0x180016774  call    __security_check_cookie
0x180016779  add     rsp, 0F8h
0x180016780  pop     r15
0x180016782  pop     r14
0x180016784  pop     r13
0x180016786  pop     rdi
0x180016787  pop     rsi
0x180016788  pop     rbp
0x180016789  retn
```
