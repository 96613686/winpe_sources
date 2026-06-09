# GetBatch(IGenericFilter *,wchar_t const *,ulong,tagBatchingGenericFilterItem *,ulong *,ulong *)

- ea: `0x14000e7ec`
- end: `0x14001022b`
- name: `?GetBatch@@YAJPEAUIGenericFilter@@PEB_WKPEAUtagBatchingGenericFilterItem@@PEAK3@Z`
- size: `6719`
- prototype: `__int64 __fastcall(struct IGenericFilter *, const wchar_t *, unsigned int, struct tagBatchingGenericFilterItem *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140013c50`

## callees

- `0x1400030a0`
- `0x1400034b0`
- `0x140003c74`
- `0x140005e88`
- `0x140006890`
- `0x140009f14`
- `0x14000b5c4`
- `0x14000c784`
- `0x14000cc34`
- `0x14000cfd4`
- `0x14000d0c8`
- `0x14000d80c`
- `0x14000e004`
- `0x14000e064`
- `0x14000e0ec`
- `0x14000e124`
- `0x14000e158`
- `0x14000e378`
- `0x14000e3ec`
- `0x14000e634`
- `0x14000e690`
- `0x14000e6f0`
- `0x14000e7ec`
- `0x1400153d4`
- `0x1400154b0`
- `0x1400154f0`
- `0x1400155e0`
- `0x14001561c`
- `0x14001569c`
- `0x1400158a8`
- `0x140015a7c`
- `0x1400165bc`
- `0x140016d14`
- `0x14001734c`
- `0x140017e98`
- `0x140018260`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f0c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f174`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f0c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f174`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x14000f06e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x14000f06e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14000f0a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14000f154`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14000f0a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14000f154`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall GetBatch(
        struct IGenericFilter *a1,
        const wchar_t *a2,
        unsigned int a3,
        struct tagBatchingGenericFilterItem *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  __int64 v9; // r12
  unsigned int v10; // r8d
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // edi
  __int64 result; // rax
  struct IGenericFilter *v18; // rdi
  struct IGenericFilter *v19; // rsi
  void *v20; // rbx
  __int64 *v21; // r14
  void *v22; // rsi
  unsigned int i; // eax
  unsigned int v24; // r12d
  __int64 v25; // r12
  volatile signed __int32 *v26; // r12
  volatile signed __int32 *v27; // r12
  volatile signed __int32 *v28; // r12
  volatile signed __int32 *v29; // r12
  _QWORD *v30; // r8
  int v31; // eax
  __int64 v32; // r8
  __int64 v33; // r9
  void *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  PROPVARIANT *v37; // rax
  HRESULT v38; // eax
  PROPVARIANT *v39; // rcx
  unsigned int v40; // edx
  int v41; // eax
  _QWORD *v42; // r8
  __int64 v43; // r8
  __int64 v44; // r9
  void *v45; // rax
  __int64 v46; // rax
  char IsEnabled; // al
  int v48; // eax
  char *v49; // rax
  char *v50; // rax
  void *v51; // rax
  void *v52; // rcx
  size_t v53; // r12
  int v54; // eax
  unsigned __int64 v55; // rdx
  char *v56; // rax
  size_t v57; // r12
  unsigned __int64 v58; // rcx
  char *v59; // rax
  __int64 v60; // r12
  void *v61; // rax
  unsigned int v62; // ecx
  size_t v63; // r12
  int v64; // eax
  unsigned __int64 v65; // rdx
  char *v66; // rax
  size_t v67; // r12
  unsigned __int64 v68; // rcx
  char *v69; // rax
  __int64 v70; // r12
  void *v71; // rax
  size_t v72; // r12
  unsigned int v73; // eax
  _QWORD *v74; // r8
  int v75; // eax
  __int64 v76; // r8
  __int64 v77; // r9
  void *v78; // rax
  __int64 v79; // rax
  void *v80; // r10
  int v81; // eax
  __int64 v82; // r8
  char v83; // al
  _WORD *v84; // rdx
  __int64 v85; // r8
  int v86; // [rsp+20h] [rbp-218h]
  _BYTE v87[4]; // [rsp+30h] [rbp-208h] BYREF
  unsigned int v88; // [rsp+34h] [rbp-204h] BYREF
  unsigned int v89; // [rsp+38h] [rbp-200h]
  unsigned int v90; // [rsp+3Ch] [rbp-1FCh]
  __int64 v91; // [rsp+40h] [rbp-1F8h] BYREF
  unsigned int v92; // [rsp+48h] [rbp-1F0h] BYREF
  char v93; // [rsp+4Ch] [rbp-1ECh] BYREF
  char v94; // [rsp+4Dh] [rbp-1EBh]
  __int64 v95; // [rsp+50h] [rbp-1E8h] BYREF
  _WORD *v96; // [rsp+58h] [rbp-1E0h] BYREF
  struct IGenericFilter *v97; // [rsp+60h] [rbp-1D8h] BYREF
  __int64 v98; // [rsp+68h] [rbp-1D0h] BYREF
  __int64 v99; // [rsp+70h] [rbp-1C8h] BYREF
  void *v100; // [rsp+78h] [rbp-1C0h] BYREF
  unsigned int v101; // [rsp+80h] [rbp-1B8h] BYREF
  int v102[3]; // [rsp+84h] [rbp-1B4h] BYREF
  __int128 v103; // [rsp+90h] [rbp-1A8h] BYREF
  PROPVARIANT *pvarSrc; // [rsp+A0h] [rbp-198h] BYREF
  unsigned int v105; // [rsp+A8h] [rbp-190h]
  unsigned int *v106; // [rsp+B0h] [rbp-188h]
  int v107; // [rsp+B8h] [rbp-180h] BYREF
  int v108; // [rsp+BCh] [rbp-17Ch] BYREF
  char v109; // [rsp+C1h] [rbp-177h]
  __int64 v110; // [rsp+C8h] [rbp-170h]
  unsigned int *v111; // [rsp+D0h] [rbp-168h]
  _BYTE v112[56]; // [rsp+E0h] [rbp-158h] BYREF
  volatile signed __int32 *v113; // [rsp+118h] [rbp-120h]
  __int64 v114; // [rsp+120h] [rbp-118h]
  char v115[16]; // [rsp+128h] [rbp-110h] BYREF
  char v116[16]; // [rsp+138h] [rbp-100h] BYREF
  char v117[16]; // [rsp+148h] [rbp-F0h] BYREF
  char v118[16]; // [rsp+158h] [rbp-E0h] BYREF
  void *Src[2]; // [rsp+168h] [rbp-D0h] BYREF
  __int64 v120; // [rsp+178h] [rbp-C0h]
  _QWORD v121[2]; // [rsp+188h] [rbp-B0h] BYREF
  __int64 v122; // [rsp+198h] [rbp-A0h]
  unsigned __int64 v123; // [rsp+1A0h] [rbp-98h]
  __int128 v124; // [rsp+1A8h] [rbp-90h] BYREF
  __int128 v125; // [rsp+1B8h] [rbp-80h]
  _BYTE v126[32]; // [rsp+1C8h] [rbp-70h] BYREF
  _BYTE v127[32]; // [rsp+1E8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v114 = -2;
  v105 = a3;
  v106 = a5;
  v111 = a6;
  v109 = 1;
  v9 = 0;
  *a5 = 0;
  *a6 = 0;
  v10 = 0;
  if ( a3 )
  {
    v11 = 0;
    do
    {
      v12 = 9 * v11;
      *((_QWORD *)a4 + v12) = 0;
      *(_OWORD *)((char *)a4 + 8 * v12 + 8) = 0;
      *((_QWORD *)a4 + v12 + 3) = 0;
      *((_DWORD *)a4 + 2 * v12 + 8) = 0;
      *(_OWORD *)((char *)a4 + 8 * v12 + 40) = 0;
      *(_OWORD *)((char *)a4 + 8 * v12 + 56) = 0;
      ++v10;
      ++v11;
    }
    while ( v10 < a3 );
  }
  v13 = 0;
  v95 = 0;
  if ( a2 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    if ( v14 )
    {
      v15 = _open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEB_WK_N_Z(&v95);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF6,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\mssrch\\gather\\include\\batchchunk.hxx",
          (const char *)(unsigned int)v15,
          v86);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v95);
        return v16;
      }
      v13 = v95;
    }
  }
  try
  {
    v18 = 0;
    v97 = 0;
    v19 = 0;
    if ( a1 )
    {
      v18 = a1;
      v97 = a1;
      (*(void (__fastcall **)(struct IGenericFilter *))(*(_QWORD *)a1 + 8LL))(a1);
      v19 = a1;
    }
    if ( v19 )
    {
      v91 = 0;
      (**(void (__fastcall ***)(struct IGenericFilter *, __int64 *, void **))v19)(
        v19,
        &winrt::impl::guid_v<ITextFilter>,
        (void **)&v91);
      v20 = (void *)v91;
    }
    else
    {
      v20 = 0;
    }
    v100 = v20;
    if ( v19 )
    {
      v91 = 0;
      (**(void (__fastcall ***)(struct IGenericFilter *, __int64 *, void **))v19)(
        v19,
        &winrt::impl::guid_v<IValueFilter>,
        (void **)&v91);
      v21 = (__int64 *)v91;
      v99 = v91;
      v9 = v91;
    }
    else
    {
      v21 = 0;
      v99 = 0;
    }
    v91 = 0;
    if ( v19 )
    {
      (**(void (__fastcall ***)(struct IGenericFilter *, __int64 *, void **))v19)(
        v19,
        &winrt::impl::guid_v<ISemanticFilter>,
        (void **)&v91);
      v22 = (void *)v91;
      v98 = v91;
    }
    else
    {
      v22 = 0;
      v98 = 0;
    }
    v96 = operator new[](0x20000u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v96 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\mssrch\\gather\\include\\batchchunk.hxx",
        (const char *)0x8007000ELL,
        v86);
      std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
      if ( v91 )
        winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
      if ( v9 )
        winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
      if ( v20 )
        winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
      if ( v18 )
        winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v95);
      return 2147942414LL;
    }
    v90 = 0;
    std::wstring::wstring((__int64)v126);
    std::wstring::wstring((__int64)v127);
    for ( i = 0; ; i = v73 + 1 )
    {
      v89 = i;
      v88 = i + 1;
      if ( i + 1 >= v105
        || v13
        && (unsigned __int8)_is_signaled___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NXZ(&v95) )
      {
        goto LABEL_289;
      }
      v87[0] = 0;
      v24 = (*(__int64 (__fastcall **)(struct IGenericFilter *, _BYTE *))(*(_QWORD *)v18 + 32LL))(v18, v87);
      if ( v24 )
      {
        *v111 = v90;
        std::wstring::_Tidy_deallocate((__int64)v127);
        std::wstring::_Tidy_deallocate((__int64)v126);
        std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
        if ( v22 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
        if ( v21 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
        if ( v20 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
        if ( v18 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
LABEL_45:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v95);
        return v24;
      }
      if ( !v87[0] )
        goto LABEL_289;
      ++*v106;
      v25 = 9LL * v89;
      v110 = v25;
      *(_OWORD *)((char *)a4 + 8 * v25 + 8) = 0;
      *((_QWORD *)a4 + v25 + 3) = 0;
      v102[0] = 0;
      v92 = (*(__int64 (__fastcall **)(struct IGenericFilter *, int *))(*(_QWORD *)v18 + 40LL))(v18, v102);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49093927>::GetImpl'::`2'::impl) )
      {
        v91 = 0;
        tip2::tip_test<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::start_and_watch_errors(
          &v91,
          v112);
        wil::com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>((void **)&v91);
        if ( v102[0] == 3 )
        {
          v26 = v113;
          v91 = (__int64)v113;
          if ( v113 )
            _InterlockedIncrement(v113 + 70);
          tip2::details::shared_data<0,0,0>::begin_update((__int64)(v26 + 2));
          *((_BYTE *)v26 + 272) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>(&v91);
          v27 = v113;
          v91 = (__int64)v113;
          if ( v113 )
            _InterlockedIncrement(v113 + 70);
          tip2::details::shared_data<0,0,0>::begin_update((__int64)(v27 + 2));
          *((_DWORD *)v27 + 69) = v92;
          tip2::test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>(&v91);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl'::`2'::impl) )
          {
            if ( v92 == -2147024362 || v92 == -2147024774 )
            {
LABEL_56:
              --*v106;
              --v89;
              v28 = v113;
              v91 = (__int64)v113;
              if ( v113 )
                _InterlockedIncrement(v113 + 70);
              tip2::details::shared_data<0,0,0>::begin_update((__int64)(v28 + 2));
              tip2::details::shared_data<0,0,0>::complete_helper(v28 + 2, 2048, 10);
              tip2::test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>(&v91);
              tip2::test_watcher<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::~test_watcher<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>(v112);
              goto LABEL_286;
            }
          }
          else if ( v92 != -2147216858 )
          {
            goto LABEL_56;
          }
        }
        v29 = v113;
        v91 = (__int64)v113;
        if ( v113 )
          _InterlockedIncrement(v113 + 70);
        tip2::details::shared_data<0,0,0>::begin_update((__int64)(v29 + 2));
        tip2::details::shared_data<0,0,0>::complete_helper(v29 + 2, 2048, 10);
        tip2::test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>(&v91);
        tip2::test_watcher<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::~test_watcher<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>(v112);
        v25 = v110;
      }
      if ( v92 )
      {
        *((_DWORD *)a4 + 2 * v25) = v92;
        goto LABEL_289;
      }
      if ( (v102[0] & 0xFFFFFFFB) == 0 )
      {
        if ( !v20 )
        {
LABEL_288:
          *((_DWORD *)a4 + 2 * v25) = -2147024809;
          goto LABEL_289;
        }
        std::wstring::wstring((__int64)v121);
        v92 = 85;
        std::wstring::resize(v121, 85);
        v74 = v121;
        if ( v123 > 7 )
          v74 = (_QWORD *)v121[0];
        v75 = (*(__int64 (__fastcall **)(void *, unsigned int *, _QWORD *))(*(_QWORD *)v20 + 40LL))(v20, &v92, v74);
        if ( v75 )
        {
LABEL_237:
          *((_DWORD *)a4 + 2 * v25) = v75;
          goto LABEL_238;
        }
        if ( (unsigned __int8)std::operator!=<wchar_t>(v121, v126) )
        {
          *((_DWORD *)a4 + 2 * v25 + 1) = 3;
          *((_WORD *)a4 + 4 * v25 + 4) = 31;
          v103 = *(_OWORD *)std::wstring::operator std::wstring_view(v121, v117, v76, v77);
          v78 = BatchFilterPropVariantCopyString((__int64)&v103);
          *((_QWORD *)a4 + v25 + 2) = v78;
          if ( !v78 && v122 )
          {
            std::wstring::_Tidy_deallocate((__int64)v121);
            std::wstring::_Tidy_deallocate((__int64)v127);
            std::wstring::_Tidy_deallocate((__int64)v126);
            std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
            if ( v22 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
            if ( v21 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
            winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
            if ( v18 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
            goto LABEL_281;
          }
          v90 += v122 + 1;
          if ( v90 > 0x40000 )
            goto LABEL_238;
          std::wstring::operator=(v126, v121);
          ++*v106;
          v79 = v88;
          v89 = v88;
        }
        else
        {
          v79 = v89;
        }
        v25 = 9 * v79;
        *((_DWORD *)a4 + 18 * v79 + 1) = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57599366>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57599366>::GetImpl'::`2'::impl) )
        {
          v124 = 0;
          v125 = 0;
          v75 = (*(__int64 (__fastcall **)(void *, __int128 *))(*(_QWORD *)v20 + 32LL))(v20, &v124);
          if ( v75 )
            goto LABEL_237;
          *(_OWORD *)((char *)a4 + 8 * v25 + 40) = v124;
          *(_OWORD *)((char *)a4 + 8 * v25 + 56) = v125;
          v108 = 0;
          v75 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v20 + 24LL))(v20, &v108);
          if ( v75 )
            goto LABEL_237;
          *((_DWORD *)a4 + 2 * v25 + 8) = v108;
        }
        else
        {
          v88 = 0;
          v75 = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v20 + 24LL))(v20, &v88);
          if ( v75 )
            goto LABEL_237;
          *((_DWORD *)a4 + 2 * v25 + 8) = v88;
          v124 = 0;
          v125 = 0;
          v75 = (*(__int64 (__fastcall **)(void *, __int128 *))(*(_QWORD *)v20 + 32LL))(v20, &v124);
          if ( v75 )
            goto LABEL_237;
          *(_OWORD *)((char *)a4 + 8 * v25 + 40) = v124;
          *(_OWORD *)((char *)a4 + 8 * v25 + 56) = v125;
        }
        std::wstring::wstring((__int64)Src);
        v87[0] = 0;
        v93 = 0;
        v94 = 0;
        while ( 1 )
        {
          v88 = 0xFFFF;
          v86 = (int)v96;
          v81 = (*(__int64 (__fastcall **)(void *, _BYTE *, char *, unsigned int *))(*(_QWORD *)v80 + 48LL))(
                  v80,
                  v87,
                  &v93,
                  &v88);
          if ( v81 )
            break;
          v83 = v87[0];
          if ( v87[0] )
          {
            if ( v88 <= 0xFFFF )
            {
              v94 = 1;
              v84 = v96;
              v96[v88] = 0;
              v85 = -1;
              do
                ++v85;
              while ( v84[v85] );
              std::wstring::_Append<wchar_t>(Src);
              v83 = v87[0];
            }
            if ( v83 )
            {
              v80 = v20;
              if ( !v93 )
                continue;
            }
          }
          goto LABEL_270;
        }
        *((_DWORD *)a4 + 2 * v25) = v81;
