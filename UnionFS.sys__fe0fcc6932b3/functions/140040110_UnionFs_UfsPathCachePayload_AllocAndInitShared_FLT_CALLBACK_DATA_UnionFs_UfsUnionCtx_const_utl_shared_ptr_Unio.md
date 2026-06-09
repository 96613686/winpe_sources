# UnionFs::UfsPathCachePayload::AllocAndInitShared(_FLT_CALLBACK_DATA &,UnionFs::UfsUnionCtx const &,utl::shared_ptr<UnionFs::UfsLayerCtx>,UnionFs::UfsPathName const &,ulong,utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,UnionFs::StackEventTracer &,utl::pair<UnionFs::UfsPathName const *,UnionFs::UfsPathName const *> *)

- ea: `0x140040110`
- end: `0x140040fed`
- name: `?AllocAndInitShared@UfsPathCachePayload@UnionFs@@SAJAEAU_FLT_CALLBACK_DATA@@AEBVUfsUnionCtx@2@V?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEBVUfsPathName@2@KAEAU?$pair@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@2@@6@AEAVStackEventTracer@2@PEAU?$pair@PEBVUfsPathName@UnionFs@@PEBV12@@6@@Z`
- size: `3805`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, __int64, const UNICODE_STRING *, int, _QWORD *, struct UnionFs::Utils::CallerAccessParams *, __int64)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x140013b60`
- `0x14001568c`

## callees

- `0x14000f81c`
- `0x140027cb8`
- `0x140027ef8`
- `0x14003f41c`
- `0x14003f618`
- `0x14003f704`
- `0x14003fbd8`
- `0x14003fef8`
- `0x140040020`
- `0x140040110`
- `0x140043c08`
- `0x1400448c8`
- `0x140056c44`
- `0x140056c7c`
- `0x14006e1a0`
- `0x14006e394`
- `0x14006fc38`
- `0x140073224`
- `0x140076508`
- `0x140076fa4`
- `0x140078764`
- `0x140078dc0`
- `0x140079d44`
- `0x140079f68`
- `0x14007a0c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140040612`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040749`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040849`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040db4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040edb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f57`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040612`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040749`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040849`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040db4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040edb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040f57`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400407bf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004092c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040a47`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040d64`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040f05`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400407bf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004092c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040a47`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040d64`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040f05`
- `ntoskrnl!ObfDereferenceObject` at `0x1400401dd`
- `ntoskrnl!ObfDereferenceObject` at `0x14004022d`
- `ntoskrnl!ObfDereferenceObject` at `0x140040307`
- `ntoskrnl!ObfDereferenceObject` at `0x140040336`
- `ntoskrnl!ObfDereferenceObject` at `0x14004048c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400404bb`
- `ntoskrnl!ObfDereferenceObject` at `0x140040658`
- `ntoskrnl!ObfDereferenceObject` at `0x140040687`
- `ntoskrnl!ObfDereferenceObject` at `0x140040add`
- `ntoskrnl!ObfDereferenceObject` at `0x140040b0c`
- `ntoskrnl!ObfDereferenceObject` at `0x140040dfa`
- `ntoskrnl!ObfDereferenceObject` at `0x140040e29`
- `ntoskrnl!ObfDereferenceObject` at `0x140040f9d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400401dd`
- `ntoskrnl!ObfDereferenceObject` at `0x14004022d`
- `ntoskrnl!ObfDereferenceObject` at `0x140040307`
- `ntoskrnl!ObfDereferenceObject` at `0x140040336`
- `ntoskrnl!ObfDereferenceObject` at `0x14004048c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400404bb`
- `ntoskrnl!ObfDereferenceObject` at `0x140040658`
- `ntoskrnl!ObfDereferenceObject` at `0x140040687`
- `ntoskrnl!ObfDereferenceObject` at `0x140040add`
- `ntoskrnl!ObfDereferenceObject` at `0x140040b0c`
- `ntoskrnl!ObfDereferenceObject` at `0x140040dfa`
- `ntoskrnl!ObfDereferenceObject` at `0x140040e29`
- `ntoskrnl!ObfDereferenceObject` at `0x140040f9d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140040871`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140040871`
- `FLTMGR!FltClose` at `0x1400401f3`
- `FLTMGR!FltClose` at `0x140040243`
- `FLTMGR!FltClose` at `0x14004031b`
- `FLTMGR!FltClose` at `0x14004034c`
- `FLTMGR!FltClose` at `0x1400404a0`
- `FLTMGR!FltClose` at `0x1400404d1`
- `FLTMGR!FltClose` at `0x14004066c`
- `FLTMGR!FltClose` at `0x14004069d`
- `FLTMGR!FltClose` at `0x140040af1`
- `FLTMGR!FltClose` at `0x140040b22`
- `FLTMGR!FltClose` at `0x140040e0e`
- `FLTMGR!FltClose` at `0x140040e3f`
- `FLTMGR!FltClose` at `0x140040fb1`
- `FLTMGR!FltClose` at `0x1400401f3`
- `FLTMGR!FltClose` at `0x140040243`
- `FLTMGR!FltClose` at `0x14004031b`
- `FLTMGR!FltClose` at `0x14004034c`
- `FLTMGR!FltClose` at `0x1400404a0`
- `FLTMGR!FltClose` at `0x1400404d1`
- `FLTMGR!FltClose` at `0x14004066c`
- `FLTMGR!FltClose` at `0x14004069d`
- `FLTMGR!FltClose` at `0x140040af1`
- `FLTMGR!FltClose` at `0x140040b22`
- `FLTMGR!FltClose` at `0x140040e0e`
- `FLTMGR!FltClose` at `0x140040e3f`
- `FLTMGR!FltClose` at `0x140040fb1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400402f3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040478`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040644`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040ac9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040de6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040f89`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400402f3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040478`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040644`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040ac9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040de6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040f89`
- `FLTMGR!FltReleaseContext` at `0x1400409df`
- `FLTMGR!FltReleaseContext` at `0x140040baa`
- `FLTMGR!FltReleaseContext` at `0x140040cf9`
- `FLTMGR!FltReleaseContext` at `0x140040e9c`
- `FLTMGR!FltReleaseContext` at `0x1400409df`
- `FLTMGR!FltReleaseContext` at `0x140040baa`
- `FLTMGR!FltReleaseContext` at `0x140040cf9`
- `FLTMGR!FltReleaseContext` at `0x140040e9c`

