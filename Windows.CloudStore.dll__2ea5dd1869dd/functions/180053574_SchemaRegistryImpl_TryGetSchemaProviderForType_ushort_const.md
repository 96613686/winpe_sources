# SchemaRegistryImpl::TryGetSchemaProviderForType(ushort const *)

- ea: `0x180053574`
- end: `0x180053a59`
- name: `?TryGetSchemaProviderForType@SchemaRegistryImpl@@AEAA?AV?$com_ptr_t@UICloudStoreSchemaProvider@@Uerr_exception_policy@wil@@@wil@@PEBG@Z`
- size: `1253`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180023920`
- `0x1800532d4`
- `0x180104b40`

## callees

- `0x18000dfe4`
- `0x180016cf4`
- `0x18003e670`
- `0x18003e904`
- `0x18003f6c4`
- `0x180053574`
- `0x180053a60`
- `0x18005abfc`
- `0x18005ac4c`
- `0x180091858`
- `0x18009d8a8`
- `0x1800c8024`
- `0x1800d5484`
- `0x1800f12fc`
- `0x1801201a0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180053826`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180053826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005361d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800538c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053950`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005361d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800538c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053950`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053917`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053917`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005388f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005388f`

## string_xrefs

- `0x18005364e`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800536f5`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800537aa`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800537d9`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800538a3`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x18005392b`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800539c1`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x180053a02`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LPVOID *__fastcall SchemaRegistryImpl::TryGetSchemaProviderForType(
        SchemaRegistryImpl *this,
        LPVOID *a2,
        const unsigned __int16 *a3)
{
  __int64 **v6; // rax
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // ebx
  void *v10; // rcx
  char v11; // al
  _QWORD *AppExtensionSchemaProvider; // rax
  __int64 v13; // r10
  __int64 v14; // rax
  const WCHAR *v15; // rcx
  __int64 v16; // rdx
  WCHAR *v17; // r8
  WCHAR v18; // r9
  WCHAR *v19; // rcx
  __int64 v20; // rdx
  WCHAR *v21; // rax
  const char *v22; // r9
  __int64 v23; // r8
  const wchar_t *v24; // rcx
  __int64 v25; // rdx
  WCHAR *v26; // rax
  wchar_t v27; // r8
  WCHAR *v28; // rcx
  int v29; // eax
  LSTATUS ValueW; // eax
  int v31; // r9d
  bool v32; // sf
  HRESULT v33; // eax
  void *v34; // rcx
  LPVOID v35; // rcx
  HRESULT v36; // eax
  void *lpSecurityDescriptor; // rcx
  CloudStoreUtilities *v38; // rbx
  HKEY *v39; // r9
  int RegistryRootKey; // eax
  int v41; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  struct _SECURITY_ATTRIBUTES pcbData; // [rsp+48h] [rbp-B8h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-A0h] BYREF
  char v49; // [rsp+70h] [rbp-90h]
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[264]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  pcbData.lpSecurityDescriptor = a2;
  ppv = 0;
  if ( *((_QWORD *)this + 9) )
  {
    *(_QWORD *)&pcbData.nLength = 0;
    v38 = (SchemaRegistryImpl *)((char *)this + 56);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetImpl'::`2'::impl);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &pcbData,
      0);
    if ( *((_QWORD *)v38 + 3) > 7u )
      v38 = *(CloudStoreUtilities **)v38;
    RegistryRootKey = CloudStoreUtilities::GetRegistryRootKey(v38, L"Schema", &pcbData, v39);
    if ( RegistryRootKey != -2147024894 )
    {
      if ( RegistryRootKey < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x19A,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)(unsigned int)RegistryRootKey,
          pdwType);
      SchemaRegistryImpl::EnsureRuntimeSchemaWatcher(this);
      wil::com_ptr_t<ICloudStoreSchemaProvider,wil::err_exception_policy>::reset(&ppv);
      v41 = CloudStoreSchemaProvider_CreateInstance(&pcbData, &ppv);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x19D,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)(unsigned int)v41,
          pdwType);
      *((_DWORD *)this + 68) = 2;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&pcbData);
      goto LABEL_64;
    }
    *a2 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&pcbData);
  }
  else
  {
    pcbData.lpSecurityDescriptor = 0;
    pcbData.bInheritHandle = 0;
    v6 = (__int64 **)((__int64 (*)(void))SchemaRegistryImpl::GetAppExtensionSchemaProvider)();
    v7 = *v6;
    v8 = **v6;
    *(_QWORD *)&pclsid.Data1 = &pcbData.lpSecurityDescriptor;
    *(_QWORD *)pclsid.Data4 = 0;
    v49 = 1;
    v9 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, unsigned __int8 *, BOOL *))(v8 + 48))(
           v7,
           a3,
           pclsid.Data4,
           &pcbData.bInheritHandle);
    if ( v49 )
    {
      v10 = **(void ***)&pclsid.Data1;
      **(_QWORD **)&pclsid.Data1 = *(_QWORD *)pclsid.Data4;
      if ( v10 )
        CoTaskMemFree(v10);
    }
    if ( v9 >= 0 || v9 == -2147024891 || (v11 = 1, v9 == -2147023728) )
      v11 = 0;
    if ( v11 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A5,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
        (const char *)(unsigned int)v9,
        pdwType);
    if ( v9 != -2147024891 && v9 != -2147023728 )
    {
      AppExtensionSchemaProvider = (_QWORD *)SchemaRegistryImpl::GetAppExtensionSchemaProvider(
                                               this,
                                               2147942405LL,
                                               2147943568LL);
      wil::com_ptr_t<ICloudStoreSchemaProvider,wil::err_exception_policy>::operator=(&ppv, *AppExtensionSchemaProvider);
    }
    if ( ppv )
      goto LABEL_53;
    v13 = 2147483646;
    v14 = 2147483646;
    v15 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore";
    v16 = 260;
    v17 = SubKey;
    do
    {
      if ( !v14 )
        break;
      v18 = *v15;
      if ( !*v15 )
        break;
      ++v15;
      *v17++ = v18;
      --v14;
      --v16;
    }
    while ( v16 );
    v19 = v17 - 1;
    if ( v16 )
      v19 = v17;
    *v19 = 0;
    if ( !v16 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B1,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
        (const char *)0x8007007ALL,
        pdwType);
    v20 = 260;
    v21 = SubKey;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v20;
    }
    while ( v20 );
    v22 = v20 == 0 ? (const char *)0x80070057LL : 0LL;
    v23 = (260 - v20) & -(__int64)(v20 != 0);
    if ( v20 )
    {
      v24 = L"\\Schema\\";
      v25 = 260 - v23;
      v26 = &SubKey[v23];
      if ( v23 != 260 )
      {
        do
        {
          if ( !v13 )
            break;
          v27 = *v24;
          if ( !*v24 )
            break;
          ++v24;
          *v26++ = v27;
          --v13;
          --v25;
        }
        while ( v25 );
      }
      v28 = v26 - 1;
      if ( v25 )
        v28 = v26;
      *v28 = 0;
      v22 = v25 == 0 ? (const char *)0x8007007ALL : 0LL;
    }
    if ( (int)v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B2,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
        v22,
        pdwType);
    v29 = StringCchCatW(SubKey, 0x104u, a3);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B3,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
        (const char *)(unsigned int)v29,
        pdwType);
    pcbData.nLength = 520;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"Provider", 2u, 0, sz, &pcbData.nLength);
    v32 = ValueW < 0;
    if ( ValueW )
    {
      sz[0] = 0;
      if ( ValueW > 0 )
        v32 = 1;
    }
    if ( !v32 )
    {
LABEL_44:
      pclsid = 0;
      v33 = CLSIDFromString(sz, &pclsid);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C5,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)(unsigned int)v33,
          pdwTypea);
      v35 = ppv;
      ppv = 0;
      if ( v35 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v35 + 16LL))(v35);
      v36 = CoCreateInstance(&pclsid, 0, 0x401u, &GUID_efe84c27_afa6_485d_a70a_aa2ab5cb6c67, &ppv);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C6,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)(unsigned int)v36,
          pdwTypeb);
