# AddPackageDependency2

- ea: `0x18010d1a0`
- end: `0x18010d964`
- name: `AddPackageDependency2`
- size: `1988`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18010d180`

## callees

- `0x18000259c`
- `0x180033d08`
- `0x180034020`
- `0x180048f30`
- `0x180049440`
- `0x18004df24`
- `0x180056554`
- `0x180058768`
- `0x180067930`
- `0x180088070`
- `0x18009aa48`
- `0x18009b400`
- `0x18009bfd0`
- `0x18009c1d4`
- `0x18009c38c`
- `0x18009c538`
- `0x18009c5d0`
- `0x18009ccac`
- `0x18009d5d4`
- `0x18009da60`
- `0x1800a7f44`
- `0x1800e4edc`
- `0x18010482c`
- `0x180106f94`
- `0x18010a6cc`
- `0x18010a83c`
- `0x18010d1a0`
- `0x18014bf20`
- `0x18014c24c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRAddPackageDependency` at `0x18010d258`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRAddPackageDependency` at `0x18010d258`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d2f3`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d38d`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d497`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d5b6`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d767`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d87a`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d906`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d2f3`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d38d`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d497`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d5b6`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d767`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d87a`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SRRemovePackageDependency` at `0x18010d906`

## pseudocode

```c
__int64 __fastcall AddPackageDependency2(char *a1, int a2, unsigned int a3, _QWORD *a4, LPWCH *a5)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  LPWCH *v11; // r12
  WCHAR *v12; // rcx
  unsigned __int16 **v13; // r9
  int v14; // eax
  int v15; // eax
  struct _EVENT_DATA_DESCRIPTOR *v16; // rbx
  int v17; // eax
  unsigned int v18; // edi
  int v19; // eax
  struct ARI::DependencyMiniRepository::_HEADER *v20; // rsi
  int v21; // eax
  struct _EVENT_DATA_DESCRIPTOR *v22; // rcx
  ARI::ProcessPackageGraphEntry *v23; // rax
  struct ARI::ProcessPackageGraphEntry *v24; // rax
  struct ARI::ProcessPackageGraphEntry *v25; // rdi
  const unsigned __int16 *v26; // rdx
  int DependencyMiniRepository; // esi
  __int64 v28; // rdx
  HANDLE v29; // rcx
  bool v30; // cc
  int v31; // eax
  WCHAR *v32; // rcx
  ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH *v33; // rsi
  __int64 v34; // rdx
  const struct ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH_NODE *Node; // rax
  const WCHAR *FullName; // rax
  __int64 v37; // rcx
  bool v38; // dl
  int v39; // eax
  WCHAR *v40; // rcx
  int v41; // eax
  struct ARI::ProcessPackageGraphEntry **v42; // rcx
  signed __int32 v43; // esi
  int updated; // eax
  unsigned int v45; // r14d
  int v46; // r8d
  const unsigned __int16 *v47; // r9
  struct ARI::ProcessPackageGraphEntry **v48; // rcx
  int v49; // eax
  int v50; // eax
  WCHAR *v51; // rcx
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  int v55; // eax
  WCHAR *v56; // rcx
  int v57; // eax
  WCHAR *v58; // rcx
  void **bIgnoreCase; // [rsp+28h] [rbp-71h]
  int bIgnoreCasea; // [rsp+28h] [rbp-71h]
  int bIgnoreCaseb; // [rsp+28h] [rbp-71h]
  int bIgnoreCasec; // [rsp+28h] [rbp-71h]
  int bIgnoreCased; // [rsp+28h] [rbp-71h]
  int bIgnoreCasee; // [rsp+28h] [rbp-71h]
  int bIgnoreCasef; // [rsp+28h] [rbp-71h]
  int bIgnoreCaseg; // [rsp+28h] [rbp-71h]
  const void *v67; // [rsp+38h] [rbp-61h]
  LPWCH penv; // [rsp+58h] [rbp-41h] BYREF
  __int64 v69; // [rsp+60h] [rbp-39h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-31h] BYREF
  char v71[8]; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 v72[4]; // [rsp+78h] [rbp-21h] BYREF
  ARI::DependencyMiniRepository::_HEADER *Src; // [rsp+80h] [rbp-19h] BYREF
  __int64 v74; // [rsp+88h] [rbp-11h] BYREF
  LPWCH v75; // [rsp+90h] [rbp-9h] BYREF
  int v76[2]; // [rsp+98h] [rbp-1h] BYREF
  LPWCH *p_penv; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v78; // [rsp+A8h] [rbp+Fh] BYREF
  char v79; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+57h]
  PVOID P; // [rsp+F8h] [rbp+5Fh] BYREF
  int v82; // [rsp+100h] [rbp+67h]
  unsigned int v83; // [rsp+108h] [rbp+6Fh]

  v83 = a3;
  v82 = a2;
  if ( !a1 )
  {
    v8 = 680;
LABEL_3:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)0x80070057LL,
      (int)bIgnoreCase);
    return v9;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl'::`2'::impl)
    && !*(_WORD *)a1 )
  {
    v8 = 683;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 685;
    goto LABEL_3;
  }
  v11 = a5;
  *a4 = 0;
  if ( v11 )
    *v11 = 0;
  v69 = 0;
  p_penv = &penv;
  penv = 0;
  v78 = 0;
  v79 = 1;
  v9 = SRAddPackageDependency(a1, a3, &v69, &v78);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>(&p_penv);
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BC,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)v9,
      (int)bIgnoreCase);
