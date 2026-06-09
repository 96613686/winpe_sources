# UnionFs::UfsUnionCtx::SuppressFiles(UFS_MSG_SUPPRESS_FILES const &,ulong,UnionFs::StackEventTracer &)

- ea: `0x140065618`
- end: `0x1400666b4`
- name: `?SuppressFiles@UfsUnionCtx@UnionFs@@QEAAJAEBUUFS_MSG_SUPPRESS_FILES@@KAEAVStackEventTracer@2@@Z`
- size: `4252`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_SUPPRESS_FILES *, unsigned int, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000eae0`

## callees

- `0x140005c80`
- `0x14000f7fc`
- `0x140010b88`
- `0x140011198`
- `0x14001f428`
- `0x14002105c`
- `0x140036128`
- `0x14003ce70`
- `0x1400438e4`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14005cc5c`
- `0x14005ccd0`
- `0x14005d36c`
- `0x14005d4b8`
- `0x14005d500`
- `0x14005d54c`
- `0x140061024`
- `0x140065618`
- `0x1400666bc`
- `0x1400671f8`
- `0x140067598`
- `0x14006a3cc`
- `0x14006f20c`
- `0x14007090c`
- `0x140079a24`
- `0x140079c48`
- `0x140079da0`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400656cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065d96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065ee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065f71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065fad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065fe2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065ffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006605e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066152`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066219`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066306`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006640a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066446`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006647b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066497`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066547`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066583`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066685`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400656cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065d96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065ee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065f71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065fad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065fe2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065ffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006605e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066152`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066219`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066306`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006640a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066446`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006647b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066497`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066547`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066583`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066685`
- `ntoskrnl!ObfDereferenceObject` at `0x140065b1e`
- `ntoskrnl!ObfDereferenceObject` at `0x140065daf`
- `ntoskrnl!ObfDereferenceObject` at `0x140065e36`
- `ntoskrnl!ObfDereferenceObject` at `0x140065efa`
- `ntoskrnl!ObfDereferenceObject` at `0x14006607b`
- `ntoskrnl!ObfDereferenceObject` at `0x14006616f`
- `ntoskrnl!ObfDereferenceObject` at `0x140066232`
- `ntoskrnl!ObfDereferenceObject` at `0x140066323`
- `ntoskrnl!ObfDereferenceObject` at `0x140065b1e`
- `ntoskrnl!ObfDereferenceObject` at `0x140065daf`
- `ntoskrnl!ObfDereferenceObject` at `0x140065e36`
- `ntoskrnl!ObfDereferenceObject` at `0x140065efa`
- `ntoskrnl!ObfDereferenceObject` at `0x14006607b`
- `ntoskrnl!ObfDereferenceObject` at `0x14006616f`
- `ntoskrnl!ObfDereferenceObject` at `0x140066232`
- `ntoskrnl!ObfDereferenceObject` at `0x140066323`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140065bee`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140065bee`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006594c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006594c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065958`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065958`
- `FLTMGR!FltCreateFileEx2` at `0x140065af4`
- `FLTMGR!FltCreateFileEx2` at `0x140065af4`
- `FLTMGR!FltClose` at `0x140065dc4`
- `FLTMGR!FltClose` at `0x140065e4b`
- `FLTMGR!FltClose` at `0x140065f0f`
- `FLTMGR!FltClose` at `0x140066090`
- `FLTMGR!FltClose` at `0x140066184`
- `FLTMGR!FltClose` at `0x140066247`
- `FLTMGR!FltClose` at `0x140066338`
- `FLTMGR!FltClose` at `0x140065dc4`
- `FLTMGR!FltClose` at `0x140065e4b`
- `FLTMGR!FltClose` at `0x140065f0f`
- `FLTMGR!FltClose` at `0x140066090`
- `FLTMGR!FltClose` at `0x140066184`
- `FLTMGR!FltClose` at `0x140066247`
- `FLTMGR!FltClose` at `0x140066338`

## string_xrefs

