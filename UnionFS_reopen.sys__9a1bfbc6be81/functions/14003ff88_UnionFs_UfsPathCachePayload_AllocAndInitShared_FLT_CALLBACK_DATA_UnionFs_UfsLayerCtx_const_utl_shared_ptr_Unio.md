# UnionFs::UfsPathCachePayload::AllocAndInitShared(_FLT_CALLBACK_DATA &,UnionFs::UfsLayerCtx const &,utl::shared_ptr<UnionFs::UfsLayerCtx>,UnionFs::UfsPathName const &,ulong,utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,UnionFs::StackEventTracer &,utl::pair<UnionFs::UfsPathName const *,UnionFs::UfsPathName const *> *)

- ea: `0x14003ff88`
- end: `0x140040e64`
- name: `?AllocAndInitShared@UfsPathCachePayload@UnionFs@@SAJAEAU_FLT_CALLBACK_DATA@@AEBVUfsLayerCtx@2@V?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEBVUfsPathName@2@KAEAU?$pair@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@2@@6@AEAVStackEventTracer@2@PEAU?$pair@PEBVUfsPathName@UnionFs@@PEBV12@@6@@Z`
- size: `3804`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA Data@<rcx>, int, PVOID Entry, struct UnionFs::Utils::CallerAccessParams *, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update`

## callers

- `0x140013bb0`
- `0x1400156a8`

## callees

- `0x14000f7fc`
- `0x140027c18`
- `0x140027e58`
- `0x14003f2fc`
- `0x14003f4f8`
- `0x14003f5e4`
- `0x14003fd70`
- `0x14003fe98`
- `0x14003ff88`
- `0x140043a88`
- `0x140044748`
- `0x140056ac4`
- `0x140056afc`
- `0x14006dfb0`
- `0x14006e1a4`
- `0x140073034`
- `0x140076308`
- `0x140076da4`
- `0x14007843c`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400403c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400404af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400405ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400406fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040747`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040775`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040882`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400408cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400408fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ab5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040bb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040bfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040dae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400403c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400404af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400405ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400406fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040747`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040775`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040882`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400408cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400408fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ab5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040bb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040bfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040d80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040dae`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040525`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040688`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040727`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400408ac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040a67`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040bda`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040d60`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040525`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040688`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040727`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400408ac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040a67`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040bda`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140040d60`
- `ntoskrnl!ObfDereferenceObject` at `0x14004004d`
- `ntoskrnl!ObfDereferenceObject` at `0x14004009c`
- `ntoskrnl!ObfDereferenceObject` at `0x14004017a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400401ad`
- `ntoskrnl!ObfDereferenceObject` at `0x1400403fe`
- `ntoskrnl!ObfDereferenceObject` at `0x1400407ae`
- `ntoskrnl!ObfDereferenceObject` at `0x140040933`
- `ntoskrnl!ObfDereferenceObject` at `0x140040962`
- `ntoskrnl!ObfDereferenceObject` at `0x140040aee`
- `ntoskrnl!ObfDereferenceObject` at `0x140040c61`
- `ntoskrnl!ObfDereferenceObject` at `0x140040c90`
- `ntoskrnl!ObfDereferenceObject` at `0x140040de7`
- `ntoskrnl!ObfDereferenceObject` at `0x140040e16`
- `ntoskrnl!ObfDereferenceObject` at `0x14004004d`
- `ntoskrnl!ObfDereferenceObject` at `0x14004009c`
- `ntoskrnl!ObfDereferenceObject` at `0x14004017a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400401ad`
- `ntoskrnl!ObfDereferenceObject` at `0x1400403fe`
- `ntoskrnl!ObfDereferenceObject` at `0x1400407ae`
- `ntoskrnl!ObfDereferenceObject` at `0x140040933`
- `ntoskrnl!ObfDereferenceObject` at `0x140040962`
- `ntoskrnl!ObfDereferenceObject` at `0x140040aee`
- `ntoskrnl!ObfDereferenceObject` at `0x140040c61`
- `ntoskrnl!ObfDereferenceObject` at `0x140040c90`
- `ntoskrnl!ObfDereferenceObject` at `0x140040de7`
- `ntoskrnl!ObfDereferenceObject` at `0x140040e16`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400405d6`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400405d6`
- `FLTMGR!FltClose` at `0x140040063`
- `FLTMGR!FltClose` at `0x1400400b2`
- `FLTMGR!FltClose` at `0x14004018e`
- `FLTMGR!FltClose` at `0x1400401c3`
- `FLTMGR!FltClose` at `0x140040412`
- `FLTMGR!FltClose` at `0x1400407c2`
- `FLTMGR!FltClose` at `0x140040947`
- `FLTMGR!FltClose` at `0x140040978`
- `FLTMGR!FltClose` at `0x140040b02`
- `FLTMGR!FltClose` at `0x140040c75`
- `FLTMGR!FltClose` at `0x140040ca6`
- `FLTMGR!FltClose` at `0x140040dfb`
- `FLTMGR!FltClose` at `0x140040e2c`
- `FLTMGR!FltClose` at `0x140040063`
- `FLTMGR!FltClose` at `0x1400400b2`
- `FLTMGR!FltClose` at `0x14004018e`
- `FLTMGR!FltClose` at `0x1400401c3`
- `FLTMGR!FltClose` at `0x140040412`
- `FLTMGR!FltClose` at `0x1400407c2`
- `FLTMGR!FltClose` at `0x140040947`
- `FLTMGR!FltClose` at `0x140040978`
- `FLTMGR!FltClose` at `0x140040b02`
- `FLTMGR!FltClose` at `0x140040c75`
- `FLTMGR!FltClose` at `0x140040ca6`
- `FLTMGR!FltClose` at `0x140040dfb`
- `FLTMGR!FltClose` at `0x140040e2c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040166`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400403ea`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14004079a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14004091f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040ada`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040c4d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040dd3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040166`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400403ea`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14004079a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14004091f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040ada`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040c4d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040dd3`
- `FLTMGR!FltReleaseContext` at `0x140040845`
- `FLTMGR!FltReleaseContext` at `0x140040a00`
- `FLTMGR!FltReleaseContext` at `0x140040b73`
- `FLTMGR!FltReleaseContext` at `0x140040cfb`
- `FLTMGR!FltReleaseContext` at `0x140040845`
- `FLTMGR!FltReleaseContext` at `0x140040a00`
- `FLTMGR!FltReleaseContext` at `0x140040b73`
- `FLTMGR!FltReleaseContext` at `0x140040cfb`

