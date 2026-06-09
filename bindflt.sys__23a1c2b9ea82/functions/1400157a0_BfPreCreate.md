# BfPreCreate

- ea: `0x1400157a0`
- end: `0x1400172e0`
- name: `BfPreCreate`
- size: `6976`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001010`
- `0x140001348`
- `0x140001990`
- `0x140001fd0`
- `0x1400023d0`
- `0x140002904`
- `0x140002e0c`
- `0x140003304`
- `0x1400036f0`
- `0x140006380`
- `0x14000f9c4`
- `0x140014ccc`
- `0x140014e9c`
- `0x1400150f0`
- `0x1400154b0`
- `0x1400157a0`
- `0x1400172f0`
- `0x14001732c`
- `0x140017360`
- `0x140017920`
- `0x140017bf0`
- `0x14002184c`

## import_xrefs

- `ntoskrnl!IoSetShadowFileInformation` at `0x140015bed`
- `ntoskrnl!IoSetShadowFileInformation` at `0x140015bed`
- `ntoskrnl!PsGetHostSilo` at `0x1400160f3`
- `ntoskrnl!PsGetHostSilo` at `0x140016427`
- `ntoskrnl!PsGetHostSilo` at `0x1400160f3`
- `ntoskrnl!PsGetHostSilo` at `0x140016427`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14001620f`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14001620f`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140016228`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140016a5c`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140016228`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140016a5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015fb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001605e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016330`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400163ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016894`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015fb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001605e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016330`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400163ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016894`
- `ntoskrnl!IoGetSilo` at `0x1400168bc`
- `ntoskrnl!IoGetSilo` at `0x140016cba`
- `ntoskrnl!IoGetSilo` at `0x140016ec7`
- `ntoskrnl!IoGetSilo` at `0x14001723b`
- `ntoskrnl!IoGetSilo` at `0x1400168bc`
- `ntoskrnl!IoGetSilo` at `0x140016cba`
- `ntoskrnl!IoGetSilo` at `0x140016ec7`
- `ntoskrnl!IoGetSilo` at `0x14001723b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400172c3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400172c3`
- `FLTMGR!FltGetFileNameInformation` at `0x140016624`
- `FLTMGR!FltGetFileNameInformation` at `0x140016624`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140016173`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140016173`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x1400161d9`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x1400161d9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140015e00`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140016603`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140015e00`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140016603`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140015869`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140015869`
- `FLTMGR!FltAcquireResourceShared` at `0x140015900`
- `FLTMGR!FltAcquireResourceShared` at `0x140015c41`
- `FLTMGR!FltAcquireResourceShared` at `0x140016c87`
- `FLTMGR!FltAcquireResourceShared` at `0x140015900`
- `FLTMGR!FltAcquireResourceShared` at `0x140015c41`
- `FLTMGR!FltAcquireResourceShared` at `0x140016c87`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x140016197`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x140016197`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140015c85`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140015c85`
- `FLTMGR!FltParseFileNameInformation` at `0x14001664a`
- `FLTMGR!FltParseFileNameInformation` at `0x14001664a`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140016978`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140016978`
- `FLTMGR!FltClose` at `0x1400172b2`
- `FLTMGR!FltClose` at `0x1400172b2`
- `FLTMGR!FltSetStreamContext` at `0x140016b16`
- `FLTMGR!FltSetStreamContext` at `0x140016b16`
- `FLTMGR!FltGetStreamContext` at `0x140015abf`
- `FLTMGR!FltGetStreamContext` at `0x140015abf`
- `FLTMGR!FltGetStreamHandleContext` at `0x140015e5f`
- `FLTMGR!FltGetStreamHandleContext` at `0x140015eeb`
- `FLTMGR!FltGetStreamHandleContext` at `0x140016a11`
- `FLTMGR!FltGetStreamHandleContext` at `0x140015e5f`
- `FLTMGR!FltGetStreamHandleContext` at `0x140015eeb`
- `FLTMGR!FltGetStreamHandleContext` at `0x140016a11`
- `FLTMGR!FltReleaseContext` at `0x140015da3`
- `FLTMGR!FltReleaseContext` at `0x140015dd6`
- `FLTMGR!FltReleaseContext` at `0x140015de7`
- `FLTMGR!FltReleaseContext` at `0x140015e7e`
- `FLTMGR!FltReleaseContext` at `0x140015f0a`
- `FLTMGR!FltReleaseContext` at `0x140016a30`
- `FLTMGR!FltReleaseContext` at `0x140016bc3`
- `FLTMGR!FltReleaseContext` at `0x140016be7`
- `FLTMGR!FltReleaseContext` at `0x140015da3`
- `FLTMGR!FltReleaseContext` at `0x140015dd6`
- `FLTMGR!FltReleaseContext` at `0x140015de7`
- `FLTMGR!FltReleaseContext` at `0x140015e7e`
- `FLTMGR!FltReleaseContext` at `0x140015f0a`
- `FLTMGR!FltReleaseContext` at `0x140016a30`
- `FLTMGR!FltReleaseContext` at `0x140016bc3`
- `FLTMGR!FltReleaseContext` at `0x140016be7`
- `FLTMGR!FltReleaseResource` at `0x140015919`
- `FLTMGR!FltReleaseResource` at `0x140015c56`
- `FLTMGR!FltReleaseResource` at `0x140015cb5`
- `FLTMGR!FltReleaseResource` at `0x140016ca1`
- `FLTMGR!FltReleaseResource` at `0x1400172a1`
- `FLTMGR!FltReleaseResource` at `0x140015919`
- `FLTMGR!FltReleaseResource` at `0x140015c56`
- `FLTMGR!FltReleaseResource` at `0x140015cb5`
- `FLTMGR!FltReleaseResource` at `0x140016ca1`
- `FLTMGR!FltReleaseResource` at `0x1400172a1`
- `FLTMGR!FltGetInstanceContext` at `0x140015889`
- `FLTMGR!FltGetInstanceContext` at `0x140015889`

## string_xrefs

- `0x1400168cd`: `onecore\base\fs\wci\bindflt\filter\create.c`
- `0x140016ab1`: `onecore\base\fs\wci\bindflt\filter\create.c`
- `0x140016b72`: `onecore\base\fs\wci\bindflt\filter\create.c`
- `0x140016c38`: `onecore\base\fs\wci\bindflt\filter\create.c`
- `0x1400170ba`: `onecore\base\fs\wci\bindflt\filter\create.c`
- `0x1400171b7`: `onecore\base\fs\wci\bindflt\filter\create.c`

## pseudocode

```c
__int64 __fastcall BfPreCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  void *v5; // r13
  UCHAR OperationFlags; // r14
  PFILE_OBJECT TargetFileObject; // rax
  bool v8; // zf
  struct _FLT_INSTANCE *v9; // r12
  NTSTATUS InstanceContext; // eax
  int v11; // edx
  int v12; // ebx
  int MappingContexts; // eax
  _QWORD *v14; // r15
  _QWORD *v15; // r13
  _QWORD *v16; // rbx
  struct _ERESOURCE *v17; // rcx
  PFLT_IO_PARAMETER_BLOCK v18; // rax
  int FileName; // eax
  int v20; // eax
  int v21; // r11d
  PFLT_IO_PARAMETER_BLOCK v22; // rdx
  UCHAR v23; // cl
  PFLT_IO_PARAMETER_BLOCK v24; // rax
  ULONG v25; // r15d
  unsigned int v26; // r9d
  const UNICODE_STRING *v27; // rdx
  NTSTATUS v28; // r14d
  USHORT v29; // r12
  unsigned int v30; // r8d
  UCHAR MajorFunction; // cl
  struct _FILE_OBJECT *v32; // r15
  PFLT_INSTANCE *v33; // rax
  struct _FLT_INSTANCE *v34; // r12
  NTSTATUS StreamContext; // eax
  __int64 v36; // rdx
  _QWORD *v37; // rdx
  const UNICODE_STRING **v38; // r12
  __int64 v39; // r15
  int SetHandleContext; // eax
  _QWORD *v41; // rdx
  __int64 v42; // r8
  _QWORD *v43; // r9
  struct _ERESOURCE *v44; // rcx
  struct _FILE_OBJECT *v45; // rdx
  _QWORD *v46; // rbx
  PVOID *v47; // rax
  struct _FILE_OBJECT *v49; // rdx
  _WORD *FsContext; // rcx
  char v51; // bl
  struct _FILE_OBJECT *v52; // rdx
  _WORD *v53; // rcx
  char v54; // bl
  __int64 v55; // rcx
  __int64 Buffer; // rax
  unsigned int v57; // ebx
  _QWORD *v58; // rcx
  _QWORD *v59; // rax
  PFLT_FILE_NAME_INFORMATION v60; // r14
  int v61; // eax
  int v62; // eax
  int v63; // eax
  char v64; // r14
  __int64 v65; // rax
  PFLT_IO_PARAMETER_BLOCK v66; // rcx
  UCHAR v67; // al
  char v68; // r14
  PFLT_IO_PARAMETER_BLOCK v69; // rax
  __int64 v70; // rdx
  PVOID *p_EaList; // rcx
  unsigned int Options_high; // ebx
  __int64 HostSilo; // rax
  NTSTATUS v74; // eax
  int v75; // eax
  const UNICODE_STRING **v76; // r14
  const UNICODE_STRING *v77; // r9
  ULONG v78; // r10d
  int v79; // r8d
  const UNICODE_STRING *v80; // rdx
  __int64 v81; // rax
  __int64 *i; // r12
  PFLT_FILE_NAME_INFORMATION v83; // r14
  __int64 *v84; // rax
  int v85; // eax
  int Substring; // eax
  int v87; // eax
  char v88; // r14
  __int64 v89; // rax
  __int64 v90; // rcx
  __int64 Silo; // rax
  NTSTATUS DoesFileExistWithCrossVolumeECP; // eax
  int v93; // r9d
  __int64 v94; // rdx
  NTSTATUS Open; // eax
  NTSTATUS v96; // eax
  int v97; // edx
  __int64 v98; // rax
  int v99; // ecx
  NTSTATUS File; // eax
  int v101; // r8d
  int v102; // r9d
  int v103; // eax
  PFLT_IO_PARAMETER_BLOCK v104; // rcx
  int v105; // r9d
  struct _FLT_TAG_DATA_BUFFER *Information; // r14
  _WORD *v107; // rcx
  char v108; // bl
  NTSTATUS v109; // eax
  int v110; // r9d
  __int64 v111; // rbx
  const char *v112; // rcx
  const UNICODE_STRING *v113; // rbx
  int v114; // eax
  unsigned int EcpContextSize; // [rsp+20h] [rbp-E0h]
  int PoolTag; // [rsp+28h] [rbp-D8h]
  int PoolTaga; // [rsp+28h] [rbp-D8h]
  char Source; // [rsp+30h] [rbp-D0h]
  char Sourcea; // [rsp+30h] [rbp-D0h]
  char Sourceb; // [rsp+30h] [rbp-D0h]
  char v121; // [rsp+38h] [rbp-C8h]
  __int64 v122; // [rsp+38h] [rbp-C8h]
  char v123; // [rsp+40h] [rbp-C0h]
  __int64 v124; // [rsp+40h] [rbp-C0h]
  UNICODE_STRING *p_Name; // [rsp+48h] [rbp-B8h]
  char v126; // [rsp+50h] [rbp-B0h]
  char v127[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v128; // [rsp+64h] [rbp-9Ch]
  int v129; // [rsp+68h] [rbp-98h]
  _QWORD *v130; // [rsp+70h] [rbp-90h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+78h] [rbp-88h] BYREF
  PVOID P[2]; // [rsp+80h] [rbp-80h] BYREF
  int v133; // [rsp+90h] [rbp-70h]
  unsigned int v134; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v135; // [rsp+98h] [rbp-68h]
  __int64 *v136; // [rsp+A0h] [rbp-60h]
  ULONG Options; // [rsp+A8h] [rbp-58h]
  int v138[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v139[2]; // [rsp+B8h] [rbp-48h] BYREF
  PCUNICODE_STRING v140; // [rsp+C0h] [rbp-40h]
  PVOID EcpContext; // [rsp+C8h] [rbp-38h] BYREF
  int v142; // [rsp+D0h] [rbp-30h]
  int v143; // [rsp+D4h] [rbp-2Ch]
  PFILE_OBJECT FileObject; // [rsp+D8h] [rbp-28h]
  const UNICODE_STRING *v145; // [rsp+E0h] [rbp-20h] BYREF
  PVOID v146; // [rsp+E8h] [rbp-18h]
  PECP_LIST EcpList; // [rsp+F0h] [rbp-10h] BYREF
  int v148; // [rsp+F8h] [rbp-8h]
  ULONG v149; // [rsp+FCh] [rbp-4h]
  PFLT_CONTEXT Context; // [rsp+100h] [rbp+0h] BYREF
  __int64 v151; // [rsp+108h] [rbp+8h]
  PVOID v152[2]; // [rsp+110h] [rbp+10h] BYREF
  HANDLE FileHandle; // [rsp+120h] [rbp+20h] BYREF
  PFLT_CONTEXT v154; // [rsp+128h] [rbp+28h] BYREF
  PVOID v155[2]; // [rsp+130h] [rbp+30h] BYREF
  const UNICODE_STRING **v156; // [rsp+140h] [rbp+40h]
  PFLT_CONTEXT v157; // [rsp+190h] [rbp+90h] BYREF
  PFLT_CONTEXT NewContext; // [rsp+198h] [rbp+98h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+1A8h] [rbp+A8h] BYREF

  Iopb = CallbackData->Iopb;
  FileNameInformation = 0;
  v5 = 0;
  OperationFlags = Iopb->OperationFlags;
  Context = 0;
  *(_OWORD *)P = 0;
  FileObject = 0;
  FileHandle = 0;
  Options = Iopb->Parameters.Create.Options;
  LOWORD(NewContext) = Iopb->Parameters.Create.ShareAccess;
  v146 = &v145;
  v145 = (const UNICODE_STRING *)&v145;
  EcpList = 0;
  EcpContext = 0;
  TargetFileObject = Iopb->TargetFileObject;
  v130 = 0;
  v154 = 0;
  v127[0] = 0;
  v8 = (TargetFileObject->Flags & 0x400000) == 0;
  *(_QWORD *)v138 = 0;
  OldContext = 0;
  *(_QWORD *)v139 = 0;
  v134 = 0;
  if ( !v8 )
  {
    LODWORD(v157) = 1;
    goto LABEL_41;
  }
  v9 = *(struct _FLT_INSTANCE **)(a2 + 24);
  if ( !Iopb->MajorFunction )
  {
    FltGetEcpListFromCallbackData(g_BindFltState, CallbackData, &EcpList);
    if ( EcpList )
    {
      FltFindExtraCreateParameter(g_BindFltState, EcpList, &ECP_TYPE_REPARSED_BY_BINDFLT, &EcpContext, 0);
      if ( EcpContext )
      {
        LODWORD(v157) = (*(_DWORD *)EcpContext & 1) == 0
                     || (v111 = *((_QWORD *)EcpContext + 1), IoGetSilo(*(_QWORD *)(a2 + 32)) != v111)
                     || (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 6) == 0;
        goto LABEL_41;
      }
    }
  }
  InstanceContext = FltGetInstanceContext(v9, &Context);
  v12 = InstanceContext;
  if ( InstanceContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_191;
    v121 = InstanceContext;
    v93 = 20;
    Source = -116;
    goto LABEL_253;
  }
  MappingContexts = BfGetMappingContexts(
                      *(_QWORD *)(a2 + 32),
                      (_DWORD)Context,
                      (_DWORD)CallbackData,
                      (unsigned int)v138,
                      (__int64)&OldContext,
                      (__int64)v139);
  v12 = MappingContexts;
  if ( MappingContexts < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_191;
    v121 = MappingContexts;
    v93 = 21;
    Source = -108;
    goto LABEL_253;
  }
  v14 = *(_QWORD **)v138;
  if ( *(_QWORD *)v138 )
  {
    FltAcquireResourceShared((PERESOURCE)(*(_QWORD *)v138 + 16LL));
    v44 = (struct _ERESOURCE *)(v14 + 2);
    if ( (_QWORD *)*v14 != v14 )
    {
      FltReleaseResource(v44);
      LODWORD(v15) = (_DWORD)OldContext;
      goto LABEL_11;
    }
    FltReleaseResource(v44);
  }
  v15 = OldContext;
  if ( OldContext )
  {
    FltAcquireResourceShared((PERESOURCE)((char *)OldContext + 16));
    v17 = (struct _ERESOURCE *)(v15 + 2);
    if ( (_QWORD *)*v15 != v15 )
      goto LABEL_10;
    FltReleaseResource(v17);
  }
  v16 = *(_QWORD **)v139;
  if ( !*(_QWORD *)v139 )
  {
LABEL_38:
    v45 = *(struct _FILE_OBJECT **)(*(_QWORD *)(a2 + 32) + 64LL);
    if ( v45 )
    {
      FsContext = v45->FsContext;
      v157 = 0;
      if ( FsContext )
      {
        if ( *FsContext == 25649 && FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), v45, &v157) >= 0 )
        {
          v51 = *((_BYTE *)v157 + 80);
          FltReleaseContext(v157);
          if ( (v51 & 1) != 0 )
          {
            v12 = -1073741766;
            goto LABEL_191;
          }
        }
      }
    }
    LODWORD(v157) = 1;
    goto LABEL_40;
  }
  FltAcquireResourceShared((PERESOURCE)(*(_QWORD *)v139 + 16LL));
  v17 = (struct _ERESOURCE *)(v16 + 2);
  if ( (_QWORD *)*v16 == v16 )
  {
    FltReleaseResource(v17);
    goto LABEL_38;
  }