## string_xrefs

- `0x1400401a7`: `PUSH: Opening item in layer`
- `0x1400401b8`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x1400402ce`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x14004043b`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040557`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x1400405d4`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x14004071a`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040783`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040808`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040953`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x1400409c2`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040b91`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040c1d`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040cd8`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040546`: `PUSH: Creating post-rename path`
- `0x1400405c3`: `PUSH: Creating scratch path name`
- `0x140040709`: `PUSH: Getting caller access`
- `0x1400407f7`: `PUSH: Copying FullPathInLayer`
- `0x140040942`: `ORIGIN: Allocating path cache payload node`
- `0x140040c07`: `PUSH: Getting backing reparse data`
- `0x140040c6c`: `PUSH: Virtualizing cached reparse data`
- `0x140040cc7`: `ORIGIN: Inserting UserSidString`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::AllocAndInitShared(
        PFLT_CALLBACK_DATA Data,
        __int64 a2,
        __int64 a3,
        const UNICODE_STRING *a4,
        int a5,
        _QWORD *a6,
        struct UnionFs::Utils::CallerAccessParams *a7,
        __int64 a8)
{
  _QWORD *v8; // rax
  utl::_RefCountBase *v13; // rcx
  struct _LIST_ENTRY *v14; // rax
  struct UnionFs::Utils::CallerAccessParams *v15; // r15
  struct _FLT_INSTANCE *Flink; // r8
  int v17; // ebx
  HANDLE v18; // rcx
  utl::_RefCountBase *v19; // rcx
  HANDLE v21; // rcx
  utl::_RefCountBase *v22; // rcx
  struct _LIST_ENTRY *v23; // rdi
  struct _LIST_ENTRY *v24; // rax
  HANDLE v25; // rbx
  PVOID *p_Flink; // rcx
  int FileNameInformation; // esi
  struct _FLT_FILE_NAME_INFORMATION *v28; // rcx
  HANDLE v29; // rcx
  utl::_RefCountBase *v30; // rcx
  unsigned __int64 *v31; // rdx
  const unsigned __int16 *v32; // r8
  __int64 *v33; // rax
  volatile signed __int32 *v34; // rsi
  __int64 v35; // r14
  struct _LIST_ENTRY *v36; // rax
  struct _UNICODE_STRING *v37; // rdx
  const unsigned __int16 *v38; // r8
  void *v39; // rcx
  int Substring; // r14d
  struct _UNICODE_STRING *v41; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v42; // rcx
  HANDLE v43; // rcx
  utl::_RefCountBase *v44; // rcx
  LIST_ENTRY *v45; // rax
  LIST_ENTRY v46; // xmm1
  _OWORD *v47; // rax
  struct _UNICODE_STRING *v48; // rdx
  struct _UNICODE_STRING *v49; // rdx
  struct _UNICODE_STRING v50; // xmm1
  int CallerAccessForLayerFile; // r13d
  struct _UNICODE_STRING *v52; // rdx
  struct _UNICODE_STRING *v53; // r14
  struct _FLT_FILE_NAME_INFORMATION *v54; // rcx
  HANDLE v55; // rcx
  utl::_RefCountBase *v56; // rcx
  struct _LIST_ENTRY *v57; // rax
  const UNICODE_STRING *v58; // r14
  struct _UNICODE_STRING *v59; // rdx
  struct _UNICODE_STRING *v60; // rdx
  PVOID v61; // r14
  struct _UNICODE_STRING *v62; // r14
  PVOID v63; // rax
  __int64 v64; // rcx
  UnionFs::UfsPathCachePayloadNP *v65; // r14
  char v66; // r13
  PVOID v67; // r13
  struct _UNICODE_STRING *v68; // rdx
  struct _LIST_ENTRY *v69; // rax
  struct _FILE_OBJECT *v70; // rdx
  int Set; // eax
  struct _UNICODE_STRING *v72; // rdx
  struct _UNICODE_STRING *v73; // r15
  struct _UNICODE_STRING *v74; // rdx
  struct _UNICODE_STRING *v75; // r14
  struct _FLT_FILE_NAME_INFORMATION *v76; // rcx
  HANDLE v77; // rcx
  utl::_RefCountBase *v78; // rcx
  PVOID v79; // r13
  int v80; // eax
  struct _LIST_ENTRY *v81; // rax
  int ReparseData; // eax
  const char *v83; // rcx
  __int64 v84; // r8
  void *v85; // r8
  struct _UNICODE_STRING *v86; // rdx
  struct _UNICODE_STRING *v87; // r15
  struct _UNICODE_STRING *v88; // rdx
  struct _UNICODE_STRING *v89; // r14
  struct _FLT_FILE_NAME_INFORMATION *v90; // rcx
  HANDLE v91; // rcx
  utl::_RefCountBase *v92; // rcx
  _QWORD *v93; // rcx
  utl::_RefCountBase *v94; // r15
  struct _UNICODE_STRING *v95; // r15
  struct _UNICODE_STRING *v96; // rdx
  struct _UNICODE_STRING *v97; // r14
  struct _FLT_FILE_NAME_INFORMATION *v98; // rcx
  utl::_RefCountBase *v99; // rcx
  ULONG v100; // [rsp+28h] [rbp-E0h]
  PACL Dacl; // [rsp+30h] [rbp-D8h]
  PACL Dacla; // [rsp+30h] [rbp-D8h]
  PACL Daclb; // [rsp+30h] [rbp-D8h]
  unsigned __int8 v104; // [rsp+40h] [rbp-C8h]
  PFLT_FILE_NAME_INFORMATION FileHandle; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE FileHandle_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 P; // [rsp+60h] [rbp-A8h]
  struct _UNICODE_STRING P_8; // [rsp+68h] [rbp-A0h] BYREF
  struct _UNICODE_STRING UnicodeString_8; // [rsp+78h] [rbp-90h] BYREF
  PVOID Entry; // [rsp+88h] [rbp-80h] BYREF
  __int16 v111; // [rsp+90h] [rbp-78h]
  int v112; // [rsp+92h] [rbp-76h]
  __int16 v113; // [rsp+96h] [rbp-72h]
  PVOID v114[2]; // [rsp+98h] [rbp-70h] BYREF
  PVOID v115; // [rsp+A8h] [rbp-60h] BYREF
  int v116; // [rsp+B0h] [rbp-58h] BYREF
  struct _FLT_CALLBACK_DATA v117; // [rsp+B8h] [rbp-50h] BYREF
  UNICODE_STRING v118; // [rsp+110h] [rbp+8h] BYREF
  PVOID v121; // [rsp+188h] [rbp+80h] BYREF
  PCUNICODE_STRING SourceString; // [rsp+190h] [rbp+88h]

  SourceString = a4;
  v8 = a6;
  LODWORD(v121) = 0;
  v13 = (utl::_RefCountBase *)a6[1];
  *a6 = 0;
  v8[1] = 0;
  if ( v13 )
    utl::_RefCountBase::_DecStrong(v13);
  v14 = *(struct _LIST_ENTRY **)a3;
  v15 = a7;
  *(_OWORD *)FileHandle_8 = 0;
  Flink = (struct _FLT_INSTANCE *)v14->Blink->Flink;
  v117.QueueLinks = (LIST_ENTRY)*a4;
  v17 = UnionFs::Utils::OpenBackingFile(Data, (struct _UNICODE_STRING *)&v117.QueueLinks, Flink, FileHandle_8, (int)a7);
  if ( v17 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v17,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x22C0012006ALL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Opening item in layer",
      (const char *)Dacl);
    v18 = FileHandle_8[1];
    FileHandle_8[1] = 0;
    if ( v18 )
      ObfDereferenceObject(v18);
    if ( FileHandle_8[0] )
      FltClose(FileHandle_8[0]);
    v19 = *(utl::_RefCountBase **)(a3 + 8);
    if ( v19 )
      utl::_RefCountBase::_DecStrong(v19);
    return (unsigned int)v17;
  }
  if ( v17 == 260 )
  {
    v21 = FileHandle_8[1];
    FileHandle_8[1] = 0;
    if ( v21 )
      ObfDereferenceObject(v21);
    if ( FileHandle_8[0] )
      FltClose(FileHandle_8[0]);
    v22 = *(utl::_RefCountBase **)(a3 + 8);
    if ( v22 )
      utl::_RefCountBase::_DecStrong(v22);
    return 260;
  }
  v23 = (struct _LIST_ENTRY *)FileHandle_8[1];
  v24 = *(struct _LIST_ENTRY **)a3;
  v25 = FileHandle_8[0];
  *(_OWORD *)FileHandle_8 = 0u;
  p_Flink = (PVOID *)&v24->Blink->Flink;
  *(_QWORD *)&v117.RequestorMode = v25;
  v115 = v23;
  v117.QueueLinks.Flink = 0;
  v117.QueueContext[0] = *p_Flink;
  FileHandle = 0;
  v117.QueueLinks.Blink = v23;
  FileNameInformation = UnionFs::Utils::GetFileNameInformation(&v117.QueueLinks, 1025, &FileHandle, v15);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x4600012007FLL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Querying normalized layer name",
      (const char *)Dacl);
    v28 = FileHandle;
    FileHandle = 0;
    if ( v28 )
      FltReleaseFileNameInformation(v28);
    if ( v23 )
      ObfDereferenceObject(v23);
    if ( v25 )
      FltClose(v25);
    v29 = FileHandle_8[1];
    FileHandle_8[1] = 0;
    if ( v29 )
      ObfDereferenceObject(v29);
    if ( FileHandle_8[0] )
      FltClose(FileHandle_8[0]);
    v30 = *(utl::_RefCountBase **)(a3 + 8);
    if ( v30 )
      utl::_RefCountBase::_DecStrong(v30);
    return (unsigned int)FileNameInformation;
  }
  FsFltWil::AcquirePushLockShared(&Entry, a2 + 72);
  v33 = *(__int64 **)(a2 + 48);
  v34 = (volatile signed __int32 *)v33[1];
  v35 = *v33;
  if ( v34 )
    _InterlockedIncrement(v34 + 2);
  if ( Entry )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Entry, v31);
  v36 = *(struct _LIST_ENTRY **)a3;
  v118 = 0;
  P_8 = *(struct _UNICODE_STRING *)&v36[1].Flink[2].Blink;
  UnionFs::Utils::StripTrailingBackslashFromPath((UnionFs::Utils *)&P_8, 0, v32);
  v118 = *(UNICODE_STRING *)(*(_QWORD *)(v35 + 16) + 40LL);
  UnionFs::Utils::StripTrailingBackslashFromPath((UnionFs::Utils *)&v118, v37, v38);
  v111 = 0;
  UnicodeString_8 = 0;
  v39 = **(void ***)(v35 + 8);
  v112 = 0;
  v113 = 0;
  Entry = v39;
  Substring = UnionFs::Utils::RewritePath(FileHandle, &P_8, &v118, &UnicodeString_8, (int)v15, (__int64)&Entry);
  if ( Substring < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)Substring,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x46400120095LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Rewriting layer -> scratch",
      (const char *)Dacla);
LABEL_39:
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v41);
    if ( v34 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
    v42 = FileHandle;
    FileHandle = 0;
    if ( v42 )
      FltReleaseFileNameInformation(v42);
    if ( v23 )
      ObfDereferenceObject(v23);
    if ( v25 )
      FltClose(v25);
    v43 = FileHandle_8[1];
    FileHandle_8[1] = 0;
    if ( v43 )
      ObfDereferenceObject(v43);
    if ( FileHandle_8[0] )
      FltClose(FileHandle_8[0]);
    v44 = *(utl::_RefCountBase **)(a3 + 8);
    if ( v44 )
      utl::_RefCountBase::_DecStrong(v44);
    return (unsigned int)Substring;
  }
  if ( a8 )
  {
    v45 = *(LIST_ENTRY **)(a8 + 8);
    P_8 = 0;
    v46 = *v45;
    v47 = *(_OWORD **)a8;
    v117.QueueLinks = v46;
    *(_OWORD *)v114 = *v47;
    Substring = UnionFs::Utils::ReplaceFirstSubstring(
                  (UnionFs::Rtl *)&UnicodeString_8,
                  (struct _UNICODE_STRING *)v114,
                  (PCUNICODE_STRING)&v117.QueueLinks,
                  (int)v15);
    if ( Substring < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)Substring,
        (int)v15,
        (struct UnionFs::StackEventTracer *)0x215001200A7LL,
        (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
        "PUSH: Creating post-rename path",
        (const char *)Dacla);
      FsFltWil::Details::FreeUnicodeString(&P_8, v49);
      goto LABEL_39;
    }
    v50 = UnicodeString_8;
    UnicodeString_8 = P_8;
    P_8 = v50;
    FsFltWil::Details::FreeUnicodeString(&P_8, v48);
  }
  P = 0;
  CallerAccessForLayerFile = UnionFs::UfsPathName::AllocAndInit(&UnicodeString_8);
  if ( CallerAccessForLayerFile < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)CallerAccessForLayerFile,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x259001200B3LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Creating scratch path name",
      (const char *)Dacla);
LABEL_60:
    v53 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*(_BYTE *)(P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v53, v52);
      ExFreePoolWithTag(v53, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v52);
    if ( v34 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
    v54 = FileHandle;
    FileHandle = 0;
    if ( v54 )
      FltReleaseFileNameInformation(v54);
    if ( v23 )
      ObfDereferenceObject(v23);
    if ( v25 )
      FltClose(v25);
    v55 = FileHandle_8[1];
    FileHandle_8[1] = 0;
    if ( v55 )
      ObfDereferenceObject(v55);
    if ( FileHandle_8[0] )
      FltClose(FileHandle_8[0]);
    v56 = *(utl::_RefCountBase **)(a3 + 8);
    if ( v56 )
      utl::_RefCountBase::_DecStrong(v56);
    return (unsigned int)CallerAccessForLayerFile;
  }
  v57 = *(struct _LIST_ENTRY **)a3;
  v58 = SourceString;
  memset(&v117, 0, 24);
  *(UNICODE_STRING *)&v117.IoStatus.Status = *SourceString;
  CallerAccessForLayerFile = UnionFs::Utils::GetCallerAccessForLayerFile(
                               (UnionFs::Utils *)v57->Blink->Flink,
                               (const struct _FLT_INSTANCE *)v23,
                               (const struct _FILE_OBJECT *)Data,
                               &v117,
                               v15,
                               (struct UnionFs::StackEventTracer *)Dacla);
  if ( CallerAccessForLayerFile < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)CallerAccessForLayerFile,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x239001200C0LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Getting caller access",
      (const char *)Daclb);
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v117.Thread, v59);
LABEL_81:
    if ( *(_QWORD *)&v117.Flags )
      ExFreePoolWithTag(*(PVOID *)&v117.Flags, 0);
    goto LABEL_60;
  }
  Entry = 0;
  CallerAccessForLayerFile = UnionFs::UfsPathCachePayloadNP::AllocAndInit(&Entry, v15);
  if ( CallerAccessForLayerFile < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)CallerAccessForLayerFile,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x11A001200C7LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Creating NP ctx",
      (const char *)Daclb);
LABEL_85:
    v61 = Entry;
    if ( Entry )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP((UnionFs::UfsPathCachePayloadNP *)Entry);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v61);
    }
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v117.Thread, v60);
    goto LABEL_81;
  }
  v114[0] = 0;
  CallerAccessForLayerFile = UnionFs::UfsPathName::Copy(v58);
  if ( CallerAccessForLayerFile < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)CallerAccessForLayerFile,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x17B001200CDLL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Copying FullPathInLayer",
      (const char *)Daclb);
    v62 = (struct _UNICODE_STRING *)v114[0];
    if ( v114[0] )
    {
      if ( !*((_BYTE *)v114[0] + 16) )
        *(_OWORD *)v114[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v62, v60);
      ExFreePoolWithTag(v62, 0);
    }
    goto LABEL_85;
  }
  P_8 = 0;
  v63 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1664));
  if ( v63 )
  {
    v117.QueueLinks.Flink = *(struct _LIST_ENTRY **)a3;
    v64 = *(_QWORD *)(a3 + 8);
    v117.QueueLinks.Blink = (struct _LIST_ENTRY *)v64;
    if ( v64 )
      _InterlockedIncrement((volatile signed __int32 *)(v64 + 8));
    v121 = Entry;
    v65 = 0;
    v63 = (PVOID)UnionFs::UfsPathCachePayload::UfsPathCachePayload(
                   (int)v63,
                   (int)&v121,
                   (int)&v117.QueueLinks,
                   (int)v114,
                   (unsigned __int8)&v117.RequestorMode,
                   (PACL)&v115,
                   (__int64)&v117,
                   v104);
    v25 = *(HANDLE *)&v117.RequestorMode;
    v66 = 1;
    v23 = (struct _LIST_ENTRY *)v115;
  }
  else
  {
    v65 = (UnionFs::UfsPathCachePayloadNP *)Entry;
    v66 = 0;
  }
  utl::shared_ptr<UnionFs::UfsPathCachePayload>::reset<UnionFs::UfsPathCachePayload,0>(&P_8, v63);
  if ( (v66 & 1) != 0 )
  {
    v67 = v121;
    if ( v121 )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP((UnionFs::UfsPathCachePayloadNP *)v121);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v67);
    }
  }
  if ( !*(_QWORD *)&P_8.Length )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x1FA001200DCLL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "ORIGIN: Allocating path cache payload node",
      (const char *)Daclb);
LABEL_152:
    if ( P_8.Buffer )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)P_8.Buffer);
    v87 = (struct _UNICODE_STRING *)v114[0];
    if ( v114[0] )
    {
      if ( !*((_BYTE *)v114[0] + 16) )
        *(_OWORD *)v114[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v87, v68);
      ExFreePoolWithTag(v87, 0);
    }
    if ( v65 )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v65);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v65);
    }
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v117.Thread, v68);
    if ( *(_QWORD *)&v117.Flags )
      ExFreePoolWithTag(*(PVOID *)&v117.Flags, 0);
    v89 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*(_BYTE *)(P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v89, v88);
      ExFreePoolWithTag(v89, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v88);
    if ( v34 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
    v90 = FileHandle;
    FileHandle = 0;
    if ( v90 )
      FltReleaseFileNameInformation(v90);
    if ( v23 )
      ObfDereferenceObject(v23);
    if ( v25 )
      FltClose(v25);
    v91 = FileHandle_8[1];
    FileHandle_8[1] = 0;
    if ( v91 )
      ObfDereferenceObject(v91);
    if ( FileHandle_8[0] )
      FltClose(FileHandle_8[0]);
    v92 = *(utl::_RefCountBase **)(a3 + 8);
    if ( v92 )
      utl::_RefCountBase::_DecStrong(v92);
    return 3221225626LL;
  }
  v69 = *(struct _LIST_ENTRY **)a3;
  v70 = *(struct _FILE_OBJECT **)(*(_QWORD *)&P_8.Length + 64LL);
  Entry = 0;
  Set = UnionFs::UfsFileCtx::FltGetSet((PFLT_INSTANCE)v69->Blink->Flink, v70, a5);
  LODWORD(v121) = Set;
  if ( Set < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)Set,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x4A0001200EALL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Get/alloc backing file context",
      (const char *)Daclb);
    if ( Entry )
      FltReleaseContext(Entry);
LABEL_106:
    if ( P_8.Buffer )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)P_8.Buffer);
    v73 = (struct _UNICODE_STRING *)v114[0];
    if ( v114[0] )
    {
      if ( !*((_BYTE *)v114[0] + 16) )
        *(_OWORD *)v114[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v73, v72);
      ExFreePoolWithTag(v73, 0);
    }
    if ( v65 )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v65);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v65);
    }
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v117.Thread, v72);
    if ( *(_QWORD *)&v117.Flags )
      ExFreePoolWithTag(*(PVOID *)&v117.Flags, 0);
    v75 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*(_BYTE *)(P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v75, v74);
      ExFreePoolWithTag(v75, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v74);
    if ( v34 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
    v76 = FileHandle;
    FileHandle = 0;
    if ( v76 )
      FltReleaseFileNameInformation(v76);
    if ( v23 )
      ObfDereferenceObject(v23);
    if ( v25 )
      FltClose(v25);
    v77 = FileHandle_8[1];
    FileHandle_8[1] = 0;
    if ( v77 )
      ObfDereferenceObject(v77);
    if ( FileHandle_8[0] )
      FltClose(FileHandle_8[0]);
    v78 = *(utl::_RefCountBase **)(a3 + 8);
    if ( v78 )
      utl::_RefCountBase::_DecStrong(v78);
    return (unsigned int)v121;
  }
  v79 = Entry;
  v80 = UnionFs::UfsStreamCtx::FltGetSet(
          **(PFLT_INSTANCE **)(*(_QWORD *)a3 + 8LL),
          *(PFILE_OBJECT *)(*(_QWORD *)&P_8.Length + 64LL),
          (int)v15);
  LODWORD(v121) = v80;
  if ( v80 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v80,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x4A1001200F3LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Get/alloc backing stream context",
      (const char *)Daclb);
LABEL_137:
    if ( v79 )
      FltReleaseContext(v79);
    goto LABEL_106;
  }
  if ( (a5 & 0x400) != 0 )
  {
    v81 = *(struct _LIST_ENTRY **)a3;
    v115 = 0;
    v116 = 0;
    ReparseData = UnionFs::Utils::GetReparseData(
                    (PFLT_INSTANCE)v81->Blink->Flink,
                    *(PFILE_OBJECT *)(*(_QWORD *)&P_8.Length + 64LL),
                    v100);
    LODWORD(v121) = ReparseData;
    if ( ReparseData < 0 )
    {
      v83 = "PUSH: Getting backing reparse data";
      v84 = 0x79500120100LL;
      goto LABEL_143;
    }
    ReparseData = UnionFs::Utils::VirtualizeReparseData(&v115, &v116, a2, v15);
    LODWORD(v121) = ReparseData;
    if ( ReparseData < 0 )
    {
      v83 = "PUSH: Virtualizing cached reparse data";
      v84 = 0x79600120108LL;
LABEL_143:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)ReparseData,
        (int)v15,
        (struct UnionFs::StackEventTracer *)v84,
        (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
        v83,
        (const char *)Daclb);
      if ( v115 )
        ExFreePoolWithTag(v115, 0);
      goto LABEL_137;
    }
    v85 = *(void **)(*(_QWORD *)&P_8.Length + 96LL);
    *(_QWORD *)(*(_QWORD *)&P_8.Length + 96LL) = v115;
    if ( v85 )
      ExFreePoolWithTag(v85, 0);
  }
  utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::_InsertImpl<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>(
    *(_QWORD *)&P_8.Length + 104LL,
    &v117.QueueLinks,
    &v117.Thread);
  if ( !v117.QueueLinks.Flink )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)v15,
      (struct UnionFs::StackEventTracer *)0x23A00120118LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "ORIGIN: Inserting UserSidString",
      (const char *)Daclb);
    if ( v79 )
      FltReleaseContext(v79);
    goto LABEL_152;
  }
  v93 = a6;
  v94 = (utl::_RefCountBase *)a6[1];
  *(struct _UNICODE_STRING *)a6 = P_8;
  a6 = (_QWORD *)v93[2];
  v93[2] = P;
  if ( v79 )
    FltReleaseContext(v79);
  if ( v94 )
    utl::_RefCountBase::_DecStrong(v94);
  v95 = (struct _UNICODE_STRING *)v114[0];
  if ( v114[0] )
  {
    if ( !*((_BYTE *)v114[0] + 16) )
      *(_OWORD *)v114[0] = 0;
    FsFltWil::Details::FreeUnicodeString(v95, v86);
    ExFreePoolWithTag(v95, 0);
  }
  if ( v65 )
  {
    UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v65);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v65);
  }
  FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v117.Thread, v86);
  if ( *(_QWORD *)&v117.Flags )
    ExFreePoolWithTag(*(PVOID *)&v117.Flags, 0);
  v97 = (struct _UNICODE_STRING *)a6;
  if ( a6 )
  {
    if ( !*((_BYTE *)a6 + 16) )
      *(_OWORD *)a6 = 0;
    FsFltWil::Details::FreeUnicodeString(v97, v96);
    ExFreePoolWithTag(v97, 0);
  }
  FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v96);
  if ( v34 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
  v98 = FileHandle;
  FileHandle = 0;
  if ( v98 )
    FltReleaseFileNameInformation(v98);
  if ( v23 )
    ObfDereferenceObject(v23);
  if ( v25 )
    FltClose(v25);
  utl::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&__int64 ObfDereferenceObject(void *)>>>(FileHandle_8);
  v99 = *(utl::_RefCountBase **)(a3 + 8);
  if ( v99 )
    utl::_RefCountBase::_DecStrong(v99);
  return 0;
}

```

