# Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStoreCache(void)

- ea: `0x18005f34c`
- end: `0x18005f73f`
- name: `?EnsureCloudStoreCache@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ`
- size: `1011`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, __int64, __int64, HKEY *)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800393b4`
- `0x18005d938`
- `0x1800608ac`
- `0x18006635c`
- `0x18016cb7c`

## callees

- `0x18000f4b4`
- `0x18003e904`
- `0x18003f6c4`
- `0x180047904`
- `0x18005f34c`
- `0x180062040`
- `0x180094cc0`
- `0x180096384`
- `0x18009fb70`
- `0x1800b3714`
- `0x1800c8458`
- `0x1801236bc`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f57c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f5ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f61e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f675`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f57c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f5ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f61e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f675`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f4a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f4a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005f4f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005f4f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f54b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f54b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f682`

## string_xrefs

- `0x18005f59c`: `onecoreuap\shell\cloudstore\store\cache\src\registrystorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStoreCache(
        RTL_SRWLOCK *this,
        __int64 a2,
        __int64 a3,
        HKEY *a4)
{
  __int64 result; // rax
  RTL_SRWLOCK *v6; // rbx
  CloudStoreUtilities *Ptr; // rcx
  int RegistryRootKey; // eax
  unsigned int v9; // esi
  void *v10; // rax
  Windows::Internal::Storage::Cloud *v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned __int16 **v13; // r9
  int FileStorageRootPath; // ebx
  struct Windows::Internal::Storage::Cloud::IBulkLocalStorage **v15; // r8
  int Instance; // eax
  unsigned int v17; // ebx
  struct Windows::Internal::Storage::Cloud::ICloudStoreCache **v18; // r9
  int v19; // eax
  unsigned int v20; // ebx
  void *v21; // rbx
  PVOID v22; // rcx
  __int64 v23; // rcx
  LPVOID lpSecurityDescriptor; // rcx
  Windows::Internal::Storage::Cloud *v25; // rcx
  Windows::Internal::Storage::Cloud *v26; // rcx
  Windows::Internal::Storage::Cloud *v27; // rcx
  LPVOID pv; // [rsp+20h] [rbp-48h] BYREF
  LPVOID *p_pv; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int16 v30[4]; // [rsp+30h] [rbp-38h] BYREF
  char v31; // [rsp+38h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  Windows::Internal::Storage::Cloud *v33; // [rsp+70h] [rbp+8h] BYREF
  struct _SECURITY_ATTRIBUTES hKey; // [rsp+78h] [rbp+10h] BYREF

  try
  {
    if ( this[62].Ptr )
      return 0;
    *(_QWORD *)&hKey.nLength = 0;
    v6 = this + 21;
    if ( this[24].Ptr <= (PVOID)7 )
      Ptr = (CloudStoreUtilities *)&this[21];
    else
      Ptr = (CloudStoreUtilities *)v6->Ptr;
    RegistryRootKey = CloudStoreUtilities::GetRegistryRootKey(Ptr, 0, &hKey, a4);
    v9 = RegistryRootKey;
    if ( RegistryRootKey < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1185,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)RegistryRootKey,
        (int)pv);
      if ( *(_QWORD *)&hKey.nLength )
        RegCloseKey(*(HKEY *)&hKey.nLength);
      result = v9;
    }
    else
    {
      v33 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      v33 = 0;
      v10 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      if ( v10
        && (v11 = (Windows::Internal::Storage::Cloud *)Windows::Internal::Storage::Cloud::RegistryStorage::RegistryStorage(
                                                         v10,
                                                         &hKey)) != 0 )
      {
        v33 = v11;
        pv = 0;
        p_pv = &pv;
        *(_QWORD *)v30 = 0;
        v31 = 1;
        if ( v6[3].Ptr > (PVOID)7 )
          v6 = (RTL_SRWLOCK *)v6->Ptr;
        FileStorageRootPath = CloudStoreUtilities::GetFileStorageRootPath((CloudStoreUtilities *)v6, v12, v30, v13);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
        if ( FileStorageRootPath < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x118B,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)FileStorageRootPath,
            (int)pv);
          if ( pv )
            CoTaskMemFree(pv);
          v27 = v33;
          if ( v33 )
          {
            v33 = 0;
            (*(void (__fastcall **)(Windows::Internal::Storage::Cloud *))(*(_QWORD *)v27 + 16LL))(v27);
          }
          if ( *(_QWORD *)&hKey.nLength )
            RegCloseKey(*(HKEY *)&hKey.nLength);
          result = (unsigned int)FileStorageRootPath;
        }
        else
        {
          hKey.lpSecurityDescriptor = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hKey.lpSecurityDescriptor);
          Instance = Windows::Internal::Storage::Cloud::FileStorage_CreateInstance(
                       (Windows::Internal::Storage::Cloud *)pv,
                       (const unsigned __int16 *)&hKey.lpSecurityDescriptor,
                       v15);
          v17 = Instance;
          if ( Instance < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x118E,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              (const char *)(unsigned int)Instance,
              (int)pv);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hKey.lpSecurityDescriptor);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            result = v17;
          }
          else
          {
            *(_QWORD *)&hKey.bInheritHandle = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hKey.bInheritHandle);
            v19 = Windows::Internal::Storage::Cloud::CloudStoreCache_CreateInstance(
                    v33,
                    (struct Windows::Internal::Storage::Cloud::IDefaultLocalStorage *)hKey.lpSecurityDescriptor,
                    (struct Windows::Internal::Storage::Cloud::IBulkLocalStorage *)&hKey.bInheritHandle,
                    v18);
            v20 = v19;
            if ( v19 >= 0 )
            {
              AcquireSRWLockExclusive(this + 42);
              if ( !this[62].Ptr )
              {
                v21 = *(void **)&hKey.bInheritHandle;
                if ( *(_QWORD *)&hKey.bInheritHandle )
                {
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&hKey.bInheritHandle + 8LL))(*(_QWORD *)&hKey.bInheritHandle);
                  v22 = this[62].Ptr;
                  this[62].Ptr = v21;
                  if ( v22 )
                    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v22 + 16LL))(v22);
                }
              }
              if ( this != (RTL_SRWLOCK *)-336LL )
                ReleaseSRWLockExclusive(this + 42);
              v23 = *(_QWORD *)&hKey.bInheritHandle;
              if ( *(_QWORD *)&hKey.bInheritHandle )
              {
                *(_QWORD *)&hKey.bInheritHandle = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              }
              lpSecurityDescriptor = hKey.lpSecurityDescriptor;
              if ( hKey.lpSecurityDescriptor )
              {
                hKey.lpSecurityDescriptor = 0;
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpSecurityDescriptor + 16LL))(lpSecurityDescriptor);
              }
              if ( pv )
                CoTaskMemFree(pv);
              v25 = v33;
              if ( v33 )
              {
                v33 = 0;
                (*(void (__fastcall **)(Windows::Internal::Storage::Cloud *))(*(_QWORD *)v25 + 16LL))(v25);
              }
              if ( *(_QWORD *)&hKey.nLength )
                RegCloseKey(*(HKEY *)&hKey.nLength);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1191,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              (const char *)(unsigned int)v19,
              (int)pv);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hKey.bInheritHandle);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hKey.lpSecurityDescriptor);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            result = v20;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\registrystorage.cpp",
          (const char *)0x8007000ELL,
          (int)pv);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1188,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)0x8007000ELL,
          (int)pv);
        v26 = v33;
        if ( v33 )
        {
          v33 = 0;
          (*(void (__fastcall **)(Windows::Internal::Storage::Cloud *))(*(_QWORD *)v26 + 16LL))(v26);
        }
        if ( *(_QWORD *)&hKey.nLength )
          RegCloseKey(*(HKEY *)&hKey.nLength);
        result = 2147942414LL;
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v33) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x119B,
                     (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                     (const char *)a4);
    return (unsigned int)v33;
  }
  return result;
}

```

