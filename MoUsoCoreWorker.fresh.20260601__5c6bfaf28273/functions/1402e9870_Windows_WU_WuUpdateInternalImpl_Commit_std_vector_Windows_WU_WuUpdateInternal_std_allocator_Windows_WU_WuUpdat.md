# Windows::WU::WuUpdateInternalImpl::Commit(std::vector<Windows::WU::WuUpdateInternal *,std::allocator<Windows::WU::WuUpdateInternal *>> const &,Windows::WU::CommitProperties const &)

- ea: `0x1402e9870`
- end: `0x1402ea712`
- name: `?Commit@WuUpdateInternalImpl@WU@Windows@@UEAAJAEBV?$vector@PEAVWuUpdateInternal@WU@Windows@@V?$allocator@PEAVWuUpdateInternal@WU@Windows@@@std@@@std@@AEBUCommitProperties@23@@Z`
- size: `3746`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14003ff28`
- `0x140040184`
- `0x1400413a8`
- `0x140042d04`
- `0x140043284`
- `0x140045404`
- `0x1400454a0`
- `0x140057a20`
- `0x1400c695c`
- `0x1400c75e4`
- `0x14012d7d8`
- `0x14012d864`
- `0x1402b310c`
- `0x1402dab40`
- `0x1402db704`
- `0x1402e9870`
- `0x1402ea718`
- `0x1402ec8ec`
- `0x1403742a4`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1402ea443`
- `OLEAUT32!__imp_SysFreeString` at `0x1402ea457`
- `OLEAUT32!__imp_SysFreeString` at `0x1402ea443`
- `OLEAUT32!__imp_SysFreeString` at `0x1402ea457`
- `OLEAUT32!__imp_SysStringLen` at `0x1402e9b4d`
- `OLEAUT32!__imp_SysStringLen` at `0x1402e9b4d`
- `OLEAUT32!__imp_VariantClear` at `0x1402e9ad8`
- `OLEAUT32!__imp_VariantClear` at `0x1402e9cbb`
- `OLEAUT32!__imp_VariantClear` at `0x1402e9d38`
- `OLEAUT32!__imp_VariantClear` at `0x1402e9ad8`
- `OLEAUT32!__imp_VariantClear` at `0x1402e9cbb`
- `OLEAUT32!__imp_VariantClear` at `0x1402e9d38`

## string_xrefs