- `0x1400664d9`: `PUSH: Cache lookup`
- `0x14006638a`: `ORIGIN: Pushing cache entry`
- `0x140065e02`: `API: Opening scratch file with delete access`
- `0x140065e81`: `ORIGIN: Item path not found in union`
- `0x140066012`: `ORIGIN: Pushing scratch directory`
- `0x140065692`: `PUSH: Getting suppress path list`
- `0x1400664ec`: `PUSH: Combining scratchRootPath, suppressPath`
- `0x1400656fc`: `SuppressMessage.PathCount == suppressPathIds.size()`
- `0x1400661d4`: `ORIGIN: Item to mark temporary hard has no layer state`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::SuppressFiles(
        UnionFs::UfsUnionCtx *this,
        const struct UFS_MSG_SUPPRESS_FILES *a2,
        int a3,
        struct UnionFs::StackEventTracer *a4)
{
  __m128i si128; // xmm6
  int v7; // eax
  UnionFs::UfsUnionCtx *v8; // r12
  int PathRootIDsFromMsg; // ebx
  __int64 *v10; // rcx
  __int64 *v12; // rsi
  unsigned __int64 *v13; // rdx
  __int64 *v14; // rax
  volatile signed __int32 *v15; // rbx
  __int64 v16; // r14
  unsigned __int64 *v17; // rdx
  __int64 v18; // rax
  volatile signed __int32 *v19; // rbx
  UnionFs::UfsLayerCtx *v20; // rdi
  char *v21; // r15
  _BYTE *v22; // r14
  __int64 *v23; // rbx
  __int64 v24; // rdx
  NTSTATUS v25; // edi
  struct _ERESOURCE *v26; // r11
  __int64 v27; // rcx
  int v28; // edx
  struct _FLT_INSTANCE *v29; // r12
  struct _ERESOURCE *v30; // rcx
  __int64 v31; // rdx
  utl::_RefCountBase *v32; // rcx
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rdx
  char *v35; // rdi
  __int64 v36; // r8
  utl::_RefCountBase **v37; // rdx
  void *v38; // rcx
  _WORD *v39; // r12
  _QWORD *v40; // rdi
  utl::_RefCountBase *v41; // r8
  volatile signed __int32 *v42; // rdx
  __int64 v43; // rax
  char *v44; // r15
  _QWORD *v45; // rcx
  _QWORD *v46; // rax
  char v47; // di
  char v48; // di
  utl::_RefCountBase *v49; // rcx
  PVOID v50; // rcx
  struct _UNICODE_STRING *v51; // rdx
  PVOID v52; // rcx
  struct _UNICODE_STRING *v53; // rdx
  int v54; // edx
  const char *v55; // rax
  unsigned int v56; // r13d
  __int64 v57; // r8
  utl::_RefCountBase *v58; // rcx
  PVOID v59; // rcx
  struct _UNICODE_STRING *v60; // rdx
  struct _UNICODE_STRING *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rcx
  PVOID v64; // rbx
  signed __int64 v65; // r8
  const char *v66; // rax
  __int64 v67; // r8
  utl::_RefCountBase *v68; // rcx
  PVOID v69; // rcx
  struct _UNICODE_STRING *v70; // rdx
  struct _UNICODE_STRING *v71; // rdx
  utl::_RefCountBase *v72; // rcx
  PVOID v73; // rcx
  struct _UNICODE_STRING *v74; // rdx
  bool v75; // zf
  utl::_RefCountBase *v76; // rcx
  PVOID v77; // rcx
  struct _UNICODE_STRING *v78; // rdx
  struct _UNICODE_STRING *v79; // rdx
  utl::_RefCountBase *v80; // rcx
  PVOID v81; // rcx
  struct _UNICODE_STRING *v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // rcx
  PVOID v85; // rbx
  signed __int64 v86; // r8
  const char *v87; // rax
  __int64 v88; // r8
  struct _UNICODE_STRING *v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // rcx
  PVOID v92; // rbx
  signed __int64 v93; // r8
  struct _UNICODE_STRING *v94; // rdx
  const char *ObjectAttributes; // [rsp+30h] [rbp-D8h]
  const char *ObjectAttributesa; // [rsp+30h] [rbp-D8h]
  const char *ObjectAttributesb; // [rsp+30h] [rbp-D8h]
  const char *ObjectAttributesc; // [rsp+30h] [rbp-D8h]
  PVOID Object; // [rsp+88h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-78h] BYREF
  PVOID v101[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v102; // [rsp+A8h] [rbp-60h]
  struct _UNICODE_STRING v103; // [rsp+B0h] [rbp-58h] BYREF
  int v104[4]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v105; // [rsp+D0h] [rbp-38h]
  PVOID v106[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v107; // [rsp+E8h] [rbp-20h]
  int *v108; // [rsp+F0h] [rbp-18h] BYREF
  char v109; // [rsp+F8h] [rbp-10h]
  unsigned __int16 NormalizedLayerRootPath; // [rsp+100h] [rbp-8h]
  _QWORD *v111; // [rsp+108h] [rbp+0h] BYREF
  PVOID v112[2]; // [rsp+110h] [rbp+8h] BYREF
  __int64 v113; // [rsp+120h] [rbp+18h]
  struct _UNICODE_STRING UnicodeString; // [rsp+128h] [rbp+20h] BYREF
  char v115; // [rsp+138h] [rbp+30h]
  PFLT_INSTANCE Instance; // [rsp+168h] [rbp+60h]
  PFILE_OBJECT FileObject[2]; // [rsp+170h] [rbp+68h] BYREF
  char v118; // [rsp+180h] [rbp+78h]
  __int128 v119; // [rsp+188h] [rbp+80h] BYREF
  utl::_RefCountBase *v120[2]; // [rsp+198h] [rbp+90h] BYREF
  PERESOURCE Resource; // [rsp+1A8h] [rbp+A0h]
  struct _ERESOURCE *v122; // [rsp+1B0h] [rbp+A8h]
  __int128 v123; // [rsp+1B8h] [rbp+B0h]
  PVOID P[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v125; // [rsp+1D8h] [rbp+D0h]
  PVOID v126; // [rsp+1E0h] [rbp+D8h] BYREF
  UNICODE_STRING SourceString; // [rsp+1E8h] [rbp+E0h] BYREF
  _QWORD v128[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  _QWORD v129[2]; // [rsp+208h] [rbp+100h] BYREF
  struct _OBJECT_ATTRIBUTES v130; // [rsp+218h] [rbp+110h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+248h] [rbp+140h] BYREF
  __int64 v132; // [rsp+268h] [rbp+160h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+270h] [rbp+168h] BYREF
  FsFltWil::Details *v135; // [rsp+2E0h] [rbp+1D8h] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v7 = *((_DWORD *)a2 + 1);
  v8 = this;
  v125 = -1;
  *(__m128i *)P = si128;
  PathRootIDsFromMsg = UnionFs::Utils::GetPathRootIDsFromMsg((int)a2, 28, a3, (int)a2 + 28, v7, (__int64)P, a4);
  if ( PathRootIDsFromMsg < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)PathRootIDsFromMsg,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x5CF0020086CLL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
      "PUSH: Getting suppress path list",
      ObjectAttributes);
    v10 = (__int64 *)P[0];
    if ( P[0] != (PVOID)-1LL && P[0] )
LABEL_4:
      ExFreePoolWithTag(v10, 0);
    return (unsigned int)PathRootIDsFromMsg;
  }
  v12 = (__int64 *)P[0];
  if ( *((_DWORD *)a2 + 1) != ((char *)P[1] - (char *)P[0]) >> 3 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("SuppressMessage.PathCount == suppressPathIds.size()");
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  }
  v102 = -1;
  v107 = -1;
  *(__m128i *)v101 = si128;
  v105 = -1;
  *(__m128i *)v106 = si128;
  v113 = -1;
  *(__m128i *)v104 = si128;
  *(__m128i *)v112 = si128;
  FsFltWil::AcquirePushLockShared(&v135, (char *)v8 + 72);
  v14 = (__int64 *)*((_QWORD *)v8 + 6);
  v15 = (volatile signed __int32 *)v14[1];
  v16 = *v14;
  if ( v15 )
    _InterlockedIncrement(v15 + 2);
  if ( v135 )
    FsFltWil::Details::ReleasePushLockShared(v135, v13);
  Instance = **(PFLT_INSTANCE **)(v16 + 8);
  if ( v15 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v15);
  SourceString = 0;
  FsFltWil::AcquirePushLockShared(&v135, (char *)v8 + 72);
  v18 = *((_QWORD *)v8 + 6);
  v19 = *(volatile signed __int32 **)(v18 + 8);
  v20 = *(UnionFs::UfsLayerCtx **)v18;
  if ( v19 )
    _InterlockedIncrement(v19 + 2);
  if ( v135 )
    FsFltWil::Details::ReleasePushLockShared(v135, v17);
  NormalizedLayerRootPath = UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(v20, &SourceString, 1);
  if ( v19 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v19);
  v21 = (char *)v112[1];
  v109 = 1;
  v22 = v112[0];
  v23 = v12;
  v103 = 0;
  v108 = v104;
  while ( 1 )
  {
    if ( v23 == P[1] )
    {
      v109 = 0;
      PathRootIDsFromMsg = UnionFs::UfsUnionCtx::SuppressFilesImpl(
                             (int)v8,
                             (int)v101,
                             (int)v106,
                             (int)v104,
                             (__int64)v112,
                             (int)ObjectAttributes,
                             a4);
      if ( PathRootIDsFromMsg >= 0 )
      {
        wil::details::lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___::_lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___(&v108);
        FsFltWil::Details::FreeUnicodeString(&v103, v94);
        utl::vector<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>,utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>::~vector<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>,utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>(v112);
        utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v104);
        utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::~vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(v106);
        utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::~vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(v101);
        if ( v12 != (__int64 *)-1LL && v12 )
          ExFreePoolWithTag(v12, 0);
        return 0;
      }
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)PathRootIDsFromMsg,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x5C10020094BLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
        "PUSH: SuppressFilesImpl",
        ObjectAttributesc);
      goto LABEL_153;
    }
    v24 = *v23;
    *(_OWORD *)FileObject = 0;
    WORD1(FileObject[0]) = *(_WORD *)(v24 + 4) - *(_WORD *)(v24 + 2);
    LOWORD(FileObject[0]) = WORD1(FileObject[0]);
    FileObject[1] = (PFILE_OBJECT)(*(unsigned __int16 *)(v24 + 2) + v24 + 6);
    v25 = UnionFs::Utils::CombinePath(
            &SourceString,
            (PCUNICODE_STRING)FileObject,
            &v103,
            (struct _UNICODE_STRING *)a4,
            0);
    if ( v25 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v25,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x5CD00200895LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
        "PUSH: Combining scratchRootPath, suppressPath",
        ObjectAttributes);
      goto LABEL_186;
    }
    UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)&UnicodeString, &v103, NormalizedLayerRootPath);
    v75 = *((_DWORD *)v8 + 7) == 2;
    v123 = 0;
    v119 = 0;
    *(_OWORD *)v120 = 0;
    Resource = v26;
    v122 = v26;
    v27 = v75 ? *(_QWORD *)(*((_QWORD *)v8 + 4) + 16LL) : *((_QWORD *)UnionFs::g_FilterState + 10);
    ObjectAttributesa = (const char *)&v119;
    v25 = UnionFs::UfsPathCache::LookupEntryPriv(v27, Instance, &UnicodeString, 10, (_DWORD)v26);
    if ( v25 < 0 )
      break;
    v28 = (int)v8;
    v29 = Instance;
    v25 = UnionFs::Utils::MarkFileAsSoftTombstone(
            (_DWORD)Instance,
            v28,
            (unsigned int)&UnicodeString,
            13,
            (__int64)v120,
            (_DWORD)a4);
    if ( v25 < 0 )
    {
      v87 = "PUSH: Marking file as soft tombstone";
      v88 = 0x5CA002008AELL;
      goto LABEL_183;
    }
    v30 = Resource;
    Resource = 0;
    if ( v30 )
    {
      ExReleaseResourceLite(v30);
      KeLeaveCriticalRegion();
    }
    v31 = *(_QWORD *)&v104[2];
    if ( *(_QWORD *)&v104[2] == v105 )
    {
      v33 = (v105 - *(_QWORD *)v104) >> 4;
      v34 = 7 * (v33 >> 2) + 8;
      if ( v34 > 0x7FFFFFFFFFFFFFFLL )
        v34 = 0x7FFFFFFFFFFFFFFLL;
      if ( v33 >= v34
        || (v35 = (char *)v120 - *(_QWORD *)v104,
            !(unsigned __int8)utl::vector<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsPathCachePayload>>>::_SetCapacity(v104)) )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x58C002008B7LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
          "ORIGIN: Pushing cache entry",
          ObjectAttributesa);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v119);
        v75 = v115 == 0;
        goto LABEL_167;
      }
      v36 = *(_QWORD *)&v104[2];
      v37 = v120;
      if ( (unsigned __int64)v35 < *(_QWORD *)&v104[2] - *(_QWORD *)v104 )
        v37 = (utl::_RefCountBase **)&v35[*(_QWORD *)v104];
      v32 = v37[1];
      **(_QWORD **)&v104[2] = *v37;
      *(_QWORD *)(v36 + 8) = v32;
    }
    else
    {
      v32 = v120[1];
      **(_QWORD **)&v104[2] = v120[0];
      *(_QWORD *)(v31 + 8) = v32;
    }
    if ( v32 )
      _InterlockedIncrement((volatile signed __int32 *)v32 + 2);
    *(_QWORD *)&v104[2] += 16LL;
    v130.ObjectName = &v103;
    *(_QWORD *)&v130.Length = 48;
    *(_QWORD *)&v130.Attributes = 512;
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    v130.RootDirectory = 0;
    v132 = 1;
    FileObject[0] = (PFILE_OBJECT)&Object;
    v118 = 1;
    *(_OWORD *)&v130.SecurityDescriptor = 0;
    Object = 0;
    IoStatusBlock = 0;
    FileObject[1] = 0;
    FileHandle = 0;
    v25 = FltCreateFileEx2(
            *(PFLT_FILTER *)UnionFs::g_FilterState,
            v29,
            &FileHandle,
            &FileObject[1],
            0x10000u,
            &v130,
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
    if ( v118 )
    {
      v38 = *(void **)FileObject[0];
      *(_QWORD *)FileObject[0] = FileObject[1];
      if ( v38 )
        ObfDereferenceObject(v38);
    }
    if ( v25 < 0 )
    {
      LOBYTE(v135) = 0;
      if ( v25 != -1073741766 && v25 != -1073741772 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v25,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x5C7002008E1LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
          "API: Opening scratch file with delete access",
          ObjectAttributesb);
        v52 = Object;
        Object = 0;
        if ( v52 )
          ObfDereferenceObject(v52);
        if ( FileHandle )
          FltClose(FileHandle);
        goto LABEL_90;
      }
    }
    else
    {
      LOBYTE(v135) = 1;
    }
    utl::make_unique<UnionFs::FindAndStatResults,,0>(&v126);
    v39 = v126;
    if ( !v126 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x5C6002008EDLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
        "ORIGIN: Allocating findAndStatResults",
        ObjectAttributesb);