## disassembly

```asm
0x140040110  mov     rax, rsp
0x140040113  mov     [rax+20h], r9
0x140040117  mov     [rax+10h], rdx
0x14004011b  mov     [rax+8], rcx
0x14004011f  push    rbp
0x140040120  push    rbx
0x140040121  push    rsi
0x140040122  push    rdi
0x140040123  push    r12
0x140040125  push    r13
0x140040127  push    r14
0x140040129  push    r15
0x14004012b  lea     rbp, [rax-68h]
0x14004012f  sub     rsp, 128h
0x140040136  mov     rax, [rbp+60h+arg_28]
0x14004013d  xor     r13d, r13d
0x140040140  mov     dword ptr [rbp+60h+arg_10], r13d
0x140040147  mov     rdi, rcx
0x14004014a  mov     rbx, r9
0x14004014d  mov     r12, r8
0x140040150  mov     r14, rdx
0x140040153  mov     rcx, [rax+8]; this
0x140040157  mov     [rax], r13
0x14004015a  mov     [rax+8], r13
0x14004015e  test    rcx, rcx
0x140040161  jz      short loc_140040168
0x140040163  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140040168  mov     rax, [r12]
0x14004016c  lea     r9, [rsp+160h+FileHandle+8]; FileHandle
0x140040171  mov     r15, [rbp+60h+arg_30]
0x140040178  lea     rdx, [rbp+60h+Source]; char *
0x14004017c  xorps   xmm0, xmm0
0x14004017f  mov     qword ptr [rsp+160h+var_140], r15; int
0x140040184  movdqu  xmmword ptr [rsp+160h+FileHandle+8], xmm0
0x14004018a  mov     rcx, [rax+8]
0x14004018e  movups  xmm0, xmmword ptr [rbx]
0x140040191  mov     r8, [rcx]; Instance
0x140040194  mov     rcx, rdi; Data
0x140040197  movdqu  xmmword ptr [rbp+60h+Source.Length], xmm0
0x14004019c  call    ?OpenBackingFile@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@utl@@AEAVStackEventTracer@2@_N@Z; UnionFs::Utils::OpenBackingFile(_FLT_CALLBACK_DATA &,_UNICODE_STRING const &,_FLT_INSTANCE const &,utl::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>> &,UnionFs::StackEventTracer &,bool)
0x1400401a1  mov     ebx, eax
0x1400401a3  test    eax, eax
0x1400401a5  jns     short loc_140040215
0x1400401a7  lea     rax, aPushOpeningIte; "PUSH: Opening item in layer"
0x1400401ae  mov     r8, 22C0012006Ah; struct UnionFs::StackEventTracer *
0x1400401b8  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x1400401bf  mov     qword ptr [rsp+160h+var_140], rax; char *
0x1400401c4  mov     rdx, r15; int
0x1400401c7  mov     ecx, ebx; this
0x1400401c9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400401ce  mov     rcx, [rsp+160h+Object]; Object
0x1400401d3  mov     [rsp+160h+Object], r13
0x1400401d8  test    rcx, rcx
0x1400401db  jz      short loc_1400401E9
0x1400401dd  call    cs:__imp_ObfDereferenceObject
0x1400401e4  nop     dword ptr [rax+rax+00h]
0x1400401e9  mov     rcx, [rsp+160h+FileHandle+8]; FileHandle
0x1400401ee  test    rcx, rcx
0x1400401f1  jz      short loc_1400401FF
0x1400401f3  call    cs:__imp_FltClose
0x1400401fa  nop     dword ptr [rax+rax+00h]
0x1400401ff  mov     rcx, [r12+8]; this
0x140040204  test    rcx, rcx
0x140040207  jz      short loc_14004020E
0x140040209  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004020e  mov     eax, ebx
0x140040210  jmp     loc_140040FD8
0x140040215  mov     edi, 104h
0x14004021a  cmp     ebx, edi
0x14004021c  jnz     short loc_140040265
0x14004021e  mov     rcx, [rsp+160h+Object]; Object
0x140040223  mov     [rsp+160h+Object], r13
0x140040228  test    rcx, rcx
0x14004022b  jz      short loc_140040239
0x14004022d  call    cs:__imp_ObfDereferenceObject
0x140040234  nop     dword ptr [rax+rax+00h]
0x140040239  mov     rcx, [rsp+160h+FileHandle+8]; FileHandle
0x14004023e  test    rcx, rcx
0x140040241  jz      short loc_14004024F
0x140040243  call    cs:__imp_FltClose
0x14004024a  nop     dword ptr [rax+rax+00h]
0x14004024f  mov     rcx, [r12+8]; this
0x140040254  test    rcx, rcx
0x140040257  jz      short loc_14004025E
0x140040259  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004025e  mov     eax, edi
0x140040260  jmp     loc_140040FD8
0x140040265  mov     rdi, [rsp+160h+Object]
0x14004026a  lea     r8, [rsp+160h+FileHandle]
0x14004026f  mov     rax, [r12]
0x140040273  mov     r9, r15
0x140040276  mov     rbx, [rsp+160h+FileHandle+8]
0x14004027b  mov     edx, 401h
0x140040280  mov     [rsp+160h+FileHandle+8], r13
0x140040285  mov     [rsp+160h+Object], r13
0x14004028a  mov     rcx, [rax+8]
0x14004028e  mov     [rbp+60h+var_60], rbx
0x140040292  mov     [rbp+60h+var_C0], rdi
0x140040296  mov     qword ptr [rbp+60h+Source.Length], r13
0x14004029a  mov     rax, [rcx]
0x14004029d  lea     rcx, [rbp+60h+Source]
0x1400402a1  mov     [rbp+60h+var_70], rax
0x1400402a5  mov     [rsp+160h+FileHandle], r13
0x1400402aa  mov     [rbp+60h+Source.Buffer], rdi
0x1400402ae  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x1400402b3  mov     esi, eax
0x1400402b5  test    eax, eax
0x1400402b7  jns     loc_14004036E
0x1400402bd  lea     rax, aPushQueryingNo; "PUSH: Querying normalized layer name"
0x1400402c4  mov     r8, 4600012007Fh; struct UnionFs::StackEventTracer *
0x1400402ce  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x1400402d5  mov     qword ptr [rsp+160h+var_140], rax; char *
0x1400402da  mov     rdx, r15; int
0x1400402dd  mov     ecx, esi; this
0x1400402df  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400402e4  mov     rcx, [rsp+160h+FileHandle]; FileNameInformation
0x1400402e9  mov     [rsp+160h+FileHandle], r13
0x1400402ee  test    rcx, rcx
0x1400402f1  jz      short loc_1400402FF
0x1400402f3  call    cs:__imp_FltReleaseFileNameInformation
0x1400402fa  nop     dword ptr [rax+rax+00h]
0x1400402ff  test    rdi, rdi
0x140040302  jz      short loc_140040313
0x140040304  mov     rcx, rdi; Object
0x140040307  call    cs:__imp_ObfDereferenceObject
0x14004030e  nop     dword ptr [rax+rax+00h]
0x140040313  test    rbx, rbx
0x140040316  jz      short loc_140040327
0x140040318  mov     rcx, rbx; FileHandle
0x14004031b  call    cs:__imp_FltClose
0x140040322  nop     dword ptr [rax+rax+00h]
0x140040327  mov     rcx, [rsp+160h+Object]; Object
0x14004032c  mov     [rsp+160h+Object], r13
0x140040331  test    rcx, rcx
0x140040334  jz      short loc_140040342
0x140040336  call    cs:__imp_ObfDereferenceObject
0x14004033d  nop     dword ptr [rax+rax+00h]
0x140040342  mov     rcx, [rsp+160h+FileHandle+8]; FileHandle
0x140040347  test    rcx, rcx
0x14004034a  jz      short loc_140040358
0x14004034c  call    cs:__imp_FltClose
0x140040353  nop     dword ptr [rax+rax+00h]
0x140040358  mov     rcx, [r12+8]; this
0x14004035d  test    rcx, rcx
0x140040360  jz      short loc_140040367
0x140040362  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140040367  mov     eax, esi
0x140040369  jmp     loc_140040FD8
0x14004036e  lea     rdx, [r14+48h]
0x140040372  lea     rcx, [rbp+60h+Entry]
0x140040376  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14004037b  mov     rax, [r14+30h]
0x14004037f  mov     rsi, [rax+8]
0x140040383  mov     r14, [rax]
0x140040386  test    rsi, rsi
0x140040389  jz      short loc_14004038F
0x14004038b  lock inc dword ptr [rsi+8]
0x14004038f  mov     rcx, [rbp+60h+Entry]; this
0x140040393  test    rcx, rcx
0x140040396  jz      short loc_14004039D
0x140040398  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14004039d  mov     rax, [r12]
0x1400403a1  xorps   xmm0, xmm0
0x1400403a4  movups  xmmword ptr [rbp+60h+var_58.Length], xmm0
0x1400403a8  xor     edx, edx; struct _UNICODE_STRING *
0x1400403aa  mov     rcx, [rax+10h]
0x1400403ae  movups  xmm0, xmmword ptr [rcx+28h]
0x1400403b2  lea     rcx, [rsp+160h+P+8]; this
0x1400403b7  movdqu  xmmword ptr [rsp+160h+P+8], xmm0
0x1400403bd  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x1400403c2  mov     rcx, [r14+10h]
0x1400403c6  movups  xmm0, xmmword ptr [rcx+28h]
0x1400403ca  lea     rcx, [rbp+60h+var_58]; this
0x1400403ce  movdqu  xmmword ptr [rbp+60h+var_58.Length], xmm0
0x1400403d3  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x1400403d8  xorps   xmm0, xmm0
0x1400403db  mov     [rbp+60h+var_D8], r13w
0x1400403e0  movups  xmmword ptr [rsp+160h+UnicodeString+8], xmm0
0x1400403e5  mov     rax, [r14+8]
0x1400403e9  lea     r9, [rsp+160h+UnicodeString+8]; UnicodeString
0x1400403ee  lea     r8, [rbp+60h+var_58]; Source
0x1400403f2  lea     rdx, [rsp+160h+P+8]; struct _UNICODE_STRING *
0x1400403f7  mov     rcx, [rax]
0x1400403fa  xor     eax, eax
0x1400403fc  mov     [rbp+60h+var_D6], eax
0x1400403ff  mov     [rbp+60h+var_D2], ax
0x140040403  lea     rax, [rbp+60h+Entry]
0x140040407  mov     [rbp+60h+Entry], rcx
0x14004040b  mov     rcx, [rsp+160h+FileHandle]; FileNameInformation
0x140040410  mov     [rsp+160h+Dacl], rax; char *
0x140040415  mov     qword ptr [rsp+160h+var_140], r15; int
0x14004041a  call    ?RewritePath@Utils@UnionFs@@YAJAEAU_FLT_FILE_NAME_INFORMATION@@AEBU_UNICODE_STRING@@1AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEAURewritePathVolumeNameParams@12@@Z; UnionFs::Utils::RewritePath(_FLT_FILE_NAME_INFORMATION &,_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,UnionFs::Utils::RewritePathVolumeNameParams *)
0x14004041f  mov     r14d, eax
0x140040422  test    eax, eax
0x140040424  jns     loc_1400404F4
0x14004042a  lea     rax, aPushRewritingL; "PUSH: Rewriting layer -> scratch"
0x140040431  mov     r8, 46400120095h; struct UnionFs::StackEventTracer *
0x14004043b  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140040442  mov     qword ptr [rsp+160h+var_140], rax; char *
0x140040447  mov     rdx, r15; int
0x14004044a  mov     ecx, r14d; this
0x14004044d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140040452  lea     rcx, [rsp+160h+UnicodeString+8]; UnicodeString
0x140040457  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004045c  test    rsi, rsi
0x14004045f  jz      short loc_140040469
0x140040461  mov     rcx, rsi; this
0x140040464  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140040469  mov     rcx, [rsp+160h+FileHandle]; FileNameInformation
0x14004046e  mov     [rsp+160h+FileHandle], r13
0x140040473  test    rcx, rcx
0x140040476  jz      short loc_140040484
0x140040478  call    cs:__imp_FltReleaseFileNameInformation
0x14004047f  nop     dword ptr [rax+rax+00h]
0x140040484  test    rdi, rdi
0x140040487  jz      short loc_140040498
0x140040489  mov     rcx, rdi; Object
0x14004048c  call    cs:__imp_ObfDereferenceObject
0x140040493  nop     dword ptr [rax+rax+00h]
0x140040498  test    rbx, rbx
0x14004049b  jz      short loc_1400404AC
0x14004049d  mov     rcx, rbx; FileHandle
0x1400404a0  call    cs:__imp_FltClose
0x1400404a7  nop     dword ptr [rax+rax+00h]
0x1400404ac  mov     rcx, [rsp+160h+Object]; Object
0x1400404b1  mov     [rsp+160h+Object], r13
0x1400404b6  test    rcx, rcx
0x1400404b9  jz      short loc_1400404C7
0x1400404bb  call    cs:__imp_ObfDereferenceObject
0x1400404c2  nop     dword ptr [rax+rax+00h]
0x1400404c7  mov     rcx, [rsp+160h+FileHandle+8]; FileHandle
0x1400404cc  test    rcx, rcx
0x1400404cf  jz      short loc_1400404DD
0x1400404d1  call    cs:__imp_FltClose
0x1400404d8  nop     dword ptr [rax+rax+00h]
0x1400404dd  mov     rcx, [r12+8]; this
0x1400404e2  test    rcx, rcx
0x1400404e5  jz      short loc_1400404EC
0x1400404e7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400404ec  mov     eax, r14d
0x1400404ef  jmp     loc_140040FD8
0x1400404f4  mov     rcx, [rbp+60h+arg_38]
0x1400404fb  test    rcx, rcx
0x1400404fe  jz      loc_14004059D
0x140040504  mov     rax, [rcx+8]
0x140040508  lea     r9, [rsp+160h+P+8]
0x14004050d  xorps   xmm0, xmm0
0x140040510  mov     qword ptr [rsp+160h+var_140], r15; int
0x140040515  movups  xmmword ptr [rsp+160h+P+8], xmm0
0x14004051a  lea     r8, [rbp+60h+Source]; Source
0x14004051e  movups  xmm1, xmmword ptr [rax]
0x140040521  mov     rax, [rcx]
0x140040524  lea     rdx, [rbp+60h+var_D0]; struct _UNICODE_STRING *
0x140040528  lea     rcx, [rsp+160h+UnicodeString+8]; this
0x14004052d  movdqu  xmmword ptr [rbp+60h+Source.Length], xmm1
0x140040532  movups  xmm0, xmmword ptr [rax]
0x140040535  movdqu  xmmword ptr [rbp+60h+var_D0], xmm0
0x14004053a  call    ?ReplaceFirstSubstring@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@00AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ReplaceFirstSubstring(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x14004053f  mov     r14d, eax
0x140040542  test    eax, eax
0x140040544  jns     short loc_14004057D
0x140040546  lea     rax, aPushCreatingPo; "PUSH: Creating post-rename path"
0x14004054d  mov     r8, 215001200A7h; struct UnionFs::StackEventTracer *
0x140040557  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x14004055e  mov     qword ptr [rsp+160h+var_140], rax; char *
0x140040563  mov     rdx, r15; int
0x140040566  mov     ecx, r14d; this
0x140040569  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004056e  lea     rcx, [rsp+160h+P+8]; UnicodeString
0x140040573  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140040578  jmp     loc_140040452
0x14004057d  movaps  xmm1, xmmword ptr [rsp+160h+UnicodeString+8]
0x140040582  lea     rcx, [rsp+160h+P+8]; UnicodeString
0x140040587  movaps  xmm0, xmmword ptr [rsp+160h+P+8]
0x14004058c  movdqa  xmmword ptr [rsp+160h+UnicodeString+8], xmm0
0x140040592  movdqa  xmmword ptr [rsp+160h+P+8], xmm1
0x140040598  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004059d  movzx   edx, [rbp+60h+var_D8]
0x1400405a1  lea     r8, [rsp+160h+P]
0x1400405a6  mov     r9, r15
0x1400405a9  mov     [rsp+160h+P], r13
0x1400405ae  lea     rcx, [rsp+160h+UnicodeString+8]; SourceString
0x1400405b3  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400405b8  mov     r13d, eax
0x1400405bb  test    eax, eax
0x1400405bd  jns     loc_1400406C0
0x1400405c3  lea     rax, aPushCreatingSc; "PUSH: Creating scratch path name"
0x1400405ca  mov     r8, 259001200B3h; struct UnionFs::StackEventTracer *
0x1400405d4  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x1400405db  mov     qword ptr [rsp+160h+var_140], rax; char *
0x1400405e0  mov     rdx, r15; int
0x1400405e3  mov     ecx, r13d; this
0x1400405e6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400405eb  xor     r15d, r15d
0x1400405ee  mov     r14, [rsp+160h+P]
0x1400405f3  test    r14, r14
0x1400405f6  jz      short loc_14004061E
0x1400405f8  cmp     [r14+10h], r15b
0x1400405fc  jnz     short loc_140040605
0x1400405fe  xorps   xmm0, xmm0
  ... truncated ...
```
