# DataStoreCache::Create_CacheManager(DataStoreCache::IDataManager *,std::vector<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer>,std::allocator<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer>>> const &,std::vector<_GUID,std::allocator<_GUID>> const &,bool,HSTRING__ *,std::shared_ptr<UserHelpers::Impersonator> const &)

- ea: `0x1800a3bf4`
- end: `0x1800a3f31`
- name: `?Create_CacheManager@DataStoreCache@@YA?AV?$ComPtr@UICacheManager@DataStoreCache@@@WRL@Microsoft@@PEAUIDataManager@1@AEBV?$vector@V?$ComPtr@UIDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@@std@@@std@@AEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@7@_NPEAUHSTRING__@@AEBV?$shared_ptr@VImpersonator@UserHelpers@@@7@@Z`
- size: `829`
- prototype: `__int64 __fastcall(int, int, int, int, int, HSTRING string, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180038760`

## callees

- `0x18000b5f0`
- `0x18000ce94`
- `0x18001dac0`
- `0x18002f1fc`
- `0x18003ca6c`
- `0x18004f114`
- `0x1800a3748`
- `0x1800a3b18`
- `0x1800a3bf4`
- `0x1800a46b8`
- `0x1800a5310`
- `0x1800c0840`
- `0x180159f70`
- `0x18015a0b0`
- `0x18022b750`
- `0x18022cc70`
- `0x180258b14`
- `0x1803142e8`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3ce9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a3d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a3d12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3d52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3f03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3d52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3f03`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a3d9c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a3dbe`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a3d9c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a3dbe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800a3e3a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800a3e3a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800a3e28`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800a3e28`

## string_xrefs