LABEL_136:
      v73 = Object;
      Object = 0;
      if ( v73 )
        ObfDereferenceObject(v73);
      if ( FileHandle )
        FltClose(FileHandle);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v119);
      v75 = v115 == 0;
LABEL_167:
      if ( v75 )
        UnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v74);
      wil::details::lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___::_lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___(&v108);
      FsFltWil::Details::FreeUnicodeString(&v103, v82);
      if ( v22 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>(
          v83,
          v22,
          (v21 - v22) >> 3);
        if ( v22 )
          ExFreePoolWithTag(v22, 0);
      }
      utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v104);
      v85 = v106[0];
      if ( v106[0] != (PVOID)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
          v84,
          v106[0],
          ((char *)v106[1] - (char *)v106[0]) >> 4);
        if ( v85 )
          ExFreePoolWithTag(v85, 0);
      }
      if ( v101[0] != (PVOID)-1LL )
      {
        v86 = (char *)v101[1] - (char *)v101[0];
        v101[1] = v101[0];
        utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
          v84,
          v101[0],
          v86 >> 4);
        if ( v101[0] )
          ExFreePoolWithTag(v101[0], 0);
      }
LABEL_178:
      if ( v12 != (__int64 *)-1LL && v12 )
        ExFreePoolWithTag(v12, 0);
      return 3221225626LL;
    }
    ObjectAttributes = (const char *)a4;
    v25 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(this, &v103, &SourceString, 0, v126);
    if ( v25 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v25,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x5C5002008F6LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
        "PUSH: Checking for item in layers",
        (const char *)a4);
      if ( v39 )
      {
        v80 = (utl::_RefCountBase *)*((_QWORD *)v39 + 11);
        if ( v80 )
          utl::_RefCountBase::_DecStrong(v80);
        ExFreePoolWithTag(v39, 0);
      }
      v81 = Object;
      Object = 0;
      if ( v81 )
        ObfDereferenceObject(v81);
      if ( FileHandle )
        FltClose(FileHandle);
      goto LABEL_90;
    }
    if ( !(_BYTE)v135 )
    {
      if ( *v39 == 3 )
      {
        v54 = (int)a4;
        v55 = "ORIGIN: Item name not found in union";
        v56 = -1073741772;
        v57 = 0x5C4002008FELL;
        goto LABEL_95;
      }
      if ( *v39 == 2 )
      {
        v54 = (int)a4;
        v55 = "ORIGIN: Item path not found in union";
        v56 = -1073741766;
        v57 = 0x5C300200906LL;
LABEL_95:
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)v56,
          v54,
          (struct UnionFs::StackEventTracer *)v57,
          (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
          v55,
          ObjectAttributes);
        if ( v39 )
        {
          v58 = (utl::_RefCountBase *)*((_QWORD *)v39 + 11);
          if ( v58 )
            utl::_RefCountBase::_DecStrong(v58);
          ExFreePoolWithTag(v39, 0);
        }
        v59 = Object;
        Object = 0;
        if ( v59 )
          ObfDereferenceObject(v59);
        if ( FileHandle )
          FltClose(FileHandle);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v119);
        if ( !v115 )
          UnicodeString = 0;
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v60);
        wil::details::lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___::_lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___(&v108);
        FsFltWil::Details::FreeUnicodeString(&v103, v61);
        if ( v22 != (_BYTE *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>(
            v62,
            v22,
            (v21 - v22) >> 3);
          if ( v22 )
            ExFreePoolWithTag(v22, 0);
        }
        utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v104);
        v64 = v106[0];
        if ( v106[0] != (PVOID)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
            v63,
            v106[0],
            ((char *)v106[1] - (char *)v106[0]) >> 4);
          if ( v64 )
            ExFreePoolWithTag(v64, 0);
        }
        if ( v101[0] != (PVOID)-1LL )
        {
          v65 = (char *)v101[1] - (char *)v101[0];
          v101[1] = v101[0];
          utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
            v63,
            v101[0],
            v65 >> 4);
          if ( v101[0] )
            ExFreePoolWithTag(v101[0], 0);
        }
        if ( v12 != (__int64 *)-1LL && v12 )
          ExFreePoolWithTag(v12, 0);
        return v56;
      }
    }
    if ( *v39 != 1 )
    {
      PathRootIDsFromMsg = -1073741811;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000000DLL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x5C20020093CLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
        "ORIGIN: Item to mark temporary hard has no layer state",
        (const char *)a4);
      if ( v39 )
      {
        v76 = (utl::_RefCountBase *)*((_QWORD *)v39 + 11);
        if ( v76 )
          utl::_RefCountBase::_DecStrong(v76);
        ExFreePoolWithTag(v39, 0);
      }
      v77 = Object;
      Object = 0;
      if ( v77 )
        ObfDereferenceObject(v77);
      if ( FileHandle )
        FltClose(FileHandle);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v119);
      if ( !v115 )
        UnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v78);
