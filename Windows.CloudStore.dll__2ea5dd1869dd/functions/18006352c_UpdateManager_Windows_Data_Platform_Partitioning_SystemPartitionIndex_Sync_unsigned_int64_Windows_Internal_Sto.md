# UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::Sync(unsigned __int64,Windows::Internal::Storage::Cloud::LoadOptions,Windows::Internal::Storage::Cloud::SaveOptions)

- ea: `0x18006352c`
- end: `0x180063998`
- name: `?Sync@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAAX_KW4LoadOptions@Cloud@Storage@Internal@Windows@@W4SaveOptions@3456@@Z`
- size: `1132`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180064c48`
- `0x18010bff4`

## callees

- `0x18000dfe4`
- `0x18000e828`
- `0x18000e8d0`
- `0x18000f8dc`
- `0x180016cf4`
- `0x180029da4`
- `0x18002e010`
- `0x18003f2cc`
- `0x18003f364`
- `0x1800504d8`
- `0x18005ad88`
- `0x1800634e0`
- `0x180063510`
- `0x18006352c`
- `0x1800639a0`
- `0x180063a14`
- `0x180063ba0`
- `0x180063ca4`
- `0x1800643a4`
- `0x180064468`
- `0x180066154`
- `0x180066288`
- `0x180097e8c`
- `0x1800c1d2c`
- `0x180112a18`
- `0x1801201a0`
- `0x1801202a0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006368f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063972`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006368f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063972`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800635b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800635b0`

## string_xrefs

- `0x180063699`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`
- `0x18006392a`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`
- `0x18006393f`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`
- `0x180063954`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::Sync(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v4; // rdi
  __int64 v5; // r14
  __int64 v6; // rax
  const WCHAR *v7; // rsi
  unsigned __int64 v8; // rbx
  unsigned int v9; // eax
  UINT32 v10; // edx
  HRESULT v11; // eax
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  _QWORD *v14; // r13
  __int64 *v15; // rax
  unsigned int v16; // edx
  __int64 v17; // rcx
  void *v18; // rbx
  void *v19; // rbx
  Windows::Data::Platform::Partitioning::SystemPartitionIndex *v20; // rcx
  __int64 *v21; // rax
  Windows::Data::Platform::Partitioning::SystemPartitionIndex **v22; // rbx
  schematized_data *v23; // rbx
  const struct schematized_data *v24; // rax
  unsigned int v25; // edx
  Windows::Data::Platform::Partitioning::SystemPartitionIndex *v26; // rcx
  schematized_data *v27; // rax
  const struct bond::blob *v28; // rax
  int v29; // eax
  _QWORD *v30; // r15
  __int64 (__fastcall *v31)(_QWORD *, _QWORD, _QWORD, _QWORD); // r14
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rcx
  unsigned int v36; // edx
  Windows::Data::Platform::Partitioning::SystemPartitionIndex *v37; // rcx
  int v38; // [rsp+20h] [rbp-B9h]
  void *TypeName; // [rsp+70h] [rbp-69h] BYREF
  Windows::Data::Platform::Partitioning::SystemPartitionIndex **v40; // [rsp+78h] [rbp-61h] BYREF
  std::_Ref_count_base *v41; // [rsp+80h] [rbp-59h]
  Windows::Data::Platform::Partitioning::SystemPartitionIndex ***v42; // [rsp+88h] [rbp-51h] BYREF
  struct Windows::Storage::Streams::IBuffer *v43; // [rsp+90h] [rbp-49h] BYREF
  char v44; // [rsp+98h] [rbp-41h]
  __int64 v45; // [rsp+A0h] [rbp-39h] BYREF
  __int64 *v46; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-21h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-9h] BYREF
  HSTRING_HEADER v50; // [rsp+D8h] [rbp-1h] BYREF
  __int64 v51; // [rsp+F0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v2 = a2;
  v47 = a2;
  if ( !a2 )
  {
    v4 = (_QWORD *)*a1;
    v5 = *(_QWORD *)*a1;
    v6 = ((__int64 (*)(void))UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetTypeName)();
    v7 = (const WCHAR *)v6;
    string = 0;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
    if ( v8 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
    }
    else
    {
      v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v8);
      v10 = v9 - 1;
      if ( (unsigned int)v8 < v9 )
        v10 = v8;
      v11 = WindowsCreateStringReference(v7, v10, &hstringHeader, &string);
      if ( v11 < 0 )
      {
        RaiseException(v11, 1u, 0, 0);
        __debugbreak();
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v5 + 136))(v4, string, &v47);
      v13 = retaddr;
      if ( v12 >= 0 )
      {
        v2 = v47;
        goto LABEL_10;
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v13,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
      (const char *)(unsigned int)v12,
      v38);
  }