LABEL_10:
  FltReleaseResource(v17);
LABEL_11:
  v18 = CallbackData->Iopb;
  if ( !v18->MajorFunction && (v18->Parameters.Create.Options & 0x2000) != 0 )
  {
    v52 = *(struct _FILE_OBJECT **)(*(_QWORD *)(a2 + 32) + 64LL);
    if ( v52 )
    {
      v53 = v52->FsContext;
      v157 = 0;
      if ( v53 )
      {
        if ( *v53 == 25649 && FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), v52, &v157) >= 0 )
        {
          v54 = *((_BYTE *)v157 + 80);
          FltReleaseContext(v157);
          if ( (v54 & 1) != 0 )
          {
            v12 = -1073741637;
            goto LABEL_191;
          }
        }
      }
    }
LABEL_60:
    LODWORD(v157) = 1;
    goto LABEL_40;
  }
  FileName = BfGetPreCreateFileName(CallbackData, v127);
  v12 = FileName;
  if ( FileName < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_191;
    v121 = FileName;
    v93 = 22;
    Source = -50;
    goto LABEL_253;
  }
  if ( FileNameInformation->Name.Length == FileNameInformation->Volume.Length )
  {
    LODWORD(v157) = 1;
    goto LABEL_40;
  }
  v20 = BfCombinedMappingLookup(
          v139[0],
          (_DWORD)v15,
          (_DWORD)v14,
          (_DWORD)v9,
          (__int64)FileNameInformation,
          PoolTag,
          (unsigned __int8)~OperationFlags >> 7,
          (__int64)&v145,
          (__int64)&v134);
  v12 = v20;
  if ( v20 == -1073741766 )
  {
    v49 = *(struct _FILE_OBJECT **)(*(_QWORD *)(a2 + 32) + 64LL);
    if ( v49 )
    {
      v107 = v49->FsContext;
      v157 = 0;
      if ( v107 )
      {
        if ( *v107 == 25649 && FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), v49, &v157) >= 0 )
        {
          v108 = *((_BYTE *)v157 + 80);
          FltReleaseContext(v157);
          if ( (v108 & 1) != 0 )
          {
            v12 = IoReplaceFileObjectName(
                    *(PFILE_OBJECT *)(a2 + 32),
                    FileNameInformation->ParentDir.Buffer,
                    FileNameInformation->FinalComponent.Length + FileNameInformation->ParentDir.Length);
            if ( v12 < 0 )
              goto LABEL_191;
            *(_QWORD *)(*(_QWORD *)(a2 + 32) + 64LL) = 0;
          }
        }
      }
    }
    goto LABEL_60;
  }
  if ( v20 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_191;
    v121 = v20;
    v93 = 23;
    Source = 14;
    goto LABEL_253;
  }
  v22 = CallbackData->Iopb;
  v23 = v22->OperationFlags;
  if ( (v23 & 4) != 0 && !*(_QWORD *)(*(_QWORD *)(a2 + 32) + 64LL) )
  {
    v22->OperationFlags = v23 & 0xFB;
    FltReleaseFileNameInformation(FileNameInformation);
    FileNameInformation = 0;
    v12 = FltGetFileNameInformation(CallbackData, 0x302u, &FileNameInformation);
    if ( v12 < 0 )
    {
LABEL_251:
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_191;
      v121 = v12;
      v93 = 24;
      Source = 69;
      goto LABEL_253;
    }
    if ( !FileNameInformation->Name.Length && FileNameInformation->Volume.Length )
    {
      v12 = -1073741811;
      goto LABEL_251;
    }
    v96 = FltParseFileNameInformation(FileNameInformation);
    if ( v96 < 0 )
    {
      LODWORD(v157) = 4;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v97) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v97,
          5,
          25,
          (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
          76,
          v96);
        goto LABEL_40;
      }