LABEL_153:
      wil::details::lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___::_lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___(&v108);
      FsFltWil::Details::FreeUnicodeString(&v103, v79);
      utl::vector<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>,utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>::~vector<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>,utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>(v112);
      utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v104);
      utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::~vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(v106);
      utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::~vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(v101);
      if ( v12 != (__int64 *)-1LL && v12 )
      {
        v10 = v12;
        goto LABEL_4;
      }
      return (unsigned int)PathRootIDsFromMsg;
    }
    if ( (*((_DWORD *)v39 + 16) & 0x10) != 0 )
    {
      v40 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1088));
      if ( !v40 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x5C800200918LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
          "ORIGIN: Allocating CollapseContext",
          (const char *)a4);
        if ( v39 )
        {
          v72 = (utl::_RefCountBase *)*((_QWORD *)v39 + 11);
          if ( v72 )
            utl::_RefCountBase::_DecStrong(v72);
          ExFreePoolWithTag(v39, 0);
        }
        goto LABEL_136;
      }
      v41 = v120[0];
      v42 = (volatile signed __int32 *)v120[1];
      *(_OWORD *)v120 = 0;
      if ( *((_DWORD *)this + 7) == 2 )
        v43 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL);
      else
        v43 = *((_QWORD *)UnionFs::g_FilterState + 10);
      *v40 = Instance;
      v40[1] = v43;
      v40[2] = v41;
      v40[3] = v42;
      if ( v42 )
        _InterlockedIncrement(v42 + 2);
      *((_OWORD *)v40 + 2) = 0;
      if ( v42 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v42);
      v111 = v40;
      if ( v21 == (char *)v113 )
      {
        v44 = (char *)((char *)&v111 - v22);
        if ( !(unsigned __int8)utl::vector<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>,utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>::_Grow(v112) )
        {
          v66 = "ORIGIN: Pushing collapse context";
          v67 = 0x58D0020091ELL;
LABEL_119:
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC000009ALL,
            (int)a4,
            (struct UnionFs::StackEventTracer *)v67,
            (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
            v66,
            (const char *)a4);
          utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>::~unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>(&v111);
LABEL_120:
          if ( v39 )
          {
            v68 = (utl::_RefCountBase *)*((_QWORD *)v39 + 11);
            if ( v68 )
              utl::_RefCountBase::_DecStrong(v68);
            ExFreePoolWithTag(v39, 0);
          }
          v69 = Object;
          Object = 0;
          if ( v69 )
            ObfDereferenceObject(v69);
          if ( FileHandle )
            FltClose(FileHandle);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v119);
          if ( !v115 )
            UnicodeString = 0;
          FsFltWil::Details::FreeUnicodeString(&UnicodeString, v70);
          wil::details::lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___::_lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___(&v108);
          FsFltWil::Details::FreeUnicodeString(&v103, v71);
          utl::vector<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>,utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>::~vector<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>,utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>(v112);
          utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v104);
          utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::~vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(v106);
          utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::~vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(v101);
          goto LABEL_178;
        }
        v45 = v112[1];
        v22 = v112[0];
        if ( v44 >= (char *)((char *)v112[1] - (char *)v112[0]) )
        {
          v46 = &v111;
        }
        else
        {
          v46 = (char *)v112[0] + (unsigned __int64)v44;
          v40 = *(_QWORD **)((char *)v112[0] + (unsigned __int64)v44);
        }
        *v46 = 0;
        v21 = (char *)(v45 + 1);
        *v45 = v40;
      }
      else
      {
        *(_QWORD *)v21 = v40;
        v21 += 8;
        v111 = 0;
      }
      v112[1] = v21;
      if ( !(_BYTE)v135
        || (v128[0] = Object,
            v128[1] = FileHandle,
            Object = 0,
            FileHandle = 0,
            v47 = utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::push_back(
                    v106,
                    v128),
            utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v128),
            v47) )
      {
        utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>::~unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>(&v111);
        goto LABEL_75;
      }
      v66 = "ORIGIN: Pushing scratch directory";
      v67 = 0x58E00200928LL;
      goto LABEL_119;
    }
    if ( (_BYTE)v135 )
    {
      v129[0] = Object;
      v129[1] = FileHandle;
      Object = 0;
      FileHandle = 0;
      v48 = utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>::push_back(
              v101,
              v129);
      utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v129);
      if ( !v48 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x58F00200932LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
          "ORIGIN: Pushing scratch file",
          (const char *)a4);
        goto LABEL_120;
      }
    }