LABEL_53:
      lpSecurityDescriptor = pcbData.lpSecurityDescriptor;
      pcbData.lpSecurityDescriptor = 0;
      if ( lpSecurityDescriptor )
        CoTaskMemFree(lpSecurityDescriptor);
LABEL_64:
      *a2 = ppv;
      return a2;
    }
    if ( (int)SHRegGetStringEx(HKEY_CURRENT_USER, SubKey, L"Provider", v31, sz, 0x104u) >= 0 )
    {
      *((_DWORD *)this + 68) = 1;
      goto LABEL_44;
    }
    *a2 = 0;
    v34 = pcbData.lpSecurityDescriptor;
    pcbData.lpSecurityDescriptor = 0;
    if ( v34 )
      CoTaskMemFree(v34);
  }
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&ppv);
  return a2;
}

```

## disassembly

```asm
0x180053574  mov     [rsp-8+arg_18], rbx
0x180053579  push    rbp
0x18005357a  push    rsi
0x18005357b  push    rdi
0x18005357c  push    r14
0x18005357e  push    r15
0x180053580  lea     rbp, [rsp-3B0h]
0x180053588  sub     rsp, 4B0h
0x18005358f  mov     rax, cs:__security_cookie
0x180053596  xor     rax, rsp
0x180053599  mov     [rbp+3D0h+var_30], rax
0x1800535a0  mov     r14, r8
0x1800535a3  mov     rdi, rdx
0x1800535a6  mov     rsi, rcx
0x1800535a9  mov     [rsp+4D0h+pv], rdx
0x1800535ae  xor     r15d, r15d
0x1800535b1  mov     [rsp+4D0h+ppv], r15
0x1800535b6  cmp     [rcx+48h], r15
0x1800535ba  jnz     loc_18005395B
0x1800535c0  mov     [rsp+4D0h+pv], r15
0x1800535c5  mov     [rsp+4D0h+var_478], r15d
0x1800535ca  call    ?GetAppExtensionSchemaProvider@SchemaRegistryImpl@@AEAAAEBV?$com_ptr_t@UICloudStoreSchemaProvider@@Uerr_exception_policy@wil@@@wil@@XZ; SchemaRegistryImpl::GetAppExtensionSchemaProvider(void)
0x1800535cf  mov     rcx, [rax]
0x1800535d2  mov     rax, [rcx]
0x1800535d5  lea     rdx, [rsp+4D0h+pv]
0x1800535da  mov     qword ptr [rsp+4D0h+pclsid.Data1], rdx
0x1800535df  mov     qword ptr [rsp+4D0h+pclsid.Data4], r15
0x1800535e4  mov     [rsp+4D0h+var_460], 1
0x1800535e9  lea     r9, [rsp+4D0h+var_478]
0x1800535ee  lea     r8, [rsp+4D0h+pclsid.Data4]
0x1800535f3  mov     rdx, r14
0x1800535f6  mov     rax, [rax+30h]
0x1800535fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535ff  mov     ebx, eax
0x180053601  cmp     [rsp+4D0h+var_460], r15b
0x180053606  jz      short loc_180053623
0x180053608  mov     r8, qword ptr [rsp+4D0h+pclsid.Data1]
0x18005360d  mov     rcx, [r8]; pv
0x180053610  mov     rdx, qword ptr [rsp+4D0h+pclsid.Data4]
0x180053615  mov     [r8], rdx
0x180053618  test    rcx, rcx
0x18005361b  jz      short loc_180053623
0x18005361d  call    cs:__imp_CoTaskMemFree
0x180053623  mov     edx, 80070005h
0x180053628  mov     r8d, 80070490h
0x18005362e  test    ebx, ebx
0x180053630  jns     short loc_18005363D
0x180053632  cmp     ebx, edx
0x180053634  jz      short loc_18005363D
0x180053636  cmp     ebx, r8d
0x180053639  mov     al, 1
0x18005363b  jnz     short loc_180053640
0x18005363d  mov     al, r15b
0x180053640  mov     rcx, [rbp+3D8h]; this
0x180053647  test    al, al
0x180053649  jz      short loc_180053660
0x18005364b  mov     r9d, ebx; char *
0x18005364e  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x180053655  mov     edx, 1A5h; void *
0x18005365a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053660  cmp     ebx, edx
0x180053662  jz      short loc_18005367E
0x180053664  cmp     ebx, r8d
0x180053667  jz      short loc_18005367E
0x180053669  mov     rcx, rsi
0x18005366c  call    ?GetAppExtensionSchemaProvider@SchemaRegistryImpl@@AEAAAEBV?$com_ptr_t@UICloudStoreSchemaProvider@@Uerr_exception_policy@wil@@@wil@@XZ; SchemaRegistryImpl::GetAppExtensionSchemaProvider(void)
0x180053671  mov     rdx, [rax]
0x180053674  lea     rcx, [rsp+4D0h+ppv]
0x180053679  call    ??4?$com_ptr_t@UICloudStoreSchemaProvider@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUICloudStoreSchemaProvider@@@Z; wil::com_ptr_t<ICloudStoreSchemaProvider,wil::err_exception_policy>::operator=(ICloudStoreSchemaProvider *)
0x18005367e  cmp     [rsp+4D0h+ppv], r15
0x180053683  jnz     loc_18005393D
0x180053689  mov     r10d, 7FFFFFFEh
0x18005368f  mov     eax, r10d
0x180053692  lea     rcx, pszPathIn; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180053699  mov     ebx, 104h
0x18005369e  mov     edx, ebx
0x1800536a0  lea     r8, [rbp+3D0h+SubKey]
0x1800536a4  test    rax, rax
0x1800536a7  jz      short loc_1800536C8
0x1800536a9  movzx   r9d, word ptr [rcx]
0x1800536ad  test    r9w, r9w
0x1800536b1  jz      short loc_1800536C8
0x1800536b3  add     rcx, 2
0x1800536b7  mov     [r8], r9w
0x1800536bb  add     r8, 2
0x1800536bf  dec     rax
0x1800536c2  sub     rdx, 1
0x1800536c6  jnz     short loc_1800536A4
0x1800536c8  mov     rax, rdx
0x1800536cb  neg     rax
0x1800536ce  sbb     r9d, r9d
0x1800536d1  not     r9d
0x1800536d4  mov     r11d, 8007007Ah
0x1800536da  and     r9d, r11d; char *
0x1800536dd  lea     rcx, [r8-2]
0x1800536e1  test    rdx, rdx
0x1800536e4  cmovnz  rcx, r8
0x1800536e8  mov     [rcx], r15w
0x1800536ec  mov     rcx, [rbp+3D8h]; this
0x1800536f3  jnz     short loc_180053707
0x1800536f5  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800536fc  mov     edx, 1B1h; void *
0x180053701  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053707  mov     rdx, rbx
0x18005370a  lea     rax, [rbp+3D0h+SubKey]
0x18005370e  cmp     [rax], r15w
0x180053712  jz      short loc_18005371E
0x180053714  add     rax, 2
0x180053718  sub     rdx, 1
0x18005371c  jnz     short loc_18005370E
0x18005371e  mov     rax, rdx
0x180053721  neg     rax
0x180053724  sbb     r9d, r9d
0x180053727  not     r9d
0x18005372a  and     r9d, 80070057h
0x180053731  mov     rax, rdx
0x180053734  mov     rcx, rbx
0x180053737  sub     rcx, rdx
0x18005373a  neg     rax
0x18005373d  sbb     r8, r8
0x180053740  and     r8, rcx
0x180053743  test    rdx, rdx
0x180053746  jz      short loc_18005379E
0x180053748  lea     rcx, aSchema; "\\Schema\\"
0x18005374f  mov     rdx, rbx
0x180053752  sub     rdx, r8
0x180053755  lea     rax, [rbp+3D0h+SubKey]
0x180053759  lea     rax, [rax+r8*2]
0x18005375d  jz      short loc_180053783
0x18005375f  test    r10, r10
0x180053762  jz      short loc_180053783
0x180053764  movzx   r8d, word ptr [rcx]
0x180053768  test    r8w, r8w
0x18005376c  jz      short loc_180053783
0x18005376e  add     rcx, 2
0x180053772  mov     [rax], r8w
0x180053776  add     rax, 2
0x18005377a  dec     r10
0x18005377d  sub     rdx, 1
0x180053781  jnz     short loc_18005375F
0x180053783  lea     rcx, [rax-2]
0x180053787  test    rdx, rdx
0x18005378a  cmovnz  rcx, rax
0x18005378e  mov     [rcx], r15w
0x180053792  neg     rdx
0x180053795  sbb     r9d, r9d
0x180053798  not     r9d
0x18005379b  and     r9d, r11d; char *
0x18005379e  mov     rcx, [rbp+3D8h]; this
0x1800537a5  test    r9d, r9d
0x1800537a8  jns     short loc_1800537BC
0x1800537aa  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800537b1  mov     edx, 1B2h; void *
0x1800537b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800537bc  mov     r8, r14; unsigned __int16 *
0x1800537bf  mov     rdx, rbx; unsigned __int64
0x1800537c2  lea     rcx, [rbp+3D0h+SubKey]; unsigned __int16 *
0x1800537c6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800537cb  mov     rcx, [rbp+3D8h]; this
0x1800537d2  test    eax, eax
0x1800537d4  jns     short loc_1800537EB
0x1800537d6  mov     r9d, eax; char *
0x1800537d9  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800537e0  mov     edx, 1B3h; void *
0x1800537e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800537eb  mov     [rsp+4D0h+var_488], 208h
0x1800537f3  lea     rax, [rsp+4D0h+var_488]
0x1800537f8  mov     [rsp+4D0h+pcbData], rax; pcbData
0x1800537fd  lea     rax, [rbp+3D0h+sz]
0x180053804  mov     [rsp+4D0h+pvData], rax; pvData
0x180053809  mov     [rsp+4D0h+pdwType], r15; pdwType
0x18005380e  mov     r9d, 2; dwFlags
0x180053814  lea     r8, aProvider; "Provider"
0x18005381b  lea     rdx, [rbp+3D0h+SubKey]; lpSubKey
0x18005381f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180053826  call    cs:__imp_RegGetValueW
0x18005382c  test    eax, eax
0x18005382e  jz      short loc_180053844
0x180053830  mov     [rbp+3D0h+sz], r15w
0x180053838  jle     short loc_180053844
0x18005383a  movzx   eax, ax
0x18005383d  or      eax, 80070000h
0x180053842  test    eax, eax
0x180053844  jns     short loc_18005387B
0x180053846  mov     dword ptr [rsp+4D0h+pvData], ebx; unsigned int
0x18005384a  lea     rax, [rbp+3D0h+sz]
0x180053851  mov     [rsp+4D0h+pdwType], rax; int
0x180053856  lea     r8, aProvider; "Provider"
0x18005385d  lea     rdx, [rbp+3D0h+SubKey]; unsigned __int16 *
0x180053861  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180053868  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x18005386d  test    eax, eax
0x18005386f  js      short loc_1800538B5
0x180053871  mov     dword ptr [rsi+110h], 1
0x18005387b  xorps   xmm0, xmm0
0x18005387e  movups  xmmword ptr [rsp+4D0h+pclsid.Data1], xmm0
0x180053883  lea     rdx, [rsp+4D0h+pclsid]; pclsid
0x180053888  lea     rcx, [rbp+3D0h+sz]; lpsz
0x18005388f  call    cs:__imp_CLSIDFromString
0x180053895  mov     rcx, [rbp+3D8h]; this
0x18005389c  test    eax, eax
0x18005389e  jns     short loc_1800538DD
0x1800538a0  mov     r9d, eax; char *
0x1800538a3  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800538aa  mov     edx, 1C5h; void *
0x1800538af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800538b5  mov     [rdi], r15
0x1800538b8  mov     rcx, [rsp+4D0h+pv]; pv
0x1800538bd  mov     [rsp+4D0h+pv], r15
0x1800538c2  test    rcx, rcx
0x1800538c5  jz      short loc_1800538CE
0x1800538c7  call    cs:__imp_CoTaskMemFree
0x1800538cd  nop
0x1800538ce  lea     rcx, [rsp+4D0h+ppv]
0x1800538d3  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800538d8  jmp     loc_180053A30
0x1800538dd  mov     rcx, [rsp+4D0h+ppv]
0x1800538e2  mov     [rsp+4D0h+ppv], r15
0x1800538e7  test    rcx, rcx
0x1800538ea  jz      short loc_1800538F9
0x1800538ec  mov     rax, [rcx]
0x1800538ef  mov     rax, [rax+10h]
0x1800538f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538f8  nop
0x1800538f9  lea     rax, [rsp+4D0h+ppv]
0x1800538fe  mov     [rsp+4D0h+pdwType], rax; int
0x180053903  lea     r9, _GUID_efe84c27_afa6_485d_a70a_aa2ab5cb6c67; riid
0x18005390a  xor     edx, edx; pUnkOuter
0x18005390c  mov     r8d, 401h; dwClsContext
0x180053912  lea     rcx, [rsp+4D0h+pclsid]; rclsid
0x180053917  call    cs:__imp_CoCreateInstance
0x18005391d  mov     rcx, [rbp+3D8h]; this
0x180053924  test    eax, eax
0x180053926  jns     short loc_18005393D
0x180053928  mov     r9d, eax; char *
0x18005392b  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x180053932  mov     edx, 1C6h; void *
0x180053937  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005393d  mov     rcx, [rsp+4D0h+pv]; pv
0x180053942  mov     [rsp+4D0h+pv], r15
0x180053947  test    rcx, rcx
0x18005394a  jz      loc_180053A28
0x180053950  call    cs:__imp_CoTaskMemFree
0x180053956  jmp     loc_180053A28
0x18005395b  mov     qword ptr [rsp+4D0h+var_488], r15
0x180053960  lea     rbx, [rcx+38h]
0x180053964  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers> `wil::Feature<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetImpl(void)'::`2'::impl
0x18005396b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::__private_IsEnabled(void)
0x180053970  xor     edx, edx
0x180053972  lea     rcx, [rsp+4D0h+var_488]
0x180053977  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005397c  cmp     qword ptr [rbx+18h], 7
0x180053981  jbe     short loc_180053986
0x180053983  mov     rbx, [rbx]
0x180053986  lea     r8, [rsp+4D0h+var_488]; unsigned __int16 *
0x18005398b  lea     rdx, aSchema_0; "Schema"
0x180053992  mov     rcx, rbx; this
0x180053995  call    ?GetRegistryRootKey@CloudStoreUtilities@@YAJPEBG0PEAPEAUHKEY__@@@Z; CloudStoreUtilities::GetRegistryRootKey(ushort const *,ushort const *,HKEY__ * *)
0x18005399a  cmp     eax, 80070002h
0x18005399f  jnz     short loc_1800539B3
0x1800539a1  mov     [rdi], r15
0x1800539a4  lea     rcx, [rsp+4D0h+var_488]
0x1800539a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800539ae  jmp     loc_1800538CE
0x1800539b3  mov     rcx, [rbp+3D8h]; this
0x1800539ba  test    eax, eax
0x1800539bc  jns     short loc_1800539D3
0x1800539be  mov     r9d, eax; char *
0x1800539c1  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800539c8  mov     edx, 19Ah; void *
0x1800539cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800539d3  mov     rcx, rsi; this
0x1800539d6  call    ?EnsureRuntimeSchemaWatcher@SchemaRegistryImpl@@AEAAJXZ; SchemaRegistryImpl::EnsureRuntimeSchemaWatcher(void)
0x1800539db  lea     rcx, [rsp+4D0h+ppv]
0x1800539e0  call    ?reset@?$com_ptr_t@UICloudStoreSchemaProvider@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<ICloudStoreSchemaProvider,wil::err_exception_policy>::reset(void)
0x1800539e5  lea     rdx, [rsp+4D0h+ppv]
0x1800539ea  lea     rcx, [rsp+4D0h+var_488]
0x1800539ef  call    ?CloudStoreSchemaProvider_CreateInstance@@YAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAPEAUICloudStoreSchemaProvider@@@Z; CloudStoreSchemaProvider_CreateInstance(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,ICloudStoreSchemaProvider * *)
0x1800539f4  mov     rcx, [rbp+3D8h]; this
0x1800539fb  test    eax, eax
0x1800539fd  jns     short loc_180053A14
0x1800539ff  mov     r9d, eax; char *
0x180053a02  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x180053a09  mov     edx, 19Dh; void *
0x180053a0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053a14  mov     dword ptr [rsi+110h], 2
0x180053a1e  lea     rcx, [rsp+4D0h+var_488]
0x180053a23  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180053a28  mov     rax, [rsp+4D0h+ppv]
0x180053a2d  mov     [rdi], rax
0x180053a30  mov     rax, rdi
0x180053a33  mov     rcx, [rbp+3D0h+var_30]
0x180053a3a  xor     rcx, rsp; StackCookie
0x180053a3d  call    __security_check_cookie
0x180053a42  mov     rbx, [rsp+4D0h+arg_18]
0x180053a4a  add     rsp, 4B0h
0x180053a51  pop     r15
0x180053a53  pop     r14
0x180053a55  pop     rdi
0x180053a56  pop     rsi
  ... truncated ...
```
