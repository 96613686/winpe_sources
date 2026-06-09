# PrjfPreCleanup

- ea: `0x140040670`
- end: `0x1400412bd`
- name: `PrjfPreCleanup`
- size: `3149`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140002d9c`
- `0x140002f3c`
- `0x140006570`
- `0x140006660`
- `0x140006a58`
- `0x14000a278`
- `0x14000b1d0`
- `0x14000be80`
- `0x14000d128`
- `0x14003775c`
- `0x14003c4b8`
- `0x14003cc14`
- `0x140040670`
- `0x140041a3c`
- `0x140043844`
- `0x140043d88`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004092b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400409c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004092b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400409c3`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140041128`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14004115c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140041128`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14004115c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004114d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004114d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140040980`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140040980`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400407bb`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400407bb`
- `ntoskrnl!ObfDereferenceObject` at `0x14004086e`
- `ntoskrnl!ObfDereferenceObject` at `0x14004089c`
- `ntoskrnl!ObfDereferenceObject` at `0x140040940`
- `ntoskrnl!ObfDereferenceObject` at `0x14004086e`
- `ntoskrnl!ObfDereferenceObject` at `0x14004089c`
- `ntoskrnl!ObfDereferenceObject` at `0x140040940`
- `FLTMGR!FltParseFileNameInformation` at `0x140040d56`
- `FLTMGR!FltParseFileNameInformation` at `0x140040d56`
- `FLTMGR!FltCreateFileEx2` at `0x140040bf4`
- `FLTMGR!FltCreateFileEx2` at `0x140040bf4`
- `FLTMGR!FltClose` at `0x140040856`
- `FLTMGR!FltClose` at `0x140040887`
- `FLTMGR!FltClose` at `0x140040911`
- `FLTMGR!FltClose` at `0x140040856`
- `FLTMGR!FltClose` at `0x140040887`
- `FLTMGR!FltClose` at `0x140040911`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400408b1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040955`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040cb3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400408b1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040955`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140040cb3`
- `FLTMGR!FltGetFileNameInformation` at `0x140040ad9`
- `FLTMGR!FltGetFileNameInformation` at `0x140040ccf`
- `FLTMGR!FltGetFileNameInformation` at `0x140040ad9`
- `FLTMGR!FltGetFileNameInformation` at `0x140040ccf`
- `FLTMGR!FltReferenceContext` at `0x140040fe3`
- `FLTMGR!FltReferenceContext` at `0x140040fe3`
- `FLTMGR!FltReleaseContext` at `0x1400408c9`
- `FLTMGR!FltReleaseContext` at `0x1400408de`
- `FLTMGR!FltReleaseContext` at `0x1400408f3`
- `FLTMGR!FltReleaseContext` at `0x14004096a`
- `FLTMGR!FltReleaseContext` at `0x140040995`
- `FLTMGR!FltReleaseContext` at `0x1400409a9`
- `FLTMGR!FltReleaseContext` at `0x1400408c9`
- `FLTMGR!FltReleaseContext` at `0x1400408de`
- `FLTMGR!FltReleaseContext` at `0x1400408f3`
- `FLTMGR!FltReleaseContext` at `0x14004096a`
- `FLTMGR!FltReleaseContext` at `0x140040995`
- `FLTMGR!FltReleaseContext` at `0x1400409a9`

## pseudocode

```c
__int64 __fastcall PrjfPreCleanup(struct _FLT_CALLBACK_DATA *a1, __int64 a2, struct _FLT_FILE_NAME_INFORMATION ***a3)
{
  struct _FILE_OBJECT *v4; // rdx
  struct _FLT_INSTANCE *v6; // rcx
  unsigned int v7; // esi
  struct _FLT_FILE_NAME_INFORMATION **v8; // rbx
  void *v9; // r15
  int IsFileObjectWithinActiveVirtualizationRoots; // edi
  char v11; // r12
  int v12; // edx
  int v13; // r8d
  struct _FLT_FILE_NAME_INFORMATION *v14; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v15; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v16; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v17; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v18; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rcx
  int v23; // edx
  int v24; // r8d
  NTSTATUS v25; // r12d
  struct _FLT_INSTANCE *v26; // rdx
  NTSTATUS v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  NTSTATUS v32; // eax
  int v33; // edx
  int v34; // r8d
  NTSTATUS v35; // eax
  int v36; // r8d
  __int16 v37; // cx
  __int16 v38; // ax
  int v39; // eax
  int SetContextFileObject; // eax
  int v41; // edx
  int v42; // r8d
  struct _FLT_FILE_NAME_INFORMATION *v43; // r12
  int v44; // eax
  int v45; // edx
  int v46; // r8d
  struct _FLT_FILE_NAME_INFORMATION *v47; // r12
  struct _EX_RUNDOWN_REF *v48; // r13
  __int64 v49; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v50; // r9
  BOOLEAN i; // al
  int v52; // edx
  int v53; // r8d
  int v54; // eax
  int v55; // edx
  int v56; // r8d
  unsigned int v57; // edi
  char v58[3]; // [rsp+81h] [rbp-7Fh] BYREF
  int v59; // [rsp+84h] [rbp-7Ch]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+88h] [rbp-78h] BYREF
  PVOID Object; // [rsp+90h] [rbp-70h]
  PFLT_CONTEXT Context; // [rsp+98h] [rbp-68h]
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v64; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v65; // [rsp+B0h] [rbp-50h] BYREF
  PFLT_CONTEXT v66; // [rsp+B8h] [rbp-48h]
  PFLT_CONTEXT v67; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE FileHandle; // [rsp+C8h] [rbp-38h] BYREF
  PVOID v69; // [rsp+D0h] [rbp-30h] BYREF
  PFLT_CONTEXT v70; // [rsp+D8h] [rbp-28h] BYREF
  PVOID P[2]; // [rsp+E0h] [rbp-20h] BYREF
  __m128i Name; // [rsp+F0h] [rbp-10h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+130h] [rbp+30h] BYREF
  char v78; // [rsp+1A8h] [rbp+A8h]

  Context = 0;
  v66 = 0;
  Object = 0;
  v4 = *(struct _FILE_OBJECT **)(a2 + 32);
  FileObject = 0;
  v67 = 0;
  v6 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v7 = 1;
  v59 = 1;
  v8 = 0;
  v65 = 0;
  v9 = 0;
  memset(&ObjectAttributes, 0, 44);
  v69 = 0;
  FileNameInformation = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v70 = 0;
  v64 = 0;
  *(_OWORD *)P = 0;
  if ( !(unsigned __int8)PrjfGetContextFileObjectEx(v6, v4, &v67) )
    goto LABEL_18;
  IsFileObjectWithinActiveVirtualizationRoots = PrjfIsFileObjectWithinActiveVirtualizationRoots(a1, a2, P);
  if ( IsFileObjectWithinActiveVirtualizationRoots < 0 )
    goto LABEL_18;
  if ( v67 )
  {
    v11 = *((_BYTE *)v67 + 40) & 1;
    if ( v11 )
      goto LABEL_8;
  }
  else
  {
    v11 = 0;
  }
  if ( !*((_BYTE *)Context + 280) )
    goto LABEL_13;
LABEL_8:
  v8 = (struct _FLT_FILE_NAME_INFORMATION **)ExAllocateFromPagedLookasideList(&stru_14001A840);
  if ( !v8 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v12,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        39,
        (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
        220,
        154);
    }
    v7 = 1;
    goto LABEL_13;
  }
  v78 = 0;
  memset(v8, 0, 0x48u);
  LOBYTE(v22) = 0;
  *((_BYTE *)v8 + 64) &= ~1u;
  if ( v11 )
  {
    IsFileObjectWithinActiveVirtualizationRoots = PrjfPrepareForDelete(a1);
    v78 = (_BYTE)v8[8] & 1;
    if ( IsFileObjectWithinActiveVirtualizationRoots < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = xmmword_14001A3D0 & 0x40;
        LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          518,
          v20,
          v21,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          6,
          40,
          (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          253,
          IsFileObjectWithinActiveVirtualizationRoots);
      }
      v25 = FltGetFileNameInformation(a1, 0x101u, &FileNameInformation);
      if ( v25 < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v23) = xmmword_14001A3D0 & 0x40;
          LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            518,
            v23,
            v24,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            6,
            41,
            (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            6,
            v25);
        }
