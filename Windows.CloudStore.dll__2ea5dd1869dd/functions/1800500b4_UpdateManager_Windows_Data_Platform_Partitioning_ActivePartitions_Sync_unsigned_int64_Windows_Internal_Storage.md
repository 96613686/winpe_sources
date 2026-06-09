# UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::Sync(unsigned __int64,Windows::Internal::Storage::Cloud::LoadOptions,Windows::Internal::Storage::Cloud::SaveOptions)

- ea: `0x1800500b4`
- end: `0x1800504d0`
- name: `?Sync@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAAX_KW4LoadOptions@Cloud@Storage@Internal@Windows@@W4SaveOptions@3456@@Z`
- size: `1052`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180050054`
- `0x1800c2df0`

## callees

- `0x18000dfe4`
- `0x18000e828`
- `0x18000e8d0`
- `0x18000f8dc`
- `0x180016cf4`
- `0x180029da4`
- `0x18002e010`
- `0x18003f364`
- `0x18003f3fc`
- `0x1800500b4`
- `0x1800504d8`
- `0x18005050c`
- `0x180050568`
- `0x180050728`
- `0x1800520b8`
- `0x18005ad88`
- `0x180063484`
- `0x180063ba0`
- `0x180063fb0`
- `0x180097e8c`
- `0x18009eacc`
- `0x1800c1684`
- `0x1800c1dbc`
- `0x180112a18`
- `0x1801201a0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050143`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800504c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050143`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800504c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005012d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005012d`

## string_xrefs

- `0x18005016c`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`
- `0x1800502cb`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`
- `0x18005038c`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`
- `0x1800503e0`: `onecoreuap\shell\cloudstore\store\api\src\updatehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 *__fastcall UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::Sync(__int64 *a1)
{
  _QWORD *v2; // rsi
  __int64 v3; // r14
  __int64 v4; // rax
  const WCHAR *v5; // rdi
  unsigned __int64 v6; // rbx
  unsigned int v7; // eax
  UINT32 v8; // edx
  HRESULT v9; // eax
  int v10; // eax
  _QWORD *v11; // r13
  __int64 *v12; // rax
  __int64 *result; // rax
  unsigned int v14; // edx
  Windows::Data::Platform::Partitioning::ActivePartitions *v15; // rcx
  __int64 *v16; // rax
  __int64 v17; // rdi
  Windows::Data::Platform::Partitioning::ActivePartitions **active; // rbx
  schematized_data *v19; // rbx
  const struct schematized_data *v20; // rax
  schematized_data *v21; // rax
  const struct bond::blob *v22; // rax
  int v23; // eax
  _QWORD *v24; // r15
  __int64 (__fastcall *v25)(_QWORD *, _QWORD, _QWORD, _QWORD); // r14
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rcx
  unsigned int v30; // edx
  Windows::Data::Platform::Partitioning::ActivePartitions *v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // edx
  Windows::Data::Platform::Partitioning::ActivePartitions *v34; // rcx
  int v35; // [rsp+20h] [rbp-E0h]
  const WCHAR *TypeName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v38; // [rsp+80h] [rbp-80h] BYREF
  struct Windows::Storage::Streams::IBuffer *v39; // [rsp+88h] [rbp-78h] BYREF
  char v40; // [rsp+90h] [rbp-70h]
  __int64 *v41; // [rsp+98h] [rbp-68h] BYREF
  Windows::Data::Platform::Partitioning::ActivePartitions **v42; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v43; // [rsp+A8h] [rbp-58h]
  __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER v47; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v48; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v44 = 0;
  v2 = (_QWORD *)*a1;
  v3 = *(_QWORD *)*a1;
  v4 = ((__int64 (*)(void))UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetTypeName)();
  v5 = (const WCHAR *)v4;
  string = 0;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v4 + 2 * v6) );
  if ( v6 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x1800504CFLL);
  }
  v7 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v6);
  v8 = v7 - 1;
  if ( (unsigned int)v6 < v7 )
    v8 = v6;
  v9 = WindowsCreateStringReference(v5, v8, &hstringHeader, &string);
  if ( v9 < 0 )
    RaiseException(v9, 1u, 0, 0);
  v10 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v3 + 136))(v2, string, &v44);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
      (const char *)(unsigned int)v10,
      v35);
  v11 = a1 + 1;
  if ( a1[1] )
  {
    if ( a1[2] )
    {
      v17 = v44;
      active = (Windows::Data::Platform::Partitioning::ActivePartitions **)std::make_unique<Windows::Data::Platform::Partitioning::ActivePartitions,Windows::Data::Platform::Partitioning::ActivePartitions const &,0>(&TypeName);
      std::make_shared<deserializable_data<Windows::Data::Platform::Partitioning::ActivePartitions>::state,>(&v42);
      std::unique_ptr<Windows::Data::Platform::Partitioning::ActivePartitions const>::operator=<Windows::Data::Platform::Partitioning::ActivePartitions,std::default_delete<Windows::Data::Platform::Partitioning::ActivePartitions>,0>(
        v42,
        active);
      std::unique_ptr<Windows::Data::Platform::Partitioning::ActivePartitions>::~unique_ptr<Windows::Data::Platform::Partitioning::ActivePartitions>(&TypeName);
      versioned<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>>::versioned<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>>(
        &hstringHeader,
        &v42,
        v17);
      if ( v43 )
        std::_Ref_count_base::_Decref(v43);
      v19 = (schematized_data *)deserializable_data<Windows::Data::Platform::Partitioning::ActivePartitions>::serialized(&hstringHeader);
      v20 = (const struct schematized_data *)deserializable_data<Windows::Data::Platform::Partitioning::ActivePartitions>::serialized(*v11);
      if ( (unsigned int)schematized_data::compare(v19, v20) )
      {
        v42 = 0;
        v38 = (__int64 *)&v42;
        v39 = 0;
        v40 = 1;
        v21 = (schematized_data *)deserializable_data<Windows::Data::Platform::Partitioning::ActivePartitions>::serialized(&hstringHeader);
        v22 = schematized_data::as_blob(v21);
        v23 = ConvertBondBlobToIBuffer(v22, &v39);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBA,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
            (const char *)(unsigned int)v23,
            v35);
        wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&v38);
        v41 = 0;
        v24 = (_QWORD *)*a1;
        v25 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*a1 + 88LL);
        v38 = (__int64 *)&v41;
        v39 = 0;
        v40 = 1;
        TypeName = (const WCHAR *)UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetTypeName(a1);
        Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v47, &TypeName);
        v26 = v25(v24, 0, 0, 0);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC2,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
            (const char *)(unsigned int)v26,
            0);
        v48 = 0;
        wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&v38);
        v37 = 0;
        v27 = *v41;
        v38 = &v37;
        v39 = 0;
        v40 = 1;
        v28 = (*(__int64 (__fastcall **)(__int64 *, struct Windows::Storage::Streams::IBuffer **))(v27 + 56))(v41, &v39);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC5,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\updatehelper.h",
            (const char *)(unsigned int)v28,
            0);
        wil::details::out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>(&v38);
        UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetSyncItemFromCloudStoreData(
          v29,
          &TypeName,
          v37);
        std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(
          a1 + 1,
          (__int64 *)&TypeName);
        v31 = (Windows::Data::Platform::Partitioning::ActivePartitions *)a1[2];
        a1[2] = 0;
        if ( v31 )
          Windows::Data::Platform::Partitioning::ActivePartitions::`scalar deleting destructor'(v31, v30);
        if ( TypeName )
          std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>::operator()();
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v37);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v41);
        wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v42);
      }
      else
      {
        UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::LoadInternal(a1, &v37);
        v32 = v37;
        if ( *(_QWORD *)(v37 + 16) != *(_QWORD *)(*v11 + 16LL) )
        {
          std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(
            a1 + 1,
            &v37);
          v34 = (Windows::Data::Platform::Partitioning::ActivePartitions *)a1[2];
          a1[2] = 0;
          if ( v34 )
            Windows::Data::Platform::Partitioning::ActivePartitions::`scalar deleting destructor'(v34, v33);
          v32 = v37;
        }
        if ( v32 )
          std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>::operator()();
      }
      return (__int64 *)std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>::~shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>(&hstringHeader);
    }
    else
    {
      v16 = (__int64 *)UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::LoadInternal(
                         a1,
                         &TypeName);
      result = std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(
                 a1 + 1,
                 v16);
      if ( TypeName )
        return (__int64 *)std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>::operator()();
    }
  }
  else
  {
    v12 = (__int64 *)UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::LoadInternal(a1, &TypeName);
    result = std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(
               a1 + 1,
               v12);
    v14 = (unsigned int)TypeName;
    if ( TypeName )
      result = (__int64 *)std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>::operator()();
    v15 = (Windows::Data::Platform::Partitioning::ActivePartitions *)a1[2];
    a1[2] = 0;
    if ( v15 )
      return (__int64 *)Windows::Data::Platform::Partitioning::ActivePartitions::`scalar deleting destructor'(v15, v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800500b4  push    rbp
0x1800500b6  push    rbx
0x1800500b7  push    rsi
0x1800500b8  push    rdi
0x1800500b9  push    r12
0x1800500bb  push    r13
0x1800500bd  push    r14
0x1800500bf  push    r15
0x1800500c1  lea     rbp, [rsp-8]
0x1800500c6  sub     rsp, 108h
0x1800500cd  mov     rax, cs:__security_cookie
0x1800500d4  xor     rax, rsp
0x1800500d7  mov     [rbp+40h+var_48], rax
0x1800500db  mov     r12, rcx
0x1800500de  xor     r15d, r15d
0x1800500e1  mov     [rbp+40h+var_90], r15
0x1800500e5  mov     rsi, [rcx]
0x1800500e8  mov     r14, [rsi]
0x1800500eb  call    ?GetTypeName@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAAPEBGXZ; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetTypeName(void)
0x1800500f0  mov     rdi, rax
0x1800500f3  mov     [rbp+40h+string], r15
0x1800500f7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800500fb  inc     rbx
0x1800500fe  cmp     [rax+rbx*2], r15w
0x180050103  jnz     short loc_1800500FB
0x180050105  mov     eax, 0FFFFFFFFh
0x18005010a  cmp     rbx, rax
0x18005010d  ja      loc_1800504BA
0x180050113  mov     ecx, ebx; unsigned int
0x180050115  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005011a  lea     edx, [rax-1]
0x18005011d  cmp     ebx, eax
0x18005011f  cmovb   edx, ebx; length
0x180050122  lea     r9, [rbp+40h+string]; string
0x180050126  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x18005012a  mov     rcx, rdi; sourceString
0x18005012d  call    cs:__imp_WindowsCreateStringReference
0x180050133  test    eax, eax
0x180050135  jns     short loc_18005014A
0x180050137  xor     r9d, r9d; lpArguments
0x18005013a  xor     r8d, r8d; nNumberOfArguments
0x18005013d  lea     edx, [r9+1]; dwExceptionFlags
0x180050141  mov     ecx, eax; dwExceptionCode
0x180050143  call    cs:__imp_RaiseException
0x180050149  nop
0x18005014a  lea     r8, [rbp+40h+var_90]
0x18005014e  mov     rdx, [rbp+40h+string]
0x180050152  mov     rcx, rsi
0x180050155  mov     rax, [r14+88h]
0x18005015c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050161  mov     rcx, [rbp+48h]; this
0x180050165  test    eax, eax
0x180050167  jns     short loc_18005017E
0x180050169  mov     r9d, eax; char *
0x18005016c  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180050173  mov     edx, 0A3h; void *
0x180050178  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005017e  lea     r13, [r12+8]
0x180050183  cmp     [r13+0], r15
0x180050187  jnz     short loc_1800501E4
0x180050189  lea     rdx, [rsp+140h+var_D0]
0x18005018e  mov     rcx, r12
0x180050191  call    ?LoadInternal@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@W4LoadOptions@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::LoadInternal(Windows::Internal::Storage::Cloud::LoadOptions)
0x180050196  mov     rdx, rax
0x180050199  mov     rcx, r13
0x18005019c  call    ??$?4U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@$0A@@?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>> &&)
0x1800501a1  mov     rdx, [rsp+140h+var_D0]
0x1800501a6  test    rdx, rdx
0x1800501a9  jz      short loc_1800501B0
0x1800501ab  call    ??R?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@QEBAXPEAVSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@Z; std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>::operator()(UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem *)
0x1800501b0  mov     rcx, [r12+10h]; this
0x1800501b5  mov     [r12+10h], r15
0x1800501ba  test    rcx, rcx
0x1800501bd  jz      short loc_1800501C4
0x1800501bf  call    ??_GActivePartitions@Partitioning@Platform@Data@Windows@@QEAAPEAXI@Z; Windows::Data::Platform::Partitioning::ActivePartitions::`scalar deleting destructor'(uint)
0x1800501c4  mov     rcx, [rbp+40h+var_48]
0x1800501c8  xor     rcx, rsp; StackCookie
0x1800501cb  call    __security_check_cookie
0x1800501d0  add     rsp, 108h
0x1800501d7  pop     r15
0x1800501d9  pop     r14
0x1800501db  pop     r13
0x1800501dd  pop     r12
0x1800501df  pop     rdi
0x1800501e0  pop     rsi
0x1800501e1  pop     rbx
0x1800501e2  pop     rbp
0x1800501e3  retn
0x1800501e4  mov     rdx, [r12+10h]
0x1800501e9  test    rdx, rdx
0x1800501ec  jnz     short loc_180050217
0x1800501ee  lea     rdx, [rsp+140h+var_D0]
0x1800501f3  mov     rcx, r12
0x1800501f6  call    ?LoadInternal@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@W4LoadOptions@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::LoadInternal(Windows::Internal::Storage::Cloud::LoadOptions)
0x1800501fb  mov     rdx, rax
0x1800501fe  mov     rcx, r13
0x180050201  call    ??$?4U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@$0A@@?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>> &&)
0x180050206  mov     rdx, [rsp+140h+var_D0]
0x18005020b  test    rdx, rdx
0x18005020e  jz      short loc_1800501C4
0x180050210  call    ??R?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@QEBAXPEAVSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@Z; std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>::operator()(UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem *)
0x180050215  jmp     short loc_1800501C4
0x180050217  mov     rdi, [rbp+40h+var_90]
0x18005021b  lea     rcx, [rsp+140h+var_D0]
0x180050220  call    ??$make_unique@UActivePartitions@Partitioning@Platform@Data@Windows@@AEBU12345@$0A@@std@@YA?AV?$unique_ptr@UActivePartitions@Partitioning@Platform@Data@Windows@@U?$default_delete@UActivePartitions@Partitioning@Platform@Data@Windows@@@std@@@0@AEBUActivePartitions@Partitioning@Platform@Data@Windows@@@Z; std::make_unique<Windows::Data::Platform::Partitioning::ActivePartitions,Windows::Data::Platform::Partitioning::ActivePartitions const &,0>(Windows::Data::Platform::Partitioning::ActivePartitions const &)
0x180050225  mov     rbx, rax
0x180050228  lea     rcx, [rbp+40h+var_A0]
0x18005022c  call    ??$make_shared@Ustate@?$deserializable_data@UActivePartitions@Partitioning@Platform@Data@Windows@@@@$$V@std@@YA?AV?$shared_ptr@Ustate@?$deserializable_data@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@0@XZ; std::make_shared<deserializable_data<Windows::Data::Platform::Partitioning::ActivePartitions>::state,>(void)
0x180050231  mov     rdx, rbx
0x180050234  mov     rcx, [rbp+40h+var_A0]
0x180050238  call    ??$?4UActivePartitions@Partitioning@Platform@Data@Windows@@U?$default_delete@UActivePartitions@Partitioning@Platform@Data@Windows@@@std@@$0A@@?$unique_ptr@$$CBUActivePartitions@Partitioning@Platform@Data@Windows@@U?$default_delete@$$CBUActivePartitions@Partitioning@Platform@Data@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@UActivePartitions@Partitioning@Platform@Data@Windows@@U?$default_delete@UActivePartitions@Partitioning@Platform@Data@Windows@@@std@@@1@@Z; std::unique_ptr<Windows::Data::Platform::Partitioning::ActivePartitions const>::operator=<Windows::Data::Platform::Partitioning::ActivePartitions,std::default_delete<Windows::Data::Platform::Partitioning::ActivePartitions>,0>(std::unique_ptr<Windows::Data::Platform::Partitioning::ActivePartitions> &&)
0x18005023d  nop
0x18005023e  lea     rcx, [rsp+140h+var_D0]
0x180050243  call    ??1?$unique_ptr@UActivePartitions@Partitioning@Platform@Data@Windows@@U?$default_delete@UActivePartitions@Partitioning@Platform@Data@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Data::Platform::Partitioning::ActivePartitions>::~unique_ptr<Windows::Data::Platform::Partitioning::ActivePartitions>(void)
0x180050248  mov     r8, rdi
0x18005024b  lea     rdx, [rbp+40h+var_A0]
0x18005024f  lea     rcx, [rbp+40h+hstringHeader]
0x180050253  call    ??0?$versioned@V?$deserializable_data@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@@QEAA@AEBV?$deserializable_data@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@_K@Z; versioned<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>>::versioned<deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex>>(deserializable_data<Windows::Data::Platform::Partitioning::SystemPartitionIndex> const &,unsigned __int64)
0x180050258  nop
0x180050259  mov     rcx, [rbp+40h+var_98]; this
0x18005025d  test    rcx, rcx
0x180050260  jz      short loc_180050267
0x180050262  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180050267  lea     rcx, [rbp+40h+hstringHeader]
0x18005026b  call    ?serialized@?$deserializable_data@UActivePartitions@Partitioning@Platform@Data@Windows@@@@QEBAAEBVschematized_data@@XZ; deserializable_data<Windows::Data::Platform::Partitioning::ActivePartitions>::serialized(void)
0x180050270  mov     rbx, rax
0x180050273  mov     rcx, [r13+0]
0x180050277  call    ?serialized@?$deserializable_data@UActivePartitions@Partitioning@Platform@Data@Windows@@@@QEBAAEBVschematized_data@@XZ; deserializable_data<Windows::Data::Platform::Partitioning::ActivePartitions>::serialized(void)
0x18005027c  mov     rdx, rax; struct schematized_data *
0x18005027f  mov     rcx, rbx; this
0x180050282  call    ?compare@schematized_data@@QEBAHAEBV1@@Z; schematized_data::compare(schematized_data const &)
0x180050287  test    eax, eax
0x180050289  jz      loc_18005045B
0x18005028f  mov     [rbp+40h+var_A0], r15
0x180050293  lea     rax, [rbp+40h+var_A0]
0x180050297  mov     [rbp+40h+var_C0], rax
0x18005029b  mov     [rbp+40h+var_B8], r15
0x18005029f  mov     [rbp+40h+var_B0], 1
0x1800502a3  lea     rcx, [rbp+40h+hstringHeader]
0x1800502a7  call    ?serialized@?$deserializable_data@UActivePartitions@Partitioning@Platform@Data@Windows@@@@QEBAAEBVschematized_data@@XZ; deserializable_data<Windows::Data::Platform::Partitioning::ActivePartitions>::serialized(void)
0x1800502ac  mov     rcx, rax; this
0x1800502af  call    ?as_blob@schematized_data@@QEBAAEBVblob@bond@@XZ; schematized_data::as_blob(void)
0x1800502b4  lea     rdx, [rbp+40h+var_B8]; struct Windows::Storage::Streams::IBuffer **
0x1800502b8  mov     rcx, rax; struct bond::blob *
0x1800502bb  call    ?ConvertBondBlobToIBuffer@@YAJAEBVblob@bond@@PEAPEAUIBuffer@Streams@Storage@Windows@@@Z; ConvertBondBlobToIBuffer(bond::blob const &,Windows::Storage::Streams::IBuffer * *)
0x1800502c0  mov     rcx, [rbp+48h]; this
0x1800502c4  test    eax, eax
0x1800502c6  jns     short loc_1800502DD
0x1800502c8  mov     r9d, eax; char *
0x1800502cb  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800502d2  mov     edx, 0BAh; void *
0x1800502d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800502dd  lea     rcx, [rbp+40h+var_C0]
0x1800502e1  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x1800502e6  mov     [rbp+40h+var_A8], r15
0x1800502ea  mov     r15, [r12]
0x1800502ee  mov     rax, [r15]
0x1800502f1  mov     r14, [rax+58h]
0x1800502f5  lea     rax, [rbp+40h+var_A8]
0x1800502f9  mov     [rbp+40h+var_C0], rax
0x1800502fd  mov     [rbp+40h+var_B8], 0
0x180050305  mov     [rbp+40h+var_B0], 1
0x180050309  mov     rdi, [rbp+40h+var_A0]
0x18005030d  mov     rsi, qword ptr [rbp+40h+hstringHeader.Reserved+10h]
0x180050311  mov     rax, [r13+0]
0x180050315  mov     rbx, [rax+18h]
0x180050319  mov     rcx, r12
0x18005031c  call    ?GetTypeName@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAAPEBGXZ; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetTypeName(void)
0x180050321  mov     [rsp+140h+var_D0], rax
0x180050326  lea     rdx, [rsp+140h+var_D0]
0x18005032b  lea     rcx, [rbp+40h+var_68]
0x18005032f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180050334  nop
0x180050335  lea     rcx, [rbp+40h+var_B8]
0x180050339  mov     [rsp+140h+var_E8], rcx
0x18005033e  mov     [rsp+140h+var_F0], 0
0x180050347  mov     [rsp+140h+var_F8], 10h
0x18005034f  mov     [rsp+140h+var_100], rdi
0x180050354  mov     [rsp+140h+var_108], rsi
0x180050359  mov     [rsp+140h+var_110], rbx
0x18005035e  mov     rdx, [rax+18h]
0x180050362  mov     [rsp+140h+var_118], rdx
0x180050367  xor     ebx, ebx
0x180050369  mov     qword ptr [rsp+140h+var_120], rbx; int
0x18005036e  xor     r9d, r9d
0x180050371  xor     r8d, r8d
0x180050374  xor     edx, edx
0x180050376  mov     rcx, r15
0x180050379  mov     rax, r14
0x18005037c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050381  mov     rcx, [rbp+48h]; this
0x180050385  test    eax, eax
0x180050387  jns     short loc_18005039E
0x180050389  mov     r9d, eax; char *
0x18005038c  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180050393  mov     edx, 0C2h; void *
0x180050398  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005039e  mov     [rbp+40h+var_50], rbx
0x1800503a2  lea     rcx, [rbp+40h+var_C0]
0x1800503a6  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x1800503ab  mov     [rsp+140h+var_C8], rbx
0x1800503b0  mov     rcx, [rbp+40h+var_A8]
0x1800503b4  mov     rax, [rcx]
0x1800503b7  lea     rdx, [rsp+140h+var_C8]
0x1800503bc  mov     [rbp+40h+var_C0], rdx
0x1800503c0  mov     [rbp+40h+var_B8], rbx
0x1800503c4  mov     [rbp+40h+var_B0], 1
0x1800503c8  lea     rdx, [rbp+40h+var_B8]
0x1800503cc  mov     rax, [rax+38h]
0x1800503d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503d5  mov     rcx, [rbp+48h]; this
0x1800503d9  test    eax, eax
0x1800503db  jns     short loc_1800503F2
0x1800503dd  mov     r9d, eax; char *
0x1800503e0  lea     r8, aOnecoreuapShel_37; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800503e7  mov     edx, 0C5h; void *
0x1800503ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800503f2  lea     rcx, [rbp+40h+var_C0]
0x1800503f6  call    ??1?$out_param_t@V?$com_ptr_t@UIMarshal@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>(void)
0x1800503fb  mov     r8, [rsp+140h+var_C8]
0x180050400  lea     rdx, [rsp+140h+var_D0]
0x180050405  call    ?GetSyncItemFromCloudStoreData@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::GetSyncItemFromCloudStoreData(Windows::Internal::Storage::Cloud::ICloudStoreData *)
0x18005040a  lea     rdx, [rsp+140h+var_D0]
0x18005040f  mov     rcx, r13
0x180050412  call    ??$?4U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@$0A@@?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>> &&)
0x180050417  mov     rcx, [r12+10h]; this
0x18005041c  mov     [r12+10h], rbx
0x180050421  test    rcx, rcx
0x180050424  jz      short loc_18005042B
0x180050426  call    ??_GActivePartitions@Partitioning@Platform@Data@Windows@@QEAAPEAXI@Z; Windows::Data::Platform::Partitioning::ActivePartitions::`scalar deleting destructor'(uint)
0x18005042b  mov     rdx, [rsp+140h+var_D0]
0x180050430  test    rdx, rdx
0x180050433  jz      short loc_18005043B
0x180050435  call    ??R?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@QEBAXPEAVSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@Z; std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>::operator()(UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem *)
0x18005043a  nop
0x18005043b  lea     rcx, [rsp+140h+var_C8]
0x180050440  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180050445  nop
0x180050446  lea     rcx, [rbp+40h+var_A8]
0x18005044a  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18005044f  nop
0x180050450  lea     rcx, [rbp+40h+var_A0]
0x180050454  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180050459  jmp     short loc_1800504AC
0x18005045b  lea     rdx, [rsp+140h+var_C8]
0x180050460  mov     rcx, r12
0x180050463  call    ?LoadInternal@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@AEAA?AV?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@W4LoadOptions@Cloud@Storage@Internal@Windows@@@Z; UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::LoadInternal(Windows::Internal::Storage::Cloud::LoadOptions)
0x180050468  mov     rax, [r13+0]
0x18005046c  mov     rcx, [rax+10h]
0x180050470  mov     rdx, [rsp+140h+var_C8]
0x180050475  cmp     [rdx+10h], rcx
0x180050479  jz      short loc_1800504A1
0x18005047b  lea     rdx, [rsp+140h+var_C8]
0x180050480  mov     rcx, r13
0x180050483  call    ??$?4U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@$0A@@?$unique_ptr@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@U?$default_delete@VSyncItem@?$UpdateManager@UActivePartitions@Partitioning@Platform@Data@Windows@@@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>>::operator=<std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>,0>(std::unique_ptr<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem,std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::ActivePartitions>::SyncItem>> &&)
0x180050488  mov     rcx, [r12+10h]; this
0x18005048d  mov     [r12+10h], r15
0x180050492  test    rcx, rcx
0x180050495  jz      short loc_18005049C
0x180050497  call    ??_GActivePartitions@Partitioning@Platform@Data@Windows@@QEAAPEAXI@Z; Windows::Data::Platform::Partitioning::ActivePartitions::`scalar deleting destructor'(uint)
0x18005049c  mov     rdx, [rsp+140h+var_C8]
0x1800504a1  test    rdx, rdx
0x1800504a4  jz      short loc_1800504AC
0x1800504a6  call    ??R?$default_delete@VSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@std@@QEBAXPEAVSyncItem@?$UpdateManager@USystemPartitionIndex@Partitioning@Platform@Data@Windows@@@@@Z; std::default_delete<UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem>::operator()(UpdateManager<Windows::Data::Platform::Partitioning::SystemPartitionIndex>::SyncItem *)
0x1800504ab  nop
0x1800504ac  lea     rcx, [rbp+40h+hstringHeader]
0x1800504b0  call    ??1?$shared_ptr@VDownloaderCore@Core@Downloader@Cloud@Storage@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>::~shared_ptr<Windows::Internal::Storage::Cloud::Downloader::Core::DownloaderCore>(void)
0x1800504b5  jmp     loc_1800501C4
0x1800504ba  xor     r9d, r9d; lpArguments
0x1800504bd  xor     r8d, r8d; nNumberOfArguments
0x1800504c0  lea     edx, [r9+1]; dwExceptionFlags
0x1800504c4  mov     ecx, 80070216h; dwExceptionCode
0x1800504c9  call    cs:__imp_RaiseException
```