## string_xrefs

- `0x140040017`: `PUSH: Opening item in layer`
- `0x140040028`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x14004013c`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040281`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x14004030a`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040389`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040480`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x1400404e9`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040571`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x1400406b3`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040828`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x1400409e4`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x140040b4f`: `UnionFs::UfsPathCachePayload::AllocAndInitShared`
- `0x1400402f9`: `PUSH: Creating post-rename path`
- `0x140040378`: `PUSH: Creating scratch path name`
- `0x14004046f`: `PUSH: Getting caller access`
- `0x140040560`: `PUSH: Copying FullPathInLayer`
- `0x1400406a2`: `ORIGIN: Allocating path cache payload node`
- `0x140040b3e`: `ORIGIN: Inserting UserSidString`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::AllocAndInitShared(
        PFLT_CALLBACK_DATA Data,
        __int64 a2,
        struct _LIST_ENTRY **a3,
        LIST_ENTRY *a4,
        int a5,
        struct _UNICODE_STRING *Entry,
        struct UnionFs::Utils::CallerAccessParams *a7,
        __int64 a8)
{
  struct _UNICODE_STRING *v10; // r13
  utl::_RefCountBase *Buffer; // rcx
  struct _LIST_ENTRY *v13; // rax
  struct UnionFs::Utils::CallerAccessParams *v14; // rsi
  struct _FLT_INSTANCE *Flink; // r8
  int v16; // ebx
  PFLT_FILE_NAME_INFORMATION v17; // rcx
  utl::_RefCountBase *v18; // rcx
  PFLT_FILE_NAME_INFORMATION v20; // rcx
  utl::_RefCountBase *v21; // rcx
  PFLT_FILE_NAME_INFORMATION v22; // rdi
  PFLT_FILE_NAME_INFORMATION v23; // rbx
  PVOID *p_Flink; // rcx
  const unsigned __int16 *v25; // r8
  int FileNameInformation; // r15d
  struct _FLT_FILE_NAME_INFORMATION *v27; // rcx
  PFLT_FILE_NAME_INFORMATION v28; // rcx
  utl::_RefCountBase *v29; // rcx
  struct _LIST_ENTRY *v30; // rax
  struct _UNICODE_STRING *v31; // rdx
  const unsigned __int16 *v32; // r8
  __int64 v33; // r10
  void **v34; // rax
  void *v35; // rcx
  struct _UNICODE_STRING *v36; // rdx
  LIST_ENTRY *v37; // rax
  LIST_ENTRY v38; // xmm1
  _OWORD *v39; // rax
  struct _UNICODE_STRING *v40; // rdx
  struct _UNICODE_STRING *v41; // rdx
  struct _UNICODE_STRING v42; // xmm1
  struct _UNICODE_STRING *v43; // rdx
  struct _UNICODE_STRING *v44; // rsi
  struct _FLT_FILE_NAME_INFORMATION *v45; // rcx
  struct _LIST_ENTRY *v46; // rax
  struct _UNICODE_STRING *v47; // rdx
  struct _UNICODE_STRING *v48; // rdx
  struct _UNICODE_STRING *v49; // rsi
  int v50; // eax
  char v51; // r12
  struct _UNICODE_STRING *v52; // rsi
  PVOID v53; // rax
  struct _LIST_ENTRY *v54; // rcx
  UnionFs::UfsPathCachePayloadNP *v55; // r15
  __int64 v56; // rax
  struct _UNICODE_STRING *v57; // r12
  struct _UNICODE_STRING *v58; // rdx
  struct _UNICODE_STRING *v59; // rsi
  struct _UNICODE_STRING *v60; // rdx
  struct _UNICODE_STRING *v61; // rsi
  struct _FLT_FILE_NAME_INFORMATION *v62; // rcx
  PFLT_FILE_NAME_INFORMATION v63; // rcx
  int Set; // eax
  struct _UNICODE_STRING *v65; // rdx
  struct _UNICODE_STRING *v66; // rsi
  struct _UNICODE_STRING *v67; // rdx
  struct _UNICODE_STRING *v68; // rsi
  struct _FLT_FILE_NAME_INFORMATION *v69; // rcx
  PFLT_FILE_NAME_INFORMATION v70; // rcx
  utl::_RefCountBase *v71; // rcx
  int v72; // eax
  struct _UNICODE_STRING *v73; // rdx
  struct _UNICODE_STRING *v74; // rsi
  struct _UNICODE_STRING *v75; // rdx
  struct _UNICODE_STRING *v76; // rsi
  struct _FLT_FILE_NAME_INFORMATION *v77; // rcx
  struct _UNICODE_STRING *v78; // rdx
  struct _UNICODE_STRING *v79; // rdx
  struct _UNICODE_STRING *v80; // rsi
  struct _UNICODE_STRING *v81; // rdx
  struct _UNICODE_STRING *v82; // rsi
  struct _FLT_FILE_NAME_INFORMATION *v83; // rcx
  utl::_RefCountBase *v84; // rcx
  utl::_RefCountBase *v85; // rsi
  struct _UNICODE_STRING *v86; // rsi
  struct _UNICODE_STRING *v87; // rdx
  struct _UNICODE_STRING *v88; // rsi
  struct _FLT_FILE_NAME_INFORMATION *v89; // rcx
  PFLT_FILE_NAME_INFORMATION v90; // rcx
  utl::_RefCountBase *v91; // rcx
  PACL Dacl; // [rsp+30h] [rbp-D8h]
  PACL Dacla; // [rsp+30h] [rbp-D8h]
  PACL Daclb; // [rsp+30h] [rbp-D8h]
  unsigned __int8 v95; // [rsp+40h] [rbp-C8h]
  PFLT_FILE_NAME_INFORMATION FileHandle[3]; // [rsp+48h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v97; // [rsp+68h] [rbp-A0h] BYREF
  struct _UNICODE_STRING UnicodeString_8; // [rsp+78h] [rbp-90h] BYREF
  PVOID v99; // [rsp+88h] [rbp-80h] BYREF
  __int16 v100; // [rsp+90h] [rbp-78h]
  int v101; // [rsp+92h] [rbp-76h]
  __int16 v102; // [rsp+96h] [rbp-72h]
  PVOID P[2]; // [rsp+98h] [rbp-70h] BYREF
  struct _FLT_CALLBACK_DATA v104; // [rsp+A8h] [rbp-60h] BYREF
  PVOID Object; // [rsp+100h] [rbp-8h] BYREF
  UNICODE_STRING v106; // [rsp+108h] [rbp+0h] BYREF

  v10 = Entry;
  Buffer = (utl::_RefCountBase *)Entry->Buffer;
  *(_QWORD *)&Entry->Length = 0;
  v10->Buffer = 0;
  if ( Buffer )
    utl::_RefCountBase::_DecStrong(Buffer);
  v13 = *a3;
  v14 = a7;
  *(_OWORD *)&FileHandle[1] = 0;
  Flink = (struct _FLT_INSTANCE *)v13->Blink->Flink;
  v104.QueueLinks = *a4;
  v16 = UnionFs::Utils::OpenBackingFile(Data, (char *)&v104.QueueLinks, Flink, (PHANDLE)&FileHandle[1], (int)a7);
  if ( v16 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v16,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x22C0012006ALL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Opening item in layer",
      (const char *)Dacl);
    v17 = FileHandle[2];
    FileHandle[2] = 0;
    if ( v17 )
      ObfDereferenceObject(v17);
    if ( FileHandle[1] )
      FltClose(FileHandle[1]);
    v18 = (utl::_RefCountBase *)a3[1];
    if ( v18 )
      utl::_RefCountBase::_DecStrong(v18);
    return (unsigned int)v16;
  }
  if ( v16 == 260 )
  {
    v20 = FileHandle[2];
    FileHandle[2] = 0;
    if ( v20 )
      ObfDereferenceObject(v20);
    if ( FileHandle[1] )
      FltClose(FileHandle[1]);
    v21 = (utl::_RefCountBase *)a3[1];
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
    return 260;
  }
  v22 = FileHandle[2];
  v23 = FileHandle[1];
  p_Flink = (PVOID *)&(*a3)->Blink->Flink;
  *(PFLT_FILE_NAME_INFORMATION *)&v104.RequestorMode = FileHandle[1];
  Object = FileHandle[2];
  v104.QueueLinks.Flink = 0;
  v104.QueueContext[0] = *p_Flink;
  memset(FileHandle, 0, sizeof(FileHandle));
  v104.QueueLinks.Blink = (struct _LIST_ENTRY *)Object;
  FileNameInformation = UnionFs::Utils::GetFileNameInformation(&v104.QueueLinks, 1025, FileHandle, v14);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x4600012007FLL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Querying normalized layer name",
      (const char *)Dacl);
LABEL_21:
    v27 = FileHandle[0];
    FileHandle[0] = 0;
    if ( v27 )
      FltReleaseFileNameInformation(v27);
    if ( v22 )
      ObfDereferenceObject(v22);
    if ( v23 )
      FltClose(v23);
    v28 = FileHandle[2];
    FileHandle[2] = 0;
LABEL_28:
    if ( v28 )
      ObfDereferenceObject(v28);
    if ( FileHandle[1] )
      FltClose(FileHandle[1]);
    v29 = (utl::_RefCountBase *)a3[1];
    if ( v29 )
      utl::_RefCountBase::_DecStrong(v29);
    return (unsigned int)FileNameInformation;
  }
  v30 = *a3;
  v106 = 0;
  v97 = *(struct _UNICODE_STRING *)&v30[1].Flink[2].Blink;
  UnionFs::Utils::StripTrailingBackslashFromPath((UnionFs::Utils *)&v97, 0, v25);
  v106 = *(UNICODE_STRING *)(*(_QWORD *)(a2 + 16) + 40LL);
  UnionFs::Utils::StripTrailingBackslashFromPath((UnionFs::Utils *)&v106, v31, v32);
  v34 = *(void ***)(v33 + 8);
  UnicodeString_8 = 0;
  v35 = *v34;
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v99 = v35;
  FileNameInformation = UnionFs::Utils::RewritePath(
                          FileHandle[0],
                          &v97,
                          &v106,
                          &UnicodeString_8,
                          (int)v14,
                          (__int64)&v99);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x46400120094LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Rewriting layer -> scratch",
      (const char *)Dacla);
LABEL_37:
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v36);
    goto LABEL_21;
  }
  if ( a8 )
  {
    v37 = *(LIST_ENTRY **)(a8 + 8);
    v97 = 0;
    v38 = *v37;
    v39 = *(_OWORD **)a8;
    v104.QueueLinks = v38;
    *(_OWORD *)P = *v39;
    FileNameInformation = UnionFs::Utils::ReplaceFirstSubstring(
                            (UnionFs::Rtl *)&UnicodeString_8,
                            (struct _UNICODE_STRING *)P,
                            (PCUNICODE_STRING)&v104.QueueLinks,
                            (int)v14);
    if ( FileNameInformation < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)FileNameInformation,
        (int)v14,
        (struct UnionFs::StackEventTracer *)0x215001200A6LL,
        (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
        "PUSH: Creating post-rename path",
        (const char *)Dacla);
      FsFltWil::Details::FreeUnicodeString(&v97, v41);
      goto LABEL_37;
    }
    v42 = UnicodeString_8;
    UnicodeString_8 = v97;
    v97 = v42;
    FsFltWil::Details::FreeUnicodeString(&v97, v40);
  }
  P[0] = 0;
  FileNameInformation = UnionFs::UfsPathName::AllocAndInit(&UnicodeString_8);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x259001200B2LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Creating scratch path name",
      (const char *)Dacla);
LABEL_44:
    v44 = (struct _UNICODE_STRING *)P[0];
    if ( P[0] )
    {
      if ( !*((_BYTE *)P[0] + 16) )
        *(_OWORD *)P[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v44, v43);
      ExFreePoolWithTag(v44, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v43);
    v45 = FileHandle[0];
    FileHandle[0] = 0;
    if ( v45 )
      FltReleaseFileNameInformation(v45);
    if ( v22 )
      ObfDereferenceObject(v22);
    if ( v23 )
      FltClose(v23);
    v28 = FileHandle[2];
    FileHandle[2] = 0;
    goto LABEL_28;
  }
  v46 = *a3;
  memset(&v104, 0, 24);
  *(LIST_ENTRY *)&v104.IoStatus.Status = *a4;
  FileNameInformation = UnionFs::Utils::GetCallerAccessForLayerFile(
                          (UnionFs::Utils *)v46->Blink->Flink,
                          (const struct _FLT_INSTANCE *)v22,
                          (const struct _FILE_OBJECT *)Data,
                          &v104,
                          v14,
                          (struct UnionFs::StackEventTracer *)Dacla);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x239001200BFLL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Getting caller access",
      (const char *)Daclb);
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v104.Thread, v47);
LABEL_57:
    if ( *(_QWORD *)&v104.Flags )
      ExFreePoolWithTag(*(PVOID *)&v104.Flags, 0);
    goto LABEL_44;
  }
  Entry = 0;
  FileNameInformation = UnionFs::UfsPathCachePayloadNP::AllocAndInit(&Entry, v14);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x11A001200C6LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Creating NP ctx",
      (const char *)Daclb);
LABEL_61:
    v49 = Entry;
    if ( Entry )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP((UnionFs::UfsPathCachePayloadNP *)Entry);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v49);
    }
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v104.Thread, v48);
    goto LABEL_57;
  }
  v99 = 0;
  v50 = UnionFs::UfsPathName::Copy((PCUNICODE_STRING)a4);
  v51 = 0;
  FileNameInformation = v50;
  if ( v50 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v50,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x17B001200CCLL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Copying FullPathInLayer",
      (const char *)Daclb);
    v52 = (struct _UNICODE_STRING *)v99;
    if ( v99 )
    {
      if ( !*((_BYTE *)v99 + 16) )
        *(_OWORD *)v99 = 0;
      FsFltWil::Details::FreeUnicodeString(v52, v48);
      ExFreePoolWithTag(v52, 0);
    }
    goto LABEL_61;
  }
  v97 = 0;
  v53 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1664));
  if ( v53 )
  {
    v104.QueueLinks.Flink = *a3;
    v54 = a3[1];
    v104.QueueLinks.Blink = v54;
    if ( v54 )
      _InterlockedIncrement((volatile signed __int32 *)&v54->Blink);
    v55 = 0;
    v56 = UnionFs::UfsPathCachePayload::UfsPathCachePayload(
            (int)v53,
            (int)&Entry,
            (int)&v104.QueueLinks,
            (int)&v99,
            (unsigned __int8)&v104.RequestorMode,
            (PACL)&Object,
            (__int64)&v104,
            v95);
    v23 = *(PFLT_FILE_NAME_INFORMATION *)&v104.RequestorMode;
    v51 = 1;
    v22 = (PFLT_FILE_NAME_INFORMATION)Object;
  }
  else
  {
    v55 = (UnionFs::UfsPathCachePayloadNP *)Entry;
    v56 = 0;
  }
  utl::shared_ptr<UnionFs::UfsPathCachePayload>::reset<UnionFs::UfsPathCachePayload,0>(&v97, v56);
  if ( (v51 & 1) != 0 )
  {
    v57 = Entry;
    if ( Entry )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP((UnionFs::UfsPathCachePayloadNP *)Entry);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v57);
    }
  }
  if ( !*(_QWORD *)&v97.Length )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x1FA001200DBLL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "ORIGIN: Allocating path cache payload node",
      (const char *)Daclb);
    if ( v97.Buffer )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97.Buffer);
    v59 = (struct _UNICODE_STRING *)v99;
    if ( v99 )
    {
      if ( !*((_BYTE *)v99 + 16) )
        *(_OWORD *)v99 = 0;
      FsFltWil::Details::FreeUnicodeString(v59, v58);
      ExFreePoolWithTag(v59, 0);
    }
    if ( v55 )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v55);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v55);
    }
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v104.Thread, v58);
    if ( *(_QWORD *)&v104.Flags )
      ExFreePoolWithTag(*(PVOID *)&v104.Flags, 0);
    v61 = (struct _UNICODE_STRING *)P[0];
    if ( P[0] )
    {
      if ( !*((_BYTE *)P[0] + 16) )
        *(_OWORD *)P[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v61, v60);
      ExFreePoolWithTag(v61, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v60);
    v62 = FileHandle[0];
    FileHandle[0] = 0;
    if ( v62 )
      FltReleaseFileNameInformation(v62);
    if ( v22 )
      ObfDereferenceObject(v22);
    if ( v23 )
      FltClose(v23);
    v63 = FileHandle[2];
    FileHandle[2] = 0;
LABEL_172:
    if ( v63 )
      ObfDereferenceObject(v63);
    if ( FileHandle[1] )
      FltClose(FileHandle[1]);
    v84 = (utl::_RefCountBase *)a3[1];
    if ( v84 )
      utl::_RefCountBase::_DecStrong(v84);
    return 3221225626LL;
  }
  Set = UnionFs::UfsFileCtx::FltGetSet(
          (PFLT_INSTANCE)(*a3)->Blink->Flink,
          *(PFILE_OBJECT *)(*(_QWORD *)&v97.Length + 64LL),
          a5);
  LODWORD(Entry) = Set;
  if ( Set < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)Set,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x4A0001200E9LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Get/alloc backing file context",
      (const char *)Daclb);
    if ( v97.Buffer )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97.Buffer);
    v66 = (struct _UNICODE_STRING *)v99;
    if ( v99 )
    {
      if ( !*((_BYTE *)v99 + 16) )
        *(_OWORD *)v99 = 0;
      FsFltWil::Details::FreeUnicodeString(v66, v65);
      ExFreePoolWithTag(v66, 0);
    }
    if ( v55 )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v55);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v55);
    }
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v104.Thread, v65);
    if ( *(_QWORD *)&v104.Flags )
      ExFreePoolWithTag(*(PVOID *)&v104.Flags, 0);
    v68 = (struct _UNICODE_STRING *)P[0];
    if ( P[0] )
    {
      if ( !*((_BYTE *)P[0] + 16) )
        *(_OWORD *)P[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v68, v67);
      ExFreePoolWithTag(v68, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v67);
    v69 = FileHandle[0];
    FileHandle[0] = 0;
    if ( v69 )
      FltReleaseFileNameInformation(v69);
    if ( v22 )
      ObfDereferenceObject(v22);
    if ( v23 )
      FltClose(v23);
    v70 = FileHandle[2];
    FileHandle[2] = 0;
LABEL_121:
    if ( v70 )
      ObfDereferenceObject(v70);
    if ( FileHandle[1] )
      FltClose(FileHandle[1]);
    v71 = (utl::_RefCountBase *)a3[1];
    if ( v71 )
      utl::_RefCountBase::_DecStrong(v71);
    return (unsigned int)Entry;
  }
  v72 = UnionFs::UfsStreamCtx::FltGetSet(
          (PFLT_INSTANCE)(*a3)->Blink->Flink,
          *(PFILE_OBJECT *)(*(_QWORD *)&v97.Length + 64LL),
          (int)v14);
  LODWORD(Entry) = v72;
  if ( v72 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v72,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x4A1001200F2LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "PUSH: Get/alloc backing stream context",
      (const char *)Daclb);
    if ( v97.Buffer )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97.Buffer);
    v74 = (struct _UNICODE_STRING *)v99;
    if ( v99 )
    {
      if ( !*((_BYTE *)v99 + 16) )
        *(_OWORD *)v99 = 0;
      FsFltWil::Details::FreeUnicodeString(v74, v73);
      ExFreePoolWithTag(v74, 0);
    }
    if ( v55 )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v55);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v55);
    }
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v104.Thread, v73);
    if ( *(_QWORD *)&v104.Flags )
      ExFreePoolWithTag(*(PVOID *)&v104.Flags, 0);
    v76 = (struct _UNICODE_STRING *)P[0];
    if ( P[0] )
    {
      if ( !*((_BYTE *)P[0] + 16) )
        *(_OWORD *)P[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v76, v75);
      ExFreePoolWithTag(v76, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v75);
    v77 = FileHandle[0];
    FileHandle[0] = 0;
    if ( v77 )
      FltReleaseFileNameInformation(v77);
    if ( v22 )
      ObfDereferenceObject(v22);
    if ( v23 )
      FltClose(v23);
    v70 = FileHandle[2];
    FileHandle[2] = 0;
    goto LABEL_121;
  }
  utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::_InsertImpl<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>(
    *(_QWORD *)&v97.Length + 96LL,
    &v104.QueueLinks,
    &v104.Thread);
  if ( !v104.QueueLinks.Flink )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)v14,
      (struct UnionFs::StackEventTracer *)0x23A001200FFLL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitShared",
      "ORIGIN: Inserting UserSidString",
      (const char *)Daclb);
    if ( v97.Buffer )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97.Buffer);
    v80 = (struct _UNICODE_STRING *)v99;
    if ( v99 )
    {
      if ( !*((_BYTE *)v99 + 16) )
        *(_OWORD *)v99 = 0;
      FsFltWil::Details::FreeUnicodeString(v80, v79);
      ExFreePoolWithTag(v80, 0);
    }
    if ( v55 )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v55);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v55);
    }
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v104.Thread, v79);
    if ( *(_QWORD *)&v104.Flags )
      ExFreePoolWithTag(*(PVOID *)&v104.Flags, 0);
    v82 = (struct _UNICODE_STRING *)P[0];
    if ( P[0] )
    {
      if ( !*((_BYTE *)P[0] + 16) )
        *(_OWORD *)P[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v82, v81);
      ExFreePoolWithTag(v82, 0);
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v81);
    v83 = FileHandle[0];
    FileHandle[0] = 0;
    if ( v83 )
      FltReleaseFileNameInformation(v83);
    if ( v22 )
      ObfDereferenceObject(v22);
    if ( v23 )
      FltClose(v23);
    v63 = FileHandle[2];
    FileHandle[2] = 0;
    goto LABEL_172;
  }
  v85 = (utl::_RefCountBase *)v10->Buffer;
  *v10 = v97;
  Entry = *(struct _UNICODE_STRING **)&v10[1].Length;
  *(PVOID *)&v10[1].Length = P[0];
  if ( v85 )
    utl::_RefCountBase::_DecStrong(v85);
  v86 = (struct _UNICODE_STRING *)v99;
  if ( v99 )
  {
    if ( !*((_BYTE *)v99 + 16) )
      *(_OWORD *)v99 = 0;
    FsFltWil::Details::FreeUnicodeString(v86, v78);
    ExFreePoolWithTag(v86, 0);
  }
  if ( v55 )
  {
    UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v55);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v55);
  }
  FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v104.Thread, v78);
  if ( *(_QWORD *)&v104.Flags )
    ExFreePoolWithTag(*(PVOID *)&v104.Flags, 0);
  v88 = Entry;
  if ( Entry )
  {
    if ( !LOBYTE(Entry[1].Length) )
      *Entry = 0;
    FsFltWil::Details::FreeUnicodeString(v88, v87);
    ExFreePoolWithTag(v88, 0);
  }
  FsFltWil::Details::FreeUnicodeString(&UnicodeString_8, v87);
  v89 = FileHandle[0];
  FileHandle[0] = 0;
  if ( v89 )
    FltReleaseFileNameInformation(v89);
  if ( v22 )
    ObfDereferenceObject(v22);
  if ( v23 )
    FltClose(v23);
  v90 = FileHandle[2];
  FileHandle[2] = 0;
  if ( v90 )
    ObfDereferenceObject(v90);
  if ( FileHandle[1] )
    FltClose(FileHandle[1]);
  v91 = (utl::_RefCountBase *)a3[1];
  if ( v91 )
    utl::_RefCountBase::_DecStrong(v91);
  return 0;
}

```