LABEL_58:
        LOBYTE(IsFileObjectWithinActiveVirtualizationRoots) = v25;
        goto LABEL_100;
      }
      ObjectAttributes.ObjectName = &FileNameInformation->Name;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Length = 48;
      v26 = *(struct _FLT_INSTANCE **)(a2 + 24);
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v27 = FltCreateFileEx2(
              Globals,
              v26,
              &v65,
              (PFILE_OBJECT *)&v69,
              0x10000u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x80u,
              3u,
              1u,
              0x200000u,
              0,
              0,
              0x800u,
              0);
      v31 = 0;
      LOBYTE(v25) = v27;
      if ( v27 < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v28) = xmmword_14001A3D0 & 0x40;
          LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            518,
            v28,
            v30,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            6,
            42,
            (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            44,
            v27);
        }
        goto LABEL_58;
      }
      *((_BYTE *)v8 + 64) |= 2u;
      v8[4] = (struct _FLT_FILE_NAME_INFORMATION *)v65;
      v65 = 0;
      goto LABEL_92;
    }
    v78 = (_BYTE)v8[8] & 1;
  }
  tlgDefineProvider_annotation__TlgProjfsTelemetryProviderProv(v22, v20, v21, 0);
  if ( *((_BYTE *)Context + 280) != (_BYTE)v31 )
  {
    v58[0] = v31;
    Name = 0;
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
    v32 = FltGetFileNameInformation(a1, 0x301u, &FileNameInformation);
    LOBYTE(IsFileObjectWithinActiveVirtualizationRoots) = v32;
    if ( v32 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v33) = xmmword_14001A3D0 & 0x40;
        LOBYTE(v34) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          518,
          v33,
          v34,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          6,
          43,
          (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          87,
          v32);
      }
      goto LABEL_100;
    }
    v35 = FltParseFileNameInformation(FileNameInformation);
    LOBYTE(IsFileObjectWithinActiveVirtualizationRoots) = v35;
    if ( v35 < 0 )
    {
LABEL_100:
      if ( v78
        && (int)PrjfRevertInMemoryTombstonesForDirectory(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) < 0
        && ((BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v52) = BYTE1(xmmword_14001A3D0) & 0x20;
        LOBYTE(v53) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          525,
          v52,
          v53,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          13,
          48,
          (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          13,
          IsFileObjectWithinActiveVirtualizationRoots);
      }
      if ( v8 )
      {
        if ( ((_BYTE)v8[8] & 0x40) != 0 )
        {
          v54 = PrjfRemoveInMemoryTombstone(*(PFLT_INSTANCE *)(a2 + 24));
          v57 = v54;
          if ( v54 < 0 )
          {
            if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v55) = xmmword_14001A3D0 & 0x40;
              LOBYTE(v56) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDL(
                518,
                v55,
                v56,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                6,
                49,
                (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
                35,
                v54);
            }
            PrjfTelemetryTombstoneFailureOperation(2, 4, v57);
          }
        }
      }
      v7 = v59;
      goto LABEL_13;
    }
    Name = (__m128i)FileNameInformation->Name;
    v37 = _mm_cvtsi128_si32(Name) - FileNameInformation->FinalComponent.Length;
    v38 = v37 - 2;
    Name.m128i_i16[0] = v37 - 2;
    if ( v37 - 2 == FileNameInformation->Volume.Length )
      v38 = v37;
    Name.m128i_i16[0] = v38;
    v39 = PrjfOpenPlaceHolder(
            *(_QWORD *)(a2 + 24),
            (unsigned int)&Name,
            v36,
            (unsigned int)&FileHandle,
            (__int64)&FileObject,
            (__int64)v58);
    v31 = 0;
    IsFileObjectWithinActiveVirtualizationRoots = v39;
    if ( v39 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = xmmword_14001A3D0 & 0x40;
        LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          518,
          v28,
          v30,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          6,
          44,
          (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          115,
          v39);
        Object = FileObject;
      }
      else
      {
        Object = FileObject;
      }
      goto LABEL_100;
    }
    if ( v58[0] )
    {
      Object = FileObject;
      SetContextFileObject = PrjfGetSetContextFileObject(
                               *(PFLT_INSTANCE *)(a2 + 24),
                               FileObject,
                               0,
                               0,
                               0,
                               (__int64)&v70,
                               (__int64)&v64);
      LOBYTE(IsFileObjectWithinActiveVirtualizationRoots) = SetContextFileObject;
      if ( SetContextFileObject < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v41) = xmmword_14001A3D0 & 0x40;
          LOBYTE(v42) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            518,
            v41,
            v42,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            6,
            45,
            (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            139,
            SetContextFileObject);
        }
        goto LABEL_100;
      }
      *(_BYTE *)(v64 + 44) = 1;
      v43 = (struct _FLT_FILE_NAME_INFORMATION *)Object;
      v44 = PrjfAddInMemoryTombstone(
              *(PFLT_INSTANCE *)(a2 + 24),
              &FileNameInformation->FinalComponent,
              (PFILE_OBJECT)Object,
              0);
      IsFileObjectWithinActiveVirtualizationRoots = v44;
      if ( v44 < 0 )
      {
        if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v45) = xmmword_14001A3D0 & 0x40;
          LOBYTE(v46) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            518,
            v45,
            v46,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            6,
            46,
            (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            159,
            v44);
        }
        PrjfTelemetryTombstoneFailureOperation(3, 4, (unsigned int)IsFileObjectWithinActiveVirtualizationRoots);
        goto LABEL_100;
      }
      *((_BYTE *)v8 + 64) |= 0x40u;
      v8[7] = FileNameInformation;
      FileNameInformation = 0;
      v8[5] = v43;
      v47 = (struct _FLT_FILE_NAME_INFORMATION *)Context;
      Object = 0;
      FltReferenceContext(Context);
      v31 = 0;
      v8[6] = v47;
    }
    else
    {
      Object = FileObject;
    }
  }