- `0x1800a3cfa`: `shellcommon\shell\datastorecache\cache\lib\cachemanager.cpp`
- `0x1800a3dc8`: `shellcommon\shell\datastorecache\cache\lib\cachemanager.cpp`
- `0x1800a3e60`: `shellcommon\shell\datastorecache\cache\lib\cachemanager.cpp`
- `0x1800a3eb5`: `shellcommon\shell\datastorecache\cache\lib\cachemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 *__fastcall DataStoreCache::Create_CacheManager(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        HSTRING string,
        _QWORD *a7)
{
  int v7; // r12d
  LPCWSTR v9; // rcx
  __int64 v10; // r8
  int (__fastcall ****v11)(_QWORD, GUID *, LPCWSTR *); // r14
  int (__fastcall ****v12)(_QWORD, GUID *, LPCWSTR *); // r15
  int (__fastcall ***v13)(_QWORD, GUID *, LPCWSTR *); // rdi
  int (__fastcall *v14)(_QWORD, GUID *, LPCWSTR *); // rbx
  char v15; // di
  int CallingProcessHandle; // ebx
  bool *v17; // r8
  char *v18; // rcx
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v20; // r14
  __int64 v21; // r15
  __int64 v22; // rbx
  __int64 v23; // rax
  void *v24; // rdx
  __int64 v25; // rdi
  const char *v26; // r9
  void *v27; // rdx
  LPCWSTR v28; // rbx
  int v30; // eax
  __int64 v31; // rcx
  int v33; // [rsp+20h] [rbp-60h]
  int v34; // [rsp+20h] [rbp-60h]
  __int64 v35; // [rsp+48h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-28h] BYREF
  HANDLE v38; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v39[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  __int64 v41; // [rsp+C8h] [rbp+48h] BYREF
  LPCWSTR pszPath; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v43; // [rsp+D8h] [rbp+58h]

  v43 = a4;
  v41 = a2;
  v7 = a4;
  std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(v39);
  v11 = *(int (__fastcall *****)(_QWORD, GUID *, LPCWSTR *))v10;
  v12 = *(int (__fastcall *****)(_QWORD, GUID *, LPCWSTR *))(v10 + 8);
  while ( v11 != v12 )
  {
    pszPath = 0;
    v13 = *v11;
    v14 = ***v11;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pszPath);
    if ( v14(v13, &GUID_204599e2_b346_84ef_6f70_e79b7b88cb57, &pszPath) >= 0 )
      std::vector<Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>::emplace_back<Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>(
        v39,
        &pszPath);
    v9 = pszPath;
    if ( pszPath )
    {
      pszPath = 0;
      (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)v9 + 16LL))(v9);
    }
    ++v11;
  }
  if ( v39[1] == v39[0] )
  {
    *a1 = 0;
  }
  else
  {
    v15 = 0;
    LOBYTE(pszPath) = 0;
    hObject = 0;
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(v9, 0, &hObject);
    if ( CallingProcessHandle >= 0 )
    {
      CallingProcessHandle = CallerIdentity::IsProcessAppContainer(hObject, &pszPath, v17);
      v15 = (char)pszPath;
    }
    v18 = (char *)hObject;
    hObject = 0;
    if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v18);
    if ( CallingProcessHandle < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cachemanager.cpp",
        (const char *)(unsigned int)CallingProcessHandle,
        v33);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v20 = StringRawBuffer;
    pszPath = 0;
    v21 = (__int64)a7;
    if ( v15 )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &pv,
        StringRawBuffer,
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &pszPath,
        &pv);
      if ( pv )
        CoTaskMemFree(pv);
    }
    else
    {
      v22 = -1;
      hObject = (HANDLE)-1LL;
      if ( *a7 )
      {
        v23 = UserHelpers::Impersonator::Impersonate(*a7, &v38);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::operator=(
          &hObject,
          v23);
        if ( v38 != (HANDLE)-1LL )
          wil::details::RevertImpersonateToken(v38, v24);
        v22 = (__int64)hObject;
      }
      v25 = ExpandEnvironmentStringsW(v20, 0, 0);
      std::make_unique<unsigned short [0],0>(&pv, v25);
      if ( !ExpandEnvironmentStringsW(v20, (LPWSTR)pv, v25) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x55,
          (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cachemanager.cpp",
          v26);
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v38,
        pv,
        v25);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &pszPath,
        &v38);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
      std::unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>::~unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>(&pv);
      if ( v22 != -1 )
        wil::details::RevertImpersonateToken((HANDLE)v22, v27);
      v7 = v43;
    }
    v28 = pszPath;
    if ( !PathIsUNCW(pszPath) && (PathGetDriveNumberW(v28) == -1 || v28[2] != 92) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cachemanager.cpp",
        (const char *)0x80070057LL,
        v33);
    v35 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v30 = Microsoft::WRL::Details::MakeAndInitialize<DataStoreCache::CacheManager,DataStoreCache::ICacheManager,DataStoreCache::IDataManager * &,std::vector<Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>> &,std::vector<_GUID> const &,bool &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,std::shared_ptr<UserHelpers::Impersonator> const &>(
            (unsigned int)&v35,
            (unsigned int)&v41,
            (unsigned int)v39,
            v7,
            (__int64)&a5,
            (__int64)&pszPath,
            v21);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cachemanager.cpp",
        (const char *)(unsigned int)v30,
        v34);
    *a1 = 0;
    if ( a1 == &v35 )
    {
      v31 = v35;
    }
    else
    {
      *a1 = v35;
      v31 = 0;
      v35 = 0;
    }
    if ( v31 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    if ( pszPath )
      CoTaskMemFree((LPVOID)pszPath);
  }
  std::vector<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer>>::~vector<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer>>(v39);
  return a1;
}

```

## disassembly

