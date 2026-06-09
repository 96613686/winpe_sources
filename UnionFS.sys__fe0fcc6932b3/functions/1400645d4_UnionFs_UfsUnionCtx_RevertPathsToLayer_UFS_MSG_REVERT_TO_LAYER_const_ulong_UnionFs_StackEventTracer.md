# UnionFs::UfsUnionCtx::RevertPathsToLayer(UFS_MSG_REVERT_TO_LAYER const &,ulong,UnionFs::StackEventTracer &)

- ea: `0x1400645d4`
- end: `0x1400652fc`
- name: `?RevertPathsToLayer@UfsUnionCtx@UnionFs@@QEAAJAEBUUFS_MSG_REVERT_TO_LAYER@@KAEAVStackEventTracer@2@@Z`
- size: `3368`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_REVERT_TO_LAYER *, unsigned int, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000e83c`

## callees

- `0x14000f81c`
- `0x140010ba8`
- `0x1400111b8`
- `0x14001f4c8`
- `0x1400210fc`
- `0x140036268`
- `0x14003cf90`
- `0x14003d2a8`
- `0x140043a64`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14005cddc`
- `0x1400611a4`
- `0x1400645d4`
- `0x140065304`
- `0x140067718`
- `0x14006a5bc`
- `0x14006f3fc`
- `0x140079d44`
- `0x140079f68`
- `0x14007a0c0`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400646de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064c0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006500a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065026`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400650ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006510a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065218`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065234`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400652b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400652cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400646de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064c0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006500a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065026`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400650ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006510a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065218`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065234`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400652b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400652cd`
- `ntoskrnl!ObfDereferenceObject` at `0x140064a36`
- `ntoskrnl!ObfDereferenceObject` at `0x140064aa6`
- `ntoskrnl!ObfDereferenceObject` at `0x140064c39`
- `ntoskrnl!ObfDereferenceObject` at `0x140064d07`
- `ntoskrnl!ObfDereferenceObject` at `0x140064d63`
- `ntoskrnl!ObfDereferenceObject` at `0x140064de0`
- `ntoskrnl!ObfDereferenceObject` at `0x140064e8b`
- `ntoskrnl!ObfDereferenceObject` at `0x140064f91`
- `ntoskrnl!ObfDereferenceObject` at `0x140065075`
- `ntoskrnl!ObfDereferenceObject` at `0x140065159`
- `ntoskrnl!ObfDereferenceObject` at `0x140064a36`
- `ntoskrnl!ObfDereferenceObject` at `0x140064aa6`
- `ntoskrnl!ObfDereferenceObject` at `0x140064c39`
- `ntoskrnl!ObfDereferenceObject` at `0x140064d07`
- `ntoskrnl!ObfDereferenceObject` at `0x140064d63`
- `ntoskrnl!ObfDereferenceObject` at `0x140064de0`
- `ntoskrnl!ObfDereferenceObject` at `0x140064e8b`
- `ntoskrnl!ObfDereferenceObject` at `0x140064f91`
- `ntoskrnl!ObfDereferenceObject` at `0x140065075`
- `ntoskrnl!ObfDereferenceObject` at `0x140065159`
- `FLTMGR!FltCreateFileEx2` at `0x140064a0f`
- `FLTMGR!FltCreateFileEx2` at `0x140064a0f`
- `FLTMGR!FltClose` at `0x140064a8d`
- `FLTMGR!FltClose` at `0x140064c4e`
- `FLTMGR!FltClose` at `0x140064d1c`
- `FLTMGR!FltClose` at `0x140064d78`
- `FLTMGR!FltClose` at `0x140064df5`
- `FLTMGR!FltClose` at `0x140064ea0`
- `FLTMGR!FltClose` at `0x140064fa6`
- `FLTMGR!FltClose` at `0x14006508a`
- `FLTMGR!FltClose` at `0x14006516e`
- `FLTMGR!FltClose` at `0x140064a8d`
- `FLTMGR!FltClose` at `0x140064c4e`
- `FLTMGR!FltClose` at `0x140064d1c`
- `FLTMGR!FltClose` at `0x140064d78`
- `FLTMGR!FltClose` at `0x140064df5`
- `FLTMGR!FltClose` at `0x140064ea0`
- `FLTMGR!FltClose` at `0x140064fa6`
- `FLTMGR!FltClose` at `0x14006508a`
- `FLTMGR!FltClose` at `0x14006516e`

## string_xrefs

- `0x14006518c`: `PUSH: Cache lookup`
- `0x14006469c`: `PUSH: Getting revert path list`
- `0x140064633`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x1400646ad`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064ca5`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064ce1`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064d3d`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064db9`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064e46`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064f45`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x14006504b`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140065133`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x14006519d`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x1400651c9`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x1400651b8`: `PUSH: Combining scratchRootPathNoVolume, revertPath`
- `0x14006470c`: `RevertMessage.PathCount == revertPathIds.size()`
- `0x140064d2a`: `ORIGIN: Attempted scratch deletion with DeleteExisting flag off`
- `0x140064c94`: `ORIGIN: Pushing cache entry`
- `0x140064da8`: `API: Opening scratch file with delete access`
- `0x140064e13`: `ORIGIN: Item path not found in union`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::RevertPathsToLayer(
        UnionFs::UfsUnionCtx *this,
        const struct UFS_MSG_REVERT_TO_LAYER *a2,
        int a3,
        struct UnionFs::StackEventTracer *a4)
{
  UnionFs::UfsUnionCtx *v5; // r12
  int PathRootIDsFromMsg; // ebx
  __m128i si128; // xmm6
  int v11; // eax
  __int64 *v12; // rdi
  __int64 v13; // r13
  unsigned __int64 *v14; // rdx
  __int64 *v15; // rax
  volatile signed __int32 *v16; // rbx
  __int64 v17; // r15
  struct _FLT_INSTANCE *v18; // r15
  unsigned __int64 *v19; // rdx
  __int64 v20; // rax
  volatile signed __int32 *v21; // rbx
  UnionFs::UfsLayerCtx *v22; // rsi
  int v23; // r9d
  __int64 *v24; // rbx
  __int64 v25; // rdx
  NTSTATUS v26; // esi
  __int64 v27; // r11
  __int64 v28; // rcx
  bool v29; // r15
  __int64 v30; // r12
  __int64 v31; // rcx
  char v32; // r13
  void *v33; // rcx
  char v34; // si
  PVOID v35; // rcx
  unsigned __int64 v36; // r13
  unsigned __int64 v37; // rdx
  char *v38; // rsi
  __int64 v39; // r8
  char *v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rax
  _QWORD *v43; // rsi
  int v44; // r12d
  utl::_RefCountBase *v45; // rcx
  PVOID v46; // rcx
  struct _UNICODE_STRING *v47; // rdx
  PVOID v48; // rcx
  void *v49; // rcx
  PVOID v50; // rcx
  struct _UNICODE_STRING *v51; // rdx
  struct _UNICODE_STRING *v52; // rdx
  PVOID v53; // rcx
  int v54; // edx
  const char *v55; // rax
  unsigned int v56; // r14d
  __int64 v57; // r8
  utl::_RefCountBase *v58; // rcx
  PVOID v59; // rcx
  struct _UNICODE_STRING *v60; // rdx
  struct _UNICODE_STRING *v61; // rdx
  __int64 v62; // rcx
  PVOID v63; // rbx
  utl::_RefCountBase *v64; // rcx
  PVOID v65; // rcx
  struct _UNICODE_STRING *v66; // rdx
  struct _UNICODE_STRING *v67; // rdx
  __int64 v68; // rcx
  PVOID v69; // rbx
  PVOID v70; // rcx
  struct _UNICODE_STRING *v71; // rdx
  struct _UNICODE_STRING *v72; // rdx
  __int64 v73; // rcx
  PVOID v74; // rbx
  PVOID v75; // rcx
  const char *v76; // rax
  __int64 v77; // r8
  __int64 v78; // rcx
  PVOID v79; // rbx
  struct _UNICODE_STRING *v80; // rdx
  __int64 v81; // rcx
  PVOID v82; // rbx
  const char *ObjectAttributes; // [rsp+30h] [rbp-D8h]
  const char *ObjectAttributesa; // [rsp+30h] [rbp-D8h]
  PVOID v85; // [rsp+88h] [rbp-80h] BYREF
  bool v86[2]; // [rsp+90h] [rbp-78h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-70h] BYREF
  PVOID v88[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v89; // [rsp+B0h] [rbp-58h]
  struct _UNICODE_STRING v90; // [rsp+B8h] [rbp-50h] BYREF
  int v91[4]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v92; // [rsp+D8h] [rbp-30h]
  PFLT_INSTANCE Instance; // [rsp+E0h] [rbp-28h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+E8h] [rbp-20h] BYREF
  char v95; // [rsp+F8h] [rbp-10h]
  PFILE_OBJECT FileObject[2]; // [rsp+128h] [rbp+20h] BYREF
  char v97; // [rsp+138h] [rbp+30h]
  __int64 v98; // [rsp+140h] [rbp+38h]
  PVOID Object; // [rsp+148h] [rbp+40h] BYREF
  HANDLE v100; // [rsp+150h] [rbp+48h]
  char v101[16]; // [rsp+158h] [rbp+50h] BYREF
  __int128 v102; // [rsp+168h] [rbp+60h] BYREF
  __int64 v103; // [rsp+178h] [rbp+70h]
  __int64 v104; // [rsp+180h] [rbp+78h]
  __int128 v105; // [rsp+188h] [rbp+80h]
  PVOID P[2]; // [rsp+198h] [rbp+90h] BYREF
  __int64 v107; // [rsp+1A8h] [rbp+A0h]
  PVOID v108; // [rsp+1B0h] [rbp+A8h] BYREF
  UNICODE_STRING SourceString; // [rsp+1B8h] [rbp+B0h] BYREF
  struct _OBJECT_ATTRIBUTES v110; // [rsp+1C8h] [rbp+C0h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v112; // [rsp+218h] [rbp+110h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+220h] [rbp+118h] BYREF

  v5 = this;
  v86[0] = 0;
  PathRootIDsFromMsg = UnionFs::UfsPathCache::ProcessSubtreeCollapseList(v86, a4);
  if ( PathRootIDsFromMsg < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)PathRootIDsFromMsg,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x56E00200709LL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
      "PUSH: Processing subtree collapse list",
      ObjectAttributes);
    return (unsigned int)PathRootIDsFromMsg;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v11 = *((_DWORD *)a2 + 1);
  v107 = -1;
  *(__m128i *)P = si128;
  PathRootIDsFromMsg = UnionFs::Utils::GetPathRootIDsFromMsg((int)a2, 28, a3, (int)a2 + 28, v11, (__int64)P, a4);
  if ( PathRootIDsFromMsg < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)PathRootIDsFromMsg,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x56F00200718LL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
      "PUSH: Getting revert path list",
      ObjectAttributesa);
    if ( P[0] != (PVOID)-1LL )
    {
      if ( P[0] )
        ExFreePoolWithTag(P[0], 0);
    }
    return (unsigned int)PathRootIDsFromMsg;
  }
  v12 = (__int64 *)P[0];
  if ( *((_DWORD *)a2 + 1) != ((char *)P[1] - (char *)P[0]) >> 3 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("RevertMessage.PathCount == revertPathIds.size()");
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  }
  v89 = -1;
  v98 = -1;
  *(__m128i *)v88 = si128;
  v13 = -1;
  v92 = -1;
  *(__m128i *)v91 = si128;
  FsFltWil::AcquirePushLockShared(&Instance, (char *)v5 + 72);
  v15 = (__int64 *)*((_QWORD *)v5 + 6);
  v16 = (volatile signed __int32 *)v15[1];
  v17 = *v15;
  if ( v16 )
    _InterlockedIncrement(v16 + 2);
  if ( Instance )
    FsFltWil::Details::ReleasePushLockShared(Instance, v14);
  v18 = **(struct _FLT_INSTANCE ***)(v17 + 8);
  Instance = v18;
  if ( v16 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v16);
  SourceString = 0;
  FsFltWil::AcquirePushLockShared(&FileHandle, (char *)v5 + 72);
  v20 = *((_QWORD *)v5 + 6);
  v21 = *(volatile signed __int32 **)(v20 + 8);
  v22 = *(UnionFs::UfsLayerCtx **)v20;
  if ( v21 )
    _InterlockedIncrement(v21 + 2);
  if ( FileHandle )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)FileHandle, v19);
  *(_WORD *)v86 = UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(v22, &SourceString, 1);
  if ( v21 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v21);
  v24 = v12;
  v90 = 0;
  while ( 1 )
  {
    if ( v24 == P[1] )
    {
      v26 = UnionFs::UfsUnionCtx::RevertPathsToLayerImpl((int)v5, (int)v88, (int)v91, v23, a4);
      if ( v26 >= 0 )
      {
        FsFltWil::Details::FreeUnicodeString(&v90, v80);
        utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v91);
        v82 = v88[0];
        if ( v88[0] != (PVOID)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
            v81,
            v88[0],
            ((char *)v88[1] - (char *)v88[0]) >> 4);
          if ( v82 )
            ExFreePoolWithTag(v82, 0);
        }
        if ( v12 != (__int64 *)-1LL && v12 )
          ExFreePoolWithTag(v12, 0);
        return 0;
      }
      v76 = "PUSH: Reverting items to layer state";
      v77 = 0x57C002007C8LL;
LABEL_146:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v26,
        (int)a4,
        (struct UnionFs::StackEventTracer *)v77,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
        v76,
        ObjectAttributesa);
      goto LABEL_147;
    }
    v25 = *v24;
    *(_OWORD *)FileObject = 0;
    WORD1(FileObject[0]) = *(_WORD *)(v25 + 4) - *(_WORD *)(v25 + 2);
    LOWORD(FileObject[0]) = WORD1(FileObject[0]);
    FileObject[1] = (PFILE_OBJECT)(*(unsigned __int16 *)(v25 + 2) + v25 + 6);
    v26 = UnionFs::Utils::CombinePath(
            &SourceString,
            (PCUNICODE_STRING)FileObject,
            &v90,
            (struct _UNICODE_STRING *)a4,
            0);
    if ( v26 < 0 )
    {
      v76 = "PUSH: Combining scratchRootPathNoVolume, revertPath";
      v77 = 0x57000200733LL;
      goto LABEL_146;
    }
    UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)&UnicodeString, &v90, *(unsigned __int16 *)v86);
    v103 = v27;
    *(_OWORD *)v101 = 0;
    v102 = 0;
    v104 = v27;
    v105 = 0;
    if ( *((_DWORD *)v5 + 7) == (_DWORD)v27 + 2 )
      v28 = *(_QWORD *)(*((_QWORD *)v5 + 4) + 16LL);
    else
      v28 = *((_QWORD *)UnionFs::g_FilterState + 10);
    v26 = UnionFs::UfsPathCache::LookupEntryPriv(v28, v18, &UnicodeString, (unsigned int)(v27 + 2), v27);
    if ( v26 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v26,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x5710020073FLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
        "PUSH: Cache lookup",
        v101);
      goto LABEL_82;
    }
    v29 = 0;
    if ( !(_QWORD)v102 )
      goto LABEL_32;
    v30 = *(_QWORD *)&v91[2];
    v29 = *(_WORD *)(v102 + 168) != 4;
    if ( *(_QWORD *)&v91[2] != v13 )
    {
      v31 = *((_QWORD *)&v102 + 1);
      **(_QWORD **)&v91[2] = v102;
      *(_QWORD *)(v30 + 8) = v31;
      *(_QWORD *)&v91[2] = v30 + 16;
      v5 = this;
      v102 = 0;
LABEL_32:
      v32 = 0;
      goto LABEL_33;
    }
    v36 = (v13 - *(_QWORD *)v91) >> 4;
    v37 = 7 * (v36 >> 2) + 8;
    if ( v37 > 0x7FFFFFFFFFFFFFFLL )
      v37 = 0x7FFFFFFFFFFFFFFLL;
    if ( v36 >= v37
      || (v38 = (char *)&v102 - *(_QWORD *)v91,
          v32 = 0,
          !(unsigned __int8)utl::vector<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsPathCachePayload>>>::_SetCapacity(v91)) )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x5720020074ELL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
        "ORIGIN: Pushing cache entry",
        v101);
      goto LABEL_130;
    }
    v39 = *(_QWORD *)&v91[2];
    v40 = (char *)&v102;
    if ( (unsigned __int64)v38 < *(_QWORD *)&v91[2] - *(_QWORD *)v91 )
      v40 = &v38[*(_QWORD *)v91];
    v41 = *((_QWORD *)v40 + 1);
    v5 = this;
    **(_QWORD **)&v91[2] = *(_QWORD *)v40;
    v42 = v92;
    *(_QWORD *)(v39 + 8) = v41;
    *(_QWORD *)&v91[2] = v39 + 16;
    v98 = v42;
    *(_QWORD *)v40 = 0;
    *((_QWORD *)v40 + 1) = 0;
LABEL_33:
    v110.ObjectName = &v90;
    *(_QWORD *)&v110.Length = 48;
    *(_QWORD *)&v110.Attributes = 512;
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    v110.RootDirectory = 0;
    v112 = 1;
    FileObject[0] = (PFILE_OBJECT)&v85;
    v97 = 1;
    *(_OWORD *)&v110.SecurityDescriptor = 0;
    v85 = 0;
    IoStatusBlock = 0;
    FileObject[1] = 0;
    FileHandle = 0;
    v26 = FltCreateFileEx2(
            *(PFLT_FILTER *)UnionFs::g_FilterState,
            Instance,
            &FileHandle,
            &FileObject[1],
            0x10000u,
            &v110,
            &IoStatusBlock,
            0,
            0,
            7u,
            1u,
            0x200020u,
            0,
            0,
            0,
            &DriverContext);
    if ( v97 )
    {
      v33 = *(void **)FileObject[0];
      *(_QWORD *)FileObject[0] = FileObject[1];
      if ( v33 )
        ObfDereferenceObject(v33);
    }
    if ( v26 < 0 )
    {
      if ( v26 != -1073741766 && v26 != -1073741772 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v26,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x57600200788LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
          "API: Opening scratch file with delete access",
          ObjectAttributesa);
        v53 = v85;
        v85 = 0;
        if ( v53 )
          ObfDereferenceObject(v53);
        if ( FileHandle )
          FltClose(FileHandle);
LABEL_82:
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v101);
        if ( !v95 )
          UnicodeString = 0;
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v51);
LABEL_147:
        FsFltWil::Details::FreeUnicodeString(&v90, v52);
        utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v91);
        v79 = v88[0];
        if ( v88[0] != (PVOID)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
            v78,
            v88[0],
            ((char *)v88[1] - (char *)v88[0]) >> 4);
          if ( v79 )
            ExFreePoolWithTag(v79, 0);
        }
        if ( v12 != (__int64 *)-1LL && v12 )
          ExFreePoolWithTag(v12, 0);
        return (unsigned int)v26;
      }
    }
    else
    {
      if ( (*((_DWORD *)a2 + 6) & 1) == 0 )
      {
        v26 = -1073741535;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000121LL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x57400200779LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
          "ORIGIN: Attempted scratch deletion with DeleteExisting flag off",
          ObjectAttributesa);
        v50 = v85;
        v85 = 0;
        if ( v50 )
          ObfDereferenceObject(v50);
        if ( FileHandle )
          FltClose(FileHandle);
        goto LABEL_82;
      }
      Object = v85;
      v100 = FileHandle;
      v85 = 0;
      FileHandle = 0;
      v34 = utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::push_back(
              v88,
              &Object);
      if ( v100 )
        FltClose(v100);
      v35 = Object;
      Object = 0;
      if ( v35 )
        ObfDereferenceObject(v35);
      if ( !v34 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x57500200782LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
          "ORIGIN: Pushing scratch item",
          ObjectAttributesa);
        v48 = v85;
        v85 = 0;
        if ( v48 )
          ObfDereferenceObject(v48);
        v49 = FileHandle;
        if ( FileHandle )
          goto LABEL_129;
        goto LABEL_130;
      }
      v32 = 1;
    }
    if ( !v29 )
      break;
LABEL_63:
    if ( v32 && !v29 )
    {
      v26 = -1073741811;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000000DLL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x57B002007BCLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
        "ORIGIN: Item to revert to layer has no layer state",
        ObjectAttributesa);
      v75 = v85;
      v85 = 0;
      if ( v75 )
        ObfDereferenceObject(v75);
      if ( FileHandle )
        FltClose(FileHandle);
      goto LABEL_82;
    }
    v46 = v85;
    v85 = 0;
    if ( v46 )
      ObfDereferenceObject(v46);
    if ( FileHandle )
      FltClose(FileHandle);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v101);
    if ( !v95 )
      UnicodeString = 0;
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v47);
    v5 = this;
    ++v24;
    v13 = v98;
    v18 = Instance;
  }
  utl::make_unique<UnionFs::FindAndStatResults,,0>(&v108);
  v43 = v108;
  if ( !v108 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x57700200796LL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
      "ORIGIN: Allocating findAndStatResults",
      ObjectAttributesa);
    v70 = v85;
    v85 = 0;
    if ( v70 )
      ObfDereferenceObject(v70);
    v49 = FileHandle;
    if ( FileHandle )
LABEL_129:
      FltClose(v49);
LABEL_130:
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v101);
    if ( !v95 )
      UnicodeString = 0;
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v71);
    FsFltWil::Details::FreeUnicodeString(&v90, v72);
    utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v91);
    v74 = v88[0];
    if ( v88[0] != (PVOID)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
        v73,
        v88[0],
        ((char *)v88[1] - (char *)v88[0]) >> 4);
      if ( v74 )
        ExFreePoolWithTag(v74, 0);
    }
    if ( v12 != (__int64 *)-1LL && v12 )
      ExFreePoolWithTag(v12, 0);
    return 3221225626LL;
  }
  ObjectAttributesa = (const char *)a4;
  v44 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(v5, &v90, &SourceString, 0, v108);
  if ( v44 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v44,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x5780020079FLL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
      "PUSH: Checking for item in layers",
      (const char *)a4);
    if ( v43 )
    {
      v64 = (utl::_RefCountBase *)v43[11];
      if ( v64 )
        utl::_RefCountBase::_DecStrong(v64);
      ExFreePoolWithTag(v43, 0);
    }
    v65 = v85;
    v85 = 0;
    if ( v65 )
      ObfDereferenceObject(v65);
    if ( FileHandle )
      FltClose(FileHandle);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v101);
    if ( !v95 )
      UnicodeString = 0;
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v66);
    FsFltWil::Details::FreeUnicodeString(&v90, v67);
    utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v91);
    v69 = v88[0];
    if ( v88[0] != (PVOID)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
        v68,
        v88[0],
        ((char *)v88[1] - (char *)v88[0]) >> 4);
      if ( v69 )
        ExFreePoolWithTag(v69, 0);
    }
    if ( v12 != (__int64 *)-1LL && v12 )
      ExFreePoolWithTag(v12, 0);
    return (unsigned int)v44;
  }
  if ( v32 )
    goto LABEL_59;
  if ( *(_WORD *)v43 != 3 )
  {
    if ( *(_WORD *)v43 == 2 )
    {
      v54 = (int)a4;
      v55 = "ORIGIN: Item path not found in union";
      v56 = -1073741766;
      v57 = 0x57A002007AFLL;
      goto LABEL_92;
    }
LABEL_59:
    v29 = *(_WORD *)v43 == 1;
    if ( v43 )
    {
      v45 = (utl::_RefCountBase *)v43[11];
      if ( v45 )
        utl::_RefCountBase::_DecStrong(v45);
      ExFreePoolWithTag(v43, 0);
    }
    goto LABEL_63;
  }
  v54 = (int)a4;
  v55 = "ORIGIN: Item name not found in union";
  v56 = -1073741772;
  v57 = 0x579002007A7LL;
LABEL_92:
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)v56,
    v54,
    (struct UnionFs::StackEventTracer *)v57,
    (unsigned __int64)"UnionFs::UfsUnionCtx::RevertPathsToLayer",
    v55,
    ObjectAttributesa);
  if ( v43 )
  {
    v58 = (utl::_RefCountBase *)v43[11];
    if ( v58 )
      utl::_RefCountBase::_DecStrong(v58);
    ExFreePoolWithTag(v43, 0);
  }
  v59 = v85;
  v85 = 0;
  if ( v59 )
    ObfDereferenceObject(v59);
  if ( FileHandle )
    FltClose(FileHandle);
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v101);
  if ( !v95 )
    UnicodeString = 0;
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v60);
  FsFltWil::Details::FreeUnicodeString(&v90, v61);
  utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v91);
  v63 = v88[0];
  if ( v88[0] != (PVOID)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
      v62,
      v88[0],
      ((char *)v88[1] - (char *)v88[0]) >> 4);
    if ( v63 )
      ExFreePoolWithTag(v63, 0);
  }
  if ( v12 != (__int64 *)-1LL && v12 )
    ExFreePoolWithTag(v12, 0);
  return v56;
}

```