LABEL_14:
    v12 = penv;
    penv = 0;
    if ( v12 )
      FreeEnvironmentStringsW(v12);
    return v9;
  }
  wil::AcquireSRWLockExclusive(v71, &ARI::Globals::s_packageInfoLock);
  P = 0;
  v14 = ARI::DependencyMiniRepository::BuildFilenameForPackage(0, penv, (const unsigned __int16 *)&P, v13);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C9,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)v14,
      (int)bIgnoreCase);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(P);
    if ( v69 )
    {
      v15 = SRRemovePackageDependency();
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v15,
          bIgnoreCasea);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v71);
    goto LABEL_14;
  }
  v16 = (struct _EVENT_DATA_DESCRIPTOR *)P;
  *(_QWORD *)v72 = 0;
  Src = 0;
  hObject = (HANDLE)-1LL;
  v17 = ARI::DependencyMiniRepository::Open(
          (struct _EVENT_DATA_DESCRIPTOR *)P,
          v72,
          (unsigned __int64 *)&Src,
          &hObject,
          bIgnoreCase);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CD,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)v17,
      bIgnoreCaseb);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v69 )
    {
      v19 = SRRemovePackageDependency();
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v19,
          bIgnoreCasec);
    }
LABEL_105:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v71);
    v58 = penv;
    penv = 0;
    if ( v58 )
      FreeEnvironmentStringsW(v58);
    return v18;
  }
  v20 = Src;
  v21 = ARI::DependencyMiniRepository::_HEADER::Verify(Src, *(unsigned __int64 *)v72);
  v18 = v21;
  if ( v21 < 0 )
  {
    v22 = (struct _EVENT_DATA_DESCRIPTOR *)&stru_1802966F0;
    if ( v16 )
      v22 = v16;
    ARI::DependencyMiniRepository::LogDMRCorrupt(
      v22,
      (const unsigned __int16 *)(unsigned int)v21,
      *(int *)v72,
      0,
      0x38495241u,
      (unsigned int)v20,
      v67);
    goto LABEL_100;
  }
  v23 = (ARI::ProcessPackageGraphEntry *)ARI::Allocate<unsigned char>(208);
  if ( !v23
    || (v24 = (struct ARI::ProcessPackageGraphEntry *)ARI::ProcessPackageGraphEntry::ProcessPackageGraphEntry(v23),
        (v25 = v24) == 0) )
  {
    v18 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCaseb);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