LABEL_92:
  LOBYTE(v28) = 0;
  v48 = (struct _EX_RUNDOWN_REF *)Context;
  tlgDefineProvider_annotation__TlgProjfsTelemetryProviderProv(v29, v28, v30, v31);
  if ( ((_BYTE)v8[8] & 0x40) != 0 )
  {
    if ( v8[6] == v50 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v49);
    for ( i = ExAcquireRundownProtection(v48 + 42); !i; i = ExAcquireRundownProtection(v48 + 42) )
      KeWaitForSingleObject(&v48[39], Executive, 0, 0, 0);
    *((_BYTE *)v8 + 64) |= 0x80u;
  }
  *a3 = v8;
  v59 = 5;
  v8 = 0;
  if ( IsFileObjectWithinActiveVirtualizationRoots < 0 )
    goto LABEL_100;
  v7 = 5;
LABEL_13:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  v9 = (void *)v64;
LABEL_18:
  if ( v65 )
    FltClose(v65);
  if ( v69 )
    ObfDereferenceObject(v69);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( Context )
    FltReleaseContext(Context);
  if ( v66 )
    FltReleaseContext(v66);
  if ( v67 )
    FltReleaseContext(v67);
  if ( v8 )
  {
    v14 = v8[4];
    if ( v14 )
      FltClose(v14);
    v15 = v8[3];
    if ( v15 )
      ExFreePoolWithTag(v15, 0x6E664A50u);
    v16 = v8[5];
    if ( v16 )
      ObfDereferenceObject(v16);
    v17 = v8[7];
    if ( v17 )
      FltReleaseFileNameInformation(v17);
    v18 = v8[6];
    if ( v18 )
      FltReleaseContext(v18);
    ExFreeToPagedLookasideList(&stru_14001A840, v8);
  }
  if ( v70 )
    FltReleaseContext(v70);
  if ( v9 )
    FltReleaseContext(v9);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E664A50u);
  return v7;
}

