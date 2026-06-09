# UnionFs::UfsUnionCtx::SuppressFiles(UFS_MSG_SUPPRESS_FILES const &,ulong,UnionFs::StackEventTracer &)

- ea: `0x140065798`
- end: `0x140066834`
- name: `?SuppressFiles@UfsUnionCtx@UnionFs@@QEAAJAEBUUFS_MSG_SUPPRESS_FILES@@KAEAVStackEventTracer@2@@Z`
- size: `4252`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_SUPPRESS_FILES *, unsigned int, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000eab0`

## callees

- `0x140005c80`
- `0x14000f81c`
- `0x140010ba8`
- `0x1400111b8`
- `0x14001f4c8`
- `0x1400210fc`
- `0x140036268`
- `0x14003cf90`
- `0x140043a64`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14005cddc`
- `0x14005ce50`
- `0x14005d4ec`
- `0x14005d638`
- `0x14005d680`
- `0x14005d6cc`
- `0x1400611a4`
- `0x140065798`
- `0x14006683c`
- `0x140067378`
- `0x140067718`
- `0x14006a5bc`
- `0x14006f3fc`
- `0x140070afc`
- `0x140079d44`
- `0x140079f68`
- `0x14007a0c0`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006584c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065f16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066061`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400660f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006612d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066162`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006617e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400661de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400662d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066399`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066486`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006658a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066617`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400666c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066703`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066738`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066754`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066805`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006584c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065f16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066061`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400660f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006612d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066162`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006617e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400661de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400662d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066399`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066486`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006658a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066617`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400666c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066703`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066738`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066754`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066805`
- `ntoskrnl!ObfDereferenceObject` at `0x140065c9e`
- `ntoskrnl!ObfDereferenceObject` at `0x140065f2f`
- `ntoskrnl!ObfDereferenceObject` at `0x140065fb6`
- `ntoskrnl!ObfDereferenceObject` at `0x14006607a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400661fb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400662ef`
- `ntoskrnl!ObfDereferenceObject` at `0x1400663b2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400664a3`
- `ntoskrnl!ObfDereferenceObject` at `0x140065c9e`
- `ntoskrnl!ObfDereferenceObject` at `0x140065f2f`
- `ntoskrnl!ObfDereferenceObject` at `0x140065fb6`
- `ntoskrnl!ObfDereferenceObject` at `0x14006607a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400661fb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400662ef`
- `ntoskrnl!ObfDereferenceObject` at `0x1400663b2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400664a3`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140065d6e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140065d6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140065acc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140065acc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065ad8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065ad8`
- `FLTMGR!FltCreateFileEx2` at `0x140065c74`
- `FLTMGR!FltCreateFileEx2` at `0x140065c74`
- `FLTMGR!FltClose` at `0x140065f44`
- `FLTMGR!FltClose` at `0x140065fcb`
- `FLTMGR!FltClose` at `0x14006608f`
- `FLTMGR!FltClose` at `0x140066210`
- `FLTMGR!FltClose` at `0x140066304`
- `FLTMGR!FltClose` at `0x1400663c7`
- `FLTMGR!FltClose` at `0x1400664b8`
- `FLTMGR!FltClose` at `0x140065f44`
- `FLTMGR!FltClose` at `0x140065fcb`
- `FLTMGR!FltClose` at `0x14006608f`
- `FLTMGR!FltClose` at `0x140066210`
- `FLTMGR!FltClose` at `0x140066304`
- `FLTMGR!FltClose` at `0x1400663c7`
- `FLTMGR!FltClose` at `0x1400664b8`

## string_xrefs

- `0x140066659`: `PUSH: Cache lookup`
- `0x14006650a`: `ORIGIN: Pushing cache entry`
- `0x140065f82`: `API: Opening scratch file with delete access`
- `0x140066001`: `ORIGIN: Item path not found in union`
- `0x140066192`: `ORIGIN: Pushing scratch directory`
- `0x140065812`: `PUSH: Getting suppress path list`
- `0x14006587c`: `SuppressMessage.PathCount == suppressPathIds.size()`
- `0x14006666c`: `PUSH: Combining scratchRootPath, suppressPath`
- `0x140066354`: `ORIGIN: Item to mark temporary hard has no layer state`

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
0x140065798  mov     rax, rsp
0x14006579b  mov     [rax+18h], rbx
0x14006579f  mov     [rax+8], rcx
0x1400657a3  push    rbp
0x1400657a4  push    rsi
0x1400657a5  push    rdi
0x1400657a6  push    r12
0x1400657a8  push    r13
0x1400657aa  push    r14
0x1400657ac  push    r15
0x1400657ae  lea     rbp, [rax-1C8h]
0x1400657b5  sub     rsp, 290h
0x1400657bc  movaps  xmmword ptr [rax-48h], xmm6
0x1400657c0  mov     r13, r9
0x1400657c3  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400657cb  lea     rax, [rbp+1C0h+P]
0x1400657d2  mov     rdi, rdx
0x1400657d5  mov     [rsp+2C0h+IoStatusBlock], r13; struct UnionFs::StackEventTracer *
0x1400657da  mov     [rsp+2C0h+ObjectAttributes], rax; char *
0x1400657df  lea     r9, [rdx+1Ch]; int
0x1400657e3  mov     eax, [rdx+4]
0x1400657e6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400657ea  mov     r12, rcx
0x1400657ed  mov     [rbp+1C0h+var_F0], r14
0x1400657f4  mov     rcx, rdi; int
0x1400657f7  mov     [rsp+2C0h+DesiredAccess], eax; int
0x1400657fb  movdqu  xmmword ptr [rbp+1C0h+P], xmm6
0x140065803  lea     edx, [r14+1Dh]; int
0x140065807  call    ?GetPathRootIDsFromMsg@Utils@UnionFs@@YAJPEBXKKQEBUUFS_PATH_ENTRY@@KAEAV?$vector@PEAVCONTAINER_ROOT_ID@UnionFs@@V?$allocator@PEAVCONTAINER_ROOT_ID@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetPathRootIDsFromMsg(void const *,ulong,ulong,UFS_PATH_ENTRY const * const,ulong,utl::vector<UnionFs::CONTAINER_ROOT_ID *,utl::allocator<UnionFs::CONTAINER_ROOT_ID *>> &,UnionFs::StackEventTracer &)
0x14006580c  mov     ebx, eax
0x14006580e  test    eax, eax
0x140065810  jns     short loc_14006585F
0x140065812  lea     rax, aPushGettingSup; "PUSH: Getting suppress path list"
0x140065819  mov     r8, 5CF0020086Ch; struct UnionFs::StackEventTracer *
0x140065823  lea     r9, aUnionfsUfsunio_17; "UnionFs::UfsUnionCtx::SuppressFiles"
0x14006582a  mov     qword ptr [rsp+2C0h+DesiredAccess], rax; char *
0x14006582f  mov     rdx, r13; int
0x140065832  mov     ecx, ebx; this
0x140065834  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140065839  mov     rcx, [rbp+1C0h+P]; P
0x140065840  cmp     rcx, r14
0x140065843  jz      short loc_140065858
0x140065845  test    rcx, rcx
0x140065848  jz      short loc_140065858
0x14006584a  xor     edx, edx; Tag
0x14006584c  call    cs:__imp_ExFreePoolWithTag
0x140065853  nop     dword ptr [rax+rax+00h]
0x140065858  mov     eax, ebx
0x14006585a  jmp     loc_140066813
0x14006585f  mov     rcx, [rbp+1C0h+P+8]
0x140065866  mov     rsi, [rbp+1C0h+P]
0x14006586d  mov     eax, [rdi+4]
0x140065870  sub     rcx, rsi
0x140065873  sar     rcx, 3
0x140065877  cmp     rax, rcx
0x14006587a  jz      short loc_140065890
0x14006587c  lea     rcx, aSuppressmessag; "SuppressMessage.PathCount == suppressPa"...
0x140065883  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140065888  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140065890  lea     rdx, [r12+48h]
0x140065895  mov     [rbp+1C0h+var_220], r14
0x140065899  lea     rcx, [rbp+1C0h+arg_8]
0x1400658a0  mov     [rbp+1C0h+var_1E0], r14
0x1400658a4  movdqu  xmmword ptr [rbp+1C0h+var_230], xmm6
0x1400658a9  mov     [rbp+1C0h+var_1F8], r14
0x1400658ad  movdqu  xmmword ptr [rbp+1C0h+var_1F0], xmm6
0x1400658b2  mov     [rbp+1C0h+var_1A8], r14
0x1400658b6  movdqu  xmmword ptr [rbp+1C0h+var_208], xmm6
0x1400658bb  movdqu  xmmword ptr [rbp+1C0h+var_1B8], xmm6
0x1400658c0  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400658c5  mov     rax, [r12+30h]
0x1400658ca  mov     rbx, [rax+8]
0x1400658ce  mov     r14, [rax]
0x1400658d1  test    rbx, rbx
0x1400658d4  jz      short loc_1400658DA
0x1400658d6  lock inc dword ptr [rbx+8]
0x1400658da  mov     rcx, [rbp+1C0h+arg_8]; this
0x1400658e1  test    rcx, rcx
0x1400658e4  jz      short loc_1400658EB
0x1400658e6  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400658eb  mov     rax, [r14+8]
0x1400658ef  mov     rax, [rax]
0x1400658f2  mov     [rbp+1C0h+Instance], rax
0x1400658f6  test    rbx, rbx
0x1400658f9  jz      short loc_140065903
0x1400658fb  mov     rcx, rbx; this
0x1400658fe  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140065903  xorps   xmm0, xmm0
0x140065906  lea     rdx, [r12+48h]
0x14006590b  lea     rcx, [rbp+1C0h+arg_8]
0x140065912  movups  xmmword ptr [rbp+1C0h+SourceString.Length], xmm0
0x140065919  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14006591e  mov     rax, [r12+30h]
0x140065923  mov     rbx, [rax+8]
0x140065927  mov     rdi, [rax]
0x14006592a  test    rbx, rbx
0x14006592d  jz      short loc_140065933
0x14006592f  lock inc dword ptr [rbx+8]
0x140065933  mov     rcx, [rbp+1C0h+arg_8]; this
0x14006593a  test    rcx, rcx
0x14006593d  jz      short loc_140065944
0x14006593f  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140065944  mov     r14d, 1
0x14006594a  lea     rdx, [rbp+1C0h+SourceString]; struct _UNICODE_STRING *
0x140065951  mov     r8b, r14b; bool
0x140065954  mov     rcx, rdi; this
0x140065957  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x14006595c  xor     edi, edi
0x14006595e  mov     [rbp+1C0h+var_1C8], ax
0x140065962  test    rbx, rbx
0x140065965  jz      short loc_14006596F
0x140065967  mov     rcx, rbx; this
0x14006596a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14006596f  mov     r15, [rbp+1C0h+var_1B8+8]
0x140065973  lea     rax, [rbp+1C0h+var_208]
0x140065977  xorps   xmm0, xmm0
0x14006597a  mov     [rbp+1C0h+var_1D0], r14b
0x14006597e  mov     r14, [rbp+1C0h+var_1B8]
0x140065982  mov     rbx, rsi
0x140065985  movups  xmmword ptr [rbp+1C0h+var_218.Length], xmm0
0x140065989  mov     [rbp+1C0h+var_1D8], rax
0x14006598d  cmp     rbx, [rbp+1C0h+P+8]
0x140065994  jz      loc_140066767
0x14006599a  mov     rdx, [rbx]
0x14006599d  lea     r8, [rbp+1C0h+var_218]; UnicodeString
0x1400659a1  xorps   xmm0, xmm0
0x1400659a4  mov     qword ptr [rsp+2C0h+DesiredAccess], rdi; struct _UNICODE_STRING *
0x1400659a9  movups  xmmword ptr [rbp+1C0h+FileObject], xmm0
0x1400659ad  mov     r9, r13; struct _UNICODE_STRING *
0x1400659b0  movzx   ecx, word ptr [rdx+4]
0x1400659b4  sub     cx, [rdx+2]
0x1400659b8  mov     word ptr [rbp+1C0h+FileObject+2], cx
0x1400659bc  mov     word ptr [rbp+1C0h+FileObject], cx
0x1400659c0  lea     rcx, [rdx+6]
0x1400659c4  movzx   eax, word ptr [rdx+2]
0x1400659c8  lea     rdx, [rbp+1C0h+FileObject]; Source
0x1400659cc  add     rcx, rax
0x1400659cf  mov     [rbp+1C0h+FileObject+8], rcx
0x1400659d3  lea     rcx, [rbp+1C0h+SourceString]; SourceString
0x1400659da  call    ?CombinePath@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@0AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEBG@Z; UnionFs::Utils::CombinePath(_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort const *)
0x1400659df  xor     r11d, r11d
0x1400659e2  mov     edi, eax
0x1400659e4  test    eax, eax
0x1400659e6  js      loc_14006666C
0x1400659ec  movzx   r8d, [rbp+1C0h+var_1C8]; unsigned __int16
0x1400659f1  lea     rdx, [rbp+1C0h+var_218]; struct _UNICODE_STRING *
0x1400659f5  lea     rcx, [rbp+1C0h+UnicodeString]; this
0x1400659f9  call    ??0UfsPathName@UnionFs@@QEAA@AEBU_UNICODE_STRING@@G@Z; UnionFs::UfsPathName::UfsPathName(_UNICODE_STRING const &,ushort)
0x1400659fe  cmp     dword ptr [r12+1Ch], 2
0x140065a04  xorps   xmm0, xmm0
0x140065a07  xorps   xmm2, xmm2
0x140065a0a  movdqa  [rbp+1C0h+var_110], xmm0
0x140065a12  xorps   xmm3, xmm3
0x140065a15  movdqa  [rbp+1C0h+var_140], xmm2
0x140065a1d  movdqa  xmmword ptr [rbp+1C0h+var_130], xmm3
0x140065a25  mov     [rbp+1C0h+Resource], r11
0x140065a2c  mov     [rbp+1C0h+var_118], r11
0x140065a33  jnz     short loc_140065A40
0x140065a35  mov     rax, [r12+20h]
0x140065a3a  mov     rcx, [rax+10h]
0x140065a3e  jmp     short loc_140065A4B
0x140065a40  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140065a47  mov     rcx, [rax+50h]
0x140065a4b  mov     rdx, [rbp+1C0h+Instance]
0x140065a4f  lea     rax, [rbp+1C0h+var_140]
0x140065a56  mov     [rsp+2C0h+AllocationSize], r11
0x140065a5b  lea     r8, [rbp+1C0h+UnicodeString]
0x140065a5f  mov     [rsp+2C0h+IoStatusBlock], r13
0x140065a64  mov     r9d, 0Ah
0x140065a6a  mov     [rsp+2C0h+ObjectAttributes], rax
0x140065a6f  mov     [rsp+2C0h+DesiredAccess], r11d
0x140065a74  call    ?LookupEntryPriv@UfsPathCache@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupEntryFlags@2@W4PrivateLookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntryPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupEntryFlags,UnionFs::PrivateLookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140065a79  mov     edi, eax
0x140065a7b  test    eax, eax
0x140065a7d  js      loc_140066659
0x140065a83  mov     rdx, r12
0x140065a86  mov     [rsp+2C0h+ObjectAttributes], r13; char *
0x140065a8b  mov     r12, [rbp+1C0h+Instance]
0x140065a8f  lea     rax, [rbp+1C0h+var_130]
0x140065a96  mov     rcx, r12
0x140065a99  mov     qword ptr [rsp+2C0h+DesiredAccess], rax
0x140065a9e  mov     r9d, 0Dh
0x140065aa4  lea     r8, [rbp+1C0h+UnicodeString]
0x140065aa8  call    ?MarkFileAsSoftTombstone@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAVUfsUnionCtx@2@AEAVUfsPathName@2@W4SoftTombstoneReason@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::MarkFileAsSoftTombstone(_FLT_INSTANCE const &,UnionFs::UfsUnionCtx &,UnionFs::UfsPathName &,UnionFs::SoftTombstoneReason,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &)
0x140065aad  mov     edi, eax
0x140065aaf  test    eax, eax
0x140065ab1  js      loc_14006662D
0x140065ab7  mov     rcx, [rbp+1C0h+Resource]; Resource
0x140065abe  xor     edi, edi
0x140065ac0  mov     [rbp+1C0h+Resource], rdi
0x140065ac7  test    rcx, rcx
0x140065aca  jz      short loc_140065AE4
0x140065acc  call    cs:__imp_ExReleaseResourceLite
0x140065ad3  nop     dword ptr [rax+rax+00h]
0x140065ad8  call    cs:__imp_KeLeaveCriticalRegion
0x140065adf  nop     dword ptr [rax+rax+00h]
0x140065ae4  mov     rdx, qword ptr [rbp+1C0h+var_208+8]
0x140065ae8  mov     rcx, [rbp+1C0h+var_1F8]
0x140065aec  cmp     rdx, rcx
0x140065aef  jz      short loc_140065B08
0x140065af1  mov     rax, [rbp+1C0h+var_130]
0x140065af8  mov     rcx, [rbp+1C0h+var_130+8]
0x140065aff  mov     [rdx], rax
0x140065b02  mov     [rdx+8], rcx
0x140065b06  jmp     short loc_140065B83
0x140065b08  sub     rcx, qword ptr [rbp+1C0h+var_208]
0x140065b0c  sar     rcx, 4
0x140065b10  mov     rax, rcx
0x140065b13  shr     rax, 2
0x140065b17  imul    rdx, rax, 7
0x140065b1b  mov     rax, 7FFFFFFFFFFFFFFh
0x140065b25  add     rdx, 8
0x140065b29  cmp     rdx, rax
0x140065b2c  cmova   rdx, rax
0x140065b30  cmp     rcx, rdx
0x140065b33  jnb     loc_14006650A
0x140065b39  lea     rdi, [rbp+1C0h+var_130]
0x140065b40  sub     rdi, qword ptr [rbp+1C0h+var_208]
0x140065b44  lea     rcx, [rbp+1C0h+var_208]
0x140065b48  call    ?_SetCapacity@?$vector@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsPathCachePayload>>>::_SetCapacity(unsigned __int64)
0x140065b4d  test    al, al
0x140065b4f  jz      loc_140066508
0x140065b55  mov     r8, qword ptr [rbp+1C0h+var_208+8]
0x140065b59  lea     rdx, [rbp+1C0h+var_130]
0x140065b60  mov     rcx, qword ptr [rbp+1C0h+var_208]
0x140065b64  mov     rax, r8
0x140065b67  sub     rax, rcx
0x140065b6a  cmp     rdi, rax
0x140065b6d  jnb     short loc_140065B73
0x140065b6f  lea     rdx, [rcx+rdi]
0x140065b73  mov     rcx, [rdx+8]
0x140065b77  xor     edi, edi
0x140065b79  mov     rax, [rdx]
0x140065b7c  mov     [r8], rax
0x140065b7f  mov     [r8+8], rcx
0x140065b83  test    rcx, rcx
0x140065b86  jz      short loc_140065B8C
0x140065b88  lock inc dword ptr [rcx+8]
0x140065b8c  add     qword ptr [rbp+1C0h+var_208+8], 10h
0x140065b91  lea     rax, [rbp+1C0h+var_218]
0x140065b95  mov     [rbp+1C0h+var_B0.ObjectName], rax
0x140065b9c  lea     r9, [rbp+1C0h+FileObject+8]; FileObject
0x140065ba0  mov     eax, 28h ; '('
0x140065ba5  mov     qword ptr [rbp+1C0h+var_B0.Length], 30h ; '0'
0x140065bb0  xorps   xmm1, xmm1
0x140065bb3  mov     qword ptr [rbp+1C0h+var_B0.Attributes], 200h
0x140065bbe  movups  xmmword ptr [rbp+1C0h+var_80.Size], xmm1
0x140065bc5  mov     [rbp+1C0h+var_80.Size], ax
0x140065bcc  lea     r8, [rbp+1C0h+FileHandle]; FileHandle
0x140065bd0  lea     ecx, [rax-27h]
0x140065bd3  mov     [rbp+1C0h+var_B0.RootDirectory], rdi
0x140065bda  mov     [rbp+1C0h+var_60], rcx
0x140065be1  lea     rax, [rbp+1C0h+Object]
0x140065be5  mov     [rbp+1C0h+FileObject], rax
0x140065be9  xorps   xmm0, xmm0
0x140065bec  mov     [rbp+1C0h+var_148], cl
0x140065bef  lea     rax, [rbp+1C0h+var_80]
0x140065bf6  mov     [rsp+2C0h+DriverContext], rax; DriverContext
0x140065bfb  mov     rdx, r12; Instance
0x140065bfe  mov     [rsp+2C0h+Flags], edi; Flags
0x140065c02  lea     rax, [rbp+1C0h+var_58]
0x140065c09  mov     [rsp+2C0h+EaLength], edi; EaLength
0x140065c0d  mov     [rsp+2C0h+EaBuffer], rdi; EaBuffer
0x140065c12  mov     [rsp+2C0h+CreateOptions], 200020h; CreateOptions
0x140065c1a  mov     [rsp+2C0h+CreateDisposition], ecx; CreateDisposition
0x140065c1e  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140065c25  mov     [rsp+2C0h+ShareAccess], 7; ShareAccess
0x140065c2d  mov     [rsp+2C0h+FileAttributes], edi; FileAttributes
0x140065c31  mov     [rsp+2C0h+AllocationSize], rdi; AllocationSize
0x140065c36  mov     [rsp+2C0h+IoStatusBlock], rax; IoStatusBlock
0x140065c3b  lea     rax, [rbp+1C0h+var_B0]
0x140065c42  movdqu  xmmword ptr [rbp+1C0h+var_B0.SecurityDescriptor], xmm0
0x140065c4a  mov     [rbp+1C0h+Object], rdi
0x140065c4e  movups  xmmword ptr [rbp+1C0h+var_58], xmm0
0x140065c55  mov     [rbp+1C0h+FileObject+8], rdi
0x140065c59  movups  xmmword ptr [rbp+1C0h+var_80.DeviceObjectHint], xmm1
0x140065c60  mov     [rbp+1C0h+FileHandle], rdi
0x140065c64  mov     rcx, [rcx]; Filter
0x140065c67  mov     [rsp+2C0h+ObjectAttributes], rax; char *
0x140065c6c  mov     [rsp+2C0h+DesiredAccess], 10000h; DesiredAccess
0x140065c74  call    cs:__imp_FltCreateFileEx2
0x140065c7b  nop     dword ptr [rax+rax+00h]
0x140065c80  xor     r12d, r12d
0x140065c83  mov     edi, eax
0x140065c85  cmp     [rbp+1C0h+var_148], r12b
0x140065c89  jz      short loc_140065CAA
0x140065c8b  mov     r8, [rbp+1C0h+FileObject]
0x140065c8f  mov     rdx, [rbp+1C0h+FileObject+8]
0x140065c93  mov     rcx, [r8]; Object
0x140065c96  mov     [r8], rdx
0x140065c99  test    rcx, rcx
0x140065c9c  jz      short loc_140065CAA
0x140065c9e  call    cs:__imp_ObfDereferenceObject
0x140065ca5  nop     dword ptr [rax+rax+00h]
0x140065caa  test    edi, edi
0x140065cac  js      short loc_140065CB7
0x140065cae  mov     byte ptr [rbp+1C0h+arg_8], 1
0x140065cb5  jmp     short loc_140065CD2
0x140065cb7  mov     byte ptr [rbp+1C0h+arg_8], r12b
0x140065cbe  cmp     edi, 0C000003Ah
  ... truncated ...
```