LABEL_100:
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v69 )
    {
      v57 = SRRemovePackageDependency();
      if ( v57 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v57,
          bIgnoreCased);
    }
    goto LABEL_105;
  }
  v26 = (const unsigned __int16 *)&stru_1802966F0;
  if ( v16 )
    v26 = (const unsigned __int16 *)v16;
  DependencyMiniRepository = ARI::Globals::LoadDependencyMiniRepository(v20, v26, v24);
  if ( DependencyMiniRepository < 0 )
  {
    v28 = 728;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)DependencyMiniRepository,
      bIgnoreCaseb);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v25);
    v29 = hObject;
    v30 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_39:
    if ( v30 )
      CloseHandle(v29);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v69 )
    {
      v31 = SRRemovePackageDependency();
      if ( v31 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v31,
          bIgnoreCasee);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v71);
    v32 = penv;
    penv = 0;
    if ( v32 )
      FreeEnvironmentStringsW(v32);
    return (unsigned int)DependencyMiniRepository;
  }
  v33 = (ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH *)*((_QWORD *)v25 + 13);
  if ( !v33 )
  {
    v34 = 731;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)0x8000FFFFLL,
      bIgnoreCaseb);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v25);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v69 )
    {
      v39 = SRRemovePackageDependency();
      if ( v39 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v39,
          bIgnoreCasef);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v71);
    v40 = penv;
    penv = 0;
    if ( v40 )
      FreeEnvironmentStringsW(v40);
    return 2147549183LL;
  }
  Node = ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH::GetNode(
           *((ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH **)v25 + 13),
           0);
  if ( !Node )
  {
    v34 = 733;
    goto LABEL_57;
  }
  FullName = ARI::DependencyMiniRepository::_PACKAGE_IDENTITY::GetFullName((const struct ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH_NODE *)((char *)Node + 8));
  if ( CompareStringOrdinal(FullName, (*(unsigned __int16 *)(v37 + 30) >> 1) - 1, penv, -1, 1) != 2 )
  {
    v34 = 734;
    goto LABEL_57;
  }
  LODWORD(P) = 0;
  DependencyMiniRepository = ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH::CountPackageFamilyInGraphByPackageFullName(
                               v33,
                               penv,
                               (unsigned int *)&P);
  if ( DependencyMiniRepository < 0 )
  {
    v28 = 736;
    goto LABEL_38;
  }
  if ( !(_DWORD)P )
  {
    v34 = 737;
    goto LABEL_57;
  }
  if ( (a3 & 2) != 0 )
  {
    *((_DWORD *)v25 + 6) = (_DWORD)P;
    ARI::ProcessPackageGraphEntry::SetAlternatePathForLoaderIsFirstPackageFamily(v25, v38);
  }
  v41 = v82;
  *((_DWORD *)v25 + 4) |= 8u;
  *((_DWORD *)v25 + 5) = v41;
  *((_QWORD *)v25 + 4) = v69;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl'::`2'::impl) )
  {
    DependencyMiniRepository = ARI::ProcessPackageGraphEntry::SetDependencyGraphId(v25, (const unsigned __int16 *)a1);
    if ( DependencyMiniRepository < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2F0,
        (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
        (const char *)(unsigned int)DependencyMiniRepository,
        (int)"%ls",
        a1);
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v25);
      v29 = hObject;
      v30 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
      goto LABEL_39;
    }
  }
  P = 0;
  DependencyMiniRepository = ARI::ProcessPackageGraphEntry::Insert(
                               v42,
                               v25,
                               a3 & 1,
                               (struct ARI::ProcessPackageGraphEntry **)&P);
  if ( DependencyMiniRepository < 0 )
  {
    v28 = 758;
    goto LABEL_38;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl'::`2'::impl) )
  {
    v43 = _InterlockedIncrement((volatile signed __int32 *)&ARI::Globals::s_generationId);
  }
  else
  {
    v43 = 0;
    _InterlockedAdd((volatile signed __int32 *)&ARI::Globals::s_generationId, 1u);
  }
  updated = ARI::Globals::UpdateLoaderAlternatePath();
  v45 = updated;
  if ( updated >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl'::`2'::impl)
      && (unsigned int)dword_18039CCD8 > 4 )
    {
      v75 = penv;
      LODWORD(Src) = v83;
      *(_DWORD *)v72 = v82;
      v74 = 0x1000000;
      LODWORD(P) = v43;
      *(_QWORD *)v76 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v52,
        (unsigned int)byte_18035B13D,
        v53,
        v54,
        (__int64)v76,
        (__int64)v72,
        (__int64)&Src,
        (__int64)&v75,
        (__int64)&P,
        (__int64)&v74);
    }
    *a4 = v69;
    v69 = 0;
    if ( v11 )
    {
      *v11 = penv;
      penv = 0;
    }
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v69 )
    {
      v55 = SRRemovePackageDependency();
      if ( v55 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v55,
          bIgnoreCaseb);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v71);
    v56 = penv;
    penv = 0;
    if ( v56 )
      FreeEnvironmentStringsW(v56);
    return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x305,
      (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
      (const char *)(unsigned int)updated,
      bIgnoreCaseb);
    ARI::DependencyMiniRepository::LogDMRRefreshPackageInfoFailed(v16, (const unsigned __int16 *)v45, v46, v47);
    v49 = ARI::ProcessPackageGraphEntry::Remove(v48, v25, (struct ARI::ProcessPackageGraphEntry *)P);
    if ( v49 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x309,
        (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
        (const char *)(unsigned int)v49,
        bIgnoreCaseg);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v16);
    if ( v69 )
    {
      v50 = SRRemovePackageDependency();
      if ( v50 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2C3,
          (unsigned int)"onecore\\base\\appmodel\\runtime\\src\\processpackagegraph.cpp",
          (const char *)(unsigned int)v50,
          bIgnoreCaseg);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v71);
    v51 = penv;
    penv = 0;
    if ( v51 )
      FreeEnvironmentStringsW(v51);
    return v45;
  }
}