## disassembly

```asm
0x14003ff88  mov     rax, rsp
0x14003ff8b  mov     [rax+20h], rbx
0x14003ff8f  mov     [rax+10h], rdx
0x14003ff93  mov     [rax+8], rcx
0x14003ff97  push    rbp
0x14003ff98  push    rsi
0x14003ff99  push    rdi
0x14003ff9a  push    r12
0x14003ff9c  push    r13
0x14003ff9e  push    r14
0x14003ffa0  push    r15
0x14003ffa2  lea     rbp, [rax-48h]
0x14003ffa6  sub     rsp, 110h
0x14003ffad  xor     r15d, r15d
0x14003ffb0  mov     rbx, rcx
0x14003ffb3  mov     dword ptr [rbp+40h+Context], r15d
0x14003ffb7  mov     r12, r9
0x14003ffba  mov     r13, [rbp+40h+Entry]
0x14003ffbe  mov     r14, r8
0x14003ffc1  mov     rcx, [r13+8]; this
0x14003ffc5  mov     [r13+0], r15
0x14003ffc9  mov     [r13+8], r15
0x14003ffcd  test    rcx, rcx
0x14003ffd0  jz      short loc_14003FFD7
0x14003ffd2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003ffd7  mov     rax, [r14]
0x14003ffda  lea     r9, [rsp+140h+FileHandle+8]; FileHandle
0x14003ffdf  mov     rsi, [rbp+40h+arg_30]
0x14003ffe6  lea     rdx, [rbp+40h+Source]; char *
0x14003ffea  xorps   xmm0, xmm0
0x14003ffed  mov     [rsp+140h+var_120], rsi; int
0x14003fff2  movdqu  xmmword ptr [rsp+140h+FileHandle+8], xmm0
0x14003fff8  mov     rcx, [rax+8]
0x14003fffc  movups  xmm0, xmmword ptr [r12]
0x140040001  mov     r8, [rcx]; Instance
0x140040004  mov     rcx, rbx; Data
0x140040007  movdqu  xmmword ptr [rbp+40h+Source.Length], xmm0
0x14004000c  call    ?OpenBackingFile@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@utl@@AEAVStackEventTracer@2@_N@Z; UnionFs::Utils::OpenBackingFile(_FLT_CALLBACK_DATA &,_UNICODE_STRING const &,_FLT_INSTANCE const &,utl::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>> &,UnionFs::StackEventTracer &,bool)
0x140040011  mov     ebx, eax
0x140040013  test    eax, eax
0x140040015  jns     short loc_140040084
0x140040017  lea     rax, aPushOpeningIte; "PUSH: Opening item in layer"
0x14004001e  mov     r8, 22C0012006Ah; struct UnionFs::StackEventTracer *
0x140040028  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x14004002f  mov     [rsp+140h+var_120], rax; char *
0x140040034  mov     rdx, rsi; int
0x140040037  mov     ecx, ebx; this
0x140040039  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004003e  mov     rcx, qword ptr [rsp+140h+FileHandle+10h]; Object
0x140040043  mov     qword ptr [rsp+140h+FileHandle+10h], r15
0x140040048  test    rcx, rcx
0x14004004b  jz      short loc_140040059
0x14004004d  call    cs:__imp_ObfDereferenceObject
0x140040054  nop     dword ptr [rax+rax+00h]
0x140040059  mov     rcx, qword ptr [rsp+140h+FileHandle+8]; FileHandle
0x14004005e  test    rcx, rcx
0x140040061  jz      short loc_14004006F
0x140040063  call    cs:__imp_FltClose
0x14004006a  nop     dword ptr [rax+rax+00h]
0x14004006f  mov     rcx, [r14+8]; this
0x140040073  test    rcx, rcx
0x140040076  jz      short loc_14004007D
0x140040078  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004007d  mov     eax, ebx
0x14004007f  jmp     loc_140040E48
0x140040084  mov     edi, 104h
0x140040089  cmp     ebx, edi
0x14004008b  jnz     short loc_1400400D3
0x14004008d  mov     rcx, qword ptr [rsp+140h+FileHandle+10h]; Object
0x140040092  mov     qword ptr [rsp+140h+FileHandle+10h], r15
0x140040097  test    rcx, rcx
0x14004009a  jz      short loc_1400400A8
0x14004009c  call    cs:__imp_ObfDereferenceObject
0x1400400a3  nop     dword ptr [rax+rax+00h]
0x1400400a8  mov     rcx, qword ptr [rsp+140h+FileHandle+8]; FileHandle
0x1400400ad  test    rcx, rcx
0x1400400b0  jz      short loc_1400400BE
0x1400400b2  call    cs:__imp_FltClose
0x1400400b9  nop     dword ptr [rax+rax+00h]
0x1400400be  mov     rcx, [r14+8]; this
0x1400400c2  test    rcx, rcx
0x1400400c5  jz      short loc_1400400CC
0x1400400c7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400400cc  mov     eax, edi
0x1400400ce  jmp     loc_140040E48
0x1400400d3  mov     rdi, qword ptr [rsp+140h+FileHandle+10h]
0x1400400d8  lea     r8, [rsp+140h+FileHandle]
0x1400400dd  mov     rax, [r14]
0x1400400e0  mov     r9, rsi
0x1400400e3  mov     rbx, qword ptr [rsp+140h+FileHandle+8]
0x1400400e8  mov     edx, 401h
0x1400400ed  mov     qword ptr [rsp+140h+FileHandle+8], r15
0x1400400f2  mov     qword ptr [rsp+140h+FileHandle+10h], r15
0x1400400f7  mov     rcx, [rax+8]
0x1400400fb  mov     [rbp+40h+var_50], rbx
0x1400400ff  mov     [rbp+40h+Object], rdi
0x140040103  mov     qword ptr [rbp+40h+Source.Length], r15
0x140040107  mov     rax, [rcx]
0x14004010a  lea     rcx, [rbp+40h+Source]
0x14004010e  mov     [rbp+40h+var_60], rax
0x140040112  mov     qword ptr [rsp+140h+FileHandle], r15
0x140040117  mov     [rbp+40h+Source.Buffer], rdi
0x14004011b  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x140040120  mov     r15d, eax
0x140040123  test    eax, eax
0x140040125  jns     loc_1400401E5
0x14004012b  lea     rax, aPushQueryingNo; "PUSH: Querying normalized layer name"
0x140040132  mov     r8, 4600012007Fh; struct UnionFs::StackEventTracer *
0x14004013c  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140040143  mov     [rsp+140h+var_120], rax; char *
0x140040148  mov     rdx, rsi; int
0x14004014b  mov     ecx, r15d; this
0x14004014e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140040153  mov     rcx, qword ptr [rsp+140h+FileHandle]; FileNameInformation
0x140040158  mov     qword ptr [rsp+140h+FileHandle], 0
0x140040161  test    rcx, rcx
0x140040164  jz      short loc_140040172
0x140040166  call    cs:__imp_FltReleaseFileNameInformation
0x14004016d  nop     dword ptr [rax+rax+00h]
0x140040172  test    rdi, rdi
0x140040175  jz      short loc_140040186
0x140040177  mov     rcx, rdi; Object
0x14004017a  call    cs:__imp_ObfDereferenceObject
0x140040181  nop     dword ptr [rax+rax+00h]
0x140040186  test    rbx, rbx
0x140040189  jz      short loc_14004019A
0x14004018b  mov     rcx, rbx; FileHandle
0x14004018e  call    cs:__imp_FltClose
0x140040195  nop     dword ptr [rax+rax+00h]
0x14004019a  mov     rcx, qword ptr [rsp+140h+FileHandle+10h]; Object
0x14004019f  mov     qword ptr [rsp+140h+FileHandle+10h], 0
0x1400401a8  test    rcx, rcx
0x1400401ab  jz      short loc_1400401B9
0x1400401ad  call    cs:__imp_ObfDereferenceObject
0x1400401b4  nop     dword ptr [rax+rax+00h]
0x1400401b9  mov     rcx, qword ptr [rsp+140h+FileHandle+8]; FileHandle
0x1400401be  test    rcx, rcx
0x1400401c1  jz      short loc_1400401CF
0x1400401c3  call    cs:__imp_FltClose
0x1400401ca  nop     dword ptr [rax+rax+00h]
0x1400401cf  mov     rcx, [r14+8]; this
0x1400401d3  test    rcx, rcx
0x1400401d6  jz      short loc_1400401DD
0x1400401d8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400401dd  mov     eax, r15d
0x1400401e0  jmp     loc_140040E48
0x1400401e5  mov     rax, [r14]
0x1400401e8  xorps   xmm0, xmm0
0x1400401eb  movups  xmmword ptr [rbp+40h+var_40.Length], xmm0
0x1400401ef  xor     edx, edx; struct _UNICODE_STRING *
0x1400401f1  mov     rcx, [rax+10h]
0x1400401f5  movups  xmm0, xmmword ptr [rcx+28h]
0x1400401f9  lea     rcx, [rsp+140h+var_E8.Buffer]; this
0x1400401fe  movdqu  xmmword ptr [rsp+140h+var_E8.Buffer], xmm0
0x140040204  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x140040209  mov     r10, [rbp+40h+arg_8]
0x14004020d  mov     rcx, [r10+10h]
0x140040211  movups  xmm0, xmmword ptr [rcx+28h]
0x140040215  lea     rcx, [rbp+40h+var_40]; this
0x140040219  movdqu  xmmword ptr [rbp+40h+var_40.Length], xmm0
0x14004021e  call    ?StripTrailingBackslashFromPath@Utils@UnionFs@@YAXAEAU_UNICODE_STRING@@PEBG@Z; UnionFs::Utils::StripTrailingBackslashFromPath(_UNICODE_STRING &,ushort const *)
0x140040223  mov     rax, [r10+8]
0x140040227  lea     r9, [rsp+140h+UnicodeString+8]; UnicodeString
0x14004022c  xorps   xmm0, xmm0
0x14004022f  lea     r8, [rbp+40h+var_40]; Source
0x140040233  movups  xmmword ptr [rsp+140h+UnicodeString+8], xmm0
0x140040238  lea     rdx, [rsp+140h+var_E8.Buffer]; struct _UNICODE_STRING *
0x14004023d  mov     rcx, [rax]
0x140040240  xor     eax, eax
0x140040242  mov     [rbp+40h+var_B8], ax
0x140040246  mov     [rbp+40h+var_B6], eax
0x140040249  mov     [rbp+40h+var_B2], ax
0x14004024d  lea     rax, [rbp+40h+var_C0]
0x140040251  mov     [rbp+40h+var_C0], rcx
0x140040255  mov     rcx, qword ptr [rsp+140h+FileHandle]; FileNameInformation
0x14004025a  mov     [rsp+140h+Dacl], rax; char *
0x14004025f  mov     [rsp+140h+var_120], rsi; int
0x140040264  call    ?RewritePath@Utils@UnionFs@@YAJAEAU_FLT_FILE_NAME_INFORMATION@@AEBU_UNICODE_STRING@@1AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEAURewritePathVolumeNameParams@12@@Z; UnionFs::Utils::RewritePath(_FLT_FILE_NAME_INFORMATION &,_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,UnionFs::Utils::RewritePathVolumeNameParams *)
0x140040269  mov     r15d, eax
0x14004026c  test    eax, eax
0x14004026e  jns     short loc_1400402A7
0x140040270  lea     rax, aPushRewritingL; "PUSH: Rewriting layer -> scratch"
0x140040277  mov     r8, 46400120094h; struct UnionFs::StackEventTracer *
0x140040281  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140040288  mov     [rsp+140h+var_120], rax; char *
0x14004028d  mov     rdx, rsi; int
0x140040290  mov     ecx, r15d; this
0x140040293  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140040298  lea     rcx, [rsp+140h+UnicodeString+8]; UnicodeString
0x14004029d  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400402a2  jmp     loc_140040153
0x1400402a7  mov     rcx, [rbp+40h+arg_38]
0x1400402ae  test    rcx, rcx
0x1400402b1  jz      loc_140040350
0x1400402b7  mov     rax, [rcx+8]
0x1400402bb  lea     r9, [rsp+140h+var_E8.Buffer]
0x1400402c0  xorps   xmm0, xmm0
0x1400402c3  mov     [rsp+140h+var_120], rsi; int
0x1400402c8  movups  xmmword ptr [rsp+140h+var_E8.Buffer], xmm0
0x1400402cd  lea     r8, [rbp+40h+Source]; Source
0x1400402d1  movups  xmm1, xmmword ptr [rax]
0x1400402d4  mov     rax, [rcx]
0x1400402d7  lea     rdx, [rbp+40h+P]; struct _UNICODE_STRING *
0x1400402db  lea     rcx, [rsp+140h+UnicodeString+8]; this
0x1400402e0  movdqu  xmmword ptr [rbp+40h+Source.Length], xmm1
0x1400402e5  movups  xmm0, xmmword ptr [rax]
0x1400402e8  movdqu  xmmword ptr [rbp+40h+P], xmm0
0x1400402ed  call    ?ReplaceFirstSubstring@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@00AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ReplaceFirstSubstring(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x1400402f2  mov     r15d, eax
0x1400402f5  test    eax, eax
0x1400402f7  jns     short loc_140040330
0x1400402f9  lea     rax, aPushCreatingPo; "PUSH: Creating post-rename path"
0x140040300  mov     r8, 215001200A6h; struct UnionFs::StackEventTracer *
0x14004030a  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140040311  mov     [rsp+140h+var_120], rax; char *
0x140040316  mov     rdx, rsi; int
0x140040319  mov     ecx, r15d; this
0x14004031c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140040321  lea     rcx, [rsp+140h+var_E8.Buffer]; UnicodeString
0x140040326  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004032b  jmp     loc_140040298
0x140040330  movaps  xmm1, xmmword ptr [rsp+140h+UnicodeString+8]
0x140040335  lea     rcx, [rsp+140h+var_E8.Buffer]; UnicodeString
0x14004033a  movaps  xmm0, xmmword ptr [rsp+140h+var_E8.Buffer]
0x14004033f  movdqa  xmmword ptr [rsp+140h+UnicodeString+8], xmm0
0x140040345  movdqa  xmmword ptr [rsp+140h+var_E8.Buffer], xmm1
0x14004034b  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140040350  movzx   edx, [rbp+40h+var_B8]
0x140040354  lea     r8, [rbp+40h+P]
0x140040358  mov     r9, rsi
0x14004035b  mov     [rbp+40h+P], 0
0x140040363  lea     rcx, [rsp+140h+UnicodeString+8]; SourceString
0x140040368  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14004036d  mov     r15d, eax
0x140040370  test    eax, eax
0x140040372  jns     loc_14004042D
0x140040378  lea     rax, aPushCreatingSc; "PUSH: Creating scratch path name"
0x14004037f  mov     r8, 259001200B2h; struct UnionFs::StackEventTracer *
0x140040389  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140040390  mov     [rsp+140h+var_120], rax; char *
0x140040395  mov     rdx, rsi; int
0x140040398  mov     ecx, r15d; this
0x14004039b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400403a0  xor     r12d, r12d
0x1400403a3  mov     rsi, [rbp+40h+P]
0x1400403a7  test    rsi, rsi
0x1400403aa  jz      short loc_1400403D1
0x1400403ac  cmp     [rsi+10h], r12b
0x1400403b0  jnz     short loc_1400403B8
0x1400403b2  xorps   xmm0, xmm0
0x1400403b5  movups  xmmword ptr [rsi], xmm0
0x1400403b8  mov     rcx, rsi; UnicodeString
0x1400403bb  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400403c0  xor     edx, edx; Tag
0x1400403c2  mov     rcx, rsi; P
0x1400403c5  call    cs:__imp_ExFreePoolWithTag
0x1400403cc  nop     dword ptr [rax+rax+00h]
0x1400403d1  lea     rcx, [rsp+140h+UnicodeString+8]; UnicodeString
0x1400403d6  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400403db  mov     rcx, qword ptr [rsp+140h+FileHandle]; FileNameInformation
0x1400403e0  mov     qword ptr [rsp+140h+FileHandle], r12
0x1400403e5  test    rcx, rcx
0x1400403e8  jz      short loc_1400403F6
0x1400403ea  call    cs:__imp_FltReleaseFileNameInformation
0x1400403f1  nop     dword ptr [rax+rax+00h]
0x1400403f6  test    rdi, rdi
0x1400403f9  jz      short loc_14004040A
0x1400403fb  mov     rcx, rdi; Object
0x1400403fe  call    cs:__imp_ObfDereferenceObject
0x140040405  nop     dword ptr [rax+rax+00h]
0x14004040a  test    rbx, rbx
0x14004040d  jz      short loc_14004041E
0x14004040f  mov     rcx, rbx; FileHandle
0x140040412  call    cs:__imp_FltClose
0x140040419  nop     dword ptr [rax+rax+00h]
0x14004041e  mov     rcx, qword ptr [rsp+140h+FileHandle+10h]
0x140040423  mov     qword ptr [rsp+140h+FileHandle+10h], r12
0x140040428  jmp     loc_1400401A8
0x14004042d  mov     rax, [r14]
0x140040430  lea     r9, [rbp+40h+var_A0]; struct _FLT_CALLBACK_DATA *
0x140040434  mov     r8, [rbp+40h+arg_0]; struct _FILE_OBJECT *
0x140040438  xorps   xmm0, xmm0
0x14004043b  movups  xmmword ptr [rbp+40h+var_98.Length], xmm0
0x14004043f  mov     [rbp+40h+var_A0], 0
0x140040447  mov     rdx, rdi; struct _FLT_INSTANCE *
0x14004044a  movups  xmm0, xmmword ptr [r12]
0x14004044f  mov     [rsp+140h+var_120], rsi; struct UnionFs::Utils::CallerAccessParams *
0x140040454  movdqu  [rbp+40h+var_88], xmm0
0x140040459  mov     rcx, [rax+8]
0x14004045d  mov     rcx, [rcx]; this
0x140040460  call    ?GetCallerAccessForLayerFile@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAUCallerAccessParams@12@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetCallerAccessForLayerFile(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_CALLBACK_DATA &,UnionFs::Utils::CallerAccessParams &,UnionFs::StackEventTracer &)
0x140040465  mov     r15d, eax
0x140040468  mov     rdx, rsi; int
0x14004046b  test    eax, eax
0x14004046d  jns     short loc_1400404C0
0x14004046f  lea     rax, aPushGettingCal; "PUSH: Getting caller access"
0x140040476  mov     r8, 239001200BFh; struct UnionFs::StackEventTracer *
0x140040480  lea     r9, aUnionfsUfspath_46; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140040487  mov     [rsp+140h+var_120], rax; char *
0x14004048c  mov     ecx, r15d; this
  ... truncated ...
```
