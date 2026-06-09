# UnionFs::UfsUnionCtx::RevertPathsToLayer(UFS_MSG_REVERT_TO_LAYER const &,ulong,UnionFs::StackEventTracer &)

- ea: `0x140064454`
- end: `0x14006517c`
- name: `?RevertPathsToLayer@UfsUnionCtx@UnionFs@@QEAAJAEBUUFS_MSG_REVERT_TO_LAYER@@KAEAVStackEventTracer@2@@Z`
- size: `3368`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_REVERT_TO_LAYER *, unsigned int, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000e86c`

## callees

- `0x14000f7fc`
- `0x140010b88`
- `0x140011198`
- `0x14001f428`
- `0x14002105c`
- `0x140036128`
- `0x14003ce70`
- `0x14003d188`
- `0x1400438e4`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14005cc5c`
- `0x140061024`
- `0x140064454`
- `0x140065184`
- `0x140067598`
- `0x14006a3cc`
- `0x14006f20c`
- `0x140079a24`
- `0x140079c48`
- `0x140079da0`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006455e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064a8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064cf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064d84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064da0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064df4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ea6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065098`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400650b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065131`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006514d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006455e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064a8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064cf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064d84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064da0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064df4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064e8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064ea6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064f8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065098`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400650b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065131`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006514d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400648b6`
- `ntoskrnl!ObfDereferenceObject` at `0x140064926`
- `ntoskrnl!ObfDereferenceObject` at `0x140064ab9`
- `ntoskrnl!ObfDereferenceObject` at `0x140064b87`
- `ntoskrnl!ObfDereferenceObject` at `0x140064be3`
- `ntoskrnl!ObfDereferenceObject` at `0x140064c60`
- `ntoskrnl!ObfDereferenceObject` at `0x140064d0b`
- `ntoskrnl!ObfDereferenceObject` at `0x140064e11`
- `ntoskrnl!ObfDereferenceObject` at `0x140064ef5`
- `ntoskrnl!ObfDereferenceObject` at `0x140064fd9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400648b6`
- `ntoskrnl!ObfDereferenceObject` at `0x140064926`
- `ntoskrnl!ObfDereferenceObject` at `0x140064ab9`
- `ntoskrnl!ObfDereferenceObject` at `0x140064b87`
- `ntoskrnl!ObfDereferenceObject` at `0x140064be3`
- `ntoskrnl!ObfDereferenceObject` at `0x140064c60`
- `ntoskrnl!ObfDereferenceObject` at `0x140064d0b`
- `ntoskrnl!ObfDereferenceObject` at `0x140064e11`
- `ntoskrnl!ObfDereferenceObject` at `0x140064ef5`
- `ntoskrnl!ObfDereferenceObject` at `0x140064fd9`
- `FLTMGR!FltCreateFileEx2` at `0x14006488f`
- `FLTMGR!FltCreateFileEx2` at `0x14006488f`
- `FLTMGR!FltClose` at `0x14006490d`
- `FLTMGR!FltClose` at `0x140064ace`
- `FLTMGR!FltClose` at `0x140064b9c`
- `FLTMGR!FltClose` at `0x140064bf8`
- `FLTMGR!FltClose` at `0x140064c75`
- `FLTMGR!FltClose` at `0x140064d20`
- `FLTMGR!FltClose` at `0x140064e26`
- `FLTMGR!FltClose` at `0x140064f0a`
- `FLTMGR!FltClose` at `0x140064fee`
- `FLTMGR!FltClose` at `0x14006490d`
- `FLTMGR!FltClose` at `0x140064ace`
- `FLTMGR!FltClose` at `0x140064b9c`
- `FLTMGR!FltClose` at `0x140064bf8`
- `FLTMGR!FltClose` at `0x140064c75`
- `FLTMGR!FltClose` at `0x140064d20`
- `FLTMGR!FltClose` at `0x140064e26`
- `FLTMGR!FltClose` at `0x140064f0a`
- `FLTMGR!FltClose` at `0x140064fee`

## string_xrefs

- `0x14006500c`: `PUSH: Cache lookup`
- `0x1400644b3`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x14006452d`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064b25`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064b61`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064bbd`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064c39`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064cc6`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064dc5`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064ecb`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140064fb3`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x14006501d`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x140065049`: `UnionFs::UfsUnionCtx::RevertPathsToLayer`
- `0x14006458c`: `RevertMessage.PathCount == revertPathIds.size()`
- `0x14006451c`: `PUSH: Getting revert path list`
- `0x140064b14`: `ORIGIN: Pushing cache entry`
- `0x140065038`: `PUSH: Combining scratchRootPathNoVolume, revertPath`
- `0x140064baa`: `ORIGIN: Attempted scratch deletion with DeleteExisting flag off`
- `0x140064c28`: `API: Opening scratch file with delete access`
- `0x140064c93`: `ORIGIN: Item path not found in union`

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
    v29 = *(_WORD *)(v102 + 160) != 4;
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
0x140064454  mov     rax, rsp
0x140064457  mov     [rax+18h], rbx
0x14006445b  mov     [rax+10h], rdx
0x14006445f  mov     [rax+8], rcx
0x140064463  push    rbp
0x140064464  push    rsi
0x140064465  push    rdi
0x140064466  push    r12
0x140064468  push    r13
0x14006446a  push    r14
0x14006446c  push    r15
0x14006446e  lea     rbp, [rax-178h]
0x140064475  sub     rsp, 240h
0x14006447c  mov     rsi, rdx
0x14006447f  movaps  xmmword ptr [rax-48h], xmm6
0x140064483  mov     r12, rcx
0x140064486  mov     [rbp+170h+var_1E8], 0
0x14006448a  mov     rdx, r9; struct UnionFs::StackEventTracer *
0x14006448d  lea     rcx, [rbp+170h+var_1E8]; bool *
0x140064491  mov     r14, r9
0x140064494  mov     edi, r8d
0x140064497  call    ?ProcessSubtreeCollapseList@UfsPathCache@UnionFs@@SAJPEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::ProcessSubtreeCollapseList(bool *,UnionFs::StackEventTracer &)
0x14006449c  mov     ebx, eax
0x14006449e  test    eax, eax
0x1400644a0  jns     short loc_1400644D0
0x1400644a2  lea     rax, aPushProcessing; "PUSH: Processing subtree collapse list"
0x1400644a9  mov     r8, 56E00200709h; struct UnionFs::StackEventTracer *
0x1400644b3  lea     r9, aUnionfsUfsunio; "UnionFs::UfsUnionCtx::RevertPathsToLaye"...
0x1400644ba  mov     qword ptr [rsp+270h+DesiredAccess], rax; char *
0x1400644bf  mov     rdx, r14; int
0x1400644c2  mov     ecx, ebx; this
0x1400644c4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400644c9  mov     eax, ebx
0x1400644cb  jmp     loc_14006515B
0x1400644d0  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400644d8  lea     rax, [rbp+170h+P]
0x1400644df  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400644e3  mov     [rsp+270h+IoStatusBlock], r14; struct UnionFs::StackEventTracer *
0x1400644e8  mov     [rsp+270h+ObjectAttributes], rax; char *
0x1400644ed  lea     r9, [rsi+1Ch]; int
0x1400644f1  mov     eax, [rsi+4]
0x1400644f4  mov     r8d, edi; int
0x1400644f7  mov     rcx, rsi; int
0x1400644fa  mov     [rbp+170h+var_D0], r15
0x140064501  lea     edx, [r15+1Dh]; int
0x140064505  mov     [rsp+270h+DesiredAccess], eax; int
0x140064509  movdqu  xmmword ptr [rbp+170h+P], xmm6
0x140064511  call    ?GetPathRootIDsFromMsg@Utils@UnionFs@@YAJPEBXKKQEBUUFS_PATH_ENTRY@@KAEAV?$vector@PEAVCONTAINER_ROOT_ID@UnionFs@@V?$allocator@PEAVCONTAINER_ROOT_ID@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetPathRootIDsFromMsg(void const *,ulong,ulong,UFS_PATH_ENTRY const * const,ulong,utl::vector<UnionFs::CONTAINER_ROOT_ID *,utl::allocator<UnionFs::CONTAINER_ROOT_ID *>> &,UnionFs::StackEventTracer &)
0x140064516  mov     ebx, eax
0x140064518  test    eax, eax
0x14006451a  jns     short loc_14006456F
0x14006451c  lea     rax, aPushGettingRev; "PUSH: Getting revert path list"
0x140064523  mov     r8, 56F00200718h; struct UnionFs::StackEventTracer *
0x14006452d  lea     r9, aUnionfsUfsunio; "UnionFs::UfsUnionCtx::RevertPathsToLaye"...
0x140064534  mov     qword ptr [rsp+270h+DesiredAccess], rax; char *
0x140064539  mov     rdx, r14; int
0x14006453c  mov     ecx, ebx; this
0x14006453e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140064543  mov     rcx, [rbp+170h+P]; P
0x14006454a  cmp     rcx, r15
0x14006454d  jz      loc_1400644C9
0x140064553  test    rcx, rcx
0x140064556  jz      loc_1400644C9
0x14006455c  xor     edx, edx; Tag
0x14006455e  call    cs:__imp_ExFreePoolWithTag
0x140064565  nop     dword ptr [rax+rax+00h]
0x14006456a  jmp     loc_1400644C9
0x14006456f  mov     rcx, [rbp+170h+P+8]
0x140064576  mov     rdi, [rbp+170h+P]
0x14006457d  mov     eax, [rsi+4]
0x140064580  sub     rcx, rdi
0x140064583  sar     rcx, 3
0x140064587  cmp     rax, rcx
0x14006458a  jz      short loc_1400645A0
0x14006458c  lea     rcx, aRevertmessageP; "RevertMessage.PathCount == revertPathId"...
0x140064593  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140064598  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400645a0  lea     rdx, [r12+48h]
0x1400645a5  mov     [rbp+170h+var_1C8], r15
0x1400645a9  lea     rcx, [rbp+170h+Instance]
0x1400645ad  mov     [rbp+170h+var_138], r15
0x1400645b1  movdqu  xmmword ptr [rbp+170h+var_1D8], xmm6
0x1400645b6  mov     r13, r15
0x1400645b9  mov     [rbp+170h+var_1A0], r15
0x1400645bd  movdqu  xmmword ptr [rbp+170h+var_1B0], xmm6
0x1400645c2  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400645c7  mov     rax, [r12+30h]
0x1400645cc  mov     rbx, [rax+8]
0x1400645d0  mov     r15, [rax]
0x1400645d3  test    rbx, rbx
0x1400645d6  jz      short loc_1400645DC
0x1400645d8  lock inc dword ptr [rbx+8]
0x1400645dc  mov     rcx, [rbp+170h+Instance]; this
0x1400645e0  test    rcx, rcx
0x1400645e3  jz      short loc_1400645EA
0x1400645e5  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400645ea  mov     rax, [r15+8]
0x1400645ee  mov     r15, [rax]
0x1400645f1  mov     [rbp+170h+Instance], r15
0x1400645f5  test    rbx, rbx
0x1400645f8  jz      short loc_140064602
0x1400645fa  mov     rcx, rbx; this
0x1400645fd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140064602  xorps   xmm0, xmm0
0x140064605  lea     rdx, [r12+48h]
0x14006460a  lea     rcx, [rbp+170h+FileHandle]
0x14006460e  movups  xmmword ptr [rbp+170h+SourceString.Length], xmm0
0x140064615  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14006461a  mov     rax, [r12+30h]
0x14006461f  mov     rbx, [rax+8]
0x140064623  mov     rsi, [rax]
0x140064626  test    rbx, rbx
0x140064629  jz      short loc_14006462F
0x14006462b  lock inc dword ptr [rbx+8]
0x14006462f  mov     rcx, [rbp+170h+FileHandle]; this
0x140064633  test    rcx, rcx
0x140064636  jz      short loc_14006463D
0x140064638  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14006463d  mov     r8b, 1; bool
0x140064640  lea     rdx, [rbp+170h+SourceString]; struct _UNICODE_STRING *
0x140064647  mov     rcx, rsi; this
0x14006464a  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x14006464f  mov     word ptr [rbp+170h+var_1E8], ax
0x140064653  test    rbx, rbx
0x140064656  jz      short loc_140064660
0x140064658  mov     rcx, rbx; this
0x14006465b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140064660  xorps   xmm0, xmm0
0x140064663  mov     rbx, rdi
0x140064666  movups  xmmword ptr [rbp+170h+var_1C0.Length], xmm0
0x14006466a  cmp     rbx, [rbp+170h+P+8]
0x140064671  jz      loc_1400650C7
0x140064677  mov     rdx, [rbx]
0x14006467a  lea     r8, [rbp+170h+var_1C0]; UnicodeString
0x14006467e  xorps   xmm0, xmm0
0x140064681  mov     qword ptr [rsp+270h+DesiredAccess], 0; struct _UNICODE_STRING *
0x14006468a  movups  xmmword ptr [rbp+170h+FileObject], xmm0
0x14006468e  mov     r9, r14; struct _UNICODE_STRING *
0x140064691  movzx   ecx, word ptr [rdx+4]
0x140064695  sub     cx, [rdx+2]
0x140064699  mov     word ptr [rbp+170h+FileObject+2], cx
0x14006469d  mov     word ptr [rbp+170h+FileObject], cx
0x1400646a1  lea     rcx, [rdx+6]
0x1400646a5  movzx   eax, word ptr [rdx+2]
0x1400646a9  lea     rdx, [rbp+170h+FileObject]; Source
0x1400646ad  add     rcx, rax
0x1400646b0  mov     [rbp+170h+FileObject+8], rcx
0x1400646b4  lea     rcx, [rbp+170h+SourceString]; SourceString
0x1400646bb  call    ?CombinePath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEBG@Z; UnionFs::Utils::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort const *)
0x1400646c0  xor     r11d, r11d
0x1400646c3  mov     esi, eax
0x1400646c5  test    eax, eax
0x1400646c7  js      loc_140065038
0x1400646cd  movzx   r8d, word ptr [rbp+170h+var_1E8]; unsigned __int16
0x1400646d2  lea     rdx, [rbp+170h+var_1C0]; struct _UNICODE_STRING *
0x1400646d6  lea     rcx, [rbp+170h+UnicodeString]; this
0x1400646da  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x1400646df  lea     edx, [r11+2]
0x1400646e3  mov     [rbp+170h+var_100], r11
0x1400646e7  xorps   xmm2, xmm2
0x1400646ea  xorps   xmm3, xmm3
0x1400646ed  xorps   xmm0, xmm0
0x1400646f0  movdqa  xmmword ptr [rbp+170h+var_120], xmm2
0x1400646f5  movdqa  [rbp+170h+var_110], xmm3
0x1400646fa  mov     [rbp+170h+var_F8], r11
0x1400646fe  movdqa  [rbp+170h+var_F0], xmm0
0x140064706  cmp     [r12+1Ch], edx
0x14006470b  jnz     short loc_140064718
0x14006470d  mov     rax, [r12+20h]
0x140064712  mov     rcx, [rax+10h]
0x140064716  jmp     short loc_140064723
0x140064718  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006471f  mov     rcx, [rax+50h]
0x140064723  mov     [rsp+270h+AllocationSize], r11
0x140064728  lea     rax, [rbp+170h+var_120]
0x14006472c  mov     [rsp+270h+IoStatusBlock], r14
0x140064731  lea     r8, [rbp+170h+UnicodeString]
0x140064735  mov     r9d, edx
0x140064738  mov     [rsp+270h+ObjectAttributes], rax; char *
0x14006473d  mov     rdx, r15
0x140064740  mov     [rsp+270h+DesiredAccess], r11d
0x140064745  call    ?LookupEntryPriv@UfsPathCache@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupEntryFlags@2@W4PrivateLookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntryPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupEntryFlags,UnionFs::PrivateLookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x14006474a  mov     esi, eax
0x14006474c  test    eax, eax
0x14006474e  js      loc_14006500C
0x140064754  mov     rax, qword ptr [rbp+170h+var_110]
0x140064758  xor     r15b, r15b
0x14006475b  test    rax, rax
0x14006475e  jz      short loc_1400647A5
0x140064760  movzx   eax, word ptr [rax+0A0h]
0x140064767  nop
0x140064768  mov     r12, qword ptr [rbp+170h+var_1B0+8]
0x14006476c  cmp     ax, 4
0x140064770  setnz   r15b
0x140064774  cmp     r12, r13
0x140064777  jz      loc_140064943
0x14006477d  mov     rax, qword ptr [rbp+170h+var_110]
0x140064781  xorps   xmm0, xmm0
0x140064784  mov     rcx, qword ptr [rbp+170h+var_110+8]
0x140064788  mov     [r12], rax
0x14006478c  mov     [r12+8], rcx
0x140064791  add     r12, 10h
0x140064795  mov     qword ptr [rbp+170h+var_1B0+8], r12
0x140064799  mov     r12, [rbp+170h+arg_0]
0x1400647a0  movdqa  [rbp+170h+var_110], xmm0
0x1400647a5  xor     r13d, r13d
0x1400647a8  mov     rdx, [rbp+170h+Instance]; Instance
0x1400647ac  lea     rax, [rbp+170h+var_1C0]
0x1400647b0  mov     [rbp+170h+var_B0.ObjectName], rax
0x1400647b7  lea     r9, [rbp+170h+FileObject+8]; FileObject
0x1400647bb  mov     eax, 28h ; '('
0x1400647c0  mov     qword ptr [rbp+170h+var_B0.Length], 30h ; '0'
0x1400647cb  xorps   xmm1, xmm1
0x1400647ce  mov     qword ptr [rbp+170h+var_B0.Attributes], 200h
0x1400647d9  movups  xmmword ptr [rbp+170h+var_80.Size], xmm1
0x1400647e0  mov     [rbp+170h+var_80.Size], ax
0x1400647e7  lea     r8, [rbp+170h+FileHandle]; FileHandle
0x1400647eb  lea     ecx, [rax-27h]
0x1400647ee  mov     [rbp+170h+var_B0.RootDirectory], r13
0x1400647f5  mov     [rbp+170h+var_60], rcx
0x1400647fc  lea     rax, [rbp+170h+var_1F0]
0x140064800  mov     [rbp+170h+FileObject], rax
0x140064804  xorps   xmm0, xmm0
0x140064807  mov     [rbp+170h+var_140], cl
0x14006480a  lea     rax, [rbp+170h+var_80]
0x140064811  mov     [rsp+270h+DriverContext], rax; DriverContext
0x140064816  lea     rax, [rbp+170h+var_58]
0x14006481d  mov     [rsp+270h+Flags], r13d; Flags
0x140064822  mov     [rsp+270h+EaLength], r13d; EaLength
0x140064827  mov     [rsp+270h+EaBuffer], r13; EaBuffer
0x14006482c  mov     [rsp+270h+CreateOptions], 200020h; CreateOptions
0x140064834  mov     [rsp+270h+CreateDisposition], ecx; CreateDisposition
0x140064838  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006483f  mov     [rsp+270h+ShareAccess], 7; ShareAccess
0x140064847  mov     [rsp+270h+FileAttributes], r13d; FileAttributes
0x14006484c  mov     [rsp+270h+AllocationSize], r13; AllocationSize
0x140064851  mov     [rsp+270h+IoStatusBlock], rax; IoStatusBlock
0x140064856  lea     rax, [rbp+170h+var_B0]
0x14006485d  movdqu  xmmword ptr [rbp+170h+var_B0.SecurityDescriptor], xmm0
0x140064865  mov     [rbp+170h+var_1F0], r13
0x140064869  movups  xmmword ptr [rbp+170h+var_58], xmm0
0x140064870  mov     [rbp+170h+FileObject+8], r13
0x140064874  movups  xmmword ptr [rbp+170h+var_80.DeviceObjectHint], xmm1
0x14006487b  mov     [rbp+170h+FileHandle], r13
0x14006487f  mov     rcx, [rcx]; Filter
0x140064882  mov     [rsp+270h+ObjectAttributes], rax; char *
0x140064887  mov     [rsp+270h+DesiredAccess], 10000h; DesiredAccess
0x14006488f  call    cs:__imp_FltCreateFileEx2
0x140064896  nop     dword ptr [rax+rax+00h]
0x14006489b  mov     esi, eax
0x14006489d  cmp     [rbp+170h+var_140], r13b
0x1400648a1  jz      short loc_1400648C2
0x1400648a3  mov     r8, [rbp+170h+FileObject]
0x1400648a7  mov     rdx, [rbp+170h+FileObject+8]
0x1400648ab  mov     rcx, [r8]; Object
0x1400648ae  mov     [r8], rdx
0x1400648b1  test    rcx, rcx
0x1400648b4  jz      short loc_1400648C2
0x1400648b6  call    cs:__imp_ObfDereferenceObject
0x1400648bd  nop     dword ptr [rax+rax+00h]
0x1400648c2  test    esi, esi
0x1400648c4  js      loc_1400649DE
0x1400648ca  mov     rax, [rbp+170h+arg_8]
0x1400648d1  mov     eax, [rax+18h]
0x1400648d4  test    al, 1
0x1400648d6  jz      loc_140064BAA
0x1400648dc  mov     rax, [rbp+170h+var_1F0]
0x1400648e0  lea     rdx, [rbp+170h+Object]
0x1400648e4  mov     [rbp+170h+Object], rax
0x1400648e8  lea     rcx, [rbp+170h+var_1D8]
0x1400648ec  mov     rax, [rbp+170h+FileHandle]
0x1400648f0  mov     [rbp+170h+var_128], rax
0x1400648f4  mov     [rbp+170h+var_1F0], r13
0x1400648f8  mov     [rbp+170h+FileHandle], r13
0x1400648fc  call    ?push_back@?$vector@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@2@@utl@@QEAA_N$$QEAU?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@2@@Z; utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::push_back(utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x140064901  mov     rcx, [rbp+170h+var_128]; FileHandle
0x140064905  mov     sil, al
0x140064908  test    rcx, rcx
0x14006490b  jz      short loc_140064919
0x14006490d  call    cs:__imp_FltClose
0x140064914  nop     dword ptr [rax+rax+00h]
0x140064919  mov     rcx, [rbp+170h+Object]; Object
0x14006491d  mov     [rbp+170h+Object], r13
0x140064921  test    rcx, rcx
0x140064924  jz      short loc_140064932
0x140064926  call    cs:__imp_ObfDereferenceObject
0x14006492d  nop     dword ptr [rax+rax+00h]
0x140064932  test    sil, sil
0x140064935  jz      loc_140064B50
0x14006493b  mov     r13b, 1
0x14006493e  jmp     loc_1400649F2
0x140064943  mov     rcx, qword ptr [rbp+170h+var_1B0]
0x140064947  sub     r13, rcx
0x14006494a  sar     r13, 4
0x14006494e  mov     rax, r13
0x140064951  shr     rax, 2
0x140064955  imul    rdx, rax, 7
0x140064959  mov     rax, 7FFFFFFFFFFFFFFh
0x140064963  add     rdx, 8
0x140064967  cmp     rdx, rax
  ... truncated ...
```