LABEL_75:
    if ( v39 )
    {
      v49 = (utl::_RefCountBase *)*((_QWORD *)v39 + 11);
      if ( v49 )
        utl::_RefCountBase::_DecStrong(v49);
      ExFreePoolWithTag(v39, 0);
    }
    v50 = Object;
    Object = 0;
    if ( v50 )
      ObfDereferenceObject(v50);
    if ( FileHandle )
      FltClose(FileHandle);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v119);
    if ( !v115 )
      UnicodeString = 0;
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v51);
    v8 = this;
    ++v23;
  }
  v87 = "PUSH: Cache lookup";
  v88 = 0x5CB002008A4LL;
LABEL_183:
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v25,
    (int)a4,
    (struct UnionFs::StackEventTracer *)v88,
    (unsigned __int64)"UnionFs::UfsUnionCtx::SuppressFiles",
    v87,
    ObjectAttributesa);
LABEL_90:
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v119);
  if ( !v115 )
    UnicodeString = 0;
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v53);
LABEL_186:
  wil::details::lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___::_lambda_call__lambda_3ca26d8e119e955dd23fd3669250f40d___(&v108);
  FsFltWil::Details::FreeUnicodeString(&v103, v89);
  if ( v22 != (_BYTE *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>>(
      v90,
      v22,
      (v21 - v22) >> 3);
    if ( v22 )
      ExFreePoolWithTag(v22, 0);
  }
  utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(v104);
  v92 = v106[0];
  if ( v106[0] != (PVOID)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
      v91,
      v106[0],
      ((char *)v106[1] - (char *)v106[0]) >> 4);
    if ( v92 )
      ExFreePoolWithTag(v92, 0);
  }
  if ( v101[0] != (PVOID)-1LL )
  {
    v93 = (char *)v101[1] - (char *)v101[0];
    v101[1] = v101[0];
    utl::_RangeDestroyApc<utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>>(
      v91,
      v101[0],
      v93 >> 4);
    if ( v101[0] )
      ExFreePoolWithTag(v101[0], 0);
  }
  if ( v12 != (__int64 *)-1LL && v12 )
    ExFreePoolWithTag(v12, 0);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x140065618  mov     rax, rsp
