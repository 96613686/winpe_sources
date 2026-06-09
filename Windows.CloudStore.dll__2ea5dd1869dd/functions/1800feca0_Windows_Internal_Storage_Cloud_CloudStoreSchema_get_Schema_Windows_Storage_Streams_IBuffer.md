# Windows::Internal::Storage::Cloud::CloudStoreSchema::get_Schema(Windows::Storage::Streams::IBuffer * *)

- ea: `0x1800feca0`
- end: `0x1800ff096`
- name: `?get_Schema@CloudStoreSchema@Cloud@Storage@Internal@Windows@@UEAAJPEAPEAUIBuffer@Streams@35@@Z`
- size: `1014`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::CloudStoreSchema *__hidden this, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f4b4`
- `0x180010688`
- `0x180024020`
- `0x18003e670`
- `0x18003e904`
- `0x18003f6c4`
- `0x18005ac7c`
- `0x18007e0c8`
- `0x18007e75c`
- `0x180091b04`
- `0x1800c8458`
- `0x1800feca0`
- `0x1800ff298`
- `0x1801201a0`
- `0x1801c8984`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fedac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800feed8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fedac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800feed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fee8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fef20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fefb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fefff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff02e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fee8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fef20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fef6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fefb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fefff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff02e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStoreSchema::get_Schema(
        Windows::Internal::Storage::Cloud::CloudStoreSchema *this,
        struct Windows::Storage::Streams::IBuffer **a2)
{
  const unsigned __int16 *v4; // rdx
  unsigned __int64 v5; // r9
  int TypeNameSubKey; // eax
  unsigned int v7; // edi
  HKEY *v9; // r9
  int RegistryRootKey; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rcx
  int v15; // ebx
  unsigned int v16; // r10d
  void *v17; // rcx
  unsigned int v18; // eax
  void *v19; // rcx
  LPVOID v20; // r8
  int v21; // eax
  void *v22; // rcx
  struct Windows::Storage::Streams::IBuffer *v23; // rax
  void *v24; // rcx
  void *v25; // rcx
  LPBYTE lpData; // [rsp+20h] [rbp-298h]
  LPVOID pv; // [rsp+30h] [rbp-288h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-280h] BYREF
  struct _SECURITY_ATTRIBUTES hKey; // [rsp+40h] [rbp-278h] BYREF
  unsigned __int64 v30; // [rsp+58h] [rbp-260h] BYREF
  LPVOID *p_pv; // [rsp+60h] [rbp-258h] BYREF
  void *v32; // [rsp+68h] [rbp-250h] BYREF
  char v33; // [rsp+70h] [rbp-248h]
  unsigned __int16 v34[264]; // [rsp+80h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  *a2 = 0;
  EffectiveUserContext::Impersonate((void ***)this + 9, &hKey.lpSecurityDescriptor);
  TypeNameSubKey = Windows::Internal::Storage::Cloud::CloudStoreSchema::GetTypeNameSubKey(this, v4, v34, v5);
  v7 = TypeNameSubKey;
  if ( TypeNameSubKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\cloudstoreschema.cpp",
      (const char *)(unsigned int)TypeNameSubKey,
      (int)lpData);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hKey.lpSecurityDescriptor);
    return v7;
  }
  *(_QWORD *)&hKey.nLength = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  RegistryRootKey = CloudStoreUtilities::GetRegistryRootKey(*((CloudStoreUtilities **)this + 14), v34, &hKey, v9);
  v11 = RegistryRootKey;
  if ( RegistryRootKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\cloudstoreschema.cpp",
      (const char *)(unsigned int)RegistryRootKey,
      (int)lpData);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hKey.lpSecurityDescriptor);
    return v11;
  }
  cbData = 0;
  v12 = RegQueryValueExW(*(HKEY *)&hKey.nLength, L"Schema", 0, 0, 0, &cbData);
  if ( v12 == 2 || v12 == 1018 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hKey.lpSecurityDescriptor);
    return 2147942402LL;
  }
  else
  {
    if ( v12 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x46,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\cloudstoreschema.cpp",
              (const char *)v12,
              (unsigned int)lpData);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hKey.lpSecurityDescriptor);
      return v13;
    }
    pv = 0;
    p_pv = &pv;
    v33 = 1;
    v32 = 0;
    v30 = 0;
    v15 = ULongLongMult(cbData, 1u, &v30);
    if ( v15 >= 0 )
      v15 = CTCoAllocPolicy::Alloc(v14, v16, v30, &v32);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\cloudstoreschema.cpp",
        (const char *)(unsigned int)v15,
        (int)lpData);
      v17 = pv;
      pv = 0;
      if ( v17 )
        CoTaskMemFree(v17);
LABEL_24:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hKey.lpSecurityDescriptor);
      return (unsigned int)v15;
    }
    v18 = RegQueryValueExW(*(HKEY *)&hKey.nLength, L"Schema", 0, 0, (LPBYTE)pv, &cbData);
    if ( v18 == 2 || v18 == 1018 )
    {
      v25 = pv;
      pv = 0;
      if ( v25 )
        CoTaskMemFree(v25);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hKey.lpSecurityDescriptor);
      return 2147942402LL;
    }
    else
    {
      if ( v18 )
      {
        v15 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x4B,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\cloudstoreschema.cpp",
                (const char *)v18,
                (unsigned int)lpData);
        v19 = pv;
        pv = 0;
        if ( v19 )
          CoTaskMemFree(v19);
        goto LABEL_24;
      }
      *(_QWORD *)&hKey.bInheritHandle = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hKey.bInheritHandle);
      v20 = pv;
      pv = 0;
      v21 = Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(
              cbData,
              cbData,
              (__int64)v20,
              (void (__fastcall *)(__int64))CoTaskMemFree,
              &hKey.bInheritHandle);
      v15 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\cloudstoreschema.cpp",
          (const char *)(unsigned int)v21,
          (int)lpData);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hKey.bInheritHandle);
        v22 = pv;
        pv = 0;
        if ( v22 )
          CoTaskMemFree(v22);
        goto LABEL_24;
      }
      v23 = *(struct Windows::Storage::Streams::IBuffer **)&hKey.bInheritHandle;
      *(_QWORD *)&hKey.bInheritHandle = 0;
      *a2 = v23;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hKey.bInheritHandle);
      v24 = pv;
      pv = 0;
      if ( v24 )
        CoTaskMemFree(v24);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hKey.lpSecurityDescriptor);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800feca0  mov     [rsp+arg_10], rbx
0x1800feca5  push    rsi
0x1800feca6  push    rdi
0x1800feca7  push    r14
0x1800feca9  sub     rsp, 2A0h
0x1800fecb0  mov     rax, cs:__security_cookie
0x1800fecb7  xor     rax, rsp
0x1800fecba  mov     [rsp+2B8h+var_28], rax
0x1800fecc2  mov     rsi, rdx
0x1800fecc5  mov     rbx, rcx
0x1800fecc8  xor     r14d, r14d
0x1800feccb  mov     [rdx], r14
0x1800fecce  add     rcx, 48h ; 'H'
0x1800fecd2  lea     rdx, [rsp+2B8h+var_270]
0x1800fecd7  call    ?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; EffectiveUserContext::Impersonate(void)
0x1800fecdc  nop
0x1800fecdd  lea     r8, [rsp+2B8h+var_238]; unsigned __int16 *
0x1800fece5  mov     rcx, rbx; this
0x1800fece8  call    ?GetTypeNameSubKey@CloudStoreSchema@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAG_K@Z; Windows::Internal::Storage::Cloud::CloudStoreSchema::GetTypeNameSubKey(ushort const *,ushort *,unsigned __int64)
0x1800feced  mov     edi, eax
0x1800fecef  test    eax, eax
0x1800fecf1  jns     short loc_1800FED20
0x1800fecf3  mov     rcx, [rsp+2B8h]; this
0x1800fecfb  mov     r9d, eax; char *
0x1800fecfe  lea     r8, aOnecoreuapShel_49; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800fed05  lea     edx, [r14+40h]; void *
0x1800fed09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fed0e  nop
0x1800fed0f  lea     rcx, [rsp+2B8h+var_270]
0x1800fed14  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800fed19  mov     eax, edi
0x1800fed1b  jmp     loc_1800FF071
0x1800fed20  mov     [rsp+2B8h+hKey], r14
0x1800fed25  xor     edx, edx
0x1800fed27  lea     rcx, [rsp+2B8h+hKey]
0x1800fed2c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800fed31  lea     r8, [rsp+2B8h+hKey]; unsigned __int16 *
0x1800fed36  lea     rdx, [rsp+2B8h+var_238]; unsigned __int16 *
0x1800fed3e  mov     rcx, [rbx+70h]; this
0x1800fed42  call    ?GetRegistryRootKey@CloudStoreUtilities@@YAJPEBG0PEAPEAUHKEY__@@@Z; CloudStoreUtilities::GetRegistryRootKey(ushort const *,ushort const *,HKEY__ * *)
0x1800fed47  mov     ebx, eax
0x1800fed49  test    eax, eax
0x1800fed4b  jns     short loc_1800FED86
0x1800fed4d  mov     rcx, [rsp+2B8h]; this
0x1800fed55  mov     r9d, eax; char *
0x1800fed58  lea     r8, aOnecoreuapShel_49; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800fed5f  mov     edx, 43h ; 'C'; void *
0x1800fed64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fed69  nop
0x1800fed6a  lea     rcx, [rsp+2B8h+hKey]
0x1800fed6f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fed74  nop
0x1800fed75  lea     rcx, [rsp+2B8h+var_270]
0x1800fed7a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800fed7f  mov     eax, ebx
0x1800fed81  jmp     loc_1800FF071
0x1800fed86  mov     [rsp+2B8h+cbData], r14d
0x1800fed8b  lea     rax, [rsp+2B8h+cbData]
0x1800fed90  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x1800fed95  mov     [rsp+2B8h+lpData], r14; int
0x1800fed9a  xor     r9d, r9d; lpType
0x1800fed9d  xor     r8d, r8d; lpReserved
0x1800feda0  lea     rdx, aSchema_0; "Schema"
0x1800feda7  mov     rcx, [rsp+2B8h+hKey]; hKey
0x1800fedac  call    cs:__imp_RegQueryValueExW
0x1800fedb2  cmp     eax, 2
0x1800fedb5  jz      loc_1800FF051
0x1800fedbb  mov     edi, 3FAh
0x1800fedc0  cmp     eax, edi
0x1800fedc2  jz      loc_1800FF051
0x1800fedc8  test    eax, eax
0x1800fedca  jz      short loc_1800FEE06
0x1800fedcc  mov     rcx, [rsp+2B8h]; this
0x1800fedd4  mov     r9d, eax; char *
0x1800fedd7  lea     r8, aOnecoreuapShel_49; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800fedde  mov     edx, 46h ; 'F'; void *
0x1800fede3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800fede8  mov     ebx, eax
0x1800fedea  lea     rcx, [rsp+2B8h+hKey]
0x1800fedef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fedf4  nop
0x1800fedf5  lea     rcx, [rsp+2B8h+var_270]
0x1800fedfa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800fedff  mov     eax, ebx
0x1800fee01  jmp     loc_1800FF071
0x1800fee06  mov     [rsp+2B8h+pv], r14
0x1800fee0b  lea     rax, [rsp+2B8h+pv]
0x1800fee10  mov     [rsp+2B8h+var_258], rax
0x1800fee15  mov     r10d, 1
0x1800fee1b  mov     [rsp+2B8h+var_248], r10b
0x1800fee20  mov     [rsp+2B8h+var_250], r14
0x1800fee25  mov     [rsp+2B8h+var_260], r14
0x1800fee2a  mov     ecx, [rsp+2B8h+cbData]; unsigned __int64
0x1800fee2e  lea     r8, [rsp+2B8h+var_260]; unsigned __int64 *
0x1800fee33  mov     edx, r10d; unsigned __int64
0x1800fee36  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800fee3b  mov     ebx, eax
0x1800fee3d  test    eax, eax
0x1800fee3f  js      short loc_1800FEE55
0x1800fee41  lea     r9, [rsp+2B8h+var_250]; void **
0x1800fee46  mov     r8, [rsp+2B8h+var_260]; unsigned __int64
0x1800fee4b  mov     edx, r10d; unsigned int
0x1800fee4e  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800fee53  mov     ebx, eax
0x1800fee55  lea     rcx, [rsp+2B8h+var_258]
0x1800fee5a  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800fee5f  test    ebx, ebx
0x1800fee61  jns     short loc_1800FEEB2
0x1800fee63  mov     rcx, [rsp+2B8h]; this
0x1800fee6b  mov     r9d, ebx; char *
0x1800fee6e  lea     r8, aOnecoreuapShel_49; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800fee75  mov     edx, 49h ; 'I'; void *
0x1800fee7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fee7f  nop
0x1800fee80  mov     rcx, [rsp+2B8h+pv]; pv
0x1800fee85  mov     [rsp+2B8h+pv], r14
0x1800fee8a  test    rcx, rcx
0x1800fee8d  jz      short loc_1800FEE96
0x1800fee8f  call    cs:__imp_CoTaskMemFree
0x1800fee95  nop
0x1800fee96  lea     rcx, [rsp+2B8h+hKey]
0x1800fee9b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800feea0  nop
0x1800feea1  lea     rcx, [rsp+2B8h+var_270]
0x1800feea6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800feeab  mov     eax, ebx
0x1800feead  jmp     loc_1800FF071
0x1800feeb2  mov     rax, [rsp+2B8h+pv]
0x1800feeb7  lea     rcx, [rsp+2B8h+cbData]
0x1800feebc  mov     [rsp+2B8h+lpcbData], rcx; lpcbData
0x1800feec1  mov     [rsp+2B8h+lpData], rax; unsigned int
0x1800feec6  xor     r9d, r9d; lpType
0x1800feec9  xor     r8d, r8d; lpReserved
0x1800feecc  lea     rdx, aSchema_0; "Schema"
0x1800feed3  mov     rcx, [rsp+2B8h+hKey]; hKey
0x1800feed8  call    cs:__imp_RegQueryValueExW
0x1800feede  cmp     eax, 2
0x1800feee1  jz      loc_1800FF01F
0x1800feee7  cmp     eax, edi
0x1800feee9  jz      loc_1800FF01F
0x1800feeef  test    eax, eax
0x1800feef1  jz      short loc_1800FEF43
0x1800feef3  mov     rcx, [rsp+2B8h]; this
0x1800feefb  mov     r9d, eax; char *
0x1800feefe  lea     r8, aOnecoreuapShel_49; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800fef05  mov     edx, 4Bh ; 'K'; void *
0x1800fef0a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800fef0f  mov     ebx, eax
0x1800fef11  mov     rcx, [rsp+2B8h+pv]; pv
0x1800fef16  mov     [rsp+2B8h+pv], r14
0x1800fef1b  test    rcx, rcx
0x1800fef1e  jz      short loc_1800FEF27
0x1800fef20  call    cs:__imp_CoTaskMemFree
0x1800fef26  nop
0x1800fef27  lea     rcx, [rsp+2B8h+hKey]
0x1800fef2c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fef31  nop
0x1800fef32  lea     rcx, [rsp+2B8h+var_270]
0x1800fef37  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800fef3c  mov     eax, ebx
0x1800fef3e  jmp     loc_1800FF071
0x1800fef43  mov     qword ptr [rsp+2B8h+var_268], r14
0x1800fef48  lea     rcx, [rsp+2B8h+var_268]
0x1800fef4d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fef52  mov     r8, [rsp+2B8h+pv]
0x1800fef57  mov     [rsp+2B8h+pv], r14
0x1800fef5c  mov     ecx, [rsp+2B8h+cbData]
0x1800fef60  lea     rax, [rsp+2B8h+var_268]
0x1800fef65  mov     [rsp+2B8h+lpData], rax; int
0x1800fef6a  mov     r9, cs:__imp_CoTaskMemFree
0x1800fef71  mov     edx, ecx
0x1800fef73  call    ??$MakeCBuffer@P6AXPEAX@Z@Streams@Storage@Windows@@YAJIIPEAEP6AXPEAX@ZPEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(uint,uint,uchar *,void (*)(void *),Windows::Storage::Streams::IBuffer * *)
0x1800fef78  mov     ebx, eax
0x1800fef7a  test    eax, eax
0x1800fef7c  jns     short loc_1800FEFD8
0x1800fef7e  mov     rcx, [rsp+2B8h]; this
0x1800fef86  mov     r9d, eax; char *
0x1800fef89  lea     r8, aOnecoreuapShel_49; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800fef90  mov     edx, 4Eh ; 'N'; void *
0x1800fef95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fef9a  nop
0x1800fef9b  lea     rcx, [rsp+2B8h+var_268]
0x1800fefa0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fefa5  nop
0x1800fefa6  mov     rcx, [rsp+2B8h+pv]; pv
0x1800fefab  mov     [rsp+2B8h+pv], r14
0x1800fefb0  test    rcx, rcx
0x1800fefb3  jz      short loc_1800FEFBC
0x1800fefb5  call    cs:__imp_CoTaskMemFree
0x1800fefbb  nop
0x1800fefbc  lea     rcx, [rsp+2B8h+hKey]
0x1800fefc1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fefc6  nop
0x1800fefc7  lea     rcx, [rsp+2B8h+var_270]
0x1800fefcc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800fefd1  mov     eax, ebx
0x1800fefd3  jmp     loc_1800FF071
0x1800fefd8  mov     rax, qword ptr [rsp+2B8h+var_268]
0x1800fefdd  mov     qword ptr [rsp+2B8h+var_268], r14
0x1800fefe2  mov     [rsi], rax
0x1800fefe5  lea     rcx, [rsp+2B8h+var_268]
0x1800fefea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fefef  nop
0x1800feff0  mov     rcx, [rsp+2B8h+pv]; pv
0x1800feff5  mov     [rsp+2B8h+pv], r14
0x1800feffa  test    rcx, rcx
0x1800feffd  jz      short loc_1800FF006
0x1800fefff  call    cs:__imp_CoTaskMemFree
0x1800ff005  nop
0x1800ff006  lea     rcx, [rsp+2B8h+hKey]
0x1800ff00b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ff010  nop
0x1800ff011  lea     rcx, [rsp+2B8h+var_270]
0x1800ff016  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800ff01b  xor     eax, eax
0x1800ff01d  jmp     short loc_1800FF071
0x1800ff01f  mov     rcx, [rsp+2B8h+pv]; pv
0x1800ff024  mov     [rsp+2B8h+pv], r14
0x1800ff029  test    rcx, rcx
0x1800ff02c  jz      short loc_1800FF035
0x1800ff02e  call    cs:__imp_CoTaskMemFree
0x1800ff034  nop
0x1800ff035  lea     rcx, [rsp+2B8h+hKey]
0x1800ff03a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ff03f  nop
0x1800ff040  lea     rcx, [rsp+2B8h+var_270]
0x1800ff045  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800ff04a  mov     eax, 80070002h
0x1800ff04f  jmp     short loc_1800FF071
0x1800ff051  lea     rcx, [rsp+2B8h+hKey]
0x1800ff056  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ff05b  nop
0x1800ff05c  lea     rcx, [rsp+2B8h+var_270]
0x1800ff061  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800ff066  mov     eax, 80070002h
0x1800ff06b  jmp     short loc_1800FF071
0x1800ff06d  mov     eax, [rsp+2B8h+cbData]
0x1800ff071  mov     rcx, [rsp+2B8h+var_28]
0x1800ff079  xor     rcx, rsp; StackCookie
0x1800ff07c  call    __security_check_cookie
0x1800ff081  mov     rbx, [rsp+2B8h+arg_10]
0x1800ff089  add     rsp, 2A0h
0x1800ff090  pop     r14
0x1800ff092  pop     rdi
0x1800ff093  pop     rsi
0x1800ff094  retn
```