```

## disassembly

```asm
0x140040670  mov     [rsp-8+arg_10], r8
0x140040675  mov     [rsp-8+arg_8], rdx
0x14004067a  mov     [rsp-8+CallbackData], rcx
0x14004067f  push    rbp
0x140040680  push    rbx
0x140040681  push    rsi
0x140040682  push    rdi
0x140040683  push    r12
0x140040685  push    r13
0x140040687  push    r14
0x140040689  push    r15
0x14004068b  lea     rbp, [rsp-48h]
0x140040690  sub     rsp, 148h
0x140040697  xor     r13d, r13d
0x14004069a  lea     r9, [rbp+80h+var_C8]
0x14004069e  xorps   xmm0, xmm0
0x1400406a1  mov     [rbp+80h+Context], r13
0x1400406a5  xor     eax, eax
0x1400406a7  mov     [rbp+80h+var_C8], r13
0x1400406ab  mov     r14, rdx
0x1400406ae  mov     [rbp+80h+Object], rax
0x1400406b2  mov     rdx, [rdx+20h]; FileObject
0x1400406b6  lea     r8, [rbp+80h+Context]
0x1400406ba  mov     [rbp+80h+FileObject], rax
0x1400406be  mov     rdi, rcx
0x1400406c1  lea     rax, [rbp+80h+var_C0]
0x1400406c5  mov     [rbp+80h+var_C0], r13
0x1400406c9  mov     rcx, [r14+18h]; Instance
0x1400406cd  mov     esi, 1
0x1400406d2  movups  xmmword ptr [rbp+80h+var_80.ObjectName], xmm0
0x1400406d6  mov     [rbp+80h+var_FC], esi
0x1400406d9  mov     ebx, r13d
0x1400406dc  mov     [rbp+80h+var_D0], r13
0x1400406e0  mov     r15d, r13d
0x1400406e3  movups  xmmword ptr [rbp+80h+var_80.Length], xmm0
0x1400406e7  mov     [rbp+80h+var_B0], r13
0x1400406eb  movups  xmmword ptr [rbp+80h+var_80+1Ch], xmm0
0x1400406ef  mov     [rbp+80h+FileNameInformation], r13
0x1400406f3  movups  xmmword ptr [rbp+80h+var_50], xmm0
0x1400406f7  mov     [rbp+80h+FileHandle], r13
0x1400406fb  mov     [rbp+80h+var_A8], r13
0x1400406ff  mov     [rbp+80h+var_D8], r13
0x140040703  movups  xmmword ptr [rbp+80h+P], xmm0
0x140040707  mov     qword ptr [rsp+180h+DesiredAccess], rax; Context
0x14004070c  call    PrjfGetContextFileObjectEx
0x140040711  test    al, al
0x140040713  jz      loc_14004087E
0x140040719  lea     r8, [rbp+80h+P]
0x14004071d  mov     rdx, r14
0x140040720  mov     rcx, rdi
0x140040723  call    PrjfIsFileObjectWithinActiveVirtualizationRoots
0x140040728  mov     edi, eax
0x14004072a  test    eax, eax
0x14004072c  js      loc_14004087E
0x140040732  mov     rcx, [rbp+80h+var_C0]
0x140040736  mov     r15, [rbp+80h+var_C8]
0x14004073a  test    rcx, rcx
0x14004073d  jz      short loc_14004079A
0x14004073f  mov     r12b, [rcx+28h]
0x140040743  and     r12b, sil
0x140040746  test    r15, r15
0x140040749  jz      short loc_140040758
0x14004074b  test    dword ptr [r15+28h], 200h
0x140040753  mov     r14b, sil
0x140040756  jnz     short loc_14004075B
0x140040758  mov     r14b, r13b
0x14004075b  test    r15, r15
0x14004075e  jz      short loc_14004076D
0x140040760  test    dword ptr [r15+28h], 800h
0x140040768  mov     cl, sil
0x14004076b  jnz     short loc_140040770
0x14004076d  mov     cl, r13b
0x140040770  mov     [rbp+80h+var_100], cl
0x140040773  test    r15, r15
0x140040776  jz      short loc_140040785
0x140040778  test    dword ptr [r15+28h], 400h
0x140040780  jz      short loc_140040785
0x140040782  mov     r13b, sil
0x140040785  test    r12b, r12b
0x140040788  jnz     short loc_1400407B4
0x14004078a  test    r14b, r14b
0x14004078d  jnz     short loc_1400407B4
0x14004078f  test    cl, cl
0x140040791  jnz     short loc_1400407B4
0x140040793  test    r13b, r13b
0x140040796  jnz     short loc_1400407B4
0x140040798  jmp     short loc_1400407A4
0x14004079a  mov     r12b, r13b
0x14004079d  mov     [rbp+80h+var_100], r13b
0x1400407a1  xor     r14b, r14b
0x1400407a4  mov     rax, [rbp+80h+Context]
0x1400407a8  cmp     [rax+118h], bl
0x1400407ae  jz      loc_14004084D
0x1400407b4  lea     rcx, stru_14001A840; Lookaside
0x1400407bb  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400407c2  nop     dword ptr [rax+rax+00h]
0x1400407c7  mov     rbx, rax
0x1400407ca  xor     eax, eax
0x1400407cc  test    rbx, rbx
0x1400407cf  jnz     loc_1400409E6
0x1400407d5  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400407db  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400407e2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400407e9  setnz   r8b
0x1400407ed  and     dl, 20h
0x1400407f0  jnz     short loc_1400407F7
0x1400407f2  test    r8b, r8b
0x1400407f5  jz      short loc_140040848
0x1400407f7  mov     r9, cs:WPP_GLOBAL_Control
0x1400407fe  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140040805  mov     [rsp+180h+CreateDisposition], 0C000009Ah
0x14004080d  mov     ecx, 205h
0x140040812  mov     [rsp+180h+ShareAccess], 6DCh
0x14004081a  mov     qword ptr [rsp+180h+FileAttributes], rax
0x14004081f  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140040826  mov     r9, [r9+40h]
0x14004082a  mov     [rsp+180h+AllocationSize], rax
0x14004082f  mov     word ptr [rsp+180h+IoStatusBlock], 27h ; '''
0x140040836  mov     dword ptr [rsp+180h+ObjectAttributes], 5
0x14004083e  mov     byte ptr [rsp+180h+DesiredAccess], 2
0x140040843  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140040848  mov     esi, 1
0x14004084d  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140040851  test    rcx, rcx
0x140040854  jz      short loc_140040862
0x140040856  call    cs:__imp_FltClose
0x14004085d  nop     dword ptr [rax+rax+00h]
0x140040862  mov     rax, [rbp+80h+Object]
0x140040866  test    rax, rax
0x140040869  jz      short loc_14004087A
0x14004086b  mov     rcx, rax; Object
0x14004086e  call    cs:__imp_ObfDereferenceObject
0x140040875  nop     dword ptr [rax+rax+00h]
0x14004087a  mov     r15, [rbp+80h+var_D8]
0x14004087e  mov     rcx, [rbp+80h+var_D0]; FileHandle
0x140040882  test    rcx, rcx
0x140040885  jz      short loc_140040893
0x140040887  call    cs:__imp_FltClose
0x14004088e  nop     dword ptr [rax+rax+00h]
0x140040893  mov     rcx, [rbp+80h+var_B0]; Object
0x140040897  test    rcx, rcx
0x14004089a  jz      short loc_1400408A8
0x14004089c  call    cs:__imp_ObfDereferenceObject
0x1400408a3  nop     dword ptr [rax+rax+00h]
0x1400408a8  mov     rcx, [rbp+80h+FileNameInformation]; FileNameInformation
0x1400408ac  test    rcx, rcx
0x1400408af  jz      short loc_1400408BD
0x1400408b1  call    cs:__imp_FltReleaseFileNameInformation
0x1400408b8  nop     dword ptr [rax+rax+00h]
0x1400408bd  mov     rax, [rbp+80h+Context]
0x1400408c1  test    rax, rax
0x1400408c4  jz      short loc_1400408D5
0x1400408c6  mov     rcx, rax; Context
0x1400408c9  call    cs:__imp_FltReleaseContext
0x1400408d0  nop     dword ptr [rax+rax+00h]
0x1400408d5  mov     rcx, [rbp+80h+var_C8]; Context
0x1400408d9  test    rcx, rcx
0x1400408dc  jz      short loc_1400408EA
0x1400408de  call    cs:__imp_FltReleaseContext
0x1400408e5  nop     dword ptr [rax+rax+00h]
0x1400408ea  mov     rcx, [rbp+80h+var_C0]; Context
0x1400408ee  test    rcx, rcx
0x1400408f1  jz      short loc_1400408FF
0x1400408f3  call    cs:__imp_FltReleaseContext
0x1400408fa  nop     dword ptr [rax+rax+00h]
0x1400408ff  test    rbx, rbx
0x140040902  jz      loc_14004098C
0x140040908  mov     rcx, [rbx+20h]; FileHandle
0x14004090c  test    rcx, rcx
0x14004090f  jz      short loc_14004091D
0x140040911  call    cs:__imp_FltClose
0x140040918  nop     dword ptr [rax+rax+00h]
0x14004091d  mov     rcx, [rbx+18h]; P
0x140040921  test    rcx, rcx
0x140040924  jz      short loc_140040937
0x140040926  mov     edx, 6E664A50h; Tag
0x14004092b  call    cs:__imp_ExFreePoolWithTag
0x140040932  nop     dword ptr [rax+rax+00h]
0x140040937  mov     rcx, [rbx+28h]; Object
0x14004093b  test    rcx, rcx
0x14004093e  jz      short loc_14004094C
0x140040940  call    cs:__imp_ObfDereferenceObject
0x140040947  nop     dword ptr [rax+rax+00h]
0x14004094c  mov     rcx, [rbx+38h]; FileNameInformation
0x140040950  test    rcx, rcx
0x140040953  jz      short loc_140040961
0x140040955  call    cs:__imp_FltReleaseFileNameInformation
0x14004095c  nop     dword ptr [rax+rax+00h]
0x140040961  mov     rcx, [rbx+30h]; Context
0x140040965  test    rcx, rcx
0x140040968  jz      short loc_140040976
0x14004096a  call    cs:__imp_FltReleaseContext
0x140040971  nop     dword ptr [rax+rax+00h]
0x140040976  mov     rdx, rbx; Entry
0x140040979  lea     rcx, stru_14001A840; Lookaside
0x140040980  call    cs:__imp_ExFreeToPagedLookasideList
0x140040987  nop     dword ptr [rax+rax+00h]
0x14004098c  mov     rcx, [rbp+80h+var_A8]; Context
0x140040990  test    rcx, rcx
0x140040993  jz      short loc_1400409A1
0x140040995  call    cs:__imp_FltReleaseContext
0x14004099c  nop     dword ptr [rax+rax+00h]
0x1400409a1  test    r15, r15
0x1400409a4  jz      short loc_1400409B5
0x1400409a6  mov     rcx, r15; Context
0x1400409a9  call    cs:__imp_FltReleaseContext
0x1400409b0  nop     dword ptr [rax+rax+00h]
0x1400409b5  mov     rcx, [rbp+80h+P+8]; P
0x1400409b9  test    rcx, rcx
0x1400409bc  jz      short loc_1400409CF
0x1400409be  mov     edx, 6E664A50h; Tag
0x1400409c3  call    cs:__imp_ExFreePoolWithTag
0x1400409ca  nop     dword ptr [rax+rax+00h]
0x1400409cf  mov     eax, esi
0x1400409d1  add     rsp, 148h
0x1400409d8  pop     r15
0x1400409da  pop     r14
0x1400409dc  pop     r13
0x1400409de  pop     r12
0x1400409e0  pop     rdi
0x1400409e1  pop     rsi
0x1400409e2  pop     rbx
0x1400409e3  pop     rbp
0x1400409e4  retn
0x1400409e6  xor     edx, edx; Val
0x1400409e8  mov     [rbp+80h+arg_18], al
0x1400409ee  mov     rcx, rbx; void *
0x1400409f1  lea     r8d, [rdx+48h]; Size
0x1400409f5  call    memset
0x1400409fa  xor     r9d, r9d
0x1400409fd  test    r15, r15
0x140040a00  jz      short loc_140040A0A
0x140040a02  mov     cl, sil
0x140040a05  cmp     [r15], esi
0x140040a08  jz      short loc_140040A0D
0x140040a0a  mov     cl, r9b
0x140040a0d  mov     al, [rbx+40h]
0x140040a10  lea     rsi, WPP_RECORDER_INITIALIZED
0x140040a17  and     al, 0FEh
0x140040a19  mov     r15d, 2
0x140040a1f  or      al, cl
0x140040a21  mov     [rbx+40h], al
0x140040a24  test    r12b, r12b
0x140040a27  jz      loc_140040C83
0x140040a2d  mov     rdx, [rbp+80h+arg_8]
0x140040a34  lea     r8, [rbp+80h+P]
0x140040a38  mov     rcx, [rbp+80h+CallbackData]; CallbackData
0x140040a3f  call    PrjfPrepareForDelete
0x140040a44  mov     edi, eax
0x140040a46  lea     r12d, [r15-1]
0x140040a4a  mov     al, [rbx+40h]
0x140040a4d  xor     r9d, r9d
0x140040a50  and     al, r12b
0x140040a53  mov     [rbp+80h+arg_18], al
0x140040a59  test    edi, edi
0x140040a5b  jns     loc_140040C7B
0x140040a61  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140040a68  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140040a6e  setnz   r8b
0x140040a72  and     dl, 40h
0x140040a75  jnz     short loc_140040A7C
0x140040a77  test    r8b, r8b
0x140040a7a  jz      short loc_140040AC9
0x140040a7c  mov     r9, cs:WPP_GLOBAL_Control
0x140040a83  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140040a8a  mov     [rsp+180h+CreateDisposition], edi
0x140040a8e  mov     ecx, 206h
0x140040a93  mov     [rsp+180h+ShareAccess], 6FDh
0x140040a9b  mov     qword ptr [rsp+180h+FileAttributes], rax
0x140040aa0  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140040aa7  mov     r9, [r9+40h]
0x140040aab  mov     [rsp+180h+AllocationSize], rax
0x140040ab0  mov     word ptr [rsp+180h+IoStatusBlock], 28h ; '('
0x140040ab7  mov     dword ptr [rsp+180h+ObjectAttributes], 6
0x140040abf  mov     byte ptr [rsp+180h+DesiredAccess], r15b
0x140040ac4  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140040ac9  mov     rcx, [rbp+80h+CallbackData]; CallbackData
0x140040ad0  lea     r8, [rbp+80h+FileNameInformation]; FileNameInformation
0x140040ad4  mov     edx, 101h; NameOptions
0x140040ad9  call    cs:__imp_FltGetFileNameInformation
0x140040ae0  nop     dword ptr [rax+rax+00h]
0x140040ae5  xor     ecx, ecx
0x140040ae7  mov     r12d, eax
0x140040aea  test    eax, eax
0x140040aec  jns     short loc_140040B5F
0x140040aee  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140040af5  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140040afb  setnz   r8b
0x140040aff  and     dl, 40h
0x140040b02  jnz     short loc_140040B09
0x140040b04  test    r8b, r8b
0x140040b07  jz      short loc_140040B57
0x140040b09  mov     [rsp+180h+CreateDisposition], r12d
0x140040b0e  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140040b15  mov     [rsp+180h+ShareAccess], 706h
0x140040b1d  mov     qword ptr [rsp+180h+FileAttributes], rax
0x140040b22  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140040b29  mov     [rsp+180h+AllocationSize], rax
0x140040b2e  mov     word ptr [rsp+180h+IoStatusBlock], 29h ; ')'
0x140040b35  mov     r9, cs:WPP_GLOBAL_Control
  ... truncated ...
```