```asm
0x1800a3bf4  mov     [rsp-38h+arg_0], rbx
0x1800a3bf9  mov     [rsp-38h+arg_18], r9
0x1800a3bfe  mov     [rsp-38h+arg_8], rdx
0x1800a3c03  push    rbp
0x1800a3c04  push    rsi
0x1800a3c05  push    rdi
0x1800a3c06  push    r12
0x1800a3c08  push    r13
0x1800a3c0a  push    r14
0x1800a3c0c  push    r15
0x1800a3c0e  mov     rbp, rsp
0x1800a3c11  sub     rsp, 80h
0x1800a3c18  mov     r12, r9
0x1800a3c1b  mov     rsi, rcx
0x1800a3c1e  xor     r13d, r13d
0x1800a3c21  lea     rcx, [rbp+var_18]
0x1800a3c25  call    ??0?$vector@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@V?$allocator@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(void)
0x1800a3c2a  nop
0x1800a3c2b  mov     r14, [r8]
0x1800a3c2e  mov     r15, [r8+8]
0x1800a3c32  jmp     short loc_1800A3C91
0x1800a3c34  mov     [rbp+pszPath], r13
0x1800a3c38  mov     rdi, [r14]
0x1800a3c3b  mov     rax, [rdi]
0x1800a3c3e  mov     rbx, [rax]
0x1800a3c41  lea     rcx, [rbp+pszPath]
0x1800a3c45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a3c4a  lea     r8, [rbp+pszPath]
0x1800a3c4e  lea     rdx, _GUID_204599e2_b346_84ef_6f70_e79b7b88cb57
0x1800a3c55  mov     rcx, rdi
0x1800a3c58  mov     rax, rbx
0x1800a3c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3c60  nop
0x1800a3c61  test    eax, eax
0x1800a3c63  js      short loc_1800A3C73
0x1800a3c65  lea     rdx, [rbp+pszPath]
0x1800a3c69  lea     rcx, [rbp+var_18]
0x1800a3c6d  call    ??$emplace_back@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@$$QEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>::emplace_back<Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>(Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer> &&)
0x1800a3c72  nop
0x1800a3c73  mov     rcx, [rbp+pszPath]
0x1800a3c77  test    rcx, rcx
0x1800a3c7a  jz      short loc_1800A3C8D
0x1800a3c7c  mov     [rbp+pszPath], r13
0x1800a3c80  mov     rax, [rcx]
0x1800a3c83  mov     rax, [rax+10h]
0x1800a3c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3c8c  nop
0x1800a3c8d  add     r14, 8
0x1800a3c91  cmp     r14, r15
0x1800a3c94  jnz     short loc_1800A3C34
0x1800a3c96  mov     rax, [rbp+var_10]
0x1800a3c9a  cmp     rax, [rbp+var_18]
0x1800a3c9e  jnz     short loc_1800A3CA8
0x1800a3ca0  mov     [rsi], r13
0x1800a3ca3  jmp     loc_1800A3F0A
0x1800a3ca8  mov     dil, r13b
0x1800a3cab  mov     byte ptr [rbp+pszPath], r13b
0x1800a3caf  mov     [rbp+hObject], r13
0x1800a3cb3  lea     r8, [rbp+hObject]
0x1800a3cb7  xor     edx, edx
0x1800a3cb9  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x1800a3cbe  mov     ebx, eax
0x1800a3cc0  test    eax, eax
0x1800a3cc2  js      short loc_1800A3CD7
0x1800a3cc4  lea     rdx, [rbp+pszPath]; void *
0x1800a3cc8  mov     rcx, [rbp+hObject]; ProcessHandle
0x1800a3ccc  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x1800a3cd1  mov     ebx, eax
0x1800a3cd3  mov     dil, byte ptr [rbp+pszPath]
0x1800a3cd7  mov     rcx, [rbp+hObject]; hObject
0x1800a3cdb  mov     [rbp+hObject], r13
0x1800a3cdf  lea     rax, [rcx-1]
0x1800a3ce3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a3ce7  ja      short loc_1800A3CEF
0x1800a3ce9  call    cs:__imp_CloseHandle
0x1800a3cef  mov     rcx, [rbp+38h]; this
0x1800a3cf3  test    ebx, ebx
0x1800a3cf5  jns     short loc_1800A3D0C
0x1800a3cf7  mov     r9d, ebx; char *
0x1800a3cfa  lea     r8, aShellcommonShe_203; "shellcommon\\shell\\datastorecache\\cac"...
0x1800a3d01  mov     edx, 41h ; 'A'; void *
0x1800a3d06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a3d0c  xor     edx, edx; length
0x1800a3d0e  mov     rcx, [rbp+string]; string
0x1800a3d12  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a3d18  mov     r14, rax
0x1800a3d1b  mov     [rbp+pszPath], r13
0x1800a3d1f  mov     r15, [rbp+arg_30]
0x1800a3d23  test    dil, dil
0x1800a3d26  jz      short loc_1800A3D5D
0x1800a3d28  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a3d2c  mov     rdx, rax
0x1800a3d2f  lea     rcx, [rbp+pv]
0x1800a3d33  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a3d38  lea     rdx, [rbp+pv]
0x1800a3d3c  lea     rcx, [rbp+pszPath]
0x1800a3d40  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800a3d45  mov     rcx, [rbp+pv]; pv
0x1800a3d49  test    rcx, rcx
0x1800a3d4c  jz      loc_1800A3E21
0x1800a3d52  call    cs:__imp_CoTaskMemFree
0x1800a3d58  jmp     loc_1800A3E21
0x1800a3d5d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a3d61  mov     [rbp+hObject], rbx
0x1800a3d65  mov     rcx, [r15]
0x1800a3d68  test    rcx, rcx
0x1800a3d6b  jz      short loc_1800A3D94
0x1800a3d6d  lea     rdx, [rbp+var_20]
0x1800a3d71  call    ?Impersonate@Impersonator@UserHelpers@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; UserHelpers::Impersonator::Impersonate(void)
0x1800a3d76  mov     rdx, rax
0x1800a3d79  lea     rcx, [rbp+hObject]
0x1800a3d7d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &&)
0x1800a3d82  mov     rcx, [rbp+var_20]; hObject
0x1800a3d86  cmp     rcx, rbx
0x1800a3d89  jz      short loc_1800A3D90
0x1800a3d8b  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800a3d90  mov     rbx, [rbp+hObject]
0x1800a3d94  xor     r8d, r8d; nSize
0x1800a3d97  xor     edx, edx; lpDst
0x1800a3d99  mov     rcx, r14; lpSrc
0x1800a3d9c  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a3da2  mov     edi, eax
0x1800a3da4  mov     edx, eax
0x1800a3da6  lea     rcx, [rbp+pv]
0x1800a3daa  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x1800a3daf  nop
0x1800a3db0  mov     r12, [rbp+38h]
0x1800a3db4  mov     r8d, edi; nSize
0x1800a3db7  mov     rdx, [rbp+pv]; lpDst
0x1800a3dbb  mov     rcx, r14; lpSrc
0x1800a3dbe  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a3dc4  test    eax, eax
0x1800a3dc6  jnz     short loc_1800A3DDB
0x1800a3dc8  lea     r8, aShellcommonShe_203; "shellcommon\\shell\\datastorecache\\cac"...
0x1800a3dcf  lea     edx, [rax+55h]; void *
0x1800a3dd2  mov     rcx, r12; this
0x1800a3dd5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800a3ddb  mov     r8, rdi
0x1800a3dde  mov     rdx, [rbp+pv]
0x1800a3de2  lea     rcx, [rbp+var_20]
0x1800a3de6  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a3deb  lea     rdx, [rbp+var_20]
0x1800a3def  lea     rcx, [rbp+pszPath]
0x1800a3df3  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800a3df8  lea     rcx, [rbp+var_20]
0x1800a3dfc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a3e01  nop
0x1800a3e02  lea     rcx, [rbp+pv]
0x1800a3e06  call    ??1?$unique_ptr@$$BY0A@UIMAGE_DOWNLOAD_RESULT@@U?$default_delete@$$BY0A@UIMAGE_DOWNLOAD_RESULT@@@std@@@std@@QEAA@XZ; std::unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>::~unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>(void)
0x1800a3e0b  nop
0x1800a3e0c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a3e10  jz      short loc_1800A3E1A
0x1800a3e12  mov     rcx, rbx; hObject
0x1800a3e15  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800a3e1a  xor     r13d, r13d
0x1800a3e1d  mov     r12, [rbp+arg_18]
0x1800a3e21  mov     rbx, [rbp+pszPath]
0x1800a3e25  mov     rcx, rbx; pszPath
0x1800a3e28  call    cs:__imp_PathIsUNCW
0x1800a3e2e  mov     edi, 5Ch ; '\'
0x1800a3e33  test    eax, eax
0x1800a3e35  jnz     short loc_1800A3E50
0x1800a3e37  mov     rcx, rbx; pszPath
0x1800a3e3a  call    cs:__imp_PathGetDriveNumberW
0x1800a3e40  cmp     eax, 0FFFFFFFFh
0x1800a3e43  jz      short loc_1800A3E4B
0x1800a3e45  cmp     [rbx+4], di
0x1800a3e49  jz      short loc_1800A3E50
0x1800a3e4b  mov     al, r13b
0x1800a3e4e  jmp     short loc_1800A3E52
0x1800a3e50  mov     al, 1
0x1800a3e52  mov     rcx, [rbp+38h]; this
0x1800a3e56  test    al, al
0x1800a3e58  jnz     short loc_1800A3E72
0x1800a3e5a  mov     r9d, 80070057h; char *
0x1800a3e60  lea     r8, aShellcommonShe_203; "shellcommon\\shell\\datastorecache\\cac"...
0x1800a3e67  mov     edx, 59h ; 'Y'; void *
0x1800a3e6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a3e72  mov     [rbp+var_38], r13
0x1800a3e76  lea     rcx, [rbp+var_38]
0x1800a3e7a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a3e7f  mov     [rsp+80h+var_50], r15
0x1800a3e84  lea     rax, [rbp+pszPath]
0x1800a3e88  mov     [rsp+80h+var_58], rax
0x1800a3e8d  lea     rax, [rbp+arg_20]
0x1800a3e91  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800a3e96  mov     r9, r12
0x1800a3e99  lea     r8, [rbp+var_18]
0x1800a3e9d  lea     rdx, [rbp+arg_8]
0x1800a3ea1  lea     rcx, [rbp+var_38]
0x1800a3ea5  call    ??$MakeAndInitialize@VCacheManager@DataStoreCache@@UICacheManager@2@AEAPEAUIDataManager@2@AEAV?$vector@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@@std@@@std@@AEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@6@AEA_NV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$shared_ptr@VImpersonator@UserHelpers@@@6@@Details@WRL@Microsoft@@YAJPEAPEAUICacheManager@DataStoreCache@@AEAPEAUIDataManager@4@AEAV?$vector@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@@std@@@std@@AEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@7@AEA_N$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$shared_ptr@VImpersonator@UserHelpers@@@7@@Z; Microsoft::WRL::Details::MakeAndInitialize<DataStoreCache::CacheManager,DataStoreCache::ICacheManager,DataStoreCache::IDataManager * &,std::vector<Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>> &,std::vector<_GUID> const &,bool &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,std::shared_ptr<UserHelpers::Impersonator> const &>(DataStoreCache::ICacheManager * *,DataStoreCache::IDataManager * &,std::vector<Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>> &,std::vector<_GUID> const &,bool &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&,std::shared_ptr<UserHelpers::Impersonator> const &)
0x1800a3eaa  mov     rcx, [rbp+38h]; this
0x1800a3eae  test    eax, eax
0x1800a3eb0  jns     short loc_1800A3EC4
0x1800a3eb2  mov     r9d, eax; char *
0x1800a3eb5  lea     r8, aShellcommonShe_203; "shellcommon\\shell\\datastorecache\\cac"...
0x1800a3ebc  mov     edx, edi; void *
0x1800a3ebe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a3ec4  mov     [rsi], r13
0x1800a3ec7  lea     rax, [rbp+var_38]
0x1800a3ecb  cmp     rsi, rax
0x1800a3ece  jz      short loc_1800A3EE0
0x1800a3ed0  mov     rax, [rbp+var_38]
0x1800a3ed4  mov     [rsi], rax
0x1800a3ed7  mov     rcx, r13
0x1800a3eda  mov     [rbp+var_38], rcx
0x1800a3ede  jmp     short loc_1800A3EE4
0x1800a3ee0  mov     rcx, [rbp+var_38]
0x1800a3ee4  test    rcx, rcx
0x1800a3ee7  jz      short loc_1800A3EFA
0x1800a3ee9  mov     [rbp+var_38], r13
0x1800a3eed  mov     rax, [rcx]
0x1800a3ef0  mov     rax, [rax+10h]
0x1800a3ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ef9  nop
0x1800a3efa  mov     rcx, [rbp+pszPath]; pv
0x1800a3efe  test    rcx, rcx
0x1800a3f01  jz      short loc_1800A3F0A
0x1800a3f03  call    cs:__imp_CoTaskMemFree
0x1800a3f09  nop
0x1800a3f0a  lea     rcx, [rbp+var_18]
0x1800a3f0e  call    ??1?$vector@V?$ComPtr@UIDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer>>::~vector<Microsoft::WRL::ComPtr<DataStoreCache::IDataStoreTransformer>>(void)
0x1800a3f13  mov     rax, rsi
0x1800a3f16  mov     rbx, [rsp+80h+arg_0]
0x1800a3f1e  add     rsp, 80h
0x1800a3f25  pop     r15
0x1800a3f27  pop     r14
0x1800a3f29  pop     r13
0x1800a3f2b  pop     r12
0x1800a3f2d  pop     rdi
0x1800a3f2e  pop     rsi
0x1800a3f2f  pop     rbp
0x1800a3f30  retn
```