LABEL_270:
        if ( v94 )
        {
          *((_WORD *)a4 + 4 * v25 + 4) = 31;
          v103 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v118, v82, 0);
          *((_QWORD *)a4 + v25 + 2) = BatchFilterPropVariantCopyString((__int64)&v103);
        }
        else
        {
          *((_WORD *)a4 + 4 * v25 + 4) = 1;
        }
        if ( !*((_QWORD *)a4 + v25 + 2) && v120 )
        {
          std::wstring::_Tidy_deallocate((__int64)Src);
          std::wstring::_Tidy_deallocate((__int64)v121);
          std::wstring::_Tidy_deallocate((__int64)v127);
          std::wstring::_Tidy_deallocate((__int64)v126);
          std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
          if ( v22 )
            winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
          if ( v21 )
            winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
          if ( v18 )
            winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
LABEL_281:
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v95);
          return 2147942414LL;
        }
        v90 += v120 + 1;
        if ( v90 > 0x40000 )
        {
          std::wstring::_Tidy_deallocate((__int64)Src);
          goto LABEL_238;
        }
        std::wstring::_Tidy_deallocate((__int64)Src);
        goto LABEL_285;
      }
      if ( v102[0] == 1 )
      {
        if ( !v21 )
          goto LABEL_288;
        std::wstring::wstring((__int64)v121);
        v92 = 85;
        std::wstring::resize(v121, 85);
        v30 = v121;
        if ( v123 > 7 )
          v30 = (_QWORD *)v121[0];
        v31 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, _QWORD *))(*v21 + 40))(v21, &v92, v30);
        if ( v31 )
        {
LABEL_71:
          *((_DWORD *)a4 + 2 * v25) = v31;
          goto LABEL_238;
        }
        if ( (unsigned __int8)std::operator!=<wchar_t>(v121, v126) )
        {
          *((_DWORD *)a4 + 2 * v25 + 1) = 3;
          *((_WORD *)a4 + 4 * v25 + 4) = 31;
          v103 = *(_OWORD *)std::wstring::operator std::wstring_view(v121, v115, v32, v33);
          v34 = BatchFilterPropVariantCopyString((__int64)&v103);
          *((_QWORD *)a4 + v25 + 2) = v34;
          if ( !v34 && v122 )
          {
            std::wstring::_Tidy_deallocate((__int64)v121);
            std::wstring::_Tidy_deallocate((__int64)v127);
            std::wstring::_Tidy_deallocate((__int64)v126);
            std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
            if ( v22 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
            winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
            if ( v20 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
            if ( v18 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
            goto LABEL_281;
          }
          v90 += v122 + 1;
          if ( v90 > 0x40000 )
            goto LABEL_238;
          std::wstring::operator=(v126, v121);
          ++*v106;
          v35 = v88;
          v89 = v88;
        }
        else
        {
          v35 = v89;
        }
        v25 = 9 * v35;
        *((_DWORD *)a4 + 18 * v35 + 1) = 1;
        v107 = 0;
        v31 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v21 + 24))(v21, &v107);
        if ( v31 )
          goto LABEL_71;
        *((_DWORD *)a4 + 2 * v25 + 8) = v107;
        v124 = 0;
        v125 = 0;
        v31 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*v21 + 32))(v21, &v124);
        if ( v31 )
          goto LABEL_71;
        *(_OWORD *)((char *)a4 + 8 * v25 + 40) = v124;
        *(_OWORD *)((char *)a4 + 8 * v25 + 56) = v125;
        pvarSrc = 0;
        v36 = *v21;
        Src[0] = &pvarSrc;
        Src[1] = 0;
        LOBYTE(v120) = 1;
        *((_DWORD *)a4 + 2 * v25) = (*(__int64 (__fastcall **)(__int64 *, void **))(v36 + 48))(v21, &Src[1]);
        wil::details::out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)Src);
        v37 = pvarSrc;
        if ( pvarSrc )
        {
          v38 = PropVariantCopy((PROPVARIANT *)a4 + v25 + 1, pvarSrc);
          v24 = v38;
          if ( v38 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x233,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\mssrch\\gather\\include\\batchchunk.hxx",
              (const char *)(unsigned int)v38,
              v86);
            PropVariantClear(pvarSrc);
            v39 = pvarSrc;
            pvarSrc = 0;
            if ( v39 )
              CoTaskMemFree(v39);
            std::wstring::_Tidy_deallocate((__int64)v121);
            std::wstring::_Tidy_deallocate((__int64)v127);
            std::wstring::_Tidy_deallocate((__int64)v126);
            std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
            if ( v22 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
            winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
            if ( v20 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
            if ( v18 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
            goto LABEL_45;
          }
          PropVariantClear(pvarSrc);
          v37 = pvarSrc;
        }
        pvarSrc = 0;
        if ( v37 )
          CoTaskMemFree(v37);
LABEL_285:
        std::wstring::_Tidy_deallocate((__int64)v121);
LABEL_286:
        v73 = v89;
        continue;
      }
      if ( v102[0] == 2 )
        break;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56253827>::__private_IsEnabled(
                               `wil::Feature<__WilFeatureTraits_Feature_56253827>::GetImpl'::`2'::impl,
                               0)
        || v102[0] != 3 )
      {
        *((_DWORD *)a4 + 2 * v25) = -2147483637;
        goto LABEL_289;
      }
      --*v106;
      v73 = v89 - 1;
    }
    if ( !v22 )
      goto LABEL_288;
    std::wstring::wstring((__int64)v121);
    v92 = v40;
    std::wstring::resize(v121, 0);
    v41 = (*(__int64 (__fastcall **)(void *, unsigned int *, _QWORD))(*(_QWORD *)v22 + 32LL))(v22, &v92, 0);
    if ( v41 == -2147024774 )
    {
      std::wstring::resize(v121, v92);
      v42 = v121;
      if ( v123 > 7 )
        v42 = (_QWORD *)v121[0];
      v41 = (*(__int64 (__fastcall **)(void *, unsigned int *, _QWORD *))(*(_QWORD *)v22 + 32LL))(v22, &v92, v42);
      if ( v41 )
      {
LABEL_123:
        *((_DWORD *)a4 + 2 * v25) = v41;
        goto LABEL_238;
      }
      std::wstring::resize(v121, v92);
    }
    else if ( v41 )
    {
      goto LABEL_123;
    }
    if ( (unsigned __int8)std::operator!=<wchar_t>(v121, v127) )
    {
      *((_DWORD *)a4 + 2 * v25 + 1) = 4;
      *((_WORD *)a4 + 4 * v25 + 4) = 31;
      v103 = *(_OWORD *)std::wstring::operator std::wstring_view(v121, v116, v43, v44);
      v45 = BatchFilterPropVariantCopyString((__int64)&v103);
      *((_QWORD *)a4 + v25 + 2) = v45;
      if ( !v45 && v122 )
      {
        std::wstring::_Tidy_deallocate((__int64)v121);
        std::wstring::_Tidy_deallocate((__int64)v127);
        std::wstring::_Tidy_deallocate((__int64)v126);
        std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
        winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
        if ( v21 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
        if ( v20 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
        if ( v18 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
        goto LABEL_281;
      }
      v90 += v122 + 1;
      if ( v90 > 0x40000 )
        goto LABEL_238;
      std::wstring::operator=(v127, v121);
      ++*v106;
      v46 = v88;
      v89 = v88;
    }
    else
    {
      v46 = v89;
    }
    v25 = 9 * v46;
    v91 = v25;
    *((_DWORD *)a4 + 2 * v25 + 1) = 2;
    v124 = 0;
    v125 = 0;
    v41 = (*(__int64 (__fastcall **)(void *, __int128 *))(*(_QWORD *)v22 + 24LL))(v22, &v124);
    if ( v41 )
      goto LABEL_123;
    *(_OWORD *)((char *)a4 + 8 * v25 + 40) = v124;
    *(_OWORD *)((char *)a4 + 8 * v25 + 56) = v125;
    v101 = 0;
    v41 = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v22 + 40LL))(v22, &v101);
    if ( v41 )
      goto LABEL_123;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49288935>::GetImpl'::`2'::impl) )
    {
      if ( v101 > 1 )
        goto LABEL_130;
    }
    else if ( v101 )
    {
LABEL_130:
      *((_DWORD *)a4 + 2 * v25) = -2147483637;
      goto LABEL_238;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49288935>::GetImpl'::`2'::impl);
    v120 = 0;
    *(_OWORD *)Src = 0;
    if ( IsEnabled )
    {
      if ( v101 == 1 )
      {
        v88 = 0;
        v48 = (*(__int64 (__fastcall **)(void *, unsigned int *, _QWORD))(*(_QWORD *)v22 + 56LL))(v22, &v88, 0);
        if ( v48 == -2147024774 )
        {
          *(void **)&v103 = Src[1];
          if ( (void *)v88 >= (void *)((char *)Src[1] - (char *)Src[0]) )
          {
            if ( (void *)v88 <= (void *)((char *)Src[1] - (char *)Src[0]) )
              goto LABEL_142;
            if ( v88 > v120 - (unsigned __int64)Src[0] )
            {
              std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(Src, v88);
              goto LABEL_142;
            }
            v110 = v88 - (unsigned __int64)((char *)Src[1] - (char *)Src[0]);
            memset_0(Src[1], 0, v110);
            v49 = (char *)(v103 + v110);
          }
          else
          {
            v49 = (char *)Src[0] + v88;
          }
          Src[1] = v49;
LABEL_142:
          v48 = (*(__int64 (__fastcall **)(void *, unsigned int *, void *))(*(_QWORD *)v22 + 56LL))(v22, &v88, Src[0]);
          if ( v48 )
            goto LABEL_166;
          *(void **)&v103 = Src[1];
          if ( (void *)v88 >= (void *)((char *)Src[1] - (char *)Src[0]) )
          {
            if ( (void *)v88 <= (void *)((char *)Src[1] - (char *)Src[0]) )
              goto LABEL_146;
            if ( v88 > v120 - (unsigned __int64)Src[0] )
            {
              std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(Src, v88);
              goto LABEL_146;
            }
            v53 = v88 - (unsigned __int64)((char *)Src[1] - (char *)Src[0]);
            memset_0(Src[1], 0, v53);
            v50 = (char *)(v53 + v103);
          }
          else
          {
            v50 = (char *)Src[0] + v88;
          }
          Src[1] = v50;
LABEL_146:
          v25 = v91;
          goto LABEL_147;
        }
        if ( !v48 )
        {
LABEL_147:
          *((_WORD *)a4 + 4 * v25 + 4) = 4113;
          *((_DWORD *)a4 + 2 * v25 + 4) = LODWORD(Src[1]) - LODWORD(Src[0]);
          v51 = BatchFilterPropVariantCopyByteArray((__int64)Src);
          *((_QWORD *)a4 + v25 + 3) = v51;
          v52 = Src[0];
          if ( !v51 && Src[0] != Src[1] )
          {
            if ( Src[0] )
            {
              std::_Deallocate<16>(Src[0], v120 - (unsigned __int64)Src[0]);
              *(_OWORD *)Src = 0;
              v120 = 0;
            }
            std::wstring::_Tidy_deallocate((__int64)v121);
            std::wstring::_Tidy_deallocate((__int64)v127);
            std::wstring::_Tidy_deallocate((__int64)v126);
            std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
            winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
            if ( v21 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
            if ( v20 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
            if ( v18 )
              winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
            goto LABEL_281;
          }
          v90 += LODWORD(Src[1]) - LODWORD(Src[0]);
          if ( v90 > 0x40000 )
            goto LABEL_167;
          if ( Src[0] )
            std::_Deallocate<16>(Src[0], v120 - (unsigned __int64)Src[0]);
          goto LABEL_285;
        }
LABEL_166:
        *((_DWORD *)a4 + 2 * v25) = v48;
        v52 = Src[0];
LABEL_167:
        if ( v52 )
        {
          std::_Deallocate<16>(v52, v120 - (_QWORD)v52);
          *(_OWORD *)Src = 0;
          v120 = 0;
        }
LABEL_238:
        std::wstring::_Tidy_deallocate((__int64)v121);
LABEL_289:
        *v111 = v90;
        std::wstring::_Tidy_deallocate((__int64)v127);
        std::wstring::_Tidy_deallocate((__int64)v126);
        std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
        if ( v22 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
        if ( v21 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
        if ( v20 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
        if ( v18 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v95);
        return 0;
      }
      v88 = 0;
      v54 = (*(__int64 (__fastcall **)(void *, unsigned int *, _QWORD))(*(_QWORD *)v22 + 48LL))(v22, &v88, 0);
      if ( v54 != -2147024774 )
      {
        if ( v54 )
        {
LABEL_199:
          *((_DWORD *)a4 + 2 * v25) = v54;
LABEL_200:
          std::vector<float>::_Tidy(Src);
          goto LABEL_238;
        }
        goto LABEL_181;
      }
      *(void **)&v103 = Src[1];
      v55 = ((char *)Src[1] - (char *)Src[0]) >> 2;
      if ( v88 >= v55 )
      {
        if ( v88 <= v55 )
          goto LABEL_177;
        if ( v88 > (unsigned __int64)((signed __int64)(v120 - (unsigned __int64)Src[0]) >> 2) )
        {
          std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(Src, v88);
          goto LABEL_177;
        }
        v57 = 4 * (v88 - v55);
        memset_0(Src[1], 0, v57);
        v56 = (char *)(v57 + v103);
        v25 = v91;
      }
      else
      {
        v56 = (char *)Src[0] + 4 * v88;
      }
      Src[1] = v56;
LABEL_177:
      v54 = (*(__int64 (__fastcall **)(void *, unsigned int *, void *))(*(_QWORD *)v22 + 48LL))(v22, &v88, Src[0]);
      if ( v54 )
        goto LABEL_199;
      *(void **)&v103 = Src[1];
      v58 = ((char *)Src[1] - (char *)Src[0]) >> 2;
      if ( v88 < v58 )
      {
        v59 = (char *)Src[0] + 4 * v88;
LABEL_180:
        Src[1] = v59;
        goto LABEL_181;
      }
      if ( v88 > v58 )
      {
        if ( v88 <= (unsigned __int64)((signed __int64)(v120 - (unsigned __int64)Src[0]) >> 2) )
        {
          v63 = 4 * (v88 - v58);
          memset_0(Src[1], 0, v63);
          v59 = (char *)(v63 + v103);
          goto LABEL_180;
        }
        std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(Src, v88);
      }
LABEL_181:
      v60 = v91;
      *((_WORD *)a4 + 4 * v91 + 4) = 4100;
      *((_DWORD *)a4 + 2 * v60 + 4) = ((char *)Src[1] - (char *)Src[0]) >> 2;
      v61 = BatchFilterPropVariantCopyFloatArray((__int64)Src);
      *((_QWORD *)a4 + v60 + 3) = v61;
      if ( !v61 && Src[0] != Src[1] )
      {
        std::vector<float>::_Tidy(Src);
        std::wstring::_Tidy_deallocate((__int64)v121);
        std::wstring::_Tidy_deallocate((__int64)v127);
        std::wstring::_Tidy_deallocate((__int64)v126);
        std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
        winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
        if ( v21 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
        if ( v20 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
        if ( v18 )
          winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
        goto LABEL_281;
      }
      v62 = v90 + 4 * (((char *)Src[1] - (char *)Src[0]) >> 2);
      v90 = v62;
LABEL_191:
      if ( v62 > 0x40000 )
        goto LABEL_200;
      std::vector<float>::_Tidy(Src);
      goto LABEL_285;
    }
    v88 = 0;
    v64 = (*(__int64 (__fastcall **)(void *, unsigned int *, _QWORD))(*(_QWORD *)v22 + 48LL))(v22, &v88, 0);
    if ( v64 != -2147024774 )
    {
      if ( v64 )
      {
LABEL_228:
        *((_DWORD *)a4 + 2 * v25) = v64;
        goto LABEL_200;
      }
      goto LABEL_213;
    }
    *(void **)&v103 = Src[1];
    v65 = ((char *)Src[1] - (char *)Src[0]) >> 2;
    if ( v88 >= v65 )
    {
      if ( v88 <= v65 )
        goto LABEL_209;
      if ( v88 > (unsigned __int64)((signed __int64)(v120 - (unsigned __int64)Src[0]) >> 2) )
      {
        std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(Src, v88);
        goto LABEL_209;
      }
      v67 = 4 * (v88 - v65);
      memset_0(Src[1], 0, v67);
      v66 = (char *)(v67 + v103);
      v25 = v91;
    }
    else
    {
      v66 = (char *)Src[0] + 4 * v88;
    }
    Src[1] = v66;
LABEL_209:
    v64 = (*(__int64 (__fastcall **)(void *, unsigned int *, void *))(*(_QWORD *)v22 + 48LL))(v22, &v88, Src[0]);
    if ( v64 )
      goto LABEL_228;
    *(void **)&v103 = Src[1];
    v68 = ((char *)Src[1] - (char *)Src[0]) >> 2;
    if ( v88 < v68 )
    {
      v69 = (char *)Src[0] + 4 * v88;
LABEL_212:
      Src[1] = v69;
      goto LABEL_213;
    }
    if ( v88 > v68 )
    {
      if ( v88 <= (unsigned __int64)((signed __int64)(v120 - (unsigned __int64)Src[0]) >> 2) )
      {
        v72 = 4 * (v88 - v68);
        memset_0(Src[1], 0, v72);
        v69 = (char *)(v72 + v103);
        goto LABEL_212;
      }
      std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(Src, v88);
    }
LABEL_213:
    v70 = v91;
    *((_WORD *)a4 + 4 * v91 + 4) = 4100;
    *((_DWORD *)a4 + 2 * v70 + 4) = ((char *)Src[1] - (char *)Src[0]) >> 2;
    v71 = BatchFilterPropVariantCopyFloatArray((__int64)Src);
    *((_QWORD *)a4 + v70 + 3) = v71;
    if ( !v71 && Src[0] != Src[1] )
    {
      std::vector<float>::_Tidy(Src);
      std::wstring::_Tidy_deallocate((__int64)v121);
      std::wstring::_Tidy_deallocate((__int64)v127);
      std::wstring::_Tidy_deallocate((__int64)v126);
      std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>((void **)&v96);
      winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v98);
      if ( v21 )
        winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v99);
      if ( v20 )
        winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v100);
      if ( v18 )
        winrt::com_ptr<ITextFilter>::unconditional_release_ref(&v97);
      goto LABEL_281;
    }
    v62 = v90 + 4 * (((char *)Src[1] - (char *)Src[0]) >> 2);
    v90 = v62;
    goto LABEL_191;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<0>(retaddr);
  }
  return result;
}

```

## disassembly

```asm
0x14000e7ec  mov     rax, rsp
0x14000e7ef  push    rdi
0x14000e7f0  push    r12
0x14000e7f2  push    r13
0x14000e7f4  push    r14
0x14000e7f6  push    r15
0x14000e7f8  sub     rsp, 210h
0x14000e7ff  mov     qword ptr [rax-118h], 0FFFFFFFFFFFFFFFEh
0x14000e80a  mov     [rax+8], rbx
0x14000e80e  mov     [rax+18h], rsi
0x14000e812  mov     rax, cs:__security_cookie
0x14000e819  xor     rax, rsp
0x14000e81c  mov     [rsp+238h+var_30], rax
0x14000e824  mov     r13, r9
0x14000e827  mov     r9d, r8d
0x14000e82a  mov     [rsp+238h+var_190], r8d
0x14000e832  mov     rbx, rcx
0x14000e835  mov     rax, [rsp+238h+arg_20]
0x14000e83d  mov     [rsp+238h+var_188], rax
0x14000e845  mov     rcx, [rsp+238h+arg_28]
0x14000e84d  mov     [rsp+238h+var_168], rcx
0x14000e855  mov     r11d, 1
0x14000e85b  mov     [rsp+238h+var_177], r11b
0x14000e863  xor     r12d, r12d
0x14000e866  mov     [rax], r12d
0x14000e869  mov     [rcx], r12d
0x14000e86c  mov     r8d, r12d
0x14000e86f  test    r9d, r9d
0x14000e872  jz      short loc_14000E8B0
0x14000e874  mov     ecx, r12d
0x14000e877  lea     rax, [rcx+rcx*8]
0x14000e87b  mov     [r13+rax*8+0], r12
0x14000e880  xorps   xmm0, xmm0
0x14000e883  xor     r10d, r10d
0x14000e886  movups  xmmword ptr [r13+rax*8+8], xmm0
0x14000e88c  mov     [r13+rax*8+18h], r10
0x14000e891  mov     [r13+rax*8+20h], r12d
0x14000e896  xorps   xmm0, xmm0
0x14000e899  movups  xmmword ptr [r13+rax*8+28h], xmm0
0x14000e89f  movups  xmmword ptr [r13+rax*8+38h], xmm0
0x14000e8a5  add     r8d, r11d
0x14000e8a8  add     rcx, r11
0x14000e8ab  cmp     r8d, r9d
0x14000e8ae  jb      short loc_14000E877
0x14000e8b0  mov     r15, r12
0x14000e8b3  mov     [rsp+238h+var_1E8], r12
0x14000e8b8  test    rdx, rdx
0x14000e8bb  jz      short loc_14000E914
0x14000e8bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e8c1  inc     rax
0x14000e8c4  cmp     [rdx+rax*2], r12w
0x14000e8c9  jnz     short loc_14000E8C1
0x14000e8cb  test    rax, rax
0x14000e8ce  jz      short loc_14000E914
0x14000e8d0  lea     rcx, [rsp+238h+var_1E8]
0x14000e8d5  call    ?open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEB_WK_N@Z
0x14000e8da  mov     edi, eax
0x14000e8dc  test    eax, eax
0x14000e8de  jns     short loc_14000E90F
0x14000e8e0  mov     rcx, [rsp+238h]; this
0x14000e8e8  mov     r9d, eax; char *
0x14000e8eb  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\Search\\mss"...
0x14000e8f2  mov     edx, 0F6h; void *
0x14000e8f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e8fc  nop
0x14000e8fd  lea     rcx, [rsp+238h+var_1E8]
0x14000e902  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e907  nop
0x14000e908  mov     eax, edi
0x14000e90a  jmp     loc_1400101FD
0x14000e90f  mov     r15, [rsp+238h+var_1E8]
0x14000e914  mov     rdi, r12
0x14000e917  mov     [rsp+238h+var_1D8], r12
0x14000e91c  mov     rsi, r12
0x14000e91f  test    rbx, rbx
0x14000e922  jz      short loc_14000E93F
0x14000e924  mov     rdi, rbx
0x14000e927  mov     [rsp+238h+var_1D8], rbx
0x14000e92c  mov     rax, [rbx]
0x14000e92f  mov     rcx, rbx
0x14000e932  mov     rax, [rax+8]
0x14000e936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e93b  nop
0x14000e93c  mov     rsi, rbx
0x14000e93f  test    rsi, rsi
0x14000e942  jnz     short loc_14000E949
0x14000e944  mov     rbx, r12
0x14000e947  jmp     short loc_14000E96D
0x14000e949  mov     [rsp+238h+var_1F8], r12
0x14000e94e  mov     rax, [rsi]
0x14000e951  lea     r8, [rsp+238h+var_1F8]
0x14000e956  lea     rdx, ??$guid_v@UITextFilter@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<ITextFilter>
0x14000e95d  mov     rcx, rsi
0x14000e960  mov     rax, [rax]
0x14000e963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e968  mov     rbx, [rsp+238h+var_1F8]
0x14000e96d  mov     [rsp+238h+var_1C0], rbx
0x14000e972  test    rsi, rsi
0x14000e975  jnz     short loc_14000E981
0x14000e977  mov     r14, r12
0x14000e97a  mov     [rsp+238h+var_1C8], r12
0x14000e97f  jmp     short loc_14000E9AD
0x14000e981  mov     [rsp+238h+var_1F8], r12
0x14000e986  mov     rax, [rsi]
0x14000e989  lea     r8, [rsp+238h+var_1F8]
0x14000e98e  lea     rdx, ??$guid_v@UIValueFilter@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IValueFilter>
0x14000e995  mov     rcx, rsi
0x14000e998  mov     rax, [rax]
0x14000e99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9a0  mov     r14, [rsp+238h+var_1F8]
0x14000e9a5  mov     [rsp+238h+var_1C8], r14
0x14000e9aa  mov     r12, r14
0x14000e9ad  xor     eax, eax
0x14000e9af  mov     [rsp+238h+var_1F8], rax
0x14000e9b4  test    rsi, rsi
0x14000e9b7  jnz     short loc_14000E9C2
0x14000e9b9  mov     esi, eax
0x14000e9bb  mov     [rsp+238h+var_1D0], rax
0x14000e9c0  jmp     short loc_14000E9EB
0x14000e9c2  mov     rax, [rsi]
0x14000e9c5  lea     r8, [rsp+238h+var_1F8]
0x14000e9ca  lea     rdx, ??$guid_v@UISemanticFilter@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<ISemanticFilter>
0x14000e9d1  mov     rcx, rsi
0x14000e9d4  mov     rax, [rax]
0x14000e9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9dc  mov     rsi, [rsp+238h+var_1F8]
0x14000e9e1  mov     [rsp+238h+var_1D0], rsi
0x14000e9e6  mov     [rsp+238h+var_1F8], rsi
0x14000e9eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e9f2  mov     ecx, 20000h; unsigned __int64
0x14000e9f7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000e9fc  mov     [rsp+238h+var_1E0], rax
0x14000ea01  test    rax, rax
0x14000ea04  jnz     loc_14000EA8E
0x14000ea0a  mov     rcx, [rsp+238h]; this
0x14000ea12  mov     r9d, 8007000Eh; char *
0x14000ea18  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\Search\\mss"...
0x14000ea1f  mov     edx, 104h; void *
0x14000ea24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ea29  nop
0x14000ea2a  lea     rcx, [rsp+238h+var_1E0]
0x14000ea2f  call    ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
0x14000ea34  nop
0x14000ea35  xor     esi, esi
0x14000ea37  cmp     [rsp+238h+var_1F8], rsi
0x14000ea3c  jz      short loc_14000EA49
0x14000ea3e  lea     rcx, [rsp+238h+var_1D0]
0x14000ea43  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14000ea48  nop
0x14000ea49  test    r12, r12
0x14000ea4c  jz      short loc_14000EA59
0x14000ea4e  lea     rcx, [rsp+238h+var_1C8]
0x14000ea53  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14000ea58  nop
0x14000ea59  test    rbx, rbx
0x14000ea5c  jz      short loc_14000EA69
0x14000ea5e  lea     rcx, [rsp+238h+var_1C0]
0x14000ea63  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14000ea68  nop
0x14000ea69  test    rdi, rdi
0x14000ea6c  jz      short loc_14000EA79
0x14000ea6e  lea     rcx, [rsp+238h+var_1D8]
0x14000ea73  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14000ea78  nop
0x14000ea79  lea     rcx, [rsp+238h+var_1E8]
0x14000ea7e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ea83  nop
0x14000ea84  mov     eax, 8007000Eh
0x14000ea89  jmp     loc_1400101FD
0x14000ea8e  mov     [rsp+238h+var_1FC], 0
0x14000ea96  lea     rcx, [rsp+238h+var_70]
0x14000ea9e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14000eaa3  nop
0x14000eaa4  lea     rcx, [rsp+238h+var_50]
0x14000eaac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14000eab1  nop
0x14000eab2  xor     eax, eax
0x14000eab4  mov     [rsp+238h+var_200], eax
0x14000eab8  inc     eax
0x14000eaba  mov     [rsp+238h+var_204], eax
0x14000eabe  cmp     eax, [rsp+238h+var_190]
0x14000eac5  jnb     loc_140010172
0x14000eacb  test    r15, r15
0x14000eace  jz      short loc_14000EAE2
0x14000ead0  lea     rcx, [rsp+238h+var_1E8]
0x14000ead5  call    ?is_signaled@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NXZ
0x14000eada  test    al, al
0x14000eadc  jnz     loc_140010172
0x14000eae2  mov     [rsp+238h+var_208], 0
0x14000eae7  mov     rax, [rdi]
0x14000eaea  lea     rdx, [rsp+238h+var_208]
0x14000eaef  mov     rcx, rdi
0x14000eaf2  mov     rax, [rax+20h]
0x14000eaf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eafb  mov     r12d, eax
0x14000eafe  xor     ecx, ecx
0x14000eb00  test    eax, eax
0x14000eb02  jz      loc_14000EB90
0x14000eb08  mov     eax, [rsp+238h+var_1FC]
0x14000eb0c  mov     rcx, [rsp+238h+var_168]
0x14000eb14  mov     [rcx], eax
0x14000eb16  lea     rcx, [rsp+238h+var_50]
0x14000eb1e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000eb23  nop
0x14000eb24  lea     rcx, [rsp+238h+var_70]
0x14000eb2c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000eb31  nop
0x14000eb32  lea     rcx, [rsp+238h+var_1E0]
0x14000eb37  call    ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
0x14000eb3c  nop
0x14000eb3d  test    rsi, rsi
0x14000eb40  jz      short loc_14000EB4D
0x14000eb42  lea     rcx, [rsp+238h+var_1D0]
0x14000eb47  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14000eb4c  nop
0x14000eb4d  test    r14, r14
0x14000eb50  jz      short loc_14000EB5D
0x14000eb52  lea     rcx, [rsp+238h+var_1C8]
0x14000eb57  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14000eb5c  nop
0x14000eb5d  test    rbx, rbx
0x14000eb60  jz      short loc_14000EB6D
0x14000eb62  lea     rcx, [rsp+238h+var_1C0]
0x14000eb67  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14000eb6c  nop
0x14000eb6d  test    rdi, rdi
0x14000eb70  jz      short loc_14000EB7D
0x14000eb72  lea     rcx, [rsp+238h+var_1D8]
0x14000eb77  call    ?unconditional_release_ref@?$com_ptr@UITextFilter@@@winrt@@AEAAXXZ; winrt::com_ptr<ITextFilter>::unconditional_release_ref(void)
0x14000eb7c  nop
0x14000eb7d  lea     rcx, [rsp+238h+var_1E8]
0x14000eb82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000eb87  nop
0x14000eb88  mov     eax, r12d
0x14000eb8b  jmp     loc_1400101FD
0x14000eb90  cmp     [rsp+238h+var_208], cl
0x14000eb94  jz      loc_140010172
0x14000eb9a  mov     rax, [rsp+238h+var_188]
0x14000eba2  inc     dword ptr [rax]
0x14000eba4  mov     eax, [rsp+238h+var_200]
0x14000eba8  lea     r12, [rax+rax*8]
0x14000ebac  mov     [rsp+238h+var_170], r12
0x14000ebb4  xorps   xmm0, xmm0
0x14000ebb7  xor     eax, eax
0x14000ebb9  movups  xmmword ptr [r13+r12*8+8], xmm0
0x14000ebbf  mov     [r13+r12*8+18h], rax
0x14000ebc4  mov     [rsp+238h+var_1B4], ecx
0x14000ebcb  mov     rax, [rdi]
0x14000ebce  lea     rdx, [rsp+238h+var_1B4]
0x14000ebd6  mov     rcx, rdi
0x14000ebd9  mov     rax, [rax+28h]
0x14000ebdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebe2  mov     [rsp+238h+var_1F0], eax
0x14000ebe6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_49093927@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_49093927@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927> `wil::Feature<__WilFeatureTraits_Feature_49093927>::GetImpl(void)'::`2'::impl
0x14000ebed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_49093927@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49093927>::__private_IsEnabled(void)
0x14000ebf2  xor     edx, edx
0x14000ebf4  test    al, al
0x14000ebf6  jz      loc_14000ED8F
0x14000ebfc  mov     [rsp+238h+var_1F8], rdx
0x14000ec01  lea     rdx, [rsp+238h+var_158]
0x14000ec09  lea     rcx, [rsp+238h+var_1F8]
0x14000ec0e  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::start_and_watch_errors(void)
0x14000ec13  lea     rcx, [rsp+238h+var_1F8]
0x14000ec18  call    ??1?$com_ptr_t@V?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>(void)
0x14000ec1d  nop
0x14000ec1e  cmp     [rsp+238h+var_1B4], 3
0x14000ec26  jnz     loc_14000ED33
0x14000ec2c  mov     r12, [rsp+238h+var_120]
0x14000ec34  mov     [rsp+238h+var_1F8], r12
0x14000ec39  test    r12, r12
0x14000ec3c  jz      short loc_14000EC47
0x14000ec3e  lock inc dword ptr [r12+118h]
0x14000ec47  lea     rcx, [r12+8]
0x14000ec4c  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x14000ec51  mov     byte ptr [r12+110h], 1
0x14000ec5a  lea     rcx, [rsp+238h+var_1F8]
0x14000ec5f  call    ??1?$test_data_control@V?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>(void)
0x14000ec64  mov     r12, [rsp+238h+var_120]
0x14000ec6c  mov     [rsp+238h+var_1F8], r12
0x14000ec71  test    r12, r12
0x14000ec74  jz      short loc_14000EC7F
0x14000ec76  lock inc dword ptr [r12+118h]
0x14000ec7f  lea     rcx, [r12+8]
0x14000ec84  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x14000ec89  mov     eax, [rsp+238h+var_1F0]
0x14000ec8d  mov     [r12+114h], eax
0x14000ec95  lea     rcx, [rsp+238h+var_1F8]
0x14000ec9a  call    ??1?$test_data_control@V?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>(void)
0x14000ec9f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x14000eca6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x14000ecab  test    al, al
0x14000ecad  jz      short loc_14000ED29
0x14000ecaf  mov     eax, [rsp+238h+var_1F0]
0x14000ecb3  cmp     eax, 80070216h
0x14000ecb8  jz      short loc_14000ECC1
0x14000ecba  cmp     eax, 8007007Ah
0x14000ecbf  jnz     short loc_14000ED33
0x14000ecc1  mov     rax, [rsp+238h+var_188]
0x14000ecc9  or      edx, 0FFFFFFFFh
0x14000eccc  add     [rax], edx
  ... truncated ...
```