LABEL_10:
  v14 = a1 + 1;
  if ( a1[1] )
  {
    if ( a1[2] )
    {
      v22 = (Windows::Data::Platform::Partitioning::SystemPartitionIndex **)std::make_unique<Windows::Data::Platform::Partitioning::SystemPartitionIndex,Windows::Data::Platform::Partitioning::SystemPartitionIndex const &,0>(&TypeName);
      std::make_shared<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::state,>(&v40);
      std::unique_ptr<Windows::Data::Platform::Partitioning::SystemPartitionIndex const>::operator=<Windows::Data::Platform::Partitioning::SystemPartitionIndex,std::default_delete<Windows::Data::Platform::Partitioning::SystemPartitionIndex>,0>(
        v40,
        v22);
      std::unique_ptr<Windows::Data::Platform::Partitioning::SystemPartitionIndex const>::~unique_ptr<Windows::Data::Platform::Partitioning::SystemPartitionIndex const>(&TypeName);
      versioned<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>>::versioned<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>>(
        &hstringHeader,
        &v40,
        v2);
      if ( v41 )
        std::_Ref_count_base::_Decref(v41);
      v23 = (schematized_data *)deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::serialized(&hstringHeader);
      v24 = (const struct schematized_data *)deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::serialized(*v14);
      if ( (unsigned int)schematized_data::compare(v23, v24) )
      {
        v40 = 0;
        v42 = &v40;
        v43 = 0;
        v44 = 1;
        v27 = (schematized_data *)deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::serialized(&hstringHeader);
        v28 = schematized_data::as_blob(v27);
        v29 = ConvertBondBlobToIBuffer(v28, &v43);
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBA,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
            (const char *)(unsigned int)v29,
            v38);
        wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&v42);
        v46 = 0;
        v30 = (_QWORD *)*a1;
        v31 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*a1 + 88LL);
        v42 = (Windows::Data::Platform::Partitioning::SystemPartitionIndex ***)&v46;
        v43 = 0;
        v44 = 1;
        TypeName = (void *)UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetTypeName(a1);
        Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v50, (const WCHAR **)&TypeName);
        v32 = v31(v30, 0, 0, 0);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC2,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
            (const char *)(unsigned int)v32,
            0);
        v51 = 0;
        wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&v42);
        v45 = 0;
        v33 = *v46;
        v42 = (Windows::Data::Platform::Partitioning::SystemPartitionIndex ***)&v45;
        v43 = 0;
        v44 = 1;
        v34 = (*(__int64 (__fastcall **)(__int64 *, struct Windows::Storage::Streams::IBuffer **))(v33 + 56))(v46, &v43);
        if ( v34 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC5,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
            (const char *)(unsigned int)v34,
            0);
        wil::details::out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>(&v42);
        UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetSyncItemFromCloudStoreData(
          v35,
          &TypeName,
          v45);
        std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(
          a1 + 1,
          (__int64 *)&TypeName);
        v37 = (Windows::Data::Platform::Partitioning::SystemPartitionIndex *)a1[2];
        a1[2] = 0;
        if ( v37 )
          Windows::Data::Platform::Partitioning::SystemPartitionIndex::`scalar deleting destructor'(v37, v36);
        std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>::~unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>(&TypeName);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v45);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v46);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v40);
      }
      else
      {
        UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::LoadInternal(a1, &v40);
        if ( v40[2] != *(Windows::Data::Platform::Partitioning::SystemPartitionIndex **)(*v14 + 16LL) )
        {
          std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(
            a1 + 1,
            (__int64 *)&v40);
          v26 = (Windows::Data::Platform::Partitioning::SystemPartitionIndex *)a1[2];
          a1[2] = 0;
          if ( v26 )
            Windows::Data::Platform::Partitioning::SystemPartitionIndex::`scalar deleting destructor'(v26, v25);
        }
        std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>::~unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>(&v40);
      }
      std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>::~shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>(&hstringHeader);
    }
    else
    {
      v21 = (__int64 *)UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::LoadInternal(
                         a1,
                         &TypeName);
      std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(
        a1 + 1,
        v21);
      std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>::~unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>(&TypeName);
    }
  }
  else
  {
    v15 = (__int64 *)UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::LoadInternal(
                       a1,
                       &TypeName);
    v17 = *v15;
    *v15 = 0;
    v18 = (void *)*v14;
    *v14 = v17;
    if ( v18 )
    {
      UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem::~SyncItem(v18);
      operator delete(v18, (const struct std::nothrow_t *)0x20);
    }
    v19 = TypeName;
    if ( TypeName )
    {
      UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem::~SyncItem(TypeName);
      operator delete(v19, (const struct std::nothrow_t *)0x20);
    }
    v20 = (Windows::Data::Platform::Partitioning::SystemPartitionIndex *)a1[2];
    a1[2] = 0;
    if ( v20 )
      Windows::Data::Platform::Partitioning::SystemPartitionIndex::`scalar deleting destructor'(v20, v16);
  }
}

```

## disassembly

```asm
0x18006352c  mov     [rsp-8+arg_10], rbx
0x180063531  push    rbp
0x180063532  push    rsi
0x180063533  push    rdi
0x180063534  push    r12
0x180063536  push    r13
0x180063538  push    r14
0x18006353a  push    r15
0x18006353c  lea     rbp, [rsp-27h]
0x180063541  sub     rsp, 100h
0x180063548  mov     rax, cs:__security_cookie
0x18006354f  xor     rax, rsp
0x180063552  mov     [rbp+57h+var_38], rax
0x180063556  mov     rdi, rdx
0x180063559  mov     r12, rcx
0x18006355c  mov     [rbp+57h+var_80], rdx
0x180063560  xor     r15d, r15d
0x180063563  test    rdx, rdx
0x180063566  jnz     short loc_1800635E5
0x180063568  mov     rdi, [rcx]
0x18006356b  mov     r14, [rdi]
0x18006356e  call    ?GetTypeName@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAAPEBGXZ; UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetTypeName(void)
0x180063573  mov     rsi, rax
0x180063576  mov     [rbp+57h+string], r15
0x18006357a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006357e  inc     rbx
0x180063581  cmp     [rax+rbx*2], r15w
0x180063586  jnz     short loc_18006357E
0x180063588  mov     eax, 0FFFFFFFFh
0x18006358d  cmp     rbx, rax
0x180063590  ja      loc_180063680
0x180063596  mov     ecx, ebx; unsigned int
0x180063598  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18006359d  lea     edx, [rax-1]
0x1800635a0  cmp     ebx, eax
0x1800635a2  cmovb   edx, ebx; length
0x1800635a5  lea     r9, [rbp+57h+string]; string
0x1800635a9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800635ad  mov     rcx, rsi; sourceString
0x1800635b0  call    cs:__imp_WindowsCreateStringReference
0x1800635b6  test    eax, eax
0x1800635b8  js      loc_180063966
0x1800635be  lea     r8, [rbp+57h+var_80]
0x1800635c2  mov     rdx, [rbp+57h+string]
0x1800635c6  mov     rcx, rdi
0x1800635c9  mov     rax, [r14+88h]
0x1800635d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635d5  mov     rcx, [rbp+5Fh]
0x1800635d9  test    eax, eax
0x1800635db  js      loc_180063696
0x1800635e1  mov     rdi, [rbp+57h+var_80]
0x1800635e5  lea     r13, [r12+8]
0x1800635ea  cmp     [r13+0], r15
0x1800635ee  jnz     loc_1800636AB
0x1800635f4  lea     rdx, [rbp+57h+var_C0]
0x1800635f8  mov     rcx, r12
0x1800635fb  call    ?LoadInternal@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@@std@@W4LoadOptions@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::LoadInternal(Windows::Internal::Storage::Cloud::LoadOptions)
0x180063600  mov     rcx, [rax]
0x180063603  mov     [rax], r15
0x180063606  mov     rbx, [r13+0]
0x18006360a  mov     [r13+0], rcx
0x18006360e  mov     edi, 20h ; ' '
0x180063613  test    rbx, rbx
0x180063616  jz      short loc_18006362A
0x180063618  mov     rcx, rbx
0x18006361b  call    ??1SyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@QEAA@XZ; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem::~SyncItem(void)
0x180063620  mov     edx, edi; struct std::nothrow_t *
0x180063622  mov     rcx, rbx; void *
0x180063625  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006362a  mov     rbx, [rbp+57h+var_C0]
0x18006362e  test    rbx, rbx
0x180063631  jz      short loc_180063646
0x180063633  mov     rcx, rbx
0x180063636  call    ??1SyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@QEAA@XZ; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem::~SyncItem(void)
0x18006363b  mov     rdx, rdi; struct std::nothrow_t *
0x18006363e  mov     rcx, rbx; void *
0x180063641  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063646  mov     rcx, [r12+10h]; this
0x18006364b  mov     [r12+10h], r15
0x180063650  test    rcx, rcx
0x180063653  jnz     loc_180063979
0x180063659  mov     rcx, [rbp+57h+var_38]
0x18006365d  xor     rcx, rsp; StackCookie
0x180063660  call    __security_check_cookie
0x180063665  mov     rbx, [rsp+130h+arg_10]
0x18006366d  add     rsp, 100h
0x180063674  pop     r15
0x180063676  pop     r14
0x180063678  pop     r13
0x18006367a  pop     r12
0x18006367c  pop     rdi
0x18006367d  pop     rsi
0x18006367e  pop     rbp
0x18006367f  retn
0x180063680  xor     r9d, r9d; lpArguments
0x180063683  xor     r8d, r8d; nNumberOfArguments
0x180063686  lea     edx, [r9+1]; dwExceptionFlags
0x18006368a  mov     ecx, 80070216h; dwExceptionCode
0x18006368f  call    cs:__imp_RaiseException
0x180063695  nop
0x180063696  mov     r9d, eax; char *
0x180063699  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800636a0  mov     edx, 0A3h; void *
0x1800636a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800636ab  mov     rdx, [r12+10h]
0x1800636b0  test    rdx, rdx
0x1800636b3  jnz     short loc_1800636D7
0x1800636b5  lea     rdx, [rbp+57h+var_C0]
0x1800636b9  mov     rcx, r12
0x1800636bc  call    ?LoadInternal@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@@std@@W4LoadOptions@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::LoadInternal(Windows::Internal::Storage::Cloud::LoadOptions)
0x1800636c1  mov     rdx, rax
0x1800636c4  mov     rcx, r13
0x1800636c7  call    ??$?4U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@$0A@@?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>> &&)
0x1800636cc  lea     rcx, [rbp+57h+var_C0]
0x1800636d0  call    ??1?$unique_ptr@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAA@XZ; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>::~unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>(void)
0x1800636d5  jmp     short loc_180063659
0x1800636d7  lea     rcx, [rbp+57h+var_C0]
0x1800636db  call    ??$make_unique@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@AEBU12345@$0A@@std@@YA?AV?$unique_ptr@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@U?$default_delete@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@std@@@0@AEBUSystemPartitionIndex@Partitioning@Platform@Data@Windows@@@Z; std::make_unique<Windows::Data::Platform::Partitioning::SystemPartitionIndex,Windows::Data::Platform::Partitioning::SystemPartitionIndex const &,0>(Windows::Data::Platform::Partitioning::SystemPartitionIndex const &)
0x1800636e0  mov     rbx, rax
0x1800636e3  lea     rcx, [rbp+57h+var_B8]
0x1800636e7  call    ??$make_shared@Ustate@?$deserializable_data@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@$$V@std@@YA?AV?$shared_ptr@Ustate@?$deserializable_data@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@0@XZ; std::make_shared<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::state,>(void)
0x1800636ec  mov     rdx, rbx
0x1800636ef  mov     rcx, [rbp+57h+var_B8]
0x1800636f3  call    ??$?4USystemPartitionIndex@Partitioning@Platform@Data@Windows@@U?$default_delete@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@std@@$0A@@?$unique_ptr@$$CBUSystemPartitionIndex@Partitioning@Platform@Data@Windows@@U?$default_delete@$$CBUSystemPartitionIndex@Partitioning@Platform@Data@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@U?$default_delete@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@std@@@1@@Z; std::unique_ptr<Windows::Data::Platform::Partitioning::SystemPartitionIndex const>::operator=<Windows::Data::Platform::Partitioning::SystemPartitionIndex,std::default_delete<Windows::Data::Platform::Partitioning::SystemPartitionIndex>,0>(std::unique_ptr<Windows::Data::Platform::Partitioning::SystemPartitionIndex> &&)
0x1800636f8  nop
0x1800636f9  lea     rcx, [rbp+57h+var_C0]
0x1800636fd  call    ??1?$unique_ptr@$$CBUSystemPartitionIndex@Partitioning@Platform@Data@Windows@@U?$default_delete@$$CBUSystemPartitionIndex@Partitioning@Platform@Data@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Data::Platform::Partitioning::SystemPartitionIndex const>::~unique_ptr<Windows::Data::Platform::Partitioning::SystemPartitionIndex const>(void)
0x180063702  mov     r8, rdi
0x180063705  lea     rdx, [rbp+57h+var_B8]
0x180063709  lea     rcx, [rbp+57h+hstringHeader]
0x18006370d  call    ??0?$versioned@V?$deserializable_data@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@@QEAA@AEBV?$deserializable_data@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@_K@Z; versioned<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>>::versioned<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>>(deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex> const &,unsigned __int64)
0x180063712  nop
0x180063713  mov     rcx, [rbp+57h+var_B0]; this
0x180063717  test    rcx, rcx
0x18006371a  jz      short loc_180063721
0x18006371c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180063721  lea     rcx, [rbp+57h+hstringHeader]
0x180063725  call    ?serialized@?$deserializable_data@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@QEBAAEBVschematized_data@@XZ; deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::serialized(void)
0x18006372a  mov     rbx, rax
0x18006372d  mov     rcx, [r13+0]
0x180063731  call    ?serialized@?$deserializable_data@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@QEBAAEBVschematized_data@@XZ; deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::serialized(void)
0x180063736  mov     rdx, rax; struct schematized_data *
0x180063739  mov     rcx, rbx; this
0x18006373c  call    ?compare@schematized_data@@QEBAHAEBV1@@Z; schematized_data::compare(schematized_data const &)
0x180063741  test    eax, eax
0x180063743  jnz     short loc_180063790
0x180063745  lea     rdx, [rbp+57h+var_B8]
0x180063749  mov     rcx, r12
0x18006374c  call    ?LoadInternal@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@@std@@W4LoadOptions@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::LoadInternal(Windows::Internal::Storage::Cloud::LoadOptions)
0x180063751  mov     rax, [r13+0]
0x180063755  mov     rcx, [rax+10h]
0x180063759  mov     rax, [rbp+57h+var_B8]
0x18006375d  cmp     [rax+10h], rcx
0x180063761  jz      short loc_180063782
0x180063763  lea     rdx, [rbp+57h+var_B8]
0x180063767  mov     rcx, r13
0x18006376a  call    ??$?4U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@$0A@@?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>> &&)
0x18006376f  mov     rcx, [r12+10h]; this
0x180063774  mov     [r12+10h], r15
0x180063779  test    rcx, rcx
0x18006377c  jnz     loc_18006398D
0x180063782  lea     rcx, [rbp+57h+var_B8]
0x180063786  call    ??1?$unique_ptr@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAA@XZ; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>::~unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>(void)
0x18006378b  jmp     loc_180063919
0x180063790  mov     [rbp+57h+var_B8], r15
0x180063794  lea     rax, [rbp+57h+var_B8]
0x180063798  mov     [rbp+57h+var_A8], rax
0x18006379c  mov     [rbp+57h+var_A0], r15
0x1800637a0  mov     [rbp+57h+var_98], 1
0x1800637a4  lea     rcx, [rbp+57h+hstringHeader]
0x1800637a8  call    ?serialized@?$deserializable_data@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@QEBAAEBVschematized_data@@XZ; deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::serialized(void)
0x1800637ad  mov     rcx, rax; this
0x1800637b0  call    ?as_blob@schematized_data@@QEBAAEBVblob@bond@@XZ; schematized_data::as_blob(void)
0x1800637b5  lea     rdx, [rbp+57h+var_A0]; struct Windows::Storage::Streams::IBuffer **
0x1800637b9  mov     rcx, rax; struct bond::blob *
0x1800637bc  call    ?ConvertBondBlobToIBuffer@@YAJAEBVblob@bond@@PEAPEAUIBuffer@Streams@Storage@Windows@@@Z; ConvertBondBlobToIBuffer(bond::blob const &,Windows::Storage::Streams::IBuffer * *)
0x1800637c1  mov     rcx, [rbp+5Fh]; this
0x1800637c5  test    eax, eax
0x1800637c7  js      loc_180063927
0x1800637cd  lea     rcx, [rbp+57h+var_A8]
0x1800637d1  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x1800637d6  mov     [rbp+57h+var_88], r15
0x1800637da  mov     r15, [r12]
0x1800637de  mov     rax, [r15]
0x1800637e1  mov     r14, [rax+58h]
0x1800637e5  lea     rax, [rbp+57h+var_88]
0x1800637e9  mov     [rbp+57h+var_A8], rax
0x1800637ed  mov     [rbp+57h+var_A0], 0
0x1800637f5  mov     [rbp+57h+var_98], 1
0x1800637f9  mov     rdi, [rbp+57h+var_B8]
0x1800637fd  mov     rsi, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x180063801  mov     rax, [r13+0]
0x180063805  mov     rbx, [rax+18h]
0x180063809  mov     rcx, r12
0x18006380c  call    ?GetTypeName@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAAPEBGXZ; UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetTypeName(void)
0x180063811  mov     [rbp+57h+var_C0], rax
0x180063815  lea     rdx, [rbp+57h+var_C0]
0x180063819  lea     rcx, [rbp+57h+var_58]
0x18006381d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180063822  nop
0x180063823  lea     rcx, [rbp+57h+var_A0]
0x180063827  mov     [rsp+130h+var_D8], rcx
0x18006382c  mov     [rsp+130h+var_E0], 0
0x180063835  mov     [rsp+130h+var_E8], 10h
0x18006383d  mov     [rsp+130h+var_F0], rdi
0x180063842  mov     [rsp+130h+var_F8], rsi
0x180063847  mov     [rsp+130h+var_100], rbx
0x18006384c  mov     rdx, [rax+18h]
0x180063850  mov     [rsp+130h+var_108], rdx
0x180063855  xor     ebx, ebx
0x180063857  mov     qword ptr [rsp+130h+var_110], rbx; int
0x18006385c  xor     r9d, r9d
0x18006385f  xor     r8d, r8d
0x180063862  xor     edx, edx
0x180063864  mov     rcx, r15
0x180063867  mov     rax, r14
0x18006386a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006386f  mov     rcx, [rbp+5Fh]; this
0x180063873  test    eax, eax
0x180063875  js      loc_18006393C
0x18006387b  mov     [rbp+57h+var_40], rbx
0x18006387f  lea     rcx, [rbp+57h+var_A8]
0x180063883  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x180063888  mov     [rbp+57h+var_90], rbx
0x18006388c  mov     rcx, [rbp+57h+var_88]
0x180063890  mov     rax, [rcx]
0x180063893  lea     rdx, [rbp+57h+var_90]
0x180063897  mov     [rbp+57h+var_A8], rdx
0x18006389b  mov     [rbp+57h+var_A0], rbx
0x18006389f  mov     [rbp+57h+var_98], 1
0x1800638a3  lea     rdx, [rbp+57h+var_A0]
0x1800638a7  mov     rax, [rax+38h]
0x1800638ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800638b0  mov     rcx, [rbp+5Fh]; this
0x1800638b4  test    eax, eax
0x1800638b6  js      loc_180063951
0x1800638bc  lea     rcx, [rbp+57h+var_A8]
0x1800638c0  call    ??1?$out_param_t@V?$com_ptr_t@UIMarshal@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>(void)
0x1800638c5  mov     r8, [rbp+57h+var_90]
0x1800638c9  lea     rdx, [rbp+57h+var_C0]
0x1800638cd  call    ?GetSyncItemFromCloudStoreData@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@@std@@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::GetSyncItemFromCloudStoreData(Windows::Internal::Storage::Cloud::ICloudStoreData *)
0x1800638d2  lea     rdx, [rbp+57h+var_C0]
0x1800638d6  mov     rcx, r13
0x1800638d9  call    ??$?4U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@$0A@@?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>> &&)
0x1800638de  mov     rcx, [r12+10h]; this
0x1800638e3  mov     [r12+10h], rbx
0x1800638e8  test    rcx, rcx
0x1800638eb  jnz     loc_180063983
0x1800638f1  lea     rcx, [rbp+57h+var_C0]
0x1800638f5  call    ??1?$unique_ptr@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAA@XZ; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>::~unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>>(void)
0x1800638fa  nop
0x1800638fb  lea     rcx, [rbp+57h+var_90]
0x1800638ff  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180063904  nop
0x180063905  lea     rcx, [rbp+57h+var_88]
0x180063909  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18006390e  nop
0x18006390f  lea     rcx, [rbp+57h+var_B8]
0x180063913  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180063918  nop
0x180063919  lea     rcx, [rbp+57h+hstringHeader]
0x18006391d  call    ??1?$shared_ptr@VDownloaderCore@Core@Downloader@Cloud@Storage@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>::~shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>(void)
0x180063922  jmp     loc_180063659
0x180063927  mov     r9d, eax; char *
0x18006392a  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180063931  mov     edx, 0BAh; void *
0x180063936  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006393c  mov     r9d, eax; char *
0x18006393f  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180063946  mov     edx, 0C2h; void *
0x18006394b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180063951  mov     r9d, eax; char *
0x180063954  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18006395b  mov     edx, 0C5h; void *
0x180063960  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180063966  xor     r9d, r9d; lpArguments
0x180063969  xor     r8d, r8d; nNumberOfArguments
0x18006396c  lea     edx, [r9+1]; dwExceptionFlags
0x180063970  mov     ecx, eax; dwExceptionCode
0x180063972  call    cs:__imp_RaiseException
0x180063978  int     3; Trap to Debugger
0x180063979  call    ??_GSystemPartitionIndex@Partitioning@Platform@Data@Windows@@QEAAPEAXI@Z; Windows::Data::Platform::Partitioning::SystemPartitionIndex::`scalar deleting destructor'(uint)
0x18006397e  jmp     loc_180063659
0x180063983  call    ??_GSystemPartitionIndex@Partitioning@Platform@Data@Windows@@QEAAPEAXI@Z; Windows::Data::Platform::Partitioning::SystemPartitionIndex::`scalar deleting destructor'(uint)
0x180063988  jmp     loc_1800638F1
0x18006398d  call    ??_GSystemPartitionIndex@Partitioning@Platform@Data@Windows@@QEAAPEAXI@Z; Windows::Data::Platform::Partitioning::SystemPartitionIndex::`scalar deleting destructor'(uint)
0x180063992  jmp     loc_180063782
```