LABEL_181:
      v5 = 0;
      goto LABEL_41;
    }
    CallbackData->Iopb->OperationFlags |= 4u;
  }
  v24 = CallbackData->Iopb;
  LOBYTE(v21) = 0;
  *(_QWORD *)v139 = 0;
  v25 = Options;
  v133 = v21;
  v149 = HIBYTE(Options);
  v26 = v134;
  v148 = -1073741766;
  LOBYTE(OldContext) = 0;
  v142 = 1;
  if ( !v24->MajorFunction )
  {
    v77 = v145;
    v78 = 0;
    LOBYTE(v79) = 0;
    while ( 1 )
    {
      *(_QWORD *)v138 = v77;
      if ( v77 == (const UNICODE_STRING *)&v145 )
      {
        v26 = v134;
        break;
      }
      v80 = v77 + 2;
      v26 = v134;
      v140 = v80;
      if ( v134 == 1 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)&v80->Length + 8LL) & 2) == 0 )
          break;
      }
      else
      {
        v140 = v80;
      }
      v81 = *(_QWORD *)&v80->Length;
      Options = ++v78;
      for ( i = *(__int64 **)(v81 + 64); i != (__int64 *)(*(_QWORD *)&v80->Length + 64LL); i = (__int64 *)*i )
      {
        if ( v26 == 1 && i == *(__int64 **)(*(_QWORD *)&v80->Length + 72LL) )
        {
          LOBYTE(v129) = 1;
        }
        else
        {
          v79 = (unsigned __int8)v79;
          if ( v78 != 1 )
            v79 = 1;
          v129 = v79;
        }
        if ( P[1] )
        {
          ExFreePoolWithTag(P[1], 0x74734642u);
          P[1] = 0;
        }
        v83 = FileNameInformation;
        LOBYTE(v157) = 0;
        LODWORD(P[0]) = 0;
        v84 = (__int64 *)i[2];
        *(_OWORD *)v152 = 0;
        v151 = *v84;
        v85 = BfFormatPathFromFileNameInfo(FileNameInformation, 0, v152);
        v12 = v85;
        if ( v85 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v27) = 2;
            WPP_RECORDER_SF_sDZd(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v27,
              8,
              85,
              (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
              160,
              (__int64)&v83->Name,
              v85);
          }
          v88 = (char)v157;
          v136 = i + 5;
          v89 = *(_QWORD *)v138 + 16LL;
          goto LABEL_144;
        }
        v136 = i + 5;
        v135 = *(_QWORD *)v138 + 16LL;
        Substring = BfReplaceFirstSubstring(v152, *(_QWORD *)v138 + 16LL, i + 5, P);
        v12 = Substring;
        if ( Substring >= 0 )
        {
          v87 = BfPrependVolumeNameFromInstance(v151, P);
          v12 = v87;
          if ( v87 < 0 )
          {
            v88 = 1;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v27) = 2;
              WPP_RECORDER_SF_sDZd(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)v27,
                8,
                87,
                (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                179,
                (__int64)P,
                v87);
            }
          }
          else
          {
            v88 = 0;
          }
          v89 = v135;
