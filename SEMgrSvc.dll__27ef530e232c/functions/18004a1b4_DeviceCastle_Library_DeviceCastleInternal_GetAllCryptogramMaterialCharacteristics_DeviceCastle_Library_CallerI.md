# DeviceCastle::Library::DeviceCastleInternal::GetAllCryptogramMaterialCharacteristics(DeviceCastle::Library::CallerIdentity &,HWND__ *,UnlockPromptingBehavior,ushort const *,_GetAllCryptogramMaterialCharacteristicsResult * *)

- ea: `0x18004a1b4`
- end: `0x18004ab30`
- name: `?GetAllCryptogramMaterialCharacteristics@DeviceCastleInternal@Library@DeviceCastle@@QEAAJAEAVCallerIdentity@23@PEAUHWND__@@W4UnlockPromptingBehavior@@PEBGPEAPEAU_GetAllCryptogramMaterialCharacteristicsResult@@@Z`
- size: `2428`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042b00`

## callees

- `0x180004ec0`
- `0x180005858`
- `0x180012680`
- `0x1800126a8`
- `0x1800194a8`
- `0x180046160`
- `0x180048d2c`
- `0x180048ee4`
- `0x180049234`
- `0x180049458`
- `0x180049908`
- `0x1800499b4`
- `0x180049bc8`
- `0x18004a1b4`
- `0x18004d298`
- `0x18004d358`
- `0x18004d9d4`
- `0x18004db3c`
- `0x18004dc80`
- `0x18004dd60`
- `0x180054248`
- `0x180054650`
- `0x18005a4f8`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a4ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a9f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aafd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ab13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a4ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a9f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aafd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ab13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a54d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a605`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a6bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a54d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a605`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a6bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DeviceCastle::Library::DeviceCastleInternal::GetAllCryptogramMaterialCharacteristics(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        void *a6)
{
  _QWORD *v8; // r12
  int IsPrepared; // ebx
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int64 v13; // rbx
  __int64 *v14; // rcx
  __int64 v15; // rdi
  unsigned __int64 v16; // rax
  _QWORD *v17; // rdx
  void *v18; // rax
  __int64 v19; // rdi
  __int64 *v20; // r9
  _QWORD *v21; // r8
  __int64 v22; // rax
  unsigned __int64 v23; // r14
  __int64 v24; // rcx
  __int64 v25; // rbx
  _QWORD *v26; // rdx
  const unsigned __int16 *v27; // rdx
  _QWORD *cotaskmem_string; // rax
  __int64 v29; // r15
  __int64 v30; // rsi
  unsigned __int64 v31; // rcx
  __int64 v32; // rdi
  LPVOID v33; // rax
  __int64 v34; // rcx
  __int64 v35; // r9
  __int64 **v36; // rcx
  __int64 *n; // rax
  __int64 v38; // rsi
  unsigned __int64 v39; // rcx
  __int64 v40; // rdi
  LPVOID v41; // rax
  __int64 v42; // rcx
  __int64 v43; // r9
  __int64 **v44; // rcx
  __int64 *ii; // rax
  __int64 v46; // rsi
  unsigned __int64 v47; // rcx
  __int64 v48; // rdi
  LPVOID v49; // rax
  __int64 v50; // rcx
  __int64 v51; // r9
  __int64 **v52; // rcx
  __int64 *jj; // rax
  _DWORD *v54; // rdi
  unsigned __int64 v55; // rax
  void *v56; // rcx
  bool v57; // zf
  void *v58; // rcx
  volatile signed __int32 *v59; // rbx
  void *v60; // rcx
  void *v61; // rcx
  volatile signed __int32 *v62; // rdi
  void *v63; // rcx
  LPVOID v64; // rax
  _QWORD *v65; // rcx
  _QWORD *i; // rax
  _QWORD *v67; // rcx
  _QWORD *j; // rax
  _QWORD *v69; // rcx
  _QWORD *k; // rax
  _QWORD *v71; // rcx
  _QWORD *m; // rax
  void *v73; // rcx
  void *v74; // rcx
  volatile signed __int32 *v75; // rbx
  volatile signed __int32 *v76; // rdi
  void *v78; // rcx
  void *v79; // rcx
  LPVOID v80; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v81; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v82; // [rsp+38h] [rbp-C8h]
  __int128 v83; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v84; // [rsp+50h] [rbp-B0h]
  __int128 v85; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v86; // [rsp+68h] [rbp-98h]
  __int128 v87; // [rsp+70h] [rbp-90h] BYREF
  __int64 v88; // [rsp+80h] [rbp-80h]
  __int128 v89; // [rsp+88h] [rbp-78h] BYREF
  __int64 v90; // [rsp+98h] [rbp-68h]
  LPVOID v91; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v92; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v93; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v95[144]; // [rsp+D0h] [rbp-30h] BYREF

  DeviceCastle::Library::Internal::ProtectionKeyManager::ProtectionKeyManager(v95);
  v93 = 0;
  v87 = 0;
  v88 = 0;
  v8 = a6;
  if ( !a6 )
  {
    IsPrepared = -2147467261;
    goto LABEL_115;
  }
  *(_QWORD *)a6 = 0;
  if ( !(unsigned __int8)DeviceCastle::Library::ValidOrDefaultName(&a5) )
  {
    IsPrepared = -2134834648;
    goto LABEL_115;
  }
  if ( !(unsigned __int8)DeviceCastle::Library::Internal::DeviceCastleDatabase::PrepareNamedCryptogramMaterialPackage(
                           a1 + 176,
                           a2,
                           a5,
                           &v93) )
  {
    IsPrepared = -2134834660;
    goto LABEL_115;
  }
  IsPrepared = DeviceCastle::Library::DeviceCastleInternal::VerifyPackageIsPrepared(a1, a2, v95, &v93);
  if ( IsPrepared < 0 )
    goto LABEL_115;
  if ( !(unsigned __int8)DeviceCastle::Library::Internal::CryptogramMaterialPackageManager::EnumerateMaterials(
                           *(_QWORD *)(v93 + 72),
                           &v87) )
  {
LABEL_114:
    IsPrepared = 0;
    goto LABEL_115;
  }
  v92 = 0;
  wil::make_unique_cotaskmem<_GetAllCryptogramMaterialPackageCharacteristicsResult,>(&v80);
  wil::make_unique_cotaskmem<_CryptogramMaterialCharacteristics [0]>(&a6, (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 5);
  v89 = 0;
  v90 = 0;
  v85 = 0;
  v86 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  memset_0(a6, 0, 72 * ((__int64)(*((_QWORD *)&v87 + 1) - v87) >> 5));
  *(_OWORD *)v80 = 0;
  v10 = (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 5;
  if ( v10 > 0xFFFFFFFF )
  {
    *(_DWORD *)v80 = -1;
    std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v83);
    std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v81);
    std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v85);
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v89);
    v78 = a6;
    a6 = 0;
    if ( v78 )
      CoTaskMemFree(v78);
    v79 = v80;
    v80 = 0;
    if ( v79 )
      CoTaskMemFree(v79);
LABEL_124:
    IsPrepared = -2147024362;
    goto LABEL_115;
  }
  *(_DWORD *)v80 = v10;
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::reserve(
    &v89,
    (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 5);
  std::vector<wistd::unique_ptr<enum CryptogramAlgorithm,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::reserve(
    &v85,
    (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 5);
  v11 = *((_QWORD *)&v87 + 1);
  v12 = v87;
  v13 = (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 5;
  v14 = (__int64 *)v81;
  if ( v13 > (v82 - (__int64)v81) >> 3 )
  {
    if ( v13 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Xlength();
    v15 = *((_QWORD *)&v81 + 1) - v81;
    v16 = 8 * v13;
    if ( 8 * v13 )
    {
      if ( v16 < 0x1000 )
      {
        v17 = operator new(8 * v13);
      }
      else
      {
        if ( v16 + 39 < v16 )
          __scrt_throw_std_bad_array_new_length();
        v18 = operator new(v16 + 39);
        if ( !v18 )
          __fastfail(5u);
        v17 = (_QWORD *)(((unsigned __int64)v18 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v17 - 1) = v18;
      }
      v14 = (__int64 *)v81;
    }
    else
    {
      v17 = 0;
    }
    v19 = v15 >> 3;
    v20 = (__int64 *)*((_QWORD *)&v81 + 1);
    v21 = v17;
    while ( v14 != v20 )
    {
      v22 = *v14;
      *v14 = 0;
      *v21++ = v22;
      ++v14;
    }
    std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Change_array(
      &v81,
      v17,
      v19,
      v13);
    v11 = *((_QWORD *)&v87 + 1);
    v12 = v87;
  }
  std::vector<wistd::unique_ptr<enum CryptogramAlgorithm,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::reserve(
    &v83,
    (v11 - v12) >> 5);
  v23 = 0;
  v24 = v87;
  if ( !((__int64)(*((_QWORD *)&v87 + 1) - v87) >> 5) )
  {
LABEL_94:
    v63 = a6;
    a6 = 0;
    *((_QWORD *)v80 + 1) = v63;
    v64 = v80;
    v80 = 0;
    *v8 = v64;
    v65 = (_QWORD *)*((_QWORD *)&v85 + 1);
    for ( i = (_QWORD *)v85; i != v65; ++i )
      *i = 0;
    v67 = (_QWORD *)*((_QWORD *)&v81 + 1);
    for ( j = (_QWORD *)v81; j != v67; ++j )
      *j = 0;
    v69 = (_QWORD *)*((_QWORD *)&v83 + 1);
    for ( k = (_QWORD *)v83; k != v69; ++k )
      *k = 0;
    v71 = (_QWORD *)*((_QWORD *)&v89 + 1);
    for ( m = (_QWORD *)v89; m != v71; ++m )
      *m = 0;
    std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v83);
    std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v81);
    std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v85);
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v89);
    v73 = a6;
    a6 = 0;
    if ( v73 )
      CoTaskMemFree(v73);
    v74 = v80;
    v80 = 0;
    if ( v74 )
      CoTaskMemFree(v74);
    v75 = (volatile signed __int32 *)*((_QWORD *)&v92 + 1);
    if ( *((_QWORD *)&v92 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v92 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
        if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
      }
    }
    goto LABEL_114;
  }
  while ( 1 )
  {
    v25 = 32 * v23;
    v26 = (_QWORD *)(32 * v23 + v24);
    if ( v26[3] > 7u )
      v26 = (_QWORD *)*v26;
    if ( !(unsigned __int8)DeviceCastle::Library::Internal::CryptogramMaterialPackageManager::LookupMaterial(
                             *(_QWORD *)(v93 + 72),
                             v26,
                             &v92) )
      break;
    v27 = (const unsigned __int16 *)(v25 + v87);
    if ( *(_QWORD *)(v25 + v87 + 24) > 7u )
      v27 = *(const unsigned __int16 **)v27;
    cotaskmem_string = (_QWORD *)wil::make_cotaskmem_string((wil *)&pv, v27, *(_QWORD *)(v25 + v87 + 16));
    if ( *((_QWORD *)&v89 + 1) == v90 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v89,
        *((_QWORD *)&v89 + 1),
        cotaskmem_string);
    }
    else
    {
      **((_QWORD **)&v89 + 1) = *cotaskmem_string;
      *cotaskmem_string = 0;
      *((_QWORD *)&v89 + 1) += 8LL;
    }
    if ( pv )
      CoTaskMemFree(pv);
    *((_QWORD *)a6 + 9 * v23) = *(_QWORD *)(v89 + 8 * v23);
    v29 = v92;
    v30 = *(_QWORD *)(v92 + 48);
    v31 = 0;
    if ( v30 )
      v31 = *(_QWORD *)(v30 + 16);
    if ( v31 > 0xFFFFFFFF )
    {
      *((_DWORD *)a6 + 18 * v23 + 2) = -1;
      goto LABEL_77;
    }
    *((_DWORD *)a6 + 18 * v23 + 2) = v31;
    if ( v31 )
    {
      v32 = (__int64)(*((_QWORD *)&v85 + 1) - v85) >> 3;
      v33 = CoTaskMemAlloc(4 * v31);
      v91 = v33;
      if ( *((_QWORD *)&v85 + 1) == v86 )
      {
        std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Emplace_reallocate<enum CryptogramMaterialPackageConfirmationResponseFormat *>(
          &v85,
          *((_QWORD *)&v85 + 1),
          &v91);
      }
      else
      {
        **((_QWORD **)&v85 + 1) = v33;
        *((_QWORD *)&v85 + 1) += 8LL;
      }
      v34 = *(_QWORD *)(v85 + 8 * v32);
      if ( !v34 )
      {
LABEL_72:
        IsPrepared = -2147024882;
        goto LABEL_86;
      }
      v35 = 0;
      *((_QWORD *)a6 + 9 * v23 + 2) = v34;
      v36 = *(__int64 ***)(v30 + 8);
      for ( n = *v36; n != (__int64 *)v36; n = (__int64 *)*n )
        *(_DWORD *)(*(_QWORD *)(v85 + 8 * v32) + 4 * v35++) = *((_DWORD *)n + 4);
    }
    v38 = *(_QWORD *)(v29 + 40);
    v39 = 0;
    if ( v38 )
      v39 = *(_QWORD *)(v38 + 16);
    if ( v39 > 0xFFFFFFFF )
    {
      *((_DWORD *)a6 + 18 * v23 + 6) = -1;
      goto LABEL_77;
    }
    *((_DWORD *)a6 + 18 * v23 + 6) = v39;
    if ( v39 )
    {
      v40 = (__int64)(*((_QWORD *)&v81 + 1) - v81) >> 3;
      v41 = CoTaskMemAlloc(4 * v39);
      v91 = v41;
      if ( *((_QWORD *)&v81 + 1) == v82 )
      {
        std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Emplace_reallocate<enum CryptogramMaterialPackageConfirmationResponseFormat *>(
          &v81,
          *((_QWORD *)&v81 + 1),
          &v91);
      }
      else
      {
        **((_QWORD **)&v81 + 1) = v41;
        *((_QWORD *)&v81 + 1) += 8LL;
      }
      v42 = *(_QWORD *)(v81 + 8 * v40);
      if ( !v42 )
        goto LABEL_72;
      v43 = 0;
      *((_QWORD *)a6 + 9 * v23 + 4) = v42;
      v44 = *(__int64 ***)(v38 + 8);
      for ( ii = *v44; ii != (__int64 *)v44; ii = (__int64 *)*ii )
        *(_DWORD *)(*(_QWORD *)(v81 + 8 * v40) + 4 * v43++) = *((_DWORD *)ii + 4);
    }
    v46 = *(_QWORD *)(v29 + 56);
    v47 = 0;
    if ( v46 )
      v47 = *(_QWORD *)(v46 + 16);
    if ( v47 > 0xFFFFFFFF )
    {
      *((_DWORD *)a6 + 18 * v23 + 10) = -1;
      goto LABEL_77;
    }
    *((_DWORD *)a6 + 18 * v23 + 10) = v47;
    if ( v47 )
    {
      v48 = (__int64)(*((_QWORD *)&v83 + 1) - v83) >> 3;
      v49 = CoTaskMemAlloc(4 * v47);
      v91 = v49;
      if ( *((_QWORD *)&v83 + 1) == v84 )
      {
        std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Emplace_reallocate<enum CryptogramMaterialPackageConfirmationResponseFormat *>(
          &v83,
          *((_QWORD *)&v83 + 1),
          &v91);
      }
      else
      {
        **((_QWORD **)&v83 + 1) = v49;
        *((_QWORD *)&v83 + 1) += 8LL;
      }
      v50 = *(_QWORD *)(v83 + 8 * v48);
      if ( !v50 )
        goto LABEL_72;
      v51 = 0;
      *((_QWORD *)a6 + 9 * v23 + 6) = v50;
      v52 = *(__int64 ***)(v46 + 8);
      for ( jj = *v52; jj != (__int64 *)v52; jj = (__int64 *)*jj )
        *(_DWORD *)(*(_QWORD *)(v83 + 8 * v48) + 4 * v51++) = *((_DWORD *)jj + 4);
    }
    *((_DWORD *)a6 + 18 * v23 + 14) = *(_DWORD *)(v29 + 64);
    *((_DWORD *)a6 + 18 * v23 + 15) = *(_DWORD *)(v29 + 68);
    *((_DWORD *)a6 + 18 * v23 + 16) = *(_DWORD *)(v29 + 68) != 0 ? 2 : 0;
    v54 = a6;
    v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v29 + 8) + 96LL))(v29 + 8);
    if ( v55 > 0xFFFFFFFF )
    {
      v54[18 * v23 + 17] = -1;
LABEL_77:
      std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v83);
      std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v81);
      std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v85);
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v89);
      v56 = a6;
      v57 = a6 == 0;
      a6 = 0;
      if ( !v57 )
        CoTaskMemFree(v56);
      v58 = v80;
      v57 = v80 == 0;
      v80 = 0;
      if ( !v57 )
        CoTaskMemFree(v58);
      v59 = (volatile signed __int32 *)*((_QWORD *)&v92 + 1);
      if ( *((_QWORD *)&v92 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v92 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
          if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
        }
      }
      goto LABEL_124;
    }
    v54[18 * v23++ + 17] = v55;
    v24 = v87;
    if ( v23 >= (__int64)(*((_QWORD *)&v87 + 1) - v87) >> 5 )
      goto LABEL_94;
  }
  IsPrepared = -2134834653;
LABEL_86:
  std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v83);
  std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v81);
  std::vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~vector<wistd::unique_ptr<enum CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v85);
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v89);
  v60 = a6;
  v57 = a6 == 0;
  a6 = 0;
  if ( !v57 )
    CoTaskMemFree(v60);
  v61 = v80;
  v57 = v80 == 0;
  v80 = 0;
  if ( !v57 )
    CoTaskMemFree(v61);
  v62 = (volatile signed __int32 *)*((_QWORD *)&v92 + 1);
  if ( *((_QWORD *)&v92 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v92 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
      if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
    }
  }
LABEL_115:
  std::vector<std::wstring>::_Tidy(&v87);
  v76 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
  if ( *((_QWORD *)&v93 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
      if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
    }
  }
  DeviceCastle::Library::Internal::ProtectionKeyManager::~ProtectionKeyManager((DeviceCastle::Library::Internal::ProtectionKeyManager *)v95);
  return (unsigned int)IsPrepared;
}

```