0x14006561b  mov     [rax+18h], rbx
0x14006561f  mov     [rax+8], rcx
0x140065623  push    rbp
0x140065624  push    rsi
0x140065625  push    rdi
0x140065626  push    r12
0x140065628  push    r13
0x14006562a  push    r14
0x14006562c  push    r15
0x14006562e  lea     rbp, [rax-1C8h]
0x140065635  sub     rsp, 290h
0x14006563c  movaps  xmmword ptr [rax-48h], xmm6
0x140065640  mov     r13, r9
0x140065643  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14006564b  lea     rax, [rbp+1C0h+P]
0x140065652  mov     rdi, rdx
0x140065655  mov     [rsp+2C0h+IoStatusBlock], r13; struct UnionFs::StackEventTracer *
0x14006565a  mov     [rsp+2C0h+ObjectAttributes], rax; char *
0x14006565f  lea     r9, [rdx+1Ch]; int
0x140065663  mov     eax, [rdx+4]
0x140065666  or      r14, 0FFFFFFFFFFFFFFFFh
0x14006566a  mov     r12, rcx
0x14006566d  mov     [rbp+1C0h+var_F0], r14
0x140065674  mov     rcx, rdi; int
0x140065677  mov     [rsp+2C0h+DesiredAccess], eax; int
0x14006567b  movdqu  xmmword ptr [rbp+1C0h+P], xmm6
0x140065683  lea     edx, [r14+1Dh]; int
0x140065687  call    ?GetPathRootIDsFromMsg@Utils@UnionFs@@YAJPEBXKKQEBUUFS_PATH_ENTRY@@KAEAV?$vector@PEAVCONTAINER_ROOT_ID@UnionFs@@V?$allocator@PEAVCONTAINER_ROOT_ID@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetPathRootIDsFromMsg(void const *,ulong,ulong,UFS_PATH_ENTRY const * const,ulong,utl::vector<UnionFs::CONTAINER_ROOT_ID *,utl::allocator<UnionFs::CONTAINER_ROOT_ID *>> &,UnionFs::StackEventTracer &)
0x14006568c  mov     ebx, eax
0x14006568e  test    eax, eax
0x140065690  jns     short loc_1400656DF
0x140065692  lea     rax, aPushGettingSup; "PUSH: Getting suppress path list"
0x140065699  mov     r8, 5CF0020086Ch; struct UnionFs::StackEventTracer *
0x1400656a3  lea     r9, aUnionfsUfsunio_17; "UnionFs::UfsUnionCtx::SuppressFiles"
0x1400656aa  mov     qword ptr [rsp+2C0h+DesiredAccess], rax; char *
0x1400656af  mov     rdx, r13; int
0x1400656b2  mov     ecx, ebx; this
0x1400656b4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400656b9  mov     rcx, [rbp+1C0h+P]; P
0x1400656c0  cmp     rcx, r14
0x1400656c3  jz      short loc_1400656D8
0x1400656c5  test    rcx, rcx
0x1400656c8  jz      short loc_1400656D8
0x1400656ca  xor     edx, edx; Tag
0x1400656cc  call    cs:__imp_ExFreePoolWithTag
0x1400656d3  nop     dword ptr [rax+rax+00h]
0x1400656d8  mov     eax, ebx
0x1400656da  jmp     loc_140066693
0x1400656df  mov     rcx, [rbp+1C0h+P+8]
0x1400656e6  mov     rsi, [rbp+1C0h+P]
0x1400656ed  mov     eax, [rdi+4]
0x1400656f0  sub     rcx, rsi
0x1400656f3  sar     rcx, 3
0x1400656f7  cmp     rax, rcx
0x1400656fa  jz      short loc_140065710
0x1400656fc  lea     rcx, aSuppressmessag; "SuppressMessage.PathCount == suppressPa"...
0x140065703  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140065708  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140065710  lea     rdx, [r12+48h]
0x140065715  mov     [rbp+1C0h+var_220], r14
0x140065719  lea     rcx, [rbp+1C0h+arg_8]
0x140065720  mov     [rbp+1C0h+var_1E0], r14
0x140065724  movdqu  xmmword ptr [rbp+1C0h+var_230], xmm6
0x140065729  mov     [rbp+1C0h+var_1F8], r14
0x14006572d  movdqu  xmmword ptr [rbp+1C0h+var_1F0], xmm6
0x140065732  mov     [rbp+1C0h+var_1A8], r14
0x140065736  movdqu  xmmword ptr [rbp+1C0h+var_208], xmm6
0x14006573b  movdqu  xmmword ptr [rbp+1C0h+var_1B8], xmm6
0x140065740  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140065745  mov     rax, [r12+30h]
0x14006574a  mov     rbx, [rax+8]
0x14006574e  mov     r14, [rax]
0x140065751  test    rbx, rbx
0x140065754  jz      short loc_14006575A
0x140065756  lock inc dword ptr [rbx+8]
0x14006575a  mov     rcx, [rbp+1C0h+arg_8]; this
0x140065761  test    rcx, rcx
0x140065764  jz      short loc_14006576B
0x140065766  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14006576b  mov     rax, [r14+8]
0x14006576f  mov     rax, [rax]
0x140065772  mov     [rbp+1C0h+Instance], rax
0x140065776  test    rbx, rbx
0x140065779  jz      short loc_140065783
0x14006577b  mov     rcx, rbx; this
0x14006577e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140065783  xorps   xmm0, xmm0
0x140065786  lea     rdx, [r12+48h]
0x14006578b  lea     rcx, [rbp+1C0h+arg_8]
0x140065792  movups  xmmword ptr [rbp+1C0h+SourceString.Length], xmm0
0x140065799  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14006579e  mov     rax, [r12+30h]
0x1400657a3  mov     rbx, [rax+8]
0x1400657a7  mov     rdi, [rax]
0x1400657aa  test    rbx, rbx
0x1400657ad  jz      short loc_1400657B3
0x1400657af  lock inc dword ptr [rbx+8]
0x1400657b3  mov     rcx, [rbp+1C0h+arg_8]; this
0x1400657ba  test    rcx, rcx
0x1400657bd  jz      short loc_1400657C4
0x1400657bf  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400657c4  mov     r14d, 1
0x1400657ca  lea     rdx, [rbp+1C0h+SourceString]; struct _UNICODE_STRING *
0x1400657d1  mov     r8b, r14b; bool
0x1400657d4  mov     rcx, rdi; this
0x1400657d7  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x1400657dc  xor     edi, edi
0x1400657de  mov     [rbp+1C0h+var_1C8], ax
0x1400657e2  test    rbx, rbx
0x1400657e5  jz      short loc_1400657EF
0x1400657e7  mov     rcx, rbx; this
0x1400657ea  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400657ef  mov     r15, [rbp+1C0h+var_1B8+8]
0x1400657f3  lea     rax, [rbp+1C0h+var_208]
0x1400657f7  xorps   xmm0, xmm0
0x1400657fa  mov     [rbp+1C0h+var_1D0], r14b
0x1400657fe  mov     r14, [rbp+1C0h+var_1B8]
0x140065802  mov     rbx, rsi
0x140065805  movups  xmmword ptr [rbp+1C0h+var_218.Length], xmm0
0x140065809  mov     [rbp+1C0h+var_1D8], rax
0x14006580d  cmp     rbx, [rbp+1C0h+P+8]
0x140065814  jz      loc_1400665E7
0x14006581a  mov     rdx, [rbx]
0x14006581d  lea     r8, [rbp+1C0h+var_218]; UnicodeString
0x140065821  xorps   xmm0, xmm0
0x140065824  mov     qword ptr [rsp+2C0h+DesiredAccess], rdi; struct _UNICODE_STRING *
0x140065829  movups  xmmword ptr [rbp+1C0h+FileObject], xmm0
0x14006582d  mov     r9, r13; struct _UNICODE_STRING *
0x140065830  movzx   ecx, word ptr [rdx+4]
0x140065834  sub     cx, [rdx+2]
0x140065838  mov     word ptr [rbp+1C0h+FileObject+2], cx
0x14006583c  mov     word ptr [rbp+1C0h+FileObject], cx
0x140065840  lea     rcx, [rdx+6]
0x140065844  movzx   eax, word ptr [rdx+2]
0x140065848  lea     rdx, [rbp+1C0h+FileObject]; Source
0x14006584c  add     rcx, rax
0x14006584f  mov     [rbp+1C0h+FileObject+8], rcx
0x140065853  lea     rcx, [rbp+1C0h+SourceString]; SourceString
0x14006585a  call    ?CombinePath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEBG@Z; UnionFs::Utils::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort const *)
0x14006585f  xor     r11d, r11d
0x140065862  mov     edi, eax
0x140065864  test    eax, eax
0x140065866  js      loc_1400664EC
0x14006586c  movzx   r8d, [rbp+1C0h+var_1C8]; unsigned __int16
0x140065871  lea     rdx, [rbp+1C0h+var_218]; struct _UNICODE_STRING *
0x140065875  lea     rcx, [rbp+1C0h+UnicodeString]; this
0x140065879  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x14006587e  cmp     dword ptr [r12+1Ch], 2
0x140065884  xorps   xmm0, xmm0
0x140065887  xorps   xmm2, xmm2
0x14006588a  movdqa  [rbp+1C0h+var_110], xmm0
0x140065892  xorps   xmm3, xmm3
0x140065895  movdqa  [rbp+1C0h+var_140], xmm2
0x14006589d  movdqa  xmmword ptr [rbp+1C0h+var_130], xmm3
0x1400658a5  mov     [rbp+1C0h+Resource], r11
0x1400658ac  mov     [rbp+1C0h+var_118], r11
0x1400658b3  jnz     short loc_1400658C0
0x1400658b5  mov     rax, [r12+20h]
0x1400658ba  mov     rcx, [rax+10h]
0x1400658be  jmp     short loc_1400658CB
0x1400658c0  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400658c7  mov     rcx, [rax+50h]
0x1400658cb  mov     rdx, [rbp+1C0h+Instance]
0x1400658cf  lea     rax, [rbp+1C0h+var_140]
0x1400658d6  mov     [rsp+2C0h+AllocationSize], r11
0x1400658db  lea     r8, [rbp+1C0h+UnicodeString]
0x1400658df  mov     [rsp+2C0h+IoStatusBlock], r13
0x1400658e4  mov     r9d, 0Ah
0x1400658ea  mov     [rsp+2C0h+ObjectAttributes], rax
0x1400658ef  mov     [rsp+2C0h+DesiredAccess], r11d
0x1400658f4  call    ?LookupEntryPriv@UfsPathCache@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupEntryFlags@2@W4PrivateLookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntryPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupEntryFlags,UnionFs::PrivateLookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x1400658f9  mov     edi, eax
0x1400658fb  test    eax, eax
0x1400658fd  js      loc_1400664D9
0x140065903  mov     rdx, r12
0x140065906  mov     [rsp+2C0h+ObjectAttributes], r13; char *
0x14006590b  mov     r12, [rbp+1C0h+Instance]
0x14006590f  lea     rax, [rbp+1C0h+var_130]
0x140065916  mov     rcx, r12
0x140065919  mov     qword ptr [rsp+2C0h+DesiredAccess], rax
0x14006591e  mov     r9d, 0Dh
0x140065924  lea     r8, [rbp+1C0h+UnicodeString]
0x140065928  call    ?MarkFileAsSoftTombstone@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAVUfsUnionCtx@2@AEAVUfsPathName@2@W4SoftTombstoneReason@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::MarkFileAsSoftTombstone(_FLT_INSTANCE const &,UnionFs::UfsUnionCtx &,UnionFs::UfsPathName &,UnionFs::SoftTombstoneReason,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &)
0x14006592d  mov     edi, eax
0x14006592f  test    eax, eax
0x140065931  js      loc_1400664AD
0x140065937  mov     rcx, [rbp+1C0h+Resource]; Resource
0x14006593e  xor     edi, edi
0x140065940  mov     [rbp+1C0h+Resource], rdi
0x140065947  test    rcx, rcx
0x14006594a  jz      short loc_140065964
0x14006594c  call    cs:__imp_ExReleaseResourceLite
0x140065953  nop     dword ptr [rax+rax+00h]
0x140065958  call    cs:__imp_KeLeaveCriticalRegion
0x14006595f  nop     dword ptr [rax+rax+00h]
0x140065964  mov     rdx, qword ptr [rbp+1C0h+var_208+8]
0x140065968  mov     rcx, [rbp+1C0h+var_1F8]
0x14006596c  cmp     rdx, rcx
0x14006596f  jz      short loc_140065988
0x140065971  mov     rax, [rbp+1C0h+var_130]
0x140065978  mov     rcx, [rbp+1C0h+var_130+8]
0x14006597f  mov     [rdx], rax
0x140065982  mov     [rdx+8], rcx
0x140065986  jmp     short loc_140065A03
0x140065988  sub     rcx, qword ptr [rbp+1C0h+var_208]
0x14006598c  sar     rcx, 4
0x140065990  mov     rax, rcx
0x140065993  shr     rax, 2
0x140065997  imul    rdx, rax, 7
0x14006599b  mov     rax, 7FFFFFFFFFFFFFFh
0x1400659a5  add     rdx, 8
0x1400659a9  cmp     rdx, rax
0x1400659ac  cmova   rdx, rax
0x1400659b0  cmp     rcx, rdx
0x1400659b3  jnb     loc_14006638A
0x1400659b9  lea     rdi, [rbp+1C0h+var_130]
0x1400659c0  sub     rdi, qword ptr [rbp+1C0h+var_208]
0x1400659c4  lea     rcx, [rbp+1C0h+var_208]
0x1400659c8  call    ?_SetCapacity@?$vector@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsPathCachePayload>>>::_SetCapacity(unsigned __int64)
0x1400659cd  test    al, al
0x1400659cf  jz      loc_140066388
0x1400659d5  mov     r8, qword ptr [rbp+1C0h+var_208+8]
0x1400659d9  lea     rdx, [rbp+1C0h+var_130]
0x1400659e0  mov     rcx, qword ptr [rbp+1C0h+var_208]
0x1400659e4  mov     rax, r8
0x1400659e7  sub     rax, rcx
0x1400659ea  cmp     rdi, rax
0x1400659ed  jnb     short loc_1400659F3
0x1400659ef  lea     rdx, [rcx+rdi]
0x1400659f3  mov     rcx, [rdx+8]
0x1400659f7  xor     edi, edi
0x1400659f9  mov     rax, [rdx]
0x1400659fc  mov     [r8], rax
0x1400659ff  mov     [r8+8], rcx
0x140065a03  test    rcx, rcx
0x140065a06  jz      short loc_140065A0C
0x140065a08  lock inc dword ptr [rcx+8]
0x140065a0c  add     qword ptr [rbp+1C0h+var_208+8], 10h
0x140065a11  lea     rax, [rbp+1C0h+var_218]
0x140065a15  mov     [rbp+1C0h+var_B0.ObjectName], rax
0x140065a1c  lea     r9, [rbp+1C0h+FileObject+8]; FileObject
0x140065a20  mov     eax, 28h ; '('
0x140065a25  mov     qword ptr [rbp+1C0h+var_B0.Length], 30h ; '0'
0x140065a30  xorps   xmm1, xmm1
0x140065a33  mov     qword ptr [rbp+1C0h+var_B0.Attributes], 200h
0x140065a3e  movups  xmmword ptr [rbp+1C0h+var_80.Size], xmm1
0x140065a45  mov     [rbp+1C0h+var_80.Size], ax
0x140065a4c  lea     r8, [rbp+1C0h+FileHandle]; FileHandle
0x140065a50  lea     ecx, [rax-27h]
0x140065a53  mov     [rbp+1C0h+var_B0.RootDirectory], rdi
0x140065a5a  mov     [rbp+1C0h+var_60], rcx
0x140065a61  lea     rax, [rbp+1C0h+Object]
0x140065a65  mov     [rbp+1C0h+FileObject], rax
0x140065a69  xorps   xmm0, xmm0
0x140065a6c  mov     [rbp+1C0h+var_148], cl
0x140065a6f  lea     rax, [rbp+1C0h+var_80]
0x140065a76  mov     [rsp+2C0h+DriverContext], rax; DriverContext
0x140065a7b  mov     rdx, r12; Instance
0x140065a7e  mov     [rsp+2C0h+Flags], edi; Flags
0x140065a82  lea     rax, [rbp+1C0h+var_58]
0x140065a89  mov     [rsp+2C0h+EaLength], edi; EaLength
0x140065a8d  mov     [rsp+2C0h+EaBuffer], rdi; EaBuffer
0x140065a92  mov     [rsp+2C0h+CreateOptions], 200020h; CreateOptions
0x140065a9a  mov     [rsp+2C0h+CreateDisposition], ecx; CreateDisposition
0x140065a9e  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140065aa5  mov     [rsp+2C0h+ShareAccess], 7; ShareAccess
0x140065aad  mov     [rsp+2C0h+FileAttributes], edi; FileAttributes
0x140065ab1  mov     [rsp+2C0h+AllocationSize], rdi; AllocationSize
0x140065ab6  mov     [rsp+2C0h+IoStatusBlock], rax; IoStatusBlock
0x140065abb  lea     rax, [rbp+1C0h+var_B0]
0x140065ac2  movdqu  xmmword ptr [rbp+1C0h+var_B0.SecurityDescriptor], xmm0
0x140065aca  mov     [rbp+1C0h+Object], rdi
0x140065ace  movups  xmmword ptr [rbp+1C0h+var_58], xmm0
0x140065ad5  mov     [rbp+1C0h+FileObject+8], rdi
0x140065ad9  movups  xmmword ptr [rbp+1C0h+var_80.DeviceObjectHint], xmm1
0x140065ae0  mov     [rbp+1C0h+FileHandle], rdi
0x140065ae4  mov     rcx, [rcx]; Filter
0x140065ae7  mov     [rsp+2C0h+ObjectAttributes], rax; char *
0x140065aec  mov     [rsp+2C0h+DesiredAccess], 10000h; DesiredAccess
0x140065af4  call    cs:__imp_FltCreateFileEx2
0x140065afb  nop     dword ptr [rax+rax+00h]
0x140065b00  xor     r12d, r12d
0x140065b03  mov     edi, eax
0x140065b05  cmp     [rbp+1C0h+var_148], r12b
0x140065b09  jz      short loc_140065B2A
0x140065b0b  mov     r8, [rbp+1C0h+FileObject]
0x140065b0f  mov     rdx, [rbp+1C0h+FileObject+8]
0x140065b13  mov     rcx, [r8]; Object
0x140065b16  mov     [r8], rdx
0x140065b19  test    rcx, rcx
0x140065b1c  jz      short loc_140065B2A
0x140065b1e  call    cs:__imp_ObfDereferenceObject
0x140065b25  nop     dword ptr [rax+rax+00h]
0x140065b2a  test    edi, edi
0x140065b2c  js      short loc_140065B37
0x140065b2e  mov     byte ptr [rbp+1C0h+arg_8], 1
0x140065b35  jmp     short loc_140065B52
0x140065b37  mov     byte ptr [rbp+1C0h+arg_8], r12b
0x140065b3e  cmp     edi, 0C000003Ah
  ... truncated ...
```