LABEL_144:
          v135 = v89;
          goto LABEL_145;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v27,
            8,
            86,
            (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
            168,
            Substring);
        }
        v88 = (char)v157;
LABEL_145:
        if ( v152[1] )
        {
          ExFreePoolWithTag(v152[1], 0x74734642u);
          v152[1] = 0;
        }
        LODWORD(v152[0]) = 0;
        if ( v88 )
          BfFreeUnicodeString(P);
        if ( v12 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_191;
          v110 = 26;
          v126 = v12;
          p_Name = &FileNameInformation->Name;
          v124 = (__int64)v136;
          v122 = v135;
          Sourceb = -93;
          goto LABEL_290;
        }
        v90 = *(unsigned int *)(*(_QWORD *)&v140->Length + 8LL);
        if ( (v90 & 4) != 0 )
          Silo = IoGetSilo(*(_QWORD *)(a2 + 32));
        else
          Silo = PsGetHostSilo(v90, v27);
        DoesFileExistWithCrossVolumeECP = BfpDoesFileExistWithCrossVolumeECP(
                                            (struct _UNICODE_STRING *)P,
                                            *(struct _FLT_INSTANCE **)i[2],
                                            Silo,
                                            0,
                                            CallbackData->Iopb->OperationFlags);
        v12 = DoesFileExistWithCrossVolumeECP;
        if ( DoesFileExistWithCrossVolumeECP >= 0 )
        {
          LOBYTE(v79) = v129;
          if ( (_BYTE)v129 )
          {
            LOBYTE(v21) = 1;
            v133 = v21;
          }
          else
          {
            LOBYTE(v21) = v133;
          }
        }
        else
        {
          if ( DoesFileExistWithCrossVolumeECP == -1073741772 )
          {
            v148 = -1073741772;
          }
          else if ( DoesFileExistWithCrossVolumeECP != -1073741766 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_191;
            v121 = DoesFileExistWithCrossVolumeECP;
            v93 = 27;
            Source = -55;
            goto LABEL_253;
          }
          LOBYTE(v79) = v129;
          v21 = (unsigned __int8)v133;
          if ( (_BYTE)v129 )
            v21 = 0;
          v133 = v21;
        }
        if ( v149 == 2 )
        {
          if ( (_BYTE)v21 )
          {
            v12 = -1073741771;
            goto LABEL_191;
          }
        }
        else
        {
          if ( v149 == 3 )
          {
            v103 = v142;
          }
          else
          {
            if ( v149 != 5 )
              goto LABEL_166;
            v103 = 4;
            v142 = 4;
          }
          if ( (_BYTE)v21 )
          {
            v104 = CallbackData->Iopb;
            LOBYTE(OldContext) = 1;
            v104->Parameters.Create.Options ^= (v149 ^ v103) << 24;
          }
        }
LABEL_166:
        v80 = v140;
        v78 = Options;
        v26 = v134;
        *(_QWORD *)v139 = i;
      }
      if ( (_BYTE)v21 )
        break;
      v77 = **(const UNICODE_STRING ***)v138;
    }
  }
  v27 = v145;
  v28 = -1073741772;
  v29 = (unsigned __int16)NewContext;
  v30 = 0;
  LOBYTE(v143) = 0;
  LOBYTE(v157) = 0;
  *(_QWORD *)v138 = 0;
  v140 = 0;
  v151 = 0;