## disassembly

```asm
0x1400645d4  mov     rax, rsp
0x1400645d7  mov     [rax+18h], rbx
0x1400645db  mov     [rax+10h], rdx
0x1400645df  mov     [rax+8], rcx
0x1400645e3  push    rbp
0x1400645e4  push    rsi
0x1400645e5  push    rdi
0x1400645e6  push    r12
0x1400645e8  push    r13
0x1400645ea  push    r14
0x1400645ec  push    r15
0x1400645ee  lea     rbp, [rax-178h]
0x1400645f5  sub     rsp, 240h
0x1400645fc  mov     rsi, rdx
0x1400645ff  movaps  xmmword ptr [rax-48h], xmm6
0x140064603  mov     r12, rcx
0x140064606  mov     [rbp+170h+var_1E8], 0
0x14006460a  mov     rdx, r9; struct UnionFs::StackEventTracer *
0x14006460d  lea     rcx, [rbp+170h+var_1E8]; bool *
0x140064611  mov     r14, r9
0x140064614  mov     edi, r8d
0x140064617  call    ?ProcessSubtreeCollapseList@UfsPathCache@UnionFs@@SAJPEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::ProcessSubtreeCollapseList(bool *,UnionFs::StackEventTracer &)
0x14006461c  mov     ebx, eax
0x14006461e  test    eax, eax
0x140064620  jns     short loc_140064650
0x140064622  lea     rax, aPushProcessing; "PUSH: Processing subtree collapse list"
0x140064629  mov     r8, 56E00200709h; struct UnionFs::StackEventTracer *
0x140064633  lea     r9, aUnionfsUfsunio; "UnionFs::UfsUnionCtx::RevertPathsToLaye"...
0x14006463a  mov     qword ptr [rsp+270h+DesiredAccess], rax; char *
0x14006463f  mov     rdx, r14; int
0x140064642  mov     ecx, ebx; this
0x140064644  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140064649  mov     eax, ebx
0x14006464b  jmp     loc_1400652DB
0x140064650  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140064658  lea     rax, [rbp+170h+P]
0x14006465f  or      r15, 0FFFFFFFFFFFFFFFFh
0x140064663  mov     [rsp+270h+IoStatusBlock], r14; struct UnionFs::StackEventTracer *
0x140064668  mov     [rsp+270h+ObjectAttributes], rax; char *
0x14006466d  lea     r9, [rsi+1Ch]; int
0x140064671  mov     eax, [rsi+4]
0x140064674  mov     r8d, edi; int
0x140064677  mov     rcx, rsi; int
0x14006467a  mov     [rbp+170h+var_D0], r15
0x140064681  lea     edx, [r15+1Dh]; int
0x140064685  mov     [rsp+270h+DesiredAccess], eax; int
0x140064689  movdqu  xmmword ptr [rbp+170h+P], xmm6
0x140064691  call    ?GetPathRootIDsFromMsg@Utils@UnionFs@@YAJPEBXKKQEBUUFS_PATH_ENTRY@@KAEAV?$vector@PEAVCONTAINER_ROOT_ID@UnionFs@@V?$allocator@PEAVCONTAINER_ROOT_ID@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetPathRootIDsFromMsg(void const *,ulong,ulong,UFS_PATH_ENTRY const * const,ulong,utl::vector<UnionFs::CONTAINER_ROOT_ID *,utl::allocator<UnionFs::CONTAINER_ROOT_ID *>> &,UnionFs::StackEventTracer &)
0x140064696  mov     ebx, eax
0x140064698  test    eax, eax
0x14006469a  jns     short loc_1400646EF
0x14006469c  lea     rax, aPushGettingRev; "PUSH: Getting revert path list"
0x1400646a3  mov     r8, 56F00200718h; struct UnionFs::StackEventTracer *
0x1400646ad  lea     r9, aUnionfsUfsunio; "UnionFs::UfsUnionCtx::RevertPathsToLaye"...
0x1400646b4  mov     qword ptr [rsp+270h+DesiredAccess], rax; char *
0x1400646b9  mov     rdx, r14; int
0x1400646bc  mov     ecx, ebx; this
0x1400646be  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400646c3  mov     rcx, [rbp+170h+P]; P
0x1400646ca  cmp     rcx, r15
0x1400646cd  jz      loc_140064649
0x1400646d3  test    rcx, rcx
0x1400646d6  jz      loc_140064649
0x1400646dc  xor     edx, edx; Tag
0x1400646de  call    cs:__imp_ExFreePoolWithTag
0x1400646e5  nop     dword ptr [rax+rax+00h]
0x1400646ea  jmp     loc_140064649
0x1400646ef  mov     rcx, [rbp+170h+P+8]
0x1400646f6  mov     rdi, [rbp+170h+P]
0x1400646fd  mov     eax, [rsi+4]
0x140064700  sub     rcx, rdi
0x140064703  sar     rcx, 3
0x140064707  cmp     rax, rcx
0x14006470a  jz      short loc_140064720
0x14006470c  lea     rcx, aRevertmessageP; "RevertMessage.PathCount == revertPathId"...
0x140064713  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140064718  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140064720  lea     rdx, [r12+48h]
0x140064725  mov     [rbp+170h+var_1C8], r15
0x140064729  lea     rcx, [rbp+170h+Instance]
0x14006472d  mov     [rbp+170h+var_138], r15
0x140064731  movdqu  xmmword ptr [rbp+170h+var_1D8], xmm6
0x140064736  mov     r13, r15
0x140064739  mov     [rbp+170h+var_1A0], r15
0x14006473d  movdqu  xmmword ptr [rbp+170h+var_1B0], xmm6
0x140064742  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140064747  mov     rax, [r12+30h]
0x14006474c  mov     rbx, [rax+8]
0x140064750  mov     r15, [rax]
0x140064753  test    rbx, rbx
0x140064756  jz      short loc_14006475C
0x140064758  lock inc dword ptr [rbx+8]
0x14006475c  mov     rcx, [rbp+170h+Instance]; this
0x140064760  test    rcx, rcx
0x140064763  jz      short loc_14006476A
0x140064765  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14006476a  mov     rax, [r15+8]
0x14006476e  mov     r15, [rax]
0x140064771  mov     [rbp+170h+Instance], r15
0x140064775  test    rbx, rbx
0x140064778  jz      short loc_140064782
0x14006477a  mov     rcx, rbx; this
0x14006477d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140064782  xorps   xmm0, xmm0
0x140064785  lea     rdx, [r12+48h]
0x14006478a  lea     rcx, [rbp+170h+FileHandle]
0x14006478e  movups  xmmword ptr [rbp+170h+SourceString.Length], xmm0
0x140064795  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14006479a  mov     rax, [r12+30h]
0x14006479f  mov     rbx, [rax+8]
0x1400647a3  mov     rsi, [rax]
0x1400647a6  test    rbx, rbx
0x1400647a9  jz      short loc_1400647AF
0x1400647ab  lock inc dword ptr [rbx+8]
0x1400647af  mov     rcx, [rbp+170h+FileHandle]; this
0x1400647b3  test    rcx, rcx
0x1400647b6  jz      short loc_1400647BD
0x1400647b8  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400647bd  mov     r8b, 1; bool
0x1400647c0  lea     rdx, [rbp+170h+SourceString]; struct _UNICODE_STRING *
0x1400647c7  mov     rcx, rsi; this
0x1400647ca  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x1400647cf  mov     word ptr [rbp+170h+var_1E8], ax
0x1400647d3  test    rbx, rbx
0x1400647d6  jz      short loc_1400647E0
0x1400647d8  mov     rcx, rbx; this
0x1400647db  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400647e0  xorps   xmm0, xmm0
0x1400647e3  mov     rbx, rdi
0x1400647e6  movups  xmmword ptr [rbp+170h+var_1C0.Length], xmm0
0x1400647ea  cmp     rbx, [rbp+170h+P+8]
0x1400647f1  jz      loc_140065247
0x1400647f7  mov     rdx, [rbx]
0x1400647fa  lea     r8, [rbp+170h+var_1C0]; UnicodeString
0x1400647fe  xorps   xmm0, xmm0
0x140064801  mov     qword ptr [rsp+270h+DesiredAccess], 0; struct _UNICODE_STRING *
0x14006480a  movups  xmmword ptr [rbp+170h+FileObject], xmm0
0x14006480e  mov     r9, r14; struct _UNICODE_STRING *
0x140064811  movzx   ecx, word ptr [rdx+4]
0x140064815  sub     cx, [rdx+2]
0x140064819  mov     word ptr [rbp+170h+FileObject+2], cx
0x14006481d  mov     word ptr [rbp+170h+FileObject], cx
0x140064821  lea     rcx, [rdx+6]
0x140064825  movzx   eax, word ptr [rdx+2]
0x140064829  lea     rdx, [rbp+170h+FileObject]; Source
0x14006482d  add     rcx, rax
0x140064830  mov     [rbp+170h+FileObject+8], rcx
0x140064834  lea     rcx, [rbp+170h+SourceString]; SourceString
0x14006483b  call    ?CombinePath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEBG@Z; UnionFs::Utils::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort const *)
0x140064840  xor     r11d, r11d
0x140064843  mov     esi, eax
0x140064845  test    eax, eax
0x140064847  js      loc_1400651B8
0x14006484d  movzx   r8d, word ptr [rbp+170h+var_1E8]; unsigned __int16
0x140064852  lea     rdx, [rbp+170h+var_1C0]; struct _UNICODE_STRING *
0x140064856  lea     rcx, [rbp+170h+UnicodeString]; this
0x14006485a  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x14006485f  lea     edx, [r11+2]
0x140064863  mov     [rbp+170h+var_100], r11
0x140064867  xorps   xmm2, xmm2
0x14006486a  xorps   xmm3, xmm3
0x14006486d  xorps   xmm0, xmm0
0x140064870  movdqa  xmmword ptr [rbp+170h+var_120], xmm2
0x140064875  movdqa  [rbp+170h+var_110], xmm3
0x14006487a  mov     [rbp+170h+var_F8], r11
0x14006487e  movdqa  [rbp+170h+var_F0], xmm0
0x140064886  cmp     [r12+1Ch], edx
0x14006488b  jnz     short loc_140064898
0x14006488d  mov     rax, [r12+20h]
0x140064892  mov     rcx, [rax+10h]
0x140064896  jmp     short loc_1400648A3
0x140064898  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006489f  mov     rcx, [rax+50h]
0x1400648a3  mov     [rsp+270h+AllocationSize], r11
0x1400648a8  lea     rax, [rbp+170h+var_120]
0x1400648ac  mov     [rsp+270h+IoStatusBlock], r14
0x1400648b1  lea     r8, [rbp+170h+UnicodeString]
0x1400648b5  mov     r9d, edx
0x1400648b8  mov     [rsp+270h+ObjectAttributes], rax; char *
0x1400648bd  mov     rdx, r15
0x1400648c0  mov     [rsp+270h+DesiredAccess], r11d
0x1400648c5  call    ?LookupEntryPriv@UfsPathCache@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupEntryFlags@2@W4PrivateLookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntryPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupEntryFlags,UnionFs::PrivateLookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x1400648ca  mov     esi, eax
0x1400648cc  test    eax, eax
0x1400648ce  js      loc_14006518C
0x1400648d4  mov     rax, qword ptr [rbp+170h+var_110]
0x1400648d8  xor     r15b, r15b
0x1400648db  test    rax, rax
0x1400648de  jz      short loc_140064925
0x1400648e0  movzx   eax, word ptr [rax+0A8h]
0x1400648e7  nop
0x1400648e8  mov     r12, qword ptr [rbp+170h+var_1B0+8]
0x1400648ec  cmp     ax, 4
0x1400648f0  setnz   r15b
0x1400648f4  cmp     r12, r13
0x1400648f7  jz      loc_140064AC3
0x1400648fd  mov     rax, qword ptr [rbp+170h+var_110]
0x140064901  xorps   xmm0, xmm0
0x140064904  mov     rcx, qword ptr [rbp+170h+var_110+8]
0x140064908  mov     [r12], rax
0x14006490c  mov     [r12+8], rcx
0x140064911  add     r12, 10h
0x140064915  mov     qword ptr [rbp+170h+var_1B0+8], r12
0x140064919  mov     r12, [rbp+170h+arg_0]
0x140064920  movdqa  [rbp+170h+var_110], xmm0
0x140064925  xor     r13d, r13d
0x140064928  mov     rdx, [rbp+170h+Instance]; Instance
0x14006492c  lea     rax, [rbp+170h+var_1C0]
0x140064930  mov     [rbp+170h+var_B0.ObjectName], rax
0x140064937  lea     r9, [rbp+170h+FileObject+8]; FileObject
0x14006493b  mov     eax, 28h ; '('
0x140064940  mov     qword ptr [rbp+170h+var_B0.Length], 30h ; '0'
0x14006494b  xorps   xmm1, xmm1
0x14006494e  mov     qword ptr [rbp+170h+var_B0.Attributes], 200h
0x140064959  movups  xmmword ptr [rbp+170h+var_80.Size], xmm1
0x140064960  mov     [rbp+170h+var_80.Size], ax
0x140064967  lea     r8, [rbp+170h+FileHandle]; FileHandle
0x14006496b  lea     ecx, [rax-27h]
0x14006496e  mov     [rbp+170h+var_B0.RootDirectory], r13
0x140064975  mov     [rbp+170h+var_60], rcx
0x14006497c  lea     rax, [rbp+170h+var_1F0]
0x140064980  mov     [rbp+170h+FileObject], rax
0x140064984  xorps   xmm0, xmm0
0x140064987  mov     [rbp+170h+var_140], cl
0x14006498a  lea     rax, [rbp+170h+var_80]
0x140064991  mov     [rsp+270h+DriverContext], rax; DriverContext
0x140064996  lea     rax, [rbp+170h+var_58]
0x14006499d  mov     [rsp+270h+Flags], r13d; Flags
0x1400649a2  mov     [rsp+270h+EaLength], r13d; EaLength
0x1400649a7  mov     [rsp+270h+EaBuffer], r13; EaBuffer
0x1400649ac  mov     [rsp+270h+CreateOptions], 200020h; CreateOptions
0x1400649b4  mov     [rsp+270h+CreateDisposition], ecx; CreateDisposition
0x1400649b8  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400649bf  mov     [rsp+270h+ShareAccess], 7; ShareAccess
0x1400649c7  mov     [rsp+270h+FileAttributes], r13d; FileAttributes
0x1400649cc  mov     [rsp+270h+AllocationSize], r13; AllocationSize
0x1400649d1  mov     [rsp+270h+IoStatusBlock], rax; IoStatusBlock
0x1400649d6  lea     rax, [rbp+170h+var_B0]
0x1400649dd  movdqu  xmmword ptr [rbp+170h+var_B0.SecurityDescriptor], xmm0
0x1400649e5  mov     [rbp+170h+var_1F0], r13
0x1400649e9  movups  xmmword ptr [rbp+170h+var_58], xmm0
0x1400649f0  mov     [rbp+170h+FileObject+8], r13
0x1400649f4  movups  xmmword ptr [rbp+170h+var_80.DeviceObjectHint], xmm1
0x1400649fb  mov     [rbp+170h+FileHandle], r13
0x1400649ff  mov     rcx, [rcx]; Filter
0x140064a02  mov     [rsp+270h+ObjectAttributes], rax; char *
0x140064a07  mov     [rsp+270h+DesiredAccess], 10000h; DesiredAccess
0x140064a0f  call    cs:__imp_FltCreateFileEx2
0x140064a16  nop     dword ptr [rax+rax+00h]
0x140064a1b  mov     esi, eax
0x140064a1d  cmp     [rbp+170h+var_140], r13b
0x140064a21  jz      short loc_140064A42
0x140064a23  mov     r8, [rbp+170h+FileObject]
0x140064a27  mov     rdx, [rbp+170h+FileObject+8]
0x140064a2b  mov     rcx, [r8]; Object
0x140064a2e  mov     [r8], rdx
0x140064a31  test    rcx, rcx
0x140064a34  jz      short loc_140064A42
0x140064a36  call    cs:__imp_ObfDereferenceObject
0x140064a3d  nop     dword ptr [rax+rax+00h]
0x140064a42  test    esi, esi
0x140064a44  js      loc_140064B5E
0x140064a4a  mov     rax, [rbp+170h+arg_8]
0x140064a51  mov     eax, [rax+18h]
0x140064a54  test    al, 1
0x140064a56  jz      loc_140064D2A
0x140064a5c  mov     rax, [rbp+170h+var_1F0]
0x140064a60  lea     rdx, [rbp+170h+Object]
0x140064a64  mov     [rbp+170h+Object], rax
0x140064a68  lea     rcx, [rbp+170h+var_1D8]
0x140064a6c  mov     rax, [rbp+170h+FileHandle]
0x140064a70  mov     [rbp+170h+var_128], rax
0x140064a74  mov     [rbp+170h+var_1F0], r13
0x140064a78  mov     [rbp+170h+FileHandle], r13
0x140064a7c  call    ?push_back@?$vector@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@2@@utl@@QEAA_N$$QEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@2@@Z; utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::push_back(utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x140064a81  mov     rcx, [rbp+170h+var_128]; FileHandle
0x140064a85  mov     sil, al
0x140064a88  test    rcx, rcx
0x140064a8b  jz      short loc_140064A99
0x140064a8d  call    cs:__imp_FltClose
0x140064a94  nop     dword ptr [rax+rax+00h]
0x140064a99  mov     rcx, [rbp+170h+Object]; Object
0x140064a9d  mov     [rbp+170h+Object], r13
0x140064aa1  test    rcx, rcx
0x140064aa4  jz      short loc_140064AB2
0x140064aa6  call    cs:__imp_ObfDereferenceObject
0x140064aad  nop     dword ptr [rax+rax+00h]
0x140064ab2  test    sil, sil
0x140064ab5  jz      loc_140064CD0
0x140064abb  mov     r13b, 1
0x140064abe  jmp     loc_140064B72
0x140064ac3  mov     rcx, qword ptr [rbp+170h+var_1B0]
0x140064ac7  sub     r13, rcx
0x140064aca  sar     r13, 4
0x140064ace  mov     rax, r13
0x140064ad1  shr     rax, 2
0x140064ad5  imul    rdx, rax, 7
0x140064ad9  mov     rax, 7FFFFFFFFFFFFFFh
0x140064ae3  add     rdx, 8
0x140064ae7  cmp     rdx, rax
  ... truncated ...
```