## disassembly

```asm
0x18005f34c  push    rbx
0x18005f34e  push    rsi
0x18005f34f  push    rdi
0x18005f350  push    r14
0x18005f352  sub     rsp, 48h
0x18005f356  mov     rdi, rcx
0x18005f359  xor     r14d, r14d
0x18005f35c  cmp     [rcx+1F0h], r14
0x18005f363  jz      short loc_18005F371
0x18005f365  xor     eax, eax
0x18005f367  add     rsp, 48h
0x18005f36b  pop     r14
0x18005f36d  pop     rdi
0x18005f36e  pop     rsi
0x18005f36f  pop     rbx
0x18005f370  retn
0x18005f371  mov     [rsp+68h+hKey], r14
0x18005f376  lea     rbx, [rcx+0A8h]
0x18005f37d  cmp     qword ptr [rbx+18h], 7
0x18005f382  jbe     loc_18005F587
0x18005f388  mov     rcx, [rbx]; this
0x18005f38b  lea     r8, [rsp+68h+hKey]; unsigned __int16 *
0x18005f390  xor     edx, edx; unsigned __int16 *
0x18005f392  call    ?GetRegistryRootKey@CloudStoreUtilities@@YAJPEBG0PEAPEAUHKEY__@@@Z; CloudStoreUtilities::GetRegistryRootKey(ushort const *,ushort const *,HKEY__ * *)
0x18005f397  mov     esi, eax
0x18005f399  test    eax, eax
0x18005f39b  js      loc_18005F5FA
0x18005f3a1  mov     [rsp+68h+arg_0], r14
0x18005f3a6  lea     rcx, [rsp+68h+arg_0]
0x18005f3ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f3b0  mov     [rsp+68h+arg_0], r14
0x18005f3b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005f3bc  mov     ecx, 18h; unsigned __int64
0x18005f3c1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005f3c6  test    rax, rax
0x18005f3c9  jz      loc_18005F58F
0x18005f3cf  lea     rdx, [rsp+68h+hKey]
0x18005f3d4  mov     rcx, rax
0x18005f3d7  call    ??0RegistryStorage@Cloud@Storage@Internal@Windows@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::Storage::Cloud::RegistryStorage::RegistryStorage(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18005f3dc  test    rax, rax
0x18005f3df  jz      loc_18005F58F
0x18005f3e5  mov     [rsp+68h+arg_0], rax
0x18005f3ea  mov     [rsp+68h+pv], r14; int
0x18005f3ef  lea     rax, [rsp+68h+pv]
0x18005f3f4  mov     [rsp+68h+var_40], rax
0x18005f3f9  mov     qword ptr [rsp+68h+var_38], r14
0x18005f3fe  mov     [rsp+68h+var_30], 1
0x18005f403  cmp     qword ptr [rbx+18h], 7
0x18005f408  jbe     short loc_18005F40D
0x18005f40a  mov     rbx, [rbx]
0x18005f40d  lea     r8, [rsp+68h+var_38]; unsigned __int16 *
0x18005f412  mov     rcx, rbx; this
0x18005f415  call    ?GetFileStorageRootPath@CloudStoreUtilities@@YAJPEBG0PEAPEAG@Z; CloudStoreUtilities::GetFileStorageRootPath(ushort const *,ushort const *,ushort * *)
0x18005f41a  mov     ebx, eax
0x18005f41c  lea     rcx, [rsp+68h+var_40]
0x18005f421  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005f426  test    ebx, ebx
0x18005f428  js      loc_18005F62B
0x18005f42e  mov     [rsp+68h+arg_10], r14
0x18005f436  lea     rcx, [rsp+68h+arg_10]
0x18005f43e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f443  lea     rdx, [rsp+68h+arg_10]; unsigned __int16 *
0x18005f44b  mov     rcx, [rsp+68h+pv]; this
0x18005f450  call    ?FileStorage_CreateInstance@Cloud@Storage@Internal@Windows@@YAJPEBGPEAPEAUIBulkLocalStorage@1234@@Z; Windows::Internal::Storage::Cloud::FileStorage_CreateInstance(ushort const *,Windows::Internal::Storage::Cloud::IBulkLocalStorage * *)
0x18005f455  mov     ebx, eax
0x18005f457  test    eax, eax
0x18005f459  js      loc_18005F68A
0x18005f45f  mov     [rsp+68h+arg_18], r14
0x18005f467  lea     rcx, [rsp+68h+arg_18]
0x18005f46f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f474  lea     r8, [rsp+68h+arg_18]; struct Windows::Internal::Storage::Cloud::IBulkLocalStorage *
0x18005f47c  mov     rdx, [rsp+68h+arg_10]; struct Windows::Internal::Storage::Cloud::IDefaultLocalStorage *
0x18005f484  mov     rcx, [rsp+68h+arg_0]; this
0x18005f489  call    ?CloudStoreCache_CreateInstance@Cloud@Storage@Internal@Windows@@YAJPEAUIDefaultLocalStorage@1234@PEAUIBulkLocalStorage@1234@PEAPEAUICloudStoreCache@1234@@Z; Windows::Internal::Storage::Cloud::CloudStoreCache_CreateInstance(Windows::Internal::Storage::Cloud::IDefaultLocalStorage *,Windows::Internal::Storage::Cloud::IBulkLocalStorage *,Windows::Internal::Storage::Cloud::ICloudStoreCache * *)
0x18005f48e  mov     ebx, eax
0x18005f490  test    eax, eax
0x18005f492  js      loc_18005F6D9
0x18005f498  lea     rsi, [rdi+150h]
0x18005f49f  mov     rcx, rsi; SRWLock
0x18005f4a2  call    cs:__imp_AcquireSRWLockExclusive
0x18005f4a8  cmp     [rdi+1F0h], r14
0x18005f4af  jnz     short loc_18005F4EE
0x18005f4b1  mov     rbx, [rsp+68h+arg_18]
0x18005f4b9  test    rbx, rbx
0x18005f4bc  jz      short loc_18005F4EE
0x18005f4be  mov     rax, [rbx]
0x18005f4c1  mov     rcx, rbx
0x18005f4c4  mov     rax, [rax+8]
0x18005f4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f4cd  nop
0x18005f4ce  mov     rcx, [rdi+1F0h]
0x18005f4d5  mov     [rdi+1F0h], rbx
0x18005f4dc  test    rcx, rcx
0x18005f4df  jz      short loc_18005F4EE
0x18005f4e1  mov     rax, [rcx]
0x18005f4e4  mov     rax, [rax+10h]
0x18005f4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f4ed  nop
0x18005f4ee  test    rsi, rsi
0x18005f4f1  jz      short loc_18005F4FD
0x18005f4f3  mov     rcx, rsi; SRWLock
0x18005f4f6  call    cs:__imp_ReleaseSRWLockExclusive
0x18005f4fc  nop
0x18005f4fd  mov     rcx, [rsp+68h+arg_18]
0x18005f505  test    rcx, rcx
0x18005f508  jz      short loc_18005F51F
0x18005f50a  mov     [rsp+68h+arg_18], r14
0x18005f512  mov     rax, [rcx]
0x18005f515  mov     rax, [rax+10h]
0x18005f519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f51e  nop
0x18005f51f  mov     rcx, [rsp+68h+arg_10]
0x18005f527  test    rcx, rcx
0x18005f52a  jz      short loc_18005F541
0x18005f52c  mov     [rsp+68h+arg_10], r14
0x18005f534  mov     rax, [rcx]
0x18005f537  mov     rax, [rax+10h]
0x18005f53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f540  nop
0x18005f541  mov     rcx, [rsp+68h+pv]; pv
0x18005f546  test    rcx, rcx
0x18005f549  jz      short loc_18005F552
0x18005f54b  call    cs:__imp_CoTaskMemFree
0x18005f551  nop
0x18005f552  mov     rcx, [rsp+68h+arg_0]
0x18005f557  test    rcx, rcx
0x18005f55a  jz      short loc_18005F56E
0x18005f55c  mov     [rsp+68h+arg_0], r14
0x18005f561  mov     rax, [rcx]
0x18005f564  mov     rax, [rax+10h]
0x18005f568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f56d  nop
0x18005f56e  mov     rcx, [rsp+68h+hKey]; hKey
0x18005f573  test    rcx, rcx
0x18005f576  jz      loc_18005F365
0x18005f57c  call    cs:__imp_RegCloseKey
0x18005f582  jmp     loc_18005F365
0x18005f587  mov     rcx, rbx
0x18005f58a  jmp     loc_18005F38B
0x18005f58f  mov     rcx, [rsp+68h]; this
0x18005f594  mov     ebx, 8007000Eh
0x18005f599  mov     r9d, ebx; char *
0x18005f59c  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18005f5a3  mov     edx, 0BEh; void *
0x18005f5a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f5ad  mov     rcx, [rsp+68h]; this
0x18005f5b2  mov     r9d, ebx; char *
0x18005f5b5  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005f5bc  mov     edx, 1188h; void *
0x18005f5c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f5c6  nop
0x18005f5c7  mov     rcx, [rsp+68h+arg_0]
0x18005f5cc  test    rcx, rcx
0x18005f5cf  jz      short loc_18005F5E3
0x18005f5d1  mov     [rsp+68h+arg_0], r14
0x18005f5d6  mov     rax, [rcx]
0x18005f5d9  mov     rax, [rax+10h]
0x18005f5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f5e2  nop
0x18005f5e3  mov     rcx, [rsp+68h+hKey]; hKey
0x18005f5e8  test    rcx, rcx
0x18005f5eb  jz      short loc_18005F5F3
0x18005f5ed  call    cs:__imp_RegCloseKey
0x18005f5f3  mov     eax, ebx
0x18005f5f5  jmp     loc_18005F367
0x18005f5fa  mov     rcx, [rsp+68h]; this
0x18005f5ff  mov     r9d, esi; char *
0x18005f602  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005f609  mov     edx, 1185h; void *
0x18005f60e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f613  nop
0x18005f614  mov     rcx, [rsp+68h+hKey]; hKey
0x18005f619  test    rcx, rcx
0x18005f61c  jz      short loc_18005F624
0x18005f61e  call    cs:__imp_RegCloseKey
0x18005f624  mov     eax, esi
0x18005f626  jmp     loc_18005F367
0x18005f62b  mov     rcx, [rsp+68h]; this
0x18005f630  mov     r9d, ebx; char *
0x18005f633  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005f63a  mov     edx, 118Bh; void *
0x18005f63f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f644  nop
0x18005f645  mov     rcx, [rsp+68h+pv]; pv
0x18005f64a  test    rcx, rcx
0x18005f64d  jnz     short loc_18005F682
0x18005f64f  mov     rcx, [rsp+68h+arg_0]
0x18005f654  test    rcx, rcx
0x18005f657  jz      short loc_18005F66B
0x18005f659  mov     [rsp+68h+arg_0], r14
0x18005f65e  mov     rax, [rcx]
0x18005f661  mov     rax, [rax+10h]
0x18005f665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f66a  nop
0x18005f66b  mov     rcx, [rsp+68h+hKey]; hKey
0x18005f670  test    rcx, rcx
0x18005f673  jz      short loc_18005F67B
0x18005f675  call    cs:__imp_RegCloseKey
0x18005f67b  mov     eax, ebx
0x18005f67d  jmp     loc_18005F367
0x18005f682  call    cs:__imp_CoTaskMemFree
0x18005f688  jmp     short loc_18005F64F
0x18005f68a  mov     rcx, [rsp+68h]; this
0x18005f68f  mov     r9d, ebx; char *
0x18005f692  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005f699  mov     edx, 118Eh; void *
0x18005f69e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f6a3  nop
0x18005f6a4  lea     rcx, [rsp+68h+arg_10]
0x18005f6ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f6b1  nop
0x18005f6b2  lea     rcx, [rsp+68h+pv]
0x18005f6b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005f6bc  nop
0x18005f6bd  lea     rcx, [rsp+68h+arg_0]
0x18005f6c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f6c7  nop
0x18005f6c8  lea     rcx, [rsp+68h+hKey]
0x18005f6cd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005f6d2  mov     eax, ebx
0x18005f6d4  jmp     loc_18005F367
0x18005f6d9  mov     rcx, [rsp+68h]; this
0x18005f6de  mov     r9d, ebx; char *
0x18005f6e1  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005f6e8  mov     edx, 1191h; void *
0x18005f6ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f6f2  nop
0x18005f6f3  lea     rcx, [rsp+68h+arg_18]
0x18005f6fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f700  nop
0x18005f701  lea     rcx, [rsp+68h+arg_10]
0x18005f709  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f70e  nop
0x18005f70f  lea     rcx, [rsp+68h+pv]
0x18005f714  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005f719  nop
0x18005f71a  lea     rcx, [rsp+68h+arg_0]
0x18005f71f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f724  nop
0x18005f725  lea     rcx, [rsp+68h+hKey]
0x18005f72a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005f72f  mov     eax, ebx
0x18005f731  jmp     loc_18005F367
0x18005f736  mov     eax, dword ptr [rsp+68h+arg_0]
0x18005f73a  jmp     loc_18005F367
```