LABEL_19:
  v156 = (const UNICODE_STRING **)v27;
  if ( v27 == (const UNICODE_STRING *)&v145 )
  {
LABEL_20:
    MajorFunction = CallbackData->Iopb->MajorFunction;
    if ( MajorFunction == 0xF2 )
    {
      LODWORD(v157) = 3;
      goto LABEL_40;
    }
    if ( MajorFunction == 0xF9 )
    {
      LODWORD(v157) = 6;
      goto LABEL_40;
    }
    if ( v28 < 0 )
    {
      if ( (_BYTE)v157 && (v28 == -1073741772 || v28 == -1073741766) )
      {
LABEL_306:
        v12 = -1073741790;
        goto LABEL_191;
      }
      v12 = v28;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_191;
      v110 = 31;
      v126 = v28;
      p_Name = &FileNameInformation->Name;
      LOBYTE(v27) = 4;
      v124 = *(_QWORD *)v139 + 40LL;
      v122 = (__int64)P;
      Sourceb = -9;
      goto LABEL_265;
    }
    v32 = FileObject;
    NewContext = 0;
    OldContext = 0;
    v33 = *(PFLT_INSTANCE **)(*(_QWORD *)v139 + 16LL);
    v130 = 0;
    v34 = *v33;
    StreamContext = FltGetStreamContext(*v33, FileObject, &NewContext);
    v12 = StreamContext;
    if ( StreamContext != -1073741275 )
    {
      if ( StreamContext < 0 )
        goto LABEL_25;
      if ( *((_QWORD *)NewContext + 14) )
      {
        v37 = NewContext;
        v130 = NewContext;
        goto LABEL_28;
      }
    }
    LOBYTE(v36) = 1;
    v12 = BfCreateStreamContext(v32, v36, &NewContext);
    if ( v12 >= 0 )
    {
      v109 = FltSetStreamContext(v34, v32, FLT_SET_CONTEXT_REPLACE_IF_EXISTS, NewContext, &OldContext);
      v12 = v109;
      if ( v109 >= 0 )
      {
        v37 = NewContext;
        v130 = NewContext;
        goto LABEL_28;
      }
      if ( v109 == -1071906814 )
      {
        FltReleaseContext(OldContext);
        v37 = NewContext;
        v130 = NewContext;
        goto LABEL_28;
      }
      FltReleaseContext(NewContext);
    }
LABEL_25:
    if ( v12 == -1071906805 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_191;
      LOBYTE(v36) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v36,
        5,
        32,
        (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
        21);
    }
    else if ( v12 >= 0 )
    {
      v37 = v130;
LABEL_28:
      v38 = *(const UNICODE_STRING ***)v138;
      v39 = *(_QWORD *)v139;
      *(_QWORD *)(*(_QWORD *)(a2 + 32) + 24LL) = v37[14];
      SetHandleContext = BfGetSetHandleContext(
                           *(PFILE_OBJECT *)(a2 + 32),
                           *(PFLT_INSTANCE *)(a2 + 24),
                           (int)FileObject,
                           (int)FileHandle,
                           v39,
                           (int)v38,
                           v140,
                           v37[14],
                           v151,
                           (__int64)&v154);
      v12 = SetHandleContext;
      if ( SetHandleContext >= 0 )
      {
        v41 = Context;
        v42 = *(_QWORD *)(a2 + 32);
        v43 = v154;
        *(_QWORD *)(v42 + 32) = v154;
        *(_BYTE *)(v42 + 72) = *(_BYTE *)(v43[1] + 72LL);
        *(_BYTE *)(v42 + 73) = *(_BYTE *)(v43[1] + 73LL);
        *(_BYTE *)(v42 + 74) = *(_BYTE *)(v43[1] + 74LL);
        *(_BYTE *)(v42 + 75) = *(_BYTE *)(v43[1] + 75LL);
        *(_BYTE *)(v42 + 76) = *(_BYTE *)(v43[1] + 76LL);
        *(_BYTE *)(v42 + 77) = *(_BYTE *)(v43[1] + 77LL);
        *(_BYTE *)(v42 + 78) = *(_BYTE *)(v43[1] + 78LL);
        *(_BYTE *)(v42 + 79) = *(_BYTE *)(v43[1] + 79LL);
        *(_QWORD *)(v42 + 40) = *(_QWORD *)(v43[1] + 40LL);
        *(_QWORD *)(v42 + 16) = v41[5];
        v12 = IoSetShadowFileInformation(*(_QWORD *)(a2 + 32), FileObject, **(_QWORD **)(v39 + 16));
        if ( v12 >= 0 )
        {
          BfUpdateFileSizes(FileObject, *(_QWORD *)(a2 + 32));
          _InterlockedIncrement((volatile signed __int32 *)Context + 8);
          if ( ((_DWORD)v38[1] & 0x10000000) == 0
            || CallbackData->Iopb->MajorFunction
            || (v113 = v38[7], (const UNICODE_STRING *)IoGetSilo(*(_QWORD *)(a2 + 32)) != v113)
            || (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 6) == 0
            || (v114 = BfSetWriteTrackingEa(**(PFLT_INSTANCE **)(v39 + 16), FileObject), v12 = v114, v114 >= 0) )
          {
            CallbackData->IoStatus.Status = v28;
            LODWORD(v157) = 4;
            goto LABEL_40;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_191;
          v121 = v114;
          v93 = 36;
          Source = 106;
LABEL_253:
          LOBYTE(v11) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            5,
            v93,
            (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
            Source,
            v121);
          goto LABEL_191;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_191;
        v126 = v12;
        p_Name = &FileNameInformation->Name;
        v110 = 35;
        v124 = v39 + 40;
        v122 = (__int64)P;
        Sourceb = 80;
LABEL_290:
        LOBYTE(v27) = 2;
LABEL_265:
        WPP_RECORDER_SF_sDZZZd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v27,
          5,
          v110,
          (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
          Sourceb,
          v122,
          v124,
          (__int64)p_Name,
          v126);
        goto LABEL_191;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_191;
      v123 = SetHandleContext;
      v105 = 34;
      LOBYTE(v36) = 2;
      Sourcea = 57;
LABEL_231:
      WPP_RECORDER_SF_sDZd(
        WPP_GLOBAL_Control->DeviceExtension,
        v36,
        5,
        v105,
        (__int64)WPP_48a527b79fd4344d8b4157379f595642_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\create.c",
        Sourcea,
        (__int64)P,
        v123);
      goto LABEL_191;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_191;
    v123 = v12;
    v105 = 33;
    Sourcea = 27;
    LOBYTE(v36) = 2;
    goto LABEL_231;
  }
  v55 = *(_QWORD *)&v27[2].Length;
  v140 = v27 + 1;
  ++v30;
  Buffer = (__int64)v27[2].Buffer;
  LOBYTE(v27) = 0;
  *(_QWORD *)v138 = v55;
  v57 = *(_DWORD *)(v55 + 8);
  v58 = (_QWORD *)(v55 + 64);
  v151 = Buffer;
  Options = v30;
  v128 = v57;
  v59 = (_QWORD *)*v58;
  v129 = (int)v27;
  v152[0] = v58;
  while ( 1 )
  {
    v135 = (__int64)v59;
    if ( v59 == v58 )
      goto LABEL_210;
    if ( v26 == 1 )
    {
      if ( (v57 & 2) != 0 && (_QWORD *)*v59 == v58 )
        LOBYTE(v129) = 1;
    }
    else if ( v26 > 1 )
    {
      if ( v30 < v26 && (_QWORD *)*v59 == v58 )
        goto LABEL_210;
      LODWORD(v27) = (unsigned __int8)v27;
      if ( v30 > 1 )
        LODWORD(v27) = 1;
      v129 = (int)v27;
    }
    if ( P[1] )
    {
      ExFreePoolWithTag(P[1], 0x74734642u);
      P[1] = 0;
    }
    v60 = FileNameInformation;
    LOBYTE(NewContext) = 0;
    LODWORD(P[0]) = 0;
    *(_OWORD *)v155 = 0;
    *(_QWORD *)v139 = **(_QWORD **)(v135 + 16);
    v61 = BfFormatPathFromFileNameInfo(FileNameInformation, 0, v155);
    v12 = v61;
    if ( v61 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 2;
        WPP_RECORDER_SF_sDZd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v27,
          8,
          85,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          160,
          (__int64)&v60->Name,
          v61);
      }
      v64 = (char)NewContext;
      v65 = v135 + 40;
      goto LABEL_92;
    }
    v136 = (__int64 *)(v135 + 40);
    v62 = BfReplaceFirstSubstring(v155, v140, v135 + 40, P);
    v12 = v62;
    if ( v62 >= 0 )
    {
      v63 = BfPrependVolumeNameFromInstance(*(_QWORD *)v139, P);
      v12 = v63;
      if ( v63 < 0 )
      {
        v64 = 1;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = 2;
          WPP_RECORDER_SF_sDZd(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v27,
            8,
            87,
            (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
            179,
            (__int64)P,
            v63);
        }
      }
      else
      {
        v64 = 0;
      }
      v65 = (__int64)v136;
LABEL_92:
      v136 = (__int64 *)v65;
      goto LABEL_93;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v27) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v27,
        8,
        86,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        168,
        v62);
    }
    v64 = (char)NewContext;
LABEL_93:
    if ( v155[1] )
    {
      ExFreePoolWithTag(v155[1], 0x74734642u);
      v155[1] = 0;
    }
    LODWORD(v155[0]) = 0;
    if ( v64 )
      BfFreeUnicodeString(P);
    if ( v12 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_191;
      v110 = 28;
      v126 = v12;
      p_Name = &FileNameInformation->Name;
      v124 = (__int64)v136;
      v122 = (__int64)v140;
      Sourceb = 80;
      goto LABEL_290;
    }
    v66 = CallbackData->Iopb;
    *(_QWORD *)v139 = v135;
    v67 = v66->MajorFunction;
    if ( v67 == 0xF2 || v67 == 0xF9 )
    {
      LOBYTE(v57) = v128;
      Open = BfpHandleNetworkQueryOpen(
               (_DWORD)CallbackData,
               *(_QWORD *)(a2 + 32),
               **(_QWORD **)(v135 + 16),
               (unsigned int)P,
               (v128 & 4) != 0);
      v28 = Open;
      if ( Open != -1073741772 && Open != -1073741766 )
      {
        if ( CallbackData->Iopb->MajorFunction != 0xF9 || Open != -1073741637 )
        {
          LODWORD(v157) = (Open >= 0) + 3;
          goto LABEL_181;
        }
        LODWORD(v157) = 6;
        goto LABEL_40;
      }
      goto LABEL_127;
    }
    v57 = v128;
    v68 = v129;
    if ( (v128 & 1) != 0 )
    {
      v66->Parameters.Create.Options = v25;
      CallbackData->Iopb->Parameters.Create.ShareAccess = v29;
      if ( v68 )
      {
        p_EaList = &CallbackData->Iopb->Parameters.QueryEa.EaList;
        LOBYTE(v157) = 0;
        LODWORD(v70) = *(_DWORD *)p_EaList;
        Options_high = HIBYTE(*(_DWORD *)p_EaList);
        goto LABEL_123;
      }
      v94 = v57 >> 4;
      LOBYTE(v94) = (v57 & 0x10) != 0;
      if ( !(unsigned __int8)BfpValidateReadOnlyCreate(CallbackData, v94) )
      {
        if ( (v57 & 2) == 0 )
          goto LABEL_306;
        LOBYTE(v157) = 1;
        v28 = -1073741790;
        goto LABEL_127;
      }
    }
    v69 = CallbackData->Iopb;
    v70 = v69->Parameters.Create.Options;
    p_EaList = &v69->Parameters.QueryEa.EaList;
    Options_high = HIBYTE(v69->Parameters.Create.Options);
    if ( !v68 )
    {
      if ( (v128 & 8) != 0 && (v69->OperationFlags & 4) == 0 )
      {
        if ( (v128 & 4) != 0 )
          HostSilo = IoGetSilo(*(_QWORD *)(a2 + 32));
        else
          HostSilo = PsGetHostSilo(v128, v70);
        v74 = BfpDoesFileExistWithCrossVolumeECP(
                (struct _UNICODE_STRING *)P,
                **(struct _FLT_INSTANCE ***)(v135 + 16),
                HostSilo,
                0x40u,
                CallbackData->Iopb->OperationFlags);
        v28 = v74;
        if ( v74 >= 0 )
        {
LABEL_111:
          v76 = *(const UNICODE_STRING ***)v138;
LABEL_112:
          if ( !EcpList )
          {
            v12 = FltAllocateExtraCreateParameterList(g_BindFltState, 0, &EcpList);
            if ( v12 < 0 )
              goto LABEL_191;
            FltSetEcpListIntoCallbackData(g_BindFltState, CallbackData, EcpList);
          }
          if ( !EcpContext )
          {
            v12 = FltAllocateExtraCreateParameter(
                    g_BindFltState,
                    &ECP_TYPE_REPARSED_BY_BINDFLT,
                    0x10u,
                    0,
                    0,
                    0x63654642u,
                    &EcpContext);
            if ( v12 < 0 )
              goto LABEL_191;
            *(_OWORD *)EcpContext = 0;
            if ( ((_DWORD)v76[1] & 0x10000000) != 0 )
            {
              *(_DWORD *)EcpContext = 1;
              *((_QWORD *)EcpContext + 1) = v76[7];
            }
            FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
          }
          v12 = IoReplaceFileObjectName(*(PFILE_OBJECT *)(a2 + 32), (PWSTR)P[1], (USHORT)P[0]);
          if ( v12 >= 0 )
          {
            CallbackData->IoStatus.Status = 260;
            CallbackData->IoStatus.Information = 0;
            LODWORD(v157) = 4;
            goto LABEL_40;
          }
          goto LABEL_191;
        }
        if ( v74 == -1073741772 )
        {
          if ( Options_high <= 5 && !(_BYTE)v133 )
          {
            v75 = 45;
            if ( _bittest(&v75, Options_high) )
              goto LABEL_111;
          }
          goto LABEL_126;
        }
        if ( v74 == -1073741766 )
          goto LABEL_126;
        if ( v74 != -1073741638 )
        {
          v12 = v74;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_191;
          v123 = v74;
          v105 = 29;
          LOBYTE(v36) = 3;
          Sourcea = 45;
          goto LABEL_231;
        }
        if ( !(_BYTE)v133 )
        {
          v76 = *(const UNICODE_STRING ***)v138;
          if ( !*(_BYTE *)(*(_QWORD *)v138 + 48LL)
            && FileNameInformation->FinalComponent.Length + (unsigned int)FileNameInformation->ParentDir.Length > v140->Length )
          {
            goto LABEL_112;
          }
        }
      }
      goto LABEL_204;
    }
LABEL_123:
    if ( !(_BYTE)v133 && (Options_high == 4 || Options_high == 1) )
    {
      v28 = v148;
LABEL_126:
      LOBYTE(v57) = v128;
      goto LABEL_127;
    }
    if ( (_BYTE)OldContext )
      *(_DWORD *)p_EaList = v70 ^ ((v149 ^ v142) << 24);
LABEL_204:
    LOBYTE(v57) = v128;
    v99 = (unsigned __int8)v143;
    if ( (CallbackData->Iopb->OperationFlags & 8) == 0 )
      v99 = 1;
    v143 = v99;
    LOBYTE(PoolTaga) = v99;
    EcpContextSize = v128;
    File = BfCreateFile(P, CallbackData, a2, **(_QWORD **)(v135 + 16));
    v28 = File;
    if ( File == -2147483603 )
    {
      if ( (_BYTE)v143 )
        break;
    }
    if ( File != -1073741772 && File != -1073741766 )
    {
      v30 = Options;
LABEL_210:
      if ( v28 == -1073741766 || v28 == -1073741772 )
      {
        v26 = v134;
        v27 = *v156;
        goto LABEL_19;
      }
      goto LABEL_20;
    }
LABEL_127:
    v58 = v152[0];
    LODWORD(v27) = v129;
    v30 = Options;
    v59 = *(_QWORD **)v135;
    v26 = v134;
  }
  Information = (struct _FLT_TAG_DATA_BUFFER *)CallbackData->IoStatus.Information;
  if ( Information && Information->TagDataLength <= 0x4000u )
  {
    CallbackData->TagData = Information;
    FltSetCallbackDataDirty(CallbackData);
    CallbackData->IoStatus.Status = 260;
    CallbackData->IoStatus.Information = Information->FileTag;
    if ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 96LL)
                  + 2 * ((unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(a2 + 32) + 88LL) >> 1)
                  - 2) == 92 )
      CallbackData->TagData->UnparsedNameLength += 2;
    LODWORD(v157) = 4;
    goto LABEL_40;
  }
  v12 = -1073741192;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v112 = "missing";
    if ( Information )
      v112 = "too big";
    WPP_RECORDER_SF_sDsZZZd(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)"too big",
      v101,
      v102,
      EcpContextSize,
      PoolTaga,
      (unsigned int)&FileHandle,
      (__int64)v112,
      (__int64)P,
      (__int64)v136,
      (__int64)&FileNameInformation->Name);
  }