- `0x1402ea60e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402ea6a1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402ea6e6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1402ea700`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1402e9b34`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e9b76`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e9c89`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402ea5f9`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402ea623`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402ea638`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402ea64d`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402ea662`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402ea677`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402ea68c`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402ea6bc`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402ea6d1`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
__int64 __fastcall Windows::WU::WuUpdateInternalImpl::Commit(__int64 a1, OLECHAR *a2, const wchar_t *a3)
{
  BSTR v4; // r12
  int v5; // eax
  int v6; // eax
  char v7; // r13
  __int64 System; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 (__fastcall *v12)(__int64, BSTR *, const wchar_t **); // r10
  __int64 v13; // rax
  __int64 v14; // rdx
  char v15; // r15
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rax
  int v19; // eax
  __int64 *v20; // r12
  __int64 v21; // r8
  VARIANTARG *v22; // rbx
  __int64 v23; // r8
  const wchar_t *v24; // rdx
  const wchar_t *v25; // rcx
  bool v26; // al
  __int64 *v27; // rbx
  __int64 (__fastcall *v28)(__int64 *, __int64, VARIANTARG *); // r15
  __int64 *v29; // rdx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rbx
  __int64 v33; // r12
  int v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rcx
  _QWORD *v39; // rax
  char v40; // r14
  volatile signed __int32 *v41; // rbx
  volatile signed __int32 *v42; // rbx
  int v43; // eax
  _QWORD *v44; // rax
  volatile signed __int32 *v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rcx
  void (__fastcall *v48)(__int64, _BYTE *, const wchar_t **); // rbx
  __int16 *traits_2_unsigned_short; // rax
  const char *v50; // r9
  __int64 v51; // r11
  __int64 v52; // rax
  volatile signed __int32 *v53; // rbx
  volatile signed __int32 *plVal; // rbx
  const char *v55; // r9
  _QWORD *v56; // rax
  __int64 **v57; // rax
  __int64 *v58; // rcx
  __int64 v59; // rax
  wchar_t **v60; // rdx
  _QWORD *v61; // rax
  volatile signed __int32 *v62; // rbx
  volatile signed __int32 *v63; // rbx
  int v64; // eax
  _QWORD *v65; // rax
  __int64 **v66; // rax
  __int64 *v67; // rcx
  __int64 v68; // rax
  wchar_t **v69; // rdx
  _QWORD *v70; // rax
  volatile signed __int32 *v71; // rbx
  volatile signed __int32 *v72; // rbx
  int v73; // eax
  int v74; // eax
  int v75; // ebx
  int v77; // [rsp+20h] [rbp-1B8h]
  int v78; // [rsp+20h] [rbp-1B8h]
  char *v79; // [rsp+30h] [rbp-1A8h]
  const wchar_t *v80; // [rsp+40h] [rbp-198h] BYREF
  volatile signed __int32 *v81; // [rsp+48h] [rbp-190h]
  __int64 v82; // [rsp+50h] [rbp-188h]
  VARIANTARG v83; // [rsp+60h] [rbp-178h] BYREF
  unsigned __int64 v84; // [rsp+78h] [rbp-160h]
  __int128 v85; // [rsp+80h] [rbp-158h]
  _BYTE v86[8]; // [rsp+90h] [rbp-148h] BYREF
  volatile signed __int32 *v87; // [rsp+98h] [rbp-140h]
  _BYTE v88[8]; // [rsp+A0h] [rbp-138h] BYREF
  volatile signed __int32 *v89; // [rsp+A8h] [rbp-130h]
  _BYTE v90[32]; // [rsp+B0h] [rbp-128h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-108h] BYREF
  __int64 v92; // [rsp+F0h] [rbp-E8h] BYREF
  __int64 v93; // [rsp+F8h] [rbp-E0h] BYREF
  __int64 v94; // [rsp+100h] [rbp-D8h] BYREF
  volatile signed __int32 *v95; // [rsp+108h] [rbp-D0h]
  __int64 *v96; // [rsp+110h] [rbp-C8h] BYREF
  BSTR v97; // [rsp+118h] [rbp-C0h] BYREF
  _QWORD *v98; // [rsp+120h] [rbp-B8h] BYREF
  wchar_t *S1[2]; // [rsp+128h] [rbp-B0h] BYREF
  size_t N; // [rsp+138h] [rbp-A0h]
  unsigned __int64 v101; // [rsp+140h] [rbp-98h]
  BSTR bstrString[2]; // [rsp+150h] [rbp-88h] BYREF
  _BYTE v103[32]; // [rsp+160h] [rbp-78h] BYREF
  char v104; // [rsp+180h] [rbp-58h]
  char v105; // [rsp+188h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v4 = a2;
  v97 = a2;
  v82 = a1;
  *(_QWORD *)&v85 = a1;
  LODWORD(v94) = 0;
  v92 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 112) + 112LL))(*(_QWORD *)(a1 + 112), &v92);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4E2,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v5,
      v77);
  v96 = 0;
  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v92)(
         v92,
         &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
         &v96);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v6,
      v77);
  v7 = 64;
  System = SystemInterface::Providers::GetSystem(v86);
  v9 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 32LL))(v9, &v94);
  v11 = *(_QWORD *)v10;
  v12 = *(__int64 (__fastcall **)(__int64, BSTR *, const wchar_t **))(**(_QWORD **)v10 + 8LL);
  v13 = -1;
  do
    ++v13;
  while ( SystemInterface::Registry::ENTERPRISE_ATTRIBUTION_ROOT[v13] );
  v80 = SystemInterface::Registry::ENTERPRISE_ATTRIBUTION_ROOT;
  v81 = (volatile signed __int32 *)v13;
  bstrString[0] = (BSTR)SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  v14 = -1;
  do
    ++v14;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v14] );
  bstrString[1] = (BSTR)v14;
  v15 = v12(v11, bstrString, &v80);
  v16 = v95;
  if ( v95 )
  {
    if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( !_InterlockedDecrement(v16 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  v17 = v87;
  if ( v87 )
  {
    if ( !_InterlockedDecrement(v87 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( !_InterlockedDecrement(v17 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  if ( v15 )
  {
    v18 = *v96;
    pvarg.vt = 11;
    pvarg.iVal = -1;
    v83 = pvarg;
    v19 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v18 + 32))(v96, 327690, &v83);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E8,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v19,
        v77);
    VariantClear(&pvarg);
  }
  if ( *((_QWORD *)a3 + 2) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl) )
    {
      Windows::WU::WuUpdateInternalImpl::InternalProperty(v82, &pvarg, 4);
      if ( pvarg.vt != 8 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4F0,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)0x8024A215LL,
          v77);
      LOBYTE(v77) = SysStringLen(pvarg.bstrVal) == 0;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x4F1,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)0x80070057LL,
        v77,
        (bool)"Session data is empty",
        v79);
      v20 = (__int64 *)a3;
      if ( *((_QWORD *)a3 + 3) > 7u )
        v20 = *(__int64 **)a3;
      memset(&v83, 0, sizeof(v83));
      v84 = 0;
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(pvarg.llVal + 2 * v21) );
      std::wstring::_Construct<1,wchar_t const *>(&v83, pvarg.llVal, v21);
      v22 = &v83;
      if ( v84 > 7 )
        v22 = *(VARIANTARG **)&v83.vt;
      *(_OWORD *)S1 = 0;
      N = 0;
      v101 = 0;
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)(pvarg.llVal + 2 * v23) );
      std::wstring::_Construct<1,wchar_t const *>(S1, pvarg.llVal, v23);
      v24 = a3;
      if ( *((_QWORD *)a3 + 3) > 7u )
        v24 = *(const wchar_t **)a3;
      v25 = (const wchar_t *)S1;
      if ( v101 > 7 )
        v25 = S1[0];
      if ( N == *((_QWORD *)a3 + 2) )
      {
        if ( N )
          v26 = wmemcmp(v25, v24, N) != 0;
        else
          v26 = 0;
      }
      else
      {
        v26 = 1;
      }
      LOBYTE(v78) = v26;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x4F2,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)0x80070057LL,
        v78,
        (bool)"Session data mismatch %s does not equal %s",
        (const char *)v22,
        v20);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(&v83);
      VariantClear(&pvarg);
      v4 = v97;
    }
    else
    {
      v27 = v96;
      v28 = *(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(*v96 + 32);
      v29 = (__int64 *)a3;
      if ( *((_QWORD *)a3 + 3) > 7u )
        v29 = *(__int64 **)a3;
      pvarg = *(VARIANTARG *)wil::make_variant_bstr(&v83, v29);
      v30 = v28(v27, 327684, &pvarg);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4F6,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          (const char *)(unsigned int)v30,
          v77);
      VariantClear(&v83);
    }
  }
  v93 = 0;
  wil::CoCreateInstance<UpdateCollection,IUpdateCollection,wil::err_exception_policy>(&v93);
  v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v93 + 96LL))(v93, *(_QWORD *)(v82 + 120), 0);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FB,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v31,
      v77);
  v32 = *(_QWORD *)v4;
  v33 = *((_QWORD *)v4 + 1);
  while ( v32 != v33 )
  {
    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v93 + 96LL))(
            v93,
            *(_QWORD *)(*(_QWORD *)v32 + 120LL),
            0);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4FF,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v34,
        v77);
    v32 += 8;
  }
  v35 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 128LL))(v92, v93);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x502,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v35,
      v77);
  if ( *((_BYTE *)a3 + 32) )
  {
    v36 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 80LL))(v92, 0xFFFFFFFFLL);
    if ( v36 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x506,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v36,
        v77);
  }
  if ( !*((_BYTE *)a3 + 33)
    || (v37 = SystemInterface::Providers::GetSystem(&v80),
        LODWORD(v94) = 65,
        v38 = *(_QWORD *)v37 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v37 + 8LL) + 4LL),
        v39 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v38 + 88LL))(v38, v86),
        v7 = 67,
        LODWORD(v94) = 67,
        v40 = 1,
        !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 32LL))(*v39)) )
  {
    v40 = 0;
  }
  if ( (v7 & 2) != 0 )
  {
    v7 &= ~2u;
    v41 = v87;
    if ( v87 )
    {
      if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
        if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
      }
    }
  }
  if ( (v7 & 1) != 0 )
  {
    v42 = v81;
    if ( v81 )
    {
      if ( _InterlockedExchangeAdd(v81 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
        if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
      }
    }
  }
  if ( v40 )
  {
    v94 = 0;
    v43 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v92)(
            v92,
            &GUID_885e76f6_f7c1_4869_951a_97613c8caef7,
            &v94);
    if ( v43 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C96,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v43,
        v77);
    v44 = (_QWORD *)SystemInterface::Service::GetSystem(v86);
    v80 = (const wchar_t *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v44 + 160LL))(*v44);
    Windows::Version::to_wstring(S1, &v80);
    v45 = v87;
    if ( v87 )
    {
      if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
    v46 = SystemInterface::Providers::GetSystem(&v83);
    v47 = *(_QWORD *)v46 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v46 + 8LL) + 4LL);
    v48 = *(void (__fastcall **)(__int64, _BYTE *, const wchar_t **))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v47 + 40LL))(
                                                                                     v47,
                                                                                     v88)
                                                                    + 32LL);
    traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"OfframpOsVersion",
                                           word_14047B45A,
                                           0);
    if ( traits_2_unsigned_short == word_14047B45A
      || (v52 = ((char *)traits_2_unsigned_short - (char *)L"OfframpOsVersion") >> 1, v52 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v50);
    }
    v80 = L"OfframpOsVersion";
    v81 = (volatile signed __int32 *)v52;
    v48(v51, v103, &v80);
    v53 = v89;
    if ( v89 )
    {
      if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
        if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
      }
    }
    plVal = v83.plVal;
    if ( v83.llVal )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v83.llVal + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))plVal)(plVal);
        if ( _InterlockedExchangeAdd(plVal + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)plVal + 8LL))(plVal);
      }
    }
    if ( v105 )
    {
      try
      {
        if ( v104 != 2 )
          std::_Throw_bad_variant_access();
        std::wstring::operator=(S1);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x518,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
          v55);
        v82 = v85;
      }
    }
    if ( v105 && v104 != -1 && v104 && v104 != 1 )
      std::wstring::~wstring(v103);
    v97 = 0;
    v56 = (_QWORD *)SystemInterface::Service::GetSystem(&v80);
    v57 = (__int64 **)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v56 + 64LL))(*v56, v88);
    v58 = *v57;
    v59 = **v57;
    v60 = S1;
    if ( v101 > 7 )
      v60 = (wchar_t **)S1[0];
    *(_QWORD *)&v85 = v60;
    *((_QWORD *)&v85 + 1) = N;
    *(_OWORD *)&v83.vt = v85;
    v61 = (_QWORD *)(*(__int64 (__fastcall **)(__int64 *, _BYTE *, VARIANTARG *))(v59 + 128))(v58, v90, &v83);
    if ( v61[3] > 7u )
      v61 = (_QWORD *)*v61;
    wil::make_bstr(&v97, v61);
    std::wstring::~wstring(v90);
    v62 = v89;
    if ( v89 )
    {
      if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
        if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
      }
    }
    v63 = v81;
    if ( v81 )
    {
      if ( _InterlockedExchangeAdd(v81 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
        if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
      }
    }
    v64 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR))(*(_QWORD *)v94 + 56LL))(v94, 2, v97);
    if ( v64 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v64,
        v77);
    bstrString[0] = 0;
    v65 = (_QWORD *)SystemInterface::Service::GetSystem(&pvarg);
    v66 = (__int64 **)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v65 + 64LL))(*v65, v86);
    v67 = *v66;
    v68 = **v66;
    v69 = S1;
    if ( v101 > 7 )
      v69 = (wchar_t **)S1[0];
    *(_QWORD *)&v85 = v69;
    *((_QWORD *)&v85 + 1) = N;
    *(_OWORD *)&v83.vt = v85;
    v70 = (_QWORD *)(*(__int64 (__fastcall **)(__int64 *, _BYTE *, VARIANTARG *))(v68 + 136))(v67, v103, &v83);
    if ( v70[3] > 7u )
      v70 = (_QWORD *)*v70;
    wil::make_bstr(bstrString, v70);
    std::wstring::~wstring(v103);
    v71 = v87;
    if ( v87 )
    {
      if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v71)(v71);
        if ( _InterlockedExchangeAdd(v71 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v71 + 8LL))(v71);
      }
    }
    v72 = pvarg.plVal;
    if ( pvarg.llVal )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pvarg.llVal + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
        if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
      }
    }
    v73 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR))(*(_QWORD *)v94 + 56LL))(v94, 3, bstrString[0]);
    if ( v73 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x521,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v73,
        v77);
    if ( bstrString[0] )
      SysFreeString(bstrString[0]);
    if ( v97 )
      SysFreeString(v97);
    std::wstring::~wstring(S1);
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
  }
  v98 = 0;
  v74 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD **))v92)(
          v92,
          &GUID_ef8208ea_2304_492d_9109_23813b0958e1,
          &v98);
  if ( v74 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v74,
      v77);
  v75 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v98 + 256LL))(v98, 0);
  if ( v75 >= 0 )
  {
    LOWORD(v94) = 257;
    *(_WORD *)(v82 + 100) = 257;
    if ( v98 )
      (*(void (__fastcall **)(_QWORD *))(*v98 + 16LL))(v98);
    if ( v93 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
    if ( v96 )
      (*(void (__fastcall **)(__int64 *))(*v96 + 16))(v96);
    if ( v92 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    return 0;
  }
  else
  {
    if ( v98 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v98 + 16LL))(v98, *v98);
    if ( v93 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
    if ( v96 )
      (*(void (__fastcall **)(__int64 *))(*v96 + 16))(v96);
    if ( v92 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    return (unsigned int)v75;
  }
}

```

## disassembly

```asm
0x1402e9870  push    rbx
0x1402e9872  push    rsi
0x1402e9873  push    rdi
0x1402e9874  push    r12
0x1402e9876  push    r13
0x1402e9878  push    r14
0x1402e987a  push    r15
0x1402e987c  sub     rsp, 1A0h
0x1402e9883  mov     rax, cs:__security_cookie
0x1402e988a  xor     rax, rsp
0x1402e988d  mov     [rsp+1D8h+var_48], rax
0x1402e9895  mov     r14, r8
0x1402e9898  mov     r12, rdx
0x1402e989b  mov     [rsp+1D8h+var_C0], rdx
0x1402e98a3  mov     [rsp+1D8h+var_188], rcx
0x1402e98a8  mov     qword ptr [rsp+1D8h+var_158], rcx
0x1402e98b0  xor     edi, edi
0x1402e98b2  mov     dword ptr [rsp+1D8h+var_D8], edi
0x1402e98b9  mov     [rsp+1D8h+var_E8], rdi
0x1402e98c1  mov     rcx, [rcx+70h]
0x1402e98c5  mov     rax, [rcx]
0x1402e98c8  mov     [rsp+1D8h+var_E8], rdi
0x1402e98d0  lea     rdx, [rsp+1D8h+var_E8]
0x1402e98d8  mov     rax, [rax+70h]
0x1402e98dc  call    _guard_dispatch_icall
0x1402e98e1  mov     rcx, [rsp+1D8h]; this
0x1402e98e9  test    eax, eax
0x1402e98eb  js      loc_1402EA5F6
0x1402e98f1  mov     rcx, [rsp+1D8h+var_E8]
0x1402e98f9  mov     [rsp+1D8h+var_C8], rdi
0x1402e9901  mov     rax, [rcx]
0x1402e9904  lea     r8, [rsp+1D8h+var_C8]
0x1402e990c  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x1402e9913  mov     rax, [rax]
0x1402e9916  call    _guard_dispatch_icall
0x1402e991b  mov     rcx, [rsp+1D8h]; this
0x1402e9923  test    eax, eax
0x1402e9925  js      loc_1402EA60B
0x1402e992b  mov     r13d, 40h ; '@'
0x1402e9931  lea     rcx, [rsp+1D8h+var_148]
0x1402e9939  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1402e993e  nop
0x1402e993f  mov     rdx, [rax]
0x1402e9942  mov     rax, [rdx+8]
0x1402e9946  movsxd  rcx, dword ptr [rax+4]
0x1402e994a  add     rdx, 8
0x1402e994e  add     rcx, rdx
0x1402e9951  mov     rax, [rcx]
0x1402e9954  lea     rdx, [rsp+1D8h+var_D8]
0x1402e995c  mov     rax, [rax+20h]
0x1402e9960  call    _guard_dispatch_icall
0x1402e9965  nop
0x1402e9966  mov     r9, [rax]
0x1402e9969  mov     rax, [r9]
0x1402e996c  mov     r10, [rax+8]
0x1402e9970  mov     rcx, cs:?ENTERPRISE_ATTRIBUTION_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::ENTERPRISE_ATTRIBUTION_ROOT
0x1402e9977  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1402e997b  mov     rax, rsi
0x1402e997e  inc     rax
0x1402e9981  cmp     [rcx+rax*2], di
0x1402e9985  jnz     short loc_1402E997E
0x1402e9987  mov     qword ptr [rsp+1D8h+var_198], rcx
0x1402e998c  mov     qword ptr [rsp+1D8h+var_198+8], rax
0x1402e9991  mov     rax, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x1402e9998  mov     [rsp+1D8h+bstrString], rax
0x1402e99a0  mov     rdx, rsi
0x1402e99a3  inc     rdx
0x1402e99a6  cmp     [rax+rdx*2], di
0x1402e99aa  jnz     short loc_1402E99A3
0x1402e99ac  mov     [rsp+1D8h+bstrString+8], rdx
0x1402e99b4  movups  xmm0, [rsp+1D8h+var_198]
0x1402e99b9  movdqu  [rsp+1D8h+var_198], xmm0
0x1402e99bf  movaps  xmm1, xmmword ptr [rsp+1D8h+bstrString]
0x1402e99c7  movdqa  xmmword ptr [rsp+1D8h+bstrString], xmm1
0x1402e99d0  lea     r8, [rsp+1D8h+var_198]
0x1402e99d5  lea     rdx, [rsp+1D8h+bstrString]
0x1402e99dd  mov     rcx, r9
0x1402e99e0  mov     rax, r10
0x1402e99e3  call    _guard_dispatch_icall
0x1402e99e8  mov     r15b, al
0x1402e99eb  mov     rbx, [rsp+1D8h+var_D0]
0x1402e99f3  test    rbx, rbx
0x1402e99f6  jz      short loc_1402E9A2C
0x1402e99f8  mov     ecx, esi
0x1402e99fa  lock xadd [rbx+8], ecx
0x1402e99ff  add     ecx, esi
0x1402e9a01  jnz     short loc_1402E9A2C
0x1402e9a03  mov     rdx, [rbx]
0x1402e9a06  mov     rcx, rbx
0x1402e9a09  mov     rax, [rdx]
0x1402e9a0c  call    _guard_dispatch_icall
0x1402e9a11  mov     eax, esi
0x1402e9a13  lock xadd [rbx+0Ch], eax
0x1402e9a18  add     eax, esi
0x1402e9a1a  jnz     short loc_1402E9A2C
0x1402e9a1c  mov     rax, [rbx]
0x1402e9a1f  mov     rcx, rbx
0x1402e9a22  mov     rax, [rax+8]
0x1402e9a26  call    _guard_dispatch_icall
0x1402e9a2b  nop
0x1402e9a2c  mov     rbx, [rsp+1D8h+var_140]
0x1402e9a34  test    rbx, rbx
0x1402e9a37  jz      short loc_1402E9A6C
0x1402e9a39  mov     eax, esi
0x1402e9a3b  lock xadd [rbx+8], eax
0x1402e9a40  add     eax, esi
0x1402e9a42  jnz     short loc_1402E9A6C
0x1402e9a44  mov     rax, [rbx]
0x1402e9a47  mov     rcx, rbx
0x1402e9a4a  mov     rax, [rax]
0x1402e9a4d  call    _guard_dispatch_icall
0x1402e9a52  mov     eax, esi
0x1402e9a54  lock xadd [rbx+0Ch], eax
0x1402e9a59  add     eax, esi
0x1402e9a5b  jnz     short loc_1402E9A6C
0x1402e9a5d  mov     rax, [rbx]
0x1402e9a60  mov     rcx, rbx
0x1402e9a63  mov     rax, [rax+8]
0x1402e9a67  call    _guard_dispatch_icall
0x1402e9a6c  test    r15b, r15b
0x1402e9a6f  jz      short loc_1402E9ADE
0x1402e9a71  mov     rcx, [rsp+1D8h+var_C8]
0x1402e9a79  mov     rax, [rcx]
0x1402e9a7c  mov     edx, 0Bh
0x1402e9a81  mov     word ptr [rsp+1D8h+pvarg], dx
0x1402e9a89  mov     word ptr [rsp+1D8h+pvarg+8], si
0x1402e9a91  movups  xmm0, xmmword ptr [rsp+1D8h+pvarg]
0x1402e9a99  movaps  xmmword ptr [rsp+1D8h+var_178], xmm0
0x1402e9a9e  movsd   xmm1, qword ptr [rsp+1D8h+pvarg+10h]
0x1402e9aa7  movsd   qword ptr [rsp+1D8h+var_178+10h], xmm1
0x1402e9aad  lea     r8, [rsp+1D8h+var_178]
0x1402e9ab2  mov     edx, 5000Ah
0x1402e9ab7  mov     rax, [rax+20h]
0x1402e9abb  call    _guard_dispatch_icall
0x1402e9ac0  mov     rcx, [rsp+1D8h]; this
0x1402e9ac8  test    eax, eax
0x1402e9aca  js      loc_1402EA620
0x1402e9ad0  lea     rcx, [rsp+1D8h+pvarg]; pvarg
0x1402e9ad8  call    cs:__imp_VariantClear
0x1402e9ade  cmp     [r14+10h], rdi
0x1402e9ae2  jz      loc_1402E9D3E
0x1402e9ae8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x1402e9aef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x1402e9af4  test    al, al
0x1402e9af6  jz      loc_1402E9CCB
0x1402e9afc  mov     r8d, 4
0x1402e9b02  lea     rdx, [rsp+1D8h+pvarg]
0x1402e9b0a  mov     rcx, [rsp+1D8h+var_188]
0x1402e9b0f  call    ?InternalProperty@WuUpdateInternalImpl@WU@Windows@@AEBA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@K@Z; Windows::WU::WuUpdateInternalImpl::InternalProperty(ulong)
0x1402e9b14  nop
0x1402e9b15  mov     rcx, [rsp+1D8h]; this
0x1402e9b1d  mov     r15d, 8
0x1402e9b23  cmp     word ptr [rsp+1D8h+pvarg], r15w
0x1402e9b2c  jz      short loc_1402E9B45
0x1402e9b2e  mov     r9d, 8024A215h; char *
0x1402e9b34  lea     r8, aCW1SSrcOrchest_28; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402e9b3b  mov     edx, 4F0h; void *
0x1402e9b40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1402e9b45  mov     rcx, qword ptr [rsp+1D8h+pvarg+8]; pbstr
0x1402e9b4d  call    cs:__imp_SysStringLen
0x1402e9b53  test    eax, eax
0x1402e9b55  setz    al
0x1402e9b58  mov     rcx, [rsp+1D8h]; this
0x1402e9b60  lea     rdx, aSessionDataIsE; "Session data is empty"
0x1402e9b67  mov     qword ptr [rsp+1D8h+var_1B0], rdx; bool
0x1402e9b6c  mov     byte ptr [rsp+1D8h+var_1B8], al; int
0x1402e9b70  mov     r9d, 80070057h; char *
0x1402e9b76  lea     r8, aCW1SSrcOrchest_28; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402e9b7d  mov     edx, 4F1h; void *
0x1402e9b82  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1402e9b87  mov     r12, r14
0x1402e9b8a  cmp     qword ptr [r14+18h], 7
0x1402e9b8f  jbe     short loc_1402E9B94
0x1402e9b91  mov     r12, [r14]
0x1402e9b94  xorps   xmm0, xmm0
0x1402e9b97  movups  xmmword ptr [rsp+1D8h+var_178], xmm0
0x1402e9b9c  mov     qword ptr [rsp+1D8h+var_178+10h], rdi
0x1402e9ba1  mov     [rsp+1D8h+var_160], rdi
0x1402e9ba6  mov     rdx, qword ptr [rsp+1D8h+pvarg+8]
0x1402e9bae  mov     r8, rsi
0x1402e9bb1  inc     r8
0x1402e9bb4  cmp     [rdx+r8*2], di
0x1402e9bb9  jnz     short loc_1402E9BB1
0x1402e9bbb  lea     rcx, [rsp+1D8h+var_178]
0x1402e9bc0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402e9bc5  nop
0x1402e9bc6  lea     rbx, [rsp+1D8h+var_178]
0x1402e9bcb  cmp     [rsp+1D8h+var_160], 7
0x1402e9bd1  cmova   rbx, qword ptr [rsp+1D8h+var_178]
0x1402e9bd7  xorps   xmm0, xmm0
0x1402e9bda  movups  xmmword ptr [rsp+1D8h+S1], xmm0
0x1402e9be2  mov     [rsp+1D8h+N], rdi
0x1402e9bea  mov     [rsp+1D8h+var_98], rdi
0x1402e9bf2  mov     rdx, qword ptr [rsp+1D8h+pvarg+8]
0x1402e9bfa  mov     r8, rsi
0x1402e9bfd  inc     r8
0x1402e9c00  cmp     [rdx+r8*2], di
0x1402e9c05  jnz     short loc_1402E9BFD
0x1402e9c07  lea     rcx, [rsp+1D8h+S1]
0x1402e9c0f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402e9c14  mov     rdx, r14
0x1402e9c17  cmp     qword ptr [r14+18h], 7
0x1402e9c1c  jbe     short loc_1402E9C21
0x1402e9c1e  mov     rdx, [r14]; S2
0x1402e9c21  mov     r8, [rsp+1D8h+N]; N
0x1402e9c29  lea     rcx, [rsp+1D8h+S1]
0x1402e9c31  cmp     [rsp+1D8h+var_98], 7
0x1402e9c3a  cmova   rcx, [rsp+1D8h+S1]; S1
0x1402e9c43  cmp     r8, [r14+10h]
0x1402e9c47  jz      short loc_1402E9C4D
0x1402e9c49  mov     al, 1
0x1402e9c4b  jmp     short loc_1402E9C61
0x1402e9c4d  test    r8, r8
0x1402e9c50  jnz     short loc_1402E9C57
0x1402e9c52  mov     al, dil
0x1402e9c55  jmp     short loc_1402E9C61
0x1402e9c57  call    wmemcmp
0x1402e9c5c  test    eax, eax
0x1402e9c5e  setnz   al
0x1402e9c61  mov     rcx, [rsp+1D8h]; this
0x1402e9c69  mov     [rsp+1D8h+var_1A0], r12
0x1402e9c6e  mov     [rsp+1D8h+var_1A8], rbx; char *
0x1402e9c73  lea     rdx, aSessionDataMis; "Session data mismatch %s does not equal"...
0x1402e9c7a  mov     qword ptr [rsp+1D8h+var_1B0], rdx; bool
0x1402e9c7f  mov     byte ptr [rsp+1D8h+var_1B8], al; int
0x1402e9c83  mov     r9d, 80070057h; char *
0x1402e9c89  lea     r8, aCW1SSrcOrchest_28; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402e9c90  mov     edx, 4F2h; void *
0x1402e9c95  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1402e9c9a  lea     rcx, [rsp+1D8h+S1]
0x1402e9ca2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402e9ca7  nop
0x1402e9ca8  lea     rcx, [rsp+1D8h+var_178]
0x1402e9cad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402e9cb2  nop
0x1402e9cb3  lea     rcx, [rsp+1D8h+pvarg]; pvarg
0x1402e9cbb  call    cs:__imp_VariantClear
0x1402e9cc1  mov     r12, [rsp+1D8h+var_C0]
0x1402e9cc9  jmp     short loc_1402E9D44
0x1402e9ccb  mov     rbx, [rsp+1D8h+var_C8]
0x1402e9cd3  mov     rax, [rbx]
0x1402e9cd6  mov     r15, [rax+20h]
0x1402e9cda  mov     rdx, r14
0x1402e9cdd  cmp     qword ptr [r14+18h], 7
0x1402e9ce2  jbe     short loc_1402E9CE7
0x1402e9ce4  mov     rdx, [r14]
0x1402e9ce7  lea     rcx, [rsp+1D8h+var_178]
0x1402e9cec  call    ?make_variant_bstr@wil@@YA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@1@PEB_W@Z; wil::make_variant_bstr(wchar_t const *)
0x1402e9cf1  nop
0x1402e9cf2  movups  xmm0, xmmword ptr [rax]
0x1402e9cf5  movaps  xmmword ptr [rsp+1D8h+pvarg], xmm0
0x1402e9cfd  movsd   xmm1, qword ptr [rax+10h]
0x1402e9d02  movsd   qword ptr [rsp+1D8h+pvarg+10h], xmm1
0x1402e9d0b  lea     r8, [rsp+1D8h+pvarg]
0x1402e9d13  mov     edx, 50004h
0x1402e9d18  mov     rcx, rbx
0x1402e9d1b  mov     rax, r15
0x1402e9d1e  call    _guard_dispatch_icall
0x1402e9d23  mov     rcx, [rsp+1D8h]; this
0x1402e9d2b  test    eax, eax
0x1402e9d2d  js      loc_1402EA635
0x1402e9d33  lea     rcx, [rsp+1D8h+var_178]; pvarg
0x1402e9d38  call    cs:__imp_VariantClear
0x1402e9d3e  mov     r15d, 8
0x1402e9d44  mov     [rsp+1D8h+var_E0], rdi
0x1402e9d4c  lea     rcx, [rsp+1D8h+var_E0]
0x1402e9d54  call    ??$CoCreateInstance@VUpdateCollection@@UIUpdateCollection@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdateCollection@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateCollection,IUpdateCollection,wil::err_exception_policy>(ulong)
0x1402e9d59  nop
0x1402e9d5a  mov     rcx, [rsp+1D8h+var_E0]
0x1402e9d62  mov     rax, [rcx]
0x1402e9d65  xor     r8d, r8d
0x1402e9d68  mov     rdx, [rsp+1D8h+var_188]
0x1402e9d6d  mov     rdx, [rdx+78h]
0x1402e9d71  mov     rax, [rax+60h]
0x1402e9d75  call    _guard_dispatch_icall
0x1402e9d7a  mov     rcx, [rsp+1D8h]; this
0x1402e9d82  test    eax, eax
0x1402e9d84  js      loc_1402EA64A
0x1402e9d8a  mov     rbx, [r12]
0x1402e9d8e  mov     r12, [r12+8]
0x1402e9d93  jmp     short loc_1402E9DC6
0x1402e9d95  mov     rdx, [rbx]
0x1402e9d98  mov     rcx, [rsp+1D8h+var_E0]
0x1402e9da0  mov     rax, [rcx]
0x1402e9da3  xor     r8d, r8d
0x1402e9da6  mov     rdx, [rdx+78h]
0x1402e9daa  mov     rax, [rax+60h]
0x1402e9dae  call    _guard_dispatch_icall
0x1402e9db3  mov     rcx, [rsp+1D8h]; this
0x1402e9dbb  test    eax, eax
0x1402e9dbd  js      loc_1402EA674
0x1402e9dc3  add     rbx, r15
0x1402e9dc6  cmp     rbx, r12
0x1402e9dc9  jnz     short loc_1402E9D95
0x1402e9dcb  mov     rcx, [rsp+1D8h+var_E8]
0x1402e9dd3  mov     rax, [rcx]
0x1402e9dd6  mov     rdx, [rsp+1D8h+var_E0]
0x1402e9dde  mov     rax, [rax+80h]
0x1402e9de5  call    _guard_dispatch_icall
0x1402e9dea  mov     rcx, [rsp+1D8h]; this
  ... truncated ...
```