## disassembly

```asm
0x18004a1b4  push    rbp
0x18004a1b6  push    rbx
0x18004a1b7  push    rsi
0x18004a1b8  push    rdi
0x18004a1b9  push    r12
0x18004a1bb  push    r13
0x18004a1bd  push    r14
0x18004a1bf  push    r15
0x18004a1c1  lea     rbp, [rsp-28h]
0x18004a1c6  sub     rsp, 128h
0x18004a1cd  mov     rbx, rdx
0x18004a1d0  mov     rdi, rcx
0x18004a1d3  xor     r13d, r13d
0x18004a1d6  lea     rcx, [rbp+60h+var_90]
0x18004a1da  call    ??0ProtectionKeyManager@Internal@Library@DeviceCastle@@QEAA@AEAVCallerIdentity@23@PEAUHWND__@@W4UnlockPromptingBehavior@@@Z; DeviceCastle::Library::Internal::ProtectionKeyManager::ProtectionKeyManager(DeviceCastle::Library::CallerIdentity &,HWND__ *,UnlockPromptingBehavior)
0x18004a1df  nop
0x18004a1e0  xorps   xmm0, xmm0
0x18004a1e3  movdqu  [rbp+60h+var_A8], xmm0
0x18004a1e8  movdqu  [rsp+160h+var_F0], xmm0
0x18004a1ee  mov     [rbp+60h+var_E0], r13
0x18004a1f2  mov     r12, [rbp+60h+arg_28]
0x18004a1f9  test    r12, r12
0x18004a1fc  jnz     short loc_18004A208
0x18004a1fe  mov     ebx, 80004003h
0x18004a203  jmp     loc_18004AA52
0x18004a208  mov     [r12], r13
0x18004a20c  lea     rcx, [rbp+60h+arg_20]
0x18004a213  call    DeviceCastle__Library__ValidOrDefaultName
0x18004a218  test    al, al
0x18004a21a  jnz     short loc_18004A226
0x18004a21c  mov     ebx, 80C10228h
0x18004a221  jmp     loc_18004AA52
0x18004a226  lea     rcx, [rdi+0B0h]
0x18004a22d  lea     r9, [rbp+60h+var_A8]
0x18004a231  mov     r8, [rbp+60h+arg_20]
0x18004a238  mov     rdx, rbx
0x18004a23b  call    ?PrepareNamedCryptogramMaterialPackage@DeviceCastleDatabase@Internal@Library@DeviceCastle@@QEAA_NAEAVCallerIdentity@34@PEBGAEAV?$shared_ptr@VExposedCryptogramMaterialInformation@Internal@Library@DeviceCastle@@@std@@@Z; DeviceCastle::Library::Internal::DeviceCastleDatabase::PrepareNamedCryptogramMaterialPackage(DeviceCastle::Library::CallerIdentity &,ushort const *,std::shared_ptr<DeviceCastle::Library::Internal::ExposedCryptogramMaterialInformation> &)
0x18004a240  test    al, al
0x18004a242  jnz     short loc_18004A24E
0x18004a244  mov     ebx, 80C1021Ch
0x18004a249  jmp     loc_18004AA52
0x18004a24e  lea     r9, [rbp+60h+var_A8]
0x18004a252  lea     r8, [rbp+60h+var_90]
0x18004a256  mov     rdx, rbx
0x18004a259  mov     rcx, rdi
0x18004a25c  call    ?VerifyPackageIsPrepared@DeviceCastleInternal@Library@DeviceCastle@@AEAAJAEAVCallerIdentity@23@AEAVProtectionKeyManager@Internal@23@AEBV?$shared_ptr@VExposedCryptogramMaterialInformation@Internal@Library@DeviceCastle@@@std@@@Z; DeviceCastle::Library::DeviceCastleInternal::VerifyPackageIsPrepared(DeviceCastle::Library::CallerIdentity &,DeviceCastle::Library::Internal::ProtectionKeyManager &,std::shared_ptr<DeviceCastle::Library::Internal::ExposedCryptogramMaterialInformation> const &)
0x18004a261  mov     ebx, eax
0x18004a263  test    eax, eax
0x18004a265  js      loc_18004AA52
0x18004a26b  lea     rdx, [rsp+160h+var_F0]
0x18004a270  mov     rcx, qword ptr [rbp+60h+var_A8]
0x18004a274  mov     rcx, [rcx+48h]
0x18004a278  call    ?EnumerateMaterials@CryptogramMaterialPackageManager@Internal@Library@DeviceCastle@@QEBA_NAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; DeviceCastle::Library::Internal::CryptogramMaterialPackageManager::EnumerateMaterials(std::vector<std::wstring> &)
0x18004a27d  test    al, al
0x18004a27f  jz      loc_18004AA4F
0x18004a285  xorps   xmm0, xmm0
0x18004a288  movdqu  [rbp+60h+var_B8], xmm0
0x18004a28d  lea     rcx, [rsp+160h+var_140]
0x18004a292  call    ??$make_unique_cotaskmem@U_GetAllCryptogramMaterialPackageCharacteristicsResult@@$$V@wil@@YA?AV?$unique_ptr@U_GetAllCryptogramMaterialPackageCharacteristicsResult@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<_GetAllCryptogramMaterialPackageCharacteristicsResult,>(void)
0x18004a297  nop
0x18004a298  mov     rdx, qword ptr [rsp+160h+var_F0+8]
0x18004a29d  sub     rdx, qword ptr [rsp+160h+var_F0]
0x18004a2a2  sar     rdx, 5
0x18004a2a6  lea     rcx, [rbp+60h+arg_28]
0x18004a2ad  call    ??$make_unique_cotaskmem@$$BY0A@U_CryptogramMaterialCharacteristics@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_CryptogramMaterialCharacteristics@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<_CryptogramMaterialCharacteristics [0]>(unsigned __int64)
0x18004a2b2  nop
0x18004a2b3  xorps   xmm0, xmm0
0x18004a2b6  movdqu  [rbp+60h+var_D8], xmm0
0x18004a2bb  mov     [rbp+60h+var_C8], r13
0x18004a2bf  movdqu  [rsp+160h+var_108], xmm0
0x18004a2c5  mov     [rsp+160h+var_F8], r13
0x18004a2ca  movdqu  [rsp+160h+var_138], xmm0
0x18004a2d0  mov     [rsp+160h+var_128], r13
0x18004a2d5  movdqu  [rsp+160h+var_120], xmm0
0x18004a2db  mov     [rsp+160h+var_110], r13
0x18004a2e0  mov     rax, qword ptr [rsp+160h+var_F0+8]
0x18004a2e5  sub     rax, qword ptr [rsp+160h+var_F0]
0x18004a2ea  sar     rax, 5
0x18004a2ee  lea     r8, [rax+rax*8]
0x18004a2f2  shl     r8, 3; Size
0x18004a2f6  xor     edx, edx; Val
0x18004a2f8  mov     rcx, [rbp+60h+arg_28]; void *
0x18004a2ff  call    memset_0
0x18004a304  xorps   xmm0, xmm0
0x18004a307  mov     rax, [rsp+160h+var_140]
0x18004a30c  movups  xmmword ptr [rax], xmm0
0x18004a30f  mov     rax, [rsp+160h+var_140]
0x18004a314  mov     rcx, qword ptr [rsp+160h+var_F0+8]
0x18004a319  sub     rcx, qword ptr [rsp+160h+var_F0]
0x18004a31e  sar     rcx, 5
0x18004a322  mov     edi, 0FFFFFFFFh
0x18004a327  cmp     rcx, rdi
0x18004a32a  ja      loc_18004AABD
0x18004a330  mov     [rax], ecx
0x18004a332  mov     rdx, qword ptr [rsp+160h+var_F0+8]
0x18004a337  sub     rdx, qword ptr [rsp+160h+var_F0]
0x18004a33c  sar     rdx, 5
0x18004a340  lea     rcx, [rbp+60h+var_D8]
0x18004a344  call    ?reserve@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX_K@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x18004a349  mov     rdx, qword ptr [rsp+160h+var_F0+8]
0x18004a34e  sub     rdx, qword ptr [rsp+160h+var_F0]
0x18004a353  sar     rdx, 5
0x18004a357  lea     rcx, [rsp+160h+var_108]
0x18004a35c  call    ?reserve@?$vector@V?$unique_ptr@W4CryptogramAlgorithm@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@W4CryptogramAlgorithm@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAAX_K@Z; std::vector<wistd::unique_ptr<CryptogramAlgorithm,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::reserve(unsigned __int64)
0x18004a361  mov     rdx, qword ptr [rsp+160h+var_F0+8]
0x18004a366  mov     rbx, rdx
0x18004a369  mov     r8, qword ptr [rsp+160h+var_F0]
0x18004a36e  sub     rbx, r8
0x18004a371  sar     rbx, 5
0x18004a375  mov     rax, [rsp+160h+var_128]
0x18004a37a  mov     rcx, qword ptr [rsp+160h+var_138]
0x18004a37f  sub     rax, rcx
0x18004a382  sar     rax, 3
0x18004a386  cmp     rbx, rax
0x18004a389  jbe     loc_18004A441
0x18004a38f  mov     rax, 1FFFFFFFFFFFFFFFh
0x18004a399  cmp     rbx, rax
0x18004a39c  ja      loc_18004AB2A
0x18004a3a2  mov     rdi, qword ptr [rsp+160h+var_138+8]
0x18004a3a7  sub     rdi, rcx
0x18004a3aa  lea     rax, ds:0[rbx*8]
0x18004a3b2  test    rax, rax
0x18004a3b5  jnz     short loc_18004A3BC
0x18004a3b7  mov     rdx, r13
0x18004a3ba  jmp     short loc_18004A3FE
0x18004a3bc  cmp     rax, 1000h
0x18004a3c2  jb      short loc_18004A3EE
0x18004a3c4  lea     rcx, [rax+27h]; Size
0x18004a3c8  cmp     rcx, rax
0x18004a3cb  jbe     loc_18004AB24
0x18004a3d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a3d6  test    rax, rax
0x18004a3d9  jnz     short loc_18004A3E0
0x18004a3db  lea     ecx, [rax+5]
0x18004a3de  int     29h; Win8: RtlFailFast(ecx)
0x18004a3e0  lea     rdx, [rax+27h]
0x18004a3e4  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18004a3e8  mov     [rdx-8], rax
0x18004a3ec  jmp     short loc_18004A3F9
0x18004a3ee  mov     rcx, rax; Size
0x18004a3f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a3f6  mov     rdx, rax
0x18004a3f9  mov     rcx, qword ptr [rsp+160h+var_138]
0x18004a3fe  sar     rdi, 3
0x18004a402  mov     r9, qword ptr [rsp+160h+var_138+8]
0x18004a407  mov     r8, rdx
0x18004a40a  jmp     short loc_18004A41D
0x18004a40c  mov     rax, [rcx]
0x18004a40f  mov     [rcx], r13
0x18004a412  mov     [r8], rax
0x18004a415  lea     r8, [r8+8]
0x18004a419  add     rcx, 8
0x18004a41d  cmp     rcx, r9
0x18004a420  jnz     short loc_18004A40C
0x18004a422  mov     r9, rbx
0x18004a425  mov     r8, rdi
0x18004a428  lea     rcx, [rsp+160h+var_138]
0x18004a42d  call    ?_Change_array@?$vector@V?$unique_ptr@W4CryptogramMaterialPackageConfirmationResponseFormat@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@W4CryptogramMaterialPackageConfirmationResponseFormat@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXQEAV?$unique_ptr@W4CryptogramMaterialPackageConfirmationResponseFormat@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K1@Z; std::vector<wistd::unique_ptr<CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Change_array(wistd::unique_ptr<CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> * const,unsigned __int64,unsigned __int64)
0x18004a432  mov     rdx, qword ptr [rsp+160h+var_F0+8]
0x18004a437  mov     r8, qword ptr [rsp+160h+var_F0]
0x18004a43c  mov     edi, 0FFFFFFFFh
0x18004a441  sub     rdx, r8
0x18004a444  sar     rdx, 5
0x18004a448  lea     rcx, [rsp+160h+var_120]
0x18004a44d  call    ?reserve@?$vector@V?$unique_ptr@W4CryptogramAlgorithm@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@W4CryptogramAlgorithm@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAAX_K@Z; std::vector<wistd::unique_ptr<CryptogramAlgorithm,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::reserve(unsigned __int64)
0x18004a452  mov     r14, r13
0x18004a455  mov     rax, qword ptr [rsp+160h+var_F0+8]
0x18004a45a  mov     rcx, qword ptr [rsp+160h+var_F0]
0x18004a45f  sub     rax, rcx
0x18004a462  sar     rax, 5
0x18004a466  test    rax, rax
0x18004a469  jz      loc_18004A931
0x18004a46f  mov     rax, qword ptr [rbp+60h+var_A8]
0x18004a473  mov     rbx, r14
0x18004a476  shl     rbx, 5
0x18004a47a  lea     rdx, [rbx+rcx]
0x18004a47e  cmp     qword ptr [rdx+18h], 7
0x18004a483  jbe     short loc_18004A488
0x18004a485  mov     rdx, [rdx]
0x18004a488  lea     r8, [rbp+60h+var_B8]
0x18004a48c  mov     rcx, [rax+48h]
0x18004a490  call    ?LookupMaterial@CryptogramMaterialPackageManager@Internal@Library@DeviceCastle@@QEBA_NPEBGAEAV?$shared_ptr@VMaterialManager@Internal@Library@DeviceCastle@@@std@@@Z; DeviceCastle::Library::Internal::CryptogramMaterialPackageManager::LookupMaterial(ushort const *,std::shared_ptr<DeviceCastle::Library::Internal::MaterialManager> &)
0x18004a495  test    al, al
0x18004a497  jz      loc_18004A880
0x18004a49d  mov     rdx, qword ptr [rsp+160h+var_F0]
0x18004a4a2  add     rdx, rbx
0x18004a4a5  mov     r8, [rdx+10h]; unsigned __int64
0x18004a4a9  cmp     qword ptr [rdx+18h], 7
0x18004a4ae  jbe     short loc_18004A4B3
0x18004a4b0  mov     rdx, [rdx]; unsigned __int16 *
0x18004a4b3  lea     rcx, [rbp+60h+pv]; this
0x18004a4b7  call    ?make_cotaskmem_string@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string(ushort const *,unsigned __int64)
0x18004a4bc  nop
0x18004a4bd  mov     rdx, qword ptr [rbp+60h+var_D8+8]
0x18004a4c1  cmp     rdx, [rbp+60h+var_C8]
0x18004a4c5  jz      short loc_18004A4D7
0x18004a4c7  mov     rcx, [rax]
0x18004a4ca  mov     [rdx], rcx
0x18004a4cd  mov     [rax], r13
0x18004a4d0  add     qword ptr [rbp+60h+var_D8+8], 8
0x18004a4d5  jmp     short loc_18004A4E4
0x18004a4d7  mov     r8, rax
0x18004a4da  lea     rcx, [rbp+60h+var_D8]
0x18004a4de  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004a4e3  nop
0x18004a4e4  mov     rcx, [rbp+60h+pv]; pv
0x18004a4e8  test    rcx, rcx
0x18004a4eb  jz      short loc_18004A4F3
0x18004a4ed  call    cs:__imp_CoTaskMemFree
0x18004a4f3  lea     rbx, [r14+r14*8]
0x18004a4f7  mov     rax, qword ptr [rbp+60h+var_D8]
0x18004a4fb  mov     rcx, [rax+r14*8]
0x18004a4ff  mov     rax, [rbp+60h+arg_28]
0x18004a506  mov     [rax+rbx*8], rcx
0x18004a50a  mov     r15, qword ptr [rbp+60h+var_B8]
0x18004a50e  mov     rsi, [r15+30h]
0x18004a512  test    rsi, rsi
0x18004a515  mov     rcx, r13
0x18004a518  jz      short loc_18004A51E
0x18004a51a  mov     rcx, [rsi+10h]
0x18004a51e  mov     rax, [rbp+60h+arg_28]
0x18004a525  cmp     rcx, rdi
0x18004a528  ja      loc_18004A7D0
0x18004a52e  mov     [rax+rbx*8+8], ecx
0x18004a532  test    rcx, rcx
0x18004a535  jz      loc_18004A5C6
0x18004a53b  mov     rdi, qword ptr [rsp+160h+var_108+8]
0x18004a540  sub     rdi, qword ptr [rsp+160h+var_108]
0x18004a545  sar     rdi, 3
0x18004a549  shl     rcx, 2; cb
0x18004a54d  call    cs:__imp_CoTaskMemAlloc
0x18004a553  mov     [rbp+60h+var_C0], rax
0x18004a557  mov     rdx, qword ptr [rsp+160h+var_108+8]
0x18004a55c  cmp     rdx, [rsp+160h+var_F8]
0x18004a561  jz      short loc_18004A56E
0x18004a563  mov     [rdx], rax
0x18004a566  add     qword ptr [rsp+160h+var_108+8], 8
0x18004a56c  jmp     short loc_18004A57C
0x18004a56e  lea     r8, [rbp+60h+var_C0]
0x18004a572  lea     rcx, [rsp+160h+var_108]
0x18004a577  call    ??$_Emplace_reallocate@PEAW4CryptogramMaterialPackageConfirmationResponseFormat@@@?$vector@V?$unique_ptr@W4CryptogramMaterialPackageConfirmationResponseFormat@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@W4CryptogramMaterialPackageConfirmationResponseFormat@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAPEAV?$unique_ptr@W4CryptogramMaterialPackageConfirmationResponseFormat@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAV23@$$QEAPEAW4CryptogramMaterialPackageConfirmationResponseFormat@@@Z; std::vector<wistd::unique_ptr<CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Emplace_reallocate<CryptogramMaterialPackageConfirmationResponseFormat *>(wistd::unique_ptr<CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> * const,CryptogramMaterialPackageConfirmationResponseFormat * &&)
0x18004a57c  mov     rax, qword ptr [rsp+160h+var_108]
0x18004a581  mov     rcx, [rax+rdi*8]
0x18004a585  test    rcx, rcx
0x18004a588  jz      loc_18004A7B4
0x18004a58e  mov     r9, r13
0x18004a591  mov     rax, [rbp+60h+arg_28]
0x18004a598  mov     [rax+rbx*8+10h], rcx
0x18004a59d  mov     rcx, [rsi+8]
0x18004a5a1  mov     rax, [rcx]
0x18004a5a4  cmp     rax, rcx
0x18004a5a7  jz      short loc_18004A5C1
0x18004a5a9  mov     rdx, qword ptr [rsp+160h+var_108]
0x18004a5ae  mov     r8, [rdx+rdi*8]
0x18004a5b2  mov     edx, [rax+10h]
0x18004a5b5  mov     [r8+r9*4], edx
0x18004a5b9  inc     r9
0x18004a5bc  mov     rax, [rax]
0x18004a5bf  jmp     short loc_18004A5A4
0x18004a5c1  mov     edi, 0FFFFFFFFh
0x18004a5c6  mov     rsi, [r15+28h]
0x18004a5ca  test    rsi, rsi
0x18004a5cd  mov     rcx, r13
0x18004a5d0  jz      short loc_18004A5D6
0x18004a5d2  mov     rcx, [rsi+10h]
0x18004a5d6  mov     rax, [rbp+60h+arg_28]
0x18004a5dd  cmp     rcx, rdi
0x18004a5e0  ja      loc_18004A7CA
0x18004a5e6  mov     [rax+rbx*8+18h], ecx
0x18004a5ea  test    rcx, rcx
0x18004a5ed  jz      loc_18004A67E
0x18004a5f3  mov     rdi, qword ptr [rsp+160h+var_138+8]
0x18004a5f8  sub     rdi, qword ptr [rsp+160h+var_138]
0x18004a5fd  sar     rdi, 3
0x18004a601  shl     rcx, 2; cb
0x18004a605  call    cs:__imp_CoTaskMemAlloc
0x18004a60b  mov     [rbp+60h+var_C0], rax
0x18004a60f  mov     rdx, qword ptr [rsp+160h+var_138+8]
0x18004a614  cmp     rdx, [rsp+160h+var_128]
0x18004a619  jz      short loc_18004A626
0x18004a61b  mov     [rdx], rax
0x18004a61e  add     qword ptr [rsp+160h+var_138+8], 8
0x18004a624  jmp     short loc_18004A634
0x18004a626  lea     r8, [rbp+60h+var_C0]
0x18004a62a  lea     rcx, [rsp+160h+var_138]
0x18004a62f  call    ??$_Emplace_reallocate@PEAW4CryptogramMaterialPackageConfirmationResponseFormat@@@?$vector@V?$unique_ptr@W4CryptogramMaterialPackageConfirmationResponseFormat@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@W4CryptogramMaterialPackageConfirmationResponseFormat@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAPEAV?$unique_ptr@W4CryptogramMaterialPackageConfirmationResponseFormat@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAV23@$$QEAPEAW4CryptogramMaterialPackageConfirmationResponseFormat@@@Z; std::vector<wistd::unique_ptr<CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Emplace_reallocate<CryptogramMaterialPackageConfirmationResponseFormat *>(wistd::unique_ptr<CryptogramMaterialPackageConfirmationResponseFormat,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> * const,CryptogramMaterialPackageConfirmationResponseFormat * &&)
0x18004a634  mov     rax, qword ptr [rsp+160h+var_138]
0x18004a639  mov     rcx, [rax+rdi*8]
0x18004a63d  test    rcx, rcx
0x18004a640  jz      loc_18004A7B4
0x18004a646  mov     r9, r13
0x18004a649  mov     rax, [rbp+60h+arg_28]
0x18004a650  mov     [rax+rbx*8+20h], rcx
0x18004a655  mov     rcx, [rsi+8]
0x18004a659  mov     rax, [rcx]
0x18004a65c  cmp     rax, rcx
0x18004a65f  jz      short loc_18004A679
0x18004a661  mov     rdx, qword ptr [rsp+160h+var_138]
0x18004a666  mov     r8, [rdx+rdi*8]
0x18004a66a  mov     edx, [rax+10h]
  ... truncated ...
```