LABEL_191:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  v98 = *(_QWORD *)(a2 + 32);
  LODWORD(v157) = 4;
  *(_QWORD *)(v98 + 24) = 0;
  *(_QWORD *)(*(_QWORD *)(a2 + 32) + 32LL) = 0;
  CallbackData->IoStatus.Status = v12;
LABEL_40:
  v5 = v130;
LABEL_41:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x74734642u);
    P[1] = 0;
  }
  LODWORD(P[0]) = 0;
  while ( v145 != (const UNICODE_STRING *)&v145 )
  {
    v46 = v146;
    if ( *(const UNICODE_STRING ***)v146 != &v145 || (v47 = (PVOID *)*((_QWORD *)v146 + 1), *v47 != v146) )
      __fastfail(3u);
    v146 = (PVOID)*((_QWORD *)v146 + 1);
    *v47 = &v145;
    BfFreeUnicodeString(v46 + 2);
    BfReleaseMappingInformation(v46[4]);
    ExFreePoolWithTag(v46, 0x706D4642u);
  }
  if ( Context )
    FltReleaseContext(Context);
  if ( FileNameInformation )
  {
    if ( v127[0] )
    {
      BfFreeUnicodeString(&FileNameInformation->Name);
      ExFreePoolWithTag(FileNameInformation, 0x6D6E4642u);
    }
    else
    {
      FltReleaseFileNameInformation(FileNameInformation);
    }
  }
  if ( v5 )
    FltReleaseContext(v5);
  if ( v154 )
    FltReleaseContext(v154);
  return (unsigned int)v157;
}