```

## disassembly

```asm
0x18010d1a0  mov     rax, rsp
0x18010d1a3  mov     [rax+20h], rbx
0x18010d1a7  mov     [rax+18h], r8d
0x18010d1ab  mov     [rax+10h], edx
0x18010d1ae  push    rbp
0x18010d1af  push    rsi
0x18010d1b0  push    rdi
0x18010d1b1  push    r12
0x18010d1b3  push    r13
0x18010d1b5  push    r14
0x18010d1b7  push    r15
0x18010d1b9  lea     rbp, [rax-57h]
0x18010d1bd  sub     rsp, 0B0h
0x18010d1c4  xor     esi, esi
0x18010d1c6  mov     r13, r9
0x18010d1c9  mov     r14d, r8d
0x18010d1cc  mov     r15, rcx
0x18010d1cf  test    rcx, rcx
0x18010d1d2  jnz     short loc_18010D1F8
0x18010d1d4  mov     edx, 2A8h; void *
0x18010d1d9  mov     rcx, [rbp+57h]; this
0x18010d1dd  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d1e4  mov     ebx, 80070057h
0x18010d1e9  mov     r9d, ebx; char *
0x18010d1ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d1f1  mov     eax, ebx
0x18010d1f3  jmp     loc_18010D949
0x18010d1f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2> `wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl(void)'::`2'::impl
0x18010d1ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(void)
0x18010d204  test    al, al
0x18010d206  jz      short loc_18010D215
0x18010d208  cmp     [r15], si
0x18010d20c  jnz     short loc_18010D215
0x18010d20e  mov     edx, 2ABh
0x18010d213  jmp     short loc_18010D1D9
0x18010d215  test    r13, r13
0x18010d218  jnz     short loc_18010D221
0x18010d21a  mov     edx, 2ADh
0x18010d21f  jmp     short loc_18010D1D9
0x18010d221  mov     r12, [rbp+4Fh+arg_20]
0x18010d225  mov     [r13+0], rsi
0x18010d229  test    r12, r12
0x18010d22c  jz      short loc_18010D232
0x18010d22e  mov     [r12], rsi
0x18010d232  lea     rax, [rbp+4Fh+penv]
0x18010d236  mov     [rbp+4Fh+var_88], rsi
0x18010d23a  lea     r9, [rbp+4Fh+var_40]
0x18010d23e  mov     [rbp+4Fh+var_48], rax
0x18010d242  lea     r8, [rbp+4Fh+var_88]
0x18010d246  mov     [rbp+4Fh+penv], rsi
0x18010d24a  mov     edx, r14d
0x18010d24d  mov     [rbp+4Fh+var_40], rsi
0x18010d251  mov     rcx, r15
0x18010d254  mov     [rbp+4Fh+var_38], 1
0x18010d258  call    cs:__imp_SRAddPackageDependency
0x18010d25e  lea     rcx, [rbp+4Fh+var_48]
0x18010d262  mov     ebx, eax
0x18010d264  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>(void)
0x18010d269  test    ebx, ebx
0x18010d26b  jns     short loc_18010D2A0
0x18010d26d  mov     rcx, [rbp+57h]; this
0x18010d271  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d278  mov     r9d, ebx; char *
0x18010d27b  mov     edx, 2BCh; void *
0x18010d280  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d285  mov     rcx, [rbp+4Fh+penv]; penv
0x18010d289  mov     [rbp+4Fh+penv], rsi
0x18010d28d  test    rcx, rcx
0x18010d290  jz      loc_18010D1F1
0x18010d296  call    FreeEnvironmentStringsW
0x18010d29b  jmp     loc_18010D1F1
0x18010d2a0  lea     rdx, ?s_packageInfoLock@Globals@ARI@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK ARI::Globals::s_packageInfoLock
0x18010d2a7  lea     rcx, [rbp+4Fh+var_78]
0x18010d2ab  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18010d2b0  mov     rdx, [rbp+4Fh+penv]; void *
0x18010d2b4  lea     r8, [rbp+4Fh+P]; unsigned __int16 *
0x18010d2b8  xor     ecx, ecx; this
0x18010d2ba  mov     [rbp+4Fh+P], rsi
0x18010d2be  call    ?BuildFilenameForPackage@DependencyMiniRepository@ARI@@YAJPEAXPEBGPEAPEAG@Z; ARI::DependencyMiniRepository::BuildFilenameForPackage(void *,ushort const *,ushort * *)
0x18010d2c3  mov     ebx, eax
0x18010d2c5  test    eax, eax
0x18010d2c7  jns     short loc_18010D323
0x18010d2c9  mov     rcx, [rbp+57h]; this
0x18010d2cd  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d2d4  mov     r9d, eax; char *
0x18010d2d7  mov     edx, 2C9h; void *
0x18010d2dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d2e1  mov     rcx, [rbp+4Fh+P]; P
0x18010d2e5  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18010d2ea  mov     rcx, [rbp+4Fh+var_88]
0x18010d2ee  test    rcx, rcx
0x18010d2f1  jz      short loc_18010D315
0x18010d2f3  call    cs:__imp_SRRemovePackageDependency
0x18010d2f9  test    eax, eax
0x18010d2fb  jns     short loc_18010D315
0x18010d2fd  mov     rcx, [rbp+57h]; this
0x18010d301  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d308  mov     r9d, eax; char *
0x18010d30b  mov     edx, 2C3h; void *
0x18010d310  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010d315  lea     rcx, [rbp+4Fh+var_78]
0x18010d319  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18010d31e  jmp     loc_18010D285
0x18010d323  mov     rbx, [rbp+4Fh+P]
0x18010d327  lea     r9, [rbp+4Fh+hObject]; void **
0x18010d32b  mov     rcx, rbx; this
0x18010d32e  mov     qword ptr [rbp+4Fh+var_70], rsi
0x18010d332  lea     r8, [rbp+4Fh+Src]; unsigned __int64 *
0x18010d336  mov     [rbp+4Fh+Src], rsi
0x18010d33a  lea     rdx, [rbp+4Fh+var_70]; unsigned __int16 *
0x18010d33e  mov     [rbp+4Fh+hObject], 0FFFFFFFFFFFFFFFFh
0x18010d346  call    ?Open@DependencyMiniRepository@ARI@@YAJPEBGPEA_KPEAPEAX2@Z; ARI::DependencyMiniRepository::Open(ushort const *,unsigned __int64 *,void * *,void * *)
0x18010d34b  mov     edi, eax
0x18010d34d  test    eax, eax
0x18010d34f  jns     short loc_18010D3C5
0x18010d351  mov     rcx, [rbp+57h]; this
0x18010d355  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d35c  mov     r9d, eax; char *
0x18010d35f  mov     edx, 2CDh; void *
0x18010d364  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d369  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18010d36d  lea     rdx, [rcx-1]
0x18010d371  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18010d375  ja      short loc_18010D37C
0x18010d377  call    CloseHandle
0x18010d37c  mov     rcx, rbx; P
0x18010d37f  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18010d384  mov     rcx, [rbp+4Fh+var_88]
0x18010d388  test    rcx, rcx
0x18010d38b  jz      short loc_18010D3AF
0x18010d38d  call    cs:__imp_SRRemovePackageDependency
0x18010d393  test    eax, eax
0x18010d395  jns     short loc_18010D3AF
0x18010d397  mov     rcx, [rbp+57h]; this
0x18010d39b  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d3a2  mov     r9d, eax; char *
0x18010d3a5  mov     edx, 2C3h; void *
0x18010d3aa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010d3af  lea     rcx, [rbp+4Fh+var_78]
0x18010d3b3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18010d3b8  mov     rcx, [rbp+4Fh+penv]
0x18010d3bc  mov     [rbp+4Fh+penv], rsi
0x18010d3c0  jmp     loc_18010D93D
0x18010d3c5  mov     rsi, [rbp+4Fh+Src]
0x18010d3c9  mov     rdx, qword ptr [rbp+4Fh+var_70]; unsigned __int64
0x18010d3cd  mov     rcx, rsi; this
0x18010d3d0  call    ?Verify@_HEADER@DependencyMiniRepository@ARI@@QEBAJ_K@Z; ARI::DependencyMiniRepository::_HEADER::Verify(unsigned __int64)
0x18010d3d5  mov     edi, eax
0x18010d3d7  test    eax, eax
0x18010d3d9  jns     short loc_18010D409
0x18010d3db  mov     r8, qword ptr [rbp+4Fh+var_70]; int
0x18010d3df  lea     rcx, stru_1802966F0
0x18010d3e6  test    rbx, rbx
0x18010d3e9  mov     [rsp+0E0h+var_B8], rsi; unsigned int
0x18010d3ee  mov     edx, eax; unsigned __int16 *
0x18010d3f0  mov     [rsp+0E0h+bIgnoreCase], 38495241h; unsigned int
0x18010d3f8  cmovnz  rcx, rbx; this
0x18010d3fc  xor     r9d, r9d; unsigned __int64
0x18010d3ff  call    ?LogDMRCorrupt@DependencyMiniRepository@ARI@@YAXPEBGJ_KIIPEBX@Z; ARI::DependencyMiniRepository::LogDMRCorrupt(ushort const *,long,unsigned __int64,uint,uint,void const *)
0x18010d404  jmp     loc_18010D8E2
0x18010d409  mov     ecx, 0D0h
0x18010d40e  call    ??$Allocate@E@ARI@@YAPEAE_K@Z; ARI::Allocate<uchar>(unsigned __int64)
0x18010d413  test    rax, rax
0x18010d416  jz      loc_18010D8BE
0x18010d41c  mov     rcx, rax; this
0x18010d41f  call    ??0ProcessPackageGraphEntry@ARI@@QEAA@XZ; ARI::ProcessPackageGraphEntry::ProcessPackageGraphEntry(void)
0x18010d424  mov     rdi, rax
0x18010d427  test    rax, rax
0x18010d42a  jz      loc_18010D8BE
0x18010d430  test    rbx, rbx
0x18010d433  lea     rdx, stru_1802966F0
0x18010d43a  mov     r8, rax; struct ARI::ProcessPackageGraphEntry *
0x18010d43d  mov     rcx, rsi; Src
0x18010d440  cmovnz  rdx, rbx; unsigned __int16 *
0x18010d444  call    ?LoadDependencyMiniRepository@Globals@ARI@@SAJPEAU_HEADER@DependencyMiniRepository@2@PEBGPEAVProcessPackageGraphEntry@2@@Z; ARI::Globals::LoadDependencyMiniRepository(ARI::DependencyMiniRepository::_HEADER *,ushort const *,ARI::ProcessPackageGraphEntry *)
0x18010d449  mov     esi, eax
0x18010d44b  test    eax, eax
0x18010d44d  jns     loc_18010D4DF
0x18010d453  mov     edx, 2D8h; void *
0x18010d458  mov     rcx, [rbp+57h]; this
0x18010d45c  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d463  mov     r9d, esi; char *
0x18010d466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d46b  mov     rcx, rdi; P
0x18010d46e  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18010d473  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18010d477  lea     rdx, [rcx-1]
0x18010d47b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18010d47f  ja      short loc_18010D486
0x18010d481  call    CloseHandle
0x18010d486  mov     rcx, rbx; P
0x18010d489  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18010d48e  mov     rcx, [rbp+4Fh+var_88]
0x18010d492  test    rcx, rcx
0x18010d495  jz      short loc_18010D4B9
0x18010d497  call    cs:__imp_SRRemovePackageDependency
0x18010d49d  test    eax, eax
0x18010d49f  jns     short loc_18010D4B9
0x18010d4a1  mov     rcx, [rbp+57h]; this
0x18010d4a5  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d4ac  mov     r9d, eax; char *
0x18010d4af  mov     edx, 2C3h; void *
0x18010d4b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010d4b9  lea     rcx, [rbp+4Fh+var_78]
0x18010d4bd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18010d4c2  mov     rcx, [rbp+4Fh+penv]; penv
0x18010d4c6  mov     [rbp+4Fh+penv], 0
0x18010d4ce  test    rcx, rcx
0x18010d4d1  jz      short loc_18010D4D8
0x18010d4d3  call    FreeEnvironmentStringsW
0x18010d4d8  mov     eax, esi
0x18010d4da  jmp     loc_18010D949
0x18010d4df  mov     rsi, [rdi+68h]
0x18010d4e3  test    rsi, rsi
0x18010d4e6  jnz     short loc_18010D4F2
0x18010d4e8  mov     edx, 2DBh
0x18010d4ed  jmp     loc_18010D574
0x18010d4f2  xor     edx, edx; unsigned int
0x18010d4f4  mov     rcx, rsi; this
0x18010d4f7  call    ?GetNode@_DEPENDENCY_GRAPH@DependencyMiniRepository@ARI@@QEBAPEBU_DEPENDENCY_GRAPH_NODE@23@I@Z; ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH::GetNode(uint)
0x18010d4fc  test    rax, rax
0x18010d4ff  jnz     short loc_18010D508
0x18010d501  mov     edx, 2DDh
0x18010d506  jmp     short loc_18010D574
0x18010d508  lea     rcx, [rax+8]; this
0x18010d50c  call    ?GetFullName@_PACKAGE_IDENTITY@DependencyMiniRepository@ARI@@QEBAPEBGXZ; ARI::DependencyMiniRepository::_PACKAGE_IDENTITY::GetFullName(void)
0x18010d511  movzx   edx, word ptr [rcx+1Eh]
0x18010d515  or      r9d, 0FFFFFFFFh; cchCount2
0x18010d519  mov     r8, [rbp+4Fh+penv]; lpString2
0x18010d51d  mov     rcx, rax; lpString1
0x18010d520  shr     edx, 1
0x18010d522  dec     edx; cchCount1
0x18010d524  mov     [rsp+0E0h+bIgnoreCase], 1; int
0x18010d52c  call    CompareStringOrdinal
0x18010d531  cmp     eax, 2
0x18010d534  jz      short loc_18010D53D
0x18010d536  mov     edx, 2DEh
0x18010d53b  jmp     short loc_18010D574
0x18010d53d  mov     rdx, [rbp+4Fh+penv]; unsigned __int16 *
0x18010d541  lea     r8, [rbp+4Fh+P]; unsigned int *
0x18010d545  mov     rcx, rsi; this
0x18010d548  mov     dword ptr [rbp+4Fh+P], 0
0x18010d54f  call    ?CountPackageFamilyInGraphByPackageFullName@_DEPENDENCY_GRAPH@DependencyMiniRepository@ARI@@QEBAJPEBGAEAI@Z; ARI::DependencyMiniRepository::_DEPENDENCY_GRAPH::CountPackageFamilyInGraphByPackageFullName(ushort const *,uint &)
0x18010d554  mov     esi, eax
0x18010d556  test    eax, eax
0x18010d558  jns     short loc_18010D564
0x18010d55a  mov     edx, 2E0h
0x18010d55f  jmp     loc_18010D458
0x18010d564  mov     eax, dword ptr [rbp+4Fh+P]
0x18010d567  test    eax, eax
0x18010d569  jnz     loc_18010D601
0x18010d56f  mov     edx, 2E1h; void *
0x18010d574  mov     rcx, [rbp+57h]; this
0x18010d578  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d57f  mov     r9d, 8000FFFFh; char *
0x18010d585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d58a  mov     rcx, rdi; P
0x18010d58d  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18010d592  mov     rcx, [rbp+4Fh+hObject]; hObject
0x18010d596  lea     rax, [rcx-1]
0x18010d59a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010d59e  ja      short loc_18010D5A5
0x18010d5a0  call    CloseHandle
0x18010d5a5  mov     rcx, rbx; P
0x18010d5a8  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18010d5ad  mov     rcx, [rbp+4Fh+var_88]
0x18010d5b1  test    rcx, rcx
0x18010d5b4  jz      short loc_18010D5D8
0x18010d5b6  call    cs:__imp_SRRemovePackageDependency
0x18010d5bc  test    eax, eax
0x18010d5be  jns     short loc_18010D5D8
0x18010d5c0  mov     rcx, [rbp+57h]; this
0x18010d5c4  lea     r8, aOnecoreBaseApp_42; "onecore\\base\\appmodel\\runtime\\src\\"...
0x18010d5cb  mov     r9d, eax; char *
0x18010d5ce  mov     edx, 2C3h; void *
0x18010d5d3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010d5d8  lea     rcx, [rbp+4Fh+var_78]
0x18010d5dc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18010d5e1  mov     rcx, [rbp+4Fh+penv]; penv
0x18010d5e5  mov     [rbp+4Fh+penv], 0
0x18010d5ed  test    rcx, rcx
0x18010d5f0  jz      short loc_18010D5F7
0x18010d5f2  call    FreeEnvironmentStringsW
0x18010d5f7  mov     eax, 8000FFFFh
0x18010d5fc  jmp     loc_18010D949
0x18010d601  test    r14b, 2
0x18010d605  jz      short loc_18010D612
0x18010d607  mov     rcx, rdi; this
0x18010d60a  mov     [rdi+18h], eax
0x18010d60d  call    ?SetAlternatePathForLoaderIsFirstPackageFamily@ProcessPackageGraphEntry@ARI@@QEAAX_N@Z; ARI::ProcessPackageGraphEntry::SetAlternatePathForLoaderIsFirstPackageFamily(bool)
0x18010d612  mov     eax, [rbp+4Fh+arg_8]
0x18010d615  or      dword ptr [rdi+10h], 8
0x18010d619  mov     [rdi+14h], eax
0x18010d61c  mov     rax, [rbp+4Fh+var_88]
0x18010d620  mov     [rdi+20h], rax
0x18010d624  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2> `wil::Feature<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::GetImpl(void)'::`2'::impl
0x18010d62b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DynamicDependency_LogPackageGraphChanges2>::__private_IsEnabled(void)
0x18010d630  test    al, al
0x18010d632  jz      short loc_18010D687
0x18010d634  mov     rdx, r15; unsigned __int16 *
  ... truncated ...
```