```

## disassembly

```asm
0x1400157a0  mov     r11, rsp
0x1400157a3  push    rbp
0x1400157a4  push    rbx
0x1400157a5  push    r13
0x1400157a7  lea     rbp, [rsp-70h]
0x1400157ac  sub     rsp, 170h
0x1400157b3  mov     r8, [rcx+10h]
0x1400157b7  xorps   xmm0, xmm0
0x1400157ba  mov     [r11+18h], rsi
0x1400157be  mov     rsi, rcx
0x1400157c1  mov     [r11-20h], rdi
0x1400157c5  mov     rdi, rdx
0x1400157c8  mov     [r11-30h], r14
0x1400157cc  mov     [r11-38h], r15
0x1400157d0  xor     r15d, r15d
0x1400157d3  mov     [rsp+180h+FileNameInformation], r15
0x1400157d8  mov     r13d, r15d
0x1400157db  movzx   r14d, byte ptr [r8+6]
0x1400157e0  mov     [rbp+80h+Context], r15
0x1400157e4  movups  xmmword ptr [rbp+80h+P], xmm0
0x1400157e8  mov     [rbp+80h+FileObject], r15
0x1400157ec  mov     [rbp+80h+FileHandle], r15
0x1400157f0  mov     eax, [r8+20h]
0x1400157f4  mov     [rbp+80h+var_D8], eax
0x1400157f7  movzx   eax, word ptr [r8+2Ah]
0x1400157fc  mov     word ptr [rbp+80h+NewContext], ax
0x140015803  lea     rax, [rbp+80h+var_A0]
0x140015807  mov     [rbp+80h+var_98], rax
0x14001580b  lea     rax, [rbp+80h+var_A0]
0x14001580f  mov     [rbp+80h+var_A0], rax
0x140015813  mov     [rbp+80h+EcpList], r15
0x140015817  mov     [rbp+80h+EcpContext], r15
0x14001581b  mov     rax, [r8+8]
0x14001581f  mov     [rsp+180h+var_110], r15
0x140015824  mov     [rbp+80h+var_58], r15
0x140015828  mov     [rsp+180h+var_120], r13b
0x14001582d  test    dword ptr [rax+50h], 400000h
0x140015834  mov     qword ptr [rbp+80h+var_D0], r15
0x140015838  mov     [rbp+80h+OldContext], r15
0x14001583f  mov     qword ptr [rbp+80h+var_C8], r15
0x140015843  mov     [rbp+80h+var_EC], r15d
0x140015847  jnz     loc_1400169C4
0x14001584d  mov     [r11-28h], r12
0x140015851  mov     r12, [rdx+18h]
0x140015855  cmp     [r8+4], r13b
0x140015859  jnz     short loc_140015882
0x14001585b  mov     rdx, rcx; CallbackData
0x14001585e  lea     r8, [rbp+80h+EcpList]; EcpList
0x140015862  mov     rcx, cs:g_BindFltState; Filter
0x140015869  call    cs:__imp_FltGetEcpListFromCallbackData
0x140015870  nop     dword ptr [rax+rax+00h]
0x140015875  mov     rdx, [rbp+80h+EcpList]; EcpList
0x140015879  test    rdx, rdx
0x14001587c  jnz     loc_140015C6E
0x140015882  lea     rdx, [rbp+80h+Context]; Context
0x140015886  mov     rcx, r12; Instance
0x140015889  call    cs:__imp_FltGetInstanceContext
0x140015890  nop     dword ptr [rax+rax+00h]
0x140015895  mov     ebx, eax
0x140015897  test    eax, eax
0x140015899  js      loc_140016CEE
0x14001589f  mov     rdx, [rbp+80h+Context]
0x1400158a3  lea     rax, [rbp+80h+var_C8]
0x1400158a7  mov     rcx, [rdi+20h]
0x1400158ab  lea     r9, [rbp+80h+var_D0]
0x1400158af  mov     qword ptr [rsp+180h+PoolTag], rax
0x1400158b4  mov     r8, rsi
0x1400158b7  lea     rax, [rbp+80h+OldContext]
0x1400158be  mov     [rsp+180h+EcpContextSize], rax
0x1400158c3  call    BfGetMappingContexts
0x1400158c8  mov     ebx, eax
0x1400158ca  test    eax, eax
0x1400158cc  js      loc_140016D19
0x1400158d2  mov     r15, qword ptr [rbp+80h+var_D0]
0x1400158d6  test    r15, r15
0x1400158d9  jnz     loc_140015C3D
0x1400158df  mov     r13, [rbp+80h+OldContext]
0x1400158e6  test    r13, r13
0x1400158e9  jnz     loc_140016C83
0x1400158ef  mov     rbx, qword ptr [rbp+80h+var_C8]
0x1400158f3  test    rbx, rbx
0x1400158f6  jz      loc_140015CC6
0x1400158fc  lea     rcx, [rbx+10h]; Resource
0x140015900  call    cs:__imp_FltAcquireResourceShared
0x140015907  nop     dword ptr [rax+rax+00h]
0x14001590c  lea     rcx, [rbx+10h]; Resource
0x140015910  cmp     [rbx], rbx
0x140015913  jz      loc_1400172A1
0x140015919  call    cs:__imp_FltReleaseResource
0x140015920  nop     dword ptr [rax+rax+00h]
0x140015925  mov     rax, [rsi+10h]
0x140015929  cmp     byte ptr [rax+4], 0
0x14001592d  jz      loc_140015E9D
0x140015933  mov     r8, [rdi+18h]
0x140015937  lea     rax, [rsp+180h+var_120]
0x14001593c  mov     rdx, [rdi+20h]
0x140015940  lea     r9, [rsp+180h+FileNameInformation]
0x140015945  mov     rcx, rsi; CallbackData
0x140015948  mov     [rsp+180h+EcpContextSize], rax; Context
0x14001594d  call    BfGetPreCreateFileName
0x140015952  mov     ebx, eax
0x140015954  test    eax, eax
0x140015956  js      loc_140016D44
0x14001595c  mov     rcx, [rsp+180h+FileNameInformation]
0x140015961  movzx   eax, word ptr [rcx+18h]
0x140015965  cmp     [rcx+8], ax
0x140015969  jz      loc_140016D6F
0x14001596f  lea     rax, [rbp+80h+var_EC]
0x140015973  not     r14b
0x140015976  mov     [rsp+180h+var_140], rax
0x14001597b  mov     r9, r12
0x14001597e  lea     rax, [rbp+80h+var_A0]
0x140015982  shr     r14b, 7
0x140015986  mov     [rsp+180h+var_148], rax
0x14001598b  mov     r8, r15
0x14001598e  mov     byte ptr [rsp+180h+Source], r14b
0x140015993  mov     rdx, r13
0x140015996  mov     [rsp+180h+EcpContextSize], rcx
0x14001599b  mov     rcx, qword ptr [rbp+80h+var_C8]
0x14001599f  call    BfCombinedMappingLookup
0x1400159a4  mov     ebx, eax
0x1400159a6  cmp     eax, 0C000003Ah
0x1400159ab  jz      loc_140015E0E
0x1400159b1  test    eax, eax
0x1400159b3  js      loc_140016D82
0x1400159b9  mov     rdx, [rsi+10h]
0x1400159bd  movzx   ecx, byte ptr [rdx+6]
0x1400159c1  test    cl, 4
0x1400159c4  jnz     loc_1400165E9
0x1400159ca  xor     r15d, r15d
0x1400159cd  mov     rax, [rsi+10h]
0x1400159d1  lea     r13, WPP_RECORDER_INITIALIZED
0x1400159d8  xor     r11b, r11b
0x1400159db  mov     qword ptr [rbp+80h+var_C8], r15
0x1400159df  mov     r15d, [rbp+80h+var_D8]
0x1400159e3  mov     r10d, 1
0x1400159e9  mov     r9d, r15d
0x1400159ec  mov     [rbp+80h+var_F0], r11d
0x1400159f0  shr     r9d, 18h
0x1400159f4  mov     [rbp+80h+var_84], r9d
0x1400159f8  mov     r9d, [rbp+80h+var_EC]
0x1400159fc  mov     [rbp+80h+var_88], 0C000003Ah
0x140015a03  mov     byte ptr [rbp+80h+OldContext], r11b
0x140015a0a  mov     [rbp+80h+var_B0], r10d
0x140015a0e  cmp     [rax+4], r11b
0x140015a12  jz      loc_1400162AB
0x140015a18  mov     rdx, [rbp+80h+var_A0]
0x140015a1c  mov     r14d, 0C0000034h
0x140015a22  movzx   r12d, word ptr [rbp+80h+NewContext]
0x140015a2a  xor     r8d, r8d
0x140015a2d  mov     byte ptr [rbp+80h+var_AC], 0
0x140015a31  mov     byte ptr [rbp+80h+arg_0], 0
0x140015a38  mov     qword ptr [rbp+80h+var_D0], 0
0x140015a40  mov     [rbp+80h+var_C0], 0
0x140015a48  mov     [rbp+80h+var_78], 0
0x140015a50  lea     rax, [rbp+80h+var_A0]
0x140015a54  mov     [rbp+80h+var_40], rdx
0x140015a58  cmp     rdx, rax
0x140015a5b  jnz     loc_140015F29
0x140015a61  mov     rax, [rsi+10h]
0x140015a65  movzx   ecx, byte ptr [rax+4]
0x140015a69  cmp     cl, 0F2h
0x140015a6c  jz      loc_1400167D6
0x140015a72  cmp     cl, 0F9h
0x140015a75  jz      loc_1400168A5
0x140015a7b  test    r14d, r14d
0x140015a7e  js      loc_14001666B
0x140015a84  mov     rcx, qword ptr [rbp+80h+var_C8]
0x140015a88  lea     r8, [rbp+80h+NewContext]; Context
0x140015a8f  mov     r15, [rbp+80h+FileObject]
0x140015a93  mov     rdx, r15; FileObject
0x140015a96  mov     [rbp+80h+NewContext], 0
0x140015aa1  mov     [rbp+80h+OldContext], 0
0x140015aac  mov     rax, [rcx+10h]
0x140015ab0  mov     [rsp+180h+var_110], 0
0x140015ab9  mov     r12, [rax]
0x140015abc  mov     rcx, r12; Instance
0x140015abf  call    cs:__imp_FltGetStreamContext
0x140015ac6  nop     dword ptr [rax+rax+00h]
0x140015acb  mov     ebx, eax
0x140015acd  cmp     eax, 0C0000225h
0x140015ad2  jz      loc_140016ADF
0x140015ad8  test    eax, eax
0x140015ada  jns     loc_140016C64
0x140015ae0  cmp     ebx, 0C01C000Bh
0x140015ae6  jz      loc_1400171B0
0x140015aec  test    ebx, ebx
0x140015aee  js      loc_1400168CD
0x140015af4  mov     rdx, [rsp+180h+var_110]
0x140015af9  mov     rax, [rdx+70h]
0x140015afd  mov     rcx, [rdi+20h]
0x140015b01  mov     r12, qword ptr [rbp+80h+var_D0]
0x140015b05  mov     r15, qword ptr [rbp+80h+var_C8]
0x140015b09  mov     [rcx+18h], rax
0x140015b0d  lea     rax, [rbp+80h+var_58]
0x140015b11  mov     r9, [rbp+80h+FileHandle]; int
0x140015b15  mov     r8, [rbp+80h+FileObject]; int
0x140015b19  mov     rcx, [rdi+20h]; FileObject
0x140015b1d  mov     [rsp+180h+var_138], rax; __int64
0x140015b22  mov     rax, [rbp+80h+var_78]
0x140015b26  mov     [rsp+180h+var_140], rax; __int64
0x140015b2b  mov     rax, [rdx+70h]
0x140015b2f  mov     rdx, [rdi+18h]; Instance
0x140015b33  mov     [rsp+180h+var_148], rax; __int64
0x140015b38  mov     rax, [rbp+80h+var_C0]
0x140015b3c  mov     [rsp+180h+Source], rax; Source
0x140015b41  mov     qword ptr [rsp+180h+PoolTag], r12; int
0x140015b46  mov     [rsp+180h+EcpContextSize], r15; int
0x140015b4b  call    BfGetSetHandleContext
0x140015b50  mov     ebx, eax
0x140015b52  test    eax, eax
0x140015b54  js      loc_140017200
0x140015b5a  mov     rdx, [rbp+80h+Context]
0x140015b5e  mov     r8, [rdi+20h]
0x140015b62  mov     r9, [rbp+80h+var_58]
0x140015b66  mov     [r8+20h], r9
0x140015b6a  mov     rax, [r9+8]
0x140015b6e  movzx   ecx, byte ptr [rax+48h]
0x140015b72  mov     [r8+48h], cl
0x140015b76  mov     rax, [r9+8]
0x140015b7a  movzx   ecx, byte ptr [rax+49h]
0x140015b7e  mov     [r8+49h], cl
0x140015b82  mov     rax, [r9+8]
0x140015b86  movzx   ecx, byte ptr [rax+4Ah]
0x140015b8a  mov     [r8+4Ah], cl
0x140015b8e  mov     rax, [r9+8]
0x140015b92  movzx   ecx, byte ptr [rax+4Bh]
0x140015b96  mov     [r8+4Bh], cl
0x140015b9a  mov     rax, [r9+8]
0x140015b9e  movzx   ecx, byte ptr [rax+4Ch]
0x140015ba2  mov     [r8+4Ch], cl
0x140015ba6  mov     rax, [r9+8]
0x140015baa  movzx   ecx, byte ptr [rax+4Dh]
0x140015bae  mov     [r8+4Dh], cl
0x140015bb2  mov     rax, [r9+8]
0x140015bb6  movzx   ecx, byte ptr [rax+4Eh]
0x140015bba  mov     [r8+4Eh], cl
0x140015bbe  mov     rax, [r9+8]
0x140015bc2  movzx   ecx, byte ptr [rax+4Fh]
0x140015bc6  mov     [r8+4Fh], cl
0x140015bca  mov     rax, [r9+8]
0x140015bce  mov     rcx, [rax+28h]
0x140015bd2  mov     [r8+28h], rcx
0x140015bd6  mov     rax, [rdx+28h]
0x140015bda  mov     [r8+10h], rax
0x140015bde  mov     r8, [r15+10h]
0x140015be2  mov     rdx, [rbp+80h+FileObject]
0x140015be6  mov     rcx, [rdi+20h]
0x140015bea  mov     r8, [r8]
0x140015bed  call    cs:__imp_IoSetShadowFileInformation
0x140015bf4  nop     dword ptr [rax+rax+00h]
0x140015bf9  mov     ebx, eax
0x140015bfb  test    eax, eax
0x140015bfd  js      loc_140017212
0x140015c03  mov     rdx, [rdi+20h]
0x140015c07  mov     rcx, [rbp+80h+FileObject]
0x140015c0b  call    BfUpdateFileSizes
0x140015c10  mov     rax, [rbp+80h+Context]
0x140015c14  lock inc dword ptr [rax+20h]
0x140015c18  test    dword ptr [r12+8], 10000000h
0x140015c21  jnz     loc_140017224
0x140015c27  mov     [rsi+18h], r14d
0x140015c2b  xor     r15d, r15d
0x140015c2e  mov     dword ptr [rbp+80h+arg_0], 4
0x140015c38  jmp     loc_140015CE5
0x140015c3d  lea     rcx, [r15+10h]; Resource
0x140015c41  call    cs:__imp_FltAcquireResourceShared
0x140015c48  nop     dword ptr [rax+rax+00h]
0x140015c4d  lea     rcx, [r15+10h]; Resource
0x140015c51  cmp     [r15], r15
0x140015c54  jz      short loc_140015CB5
0x140015c56  call    cs:__imp_FltReleaseResource
0x140015c5d  nop     dword ptr [rax+rax+00h]
0x140015c62  mov     r13, [rbp+80h+OldContext]
0x140015c69  jmp     loc_140015925
0x140015c6e  mov     rcx, cs:g_BindFltState; Filter
0x140015c75  lea     r9, [rbp+80h+EcpContext]; EcpContext
0x140015c79  lea     r8, ECP_TYPE_REPARSED_BY_BINDFLT; EcpType
0x140015c80  mov     [rsp+180h+EcpContextSize], r15; EcpContextSize
0x140015c85  call    cs:__imp_FltFindExtraCreateParameter
0x140015c8c  nop     dword ptr [rax+rax+00h]
0x140015c91  mov     rbx, [rbp+80h+EcpContext]
0x140015c95  test    rbx, rbx
0x140015c98  jz      loc_140015882
0x140015c9e  mov     eax, [rbx]
0x140015ca0  test    al, 1
0x140015ca2  jnz     loc_140016CB2
0x140015ca8  mov     eax, 1
0x140015cad  mov     dword ptr [rbp+80h+arg_0], eax
0x140015cb3  jmp     short loc_140015CEA
0x140015cb5  call    cs:__imp_FltReleaseResource
0x140015cbc  nop     dword ptr [rax+rax+00h]
0x140015cc1  jmp     loc_1400158DF
0x140015cc6  mov     rax, [rdi+20h]
0x140015cca  xor     r15d, r15d
0x140015ccd  mov     rdx, [rax+40h]; FileObject
0x140015cd1  test    rdx, rdx
0x140015cd4  jnz     loc_140015E32
0x140015cda  mov     ebx, 1
0x140015cdf  mov     dword ptr [rbp+80h+arg_0], ebx
  ... truncated ...
```
