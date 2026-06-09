# UnionFs::Utils::GetHardLinkPaths(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &,bool)

- ea: `0x14006e54c`
- end: `0x14006ed24`
- name: `?GetHardLinkPaths@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAVStackEventTracer@2@_N@Z`
- size: `2008`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001d5d0`
- `0x14006b78c`

## callees

- `0x14001c820`
- `0x14001f41c`
- `0x140043d5c`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140067bb8`
- `0x14006e54c`
- `0x140079f68`
- `0x14007a02c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006e5b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e5ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e657`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e71a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ea58`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ebc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ec54`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ecd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e5b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e5ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e657`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e71a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ea58`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ebc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ec54`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ecd1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006e7c0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006e7c0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006ea12`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006ea12`
- `ntoskrnl!PsGetHostSilo` at `0x14006e831`
- `ntoskrnl!PsGetHostSilo` at `0x14006e831`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006e7a9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006e7a9`
- `ntoskrnl!ObfDereferenceObject` at `0x14006e8fc`
- `ntoskrnl!ObfDereferenceObject` at `0x14006e9a0`
- `ntoskrnl!ObfDereferenceObject` at `0x14006eab6`
- `ntoskrnl!ObfDereferenceObject` at `0x14006e8fc`
- `ntoskrnl!ObfDereferenceObject` at `0x14006e9a0`
- `ntoskrnl!ObfDereferenceObject` at `0x14006eab6`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006e69e`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006e934`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006e69e`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006e934`
- `FLTMGR!FltCreateFileEx2` at `0x14006e8d5`
- `FLTMGR!FltCreateFileEx2` at `0x14006e8d5`
- `FLTMGR!FltClose` at `0x14006e85d`
- `FLTMGR!FltClose` at `0x14006e9b5`
- `FLTMGR!FltClose` at `0x14006eacb`
- `FLTMGR!FltClose` at `0x14006e85d`
- `FLTMGR!FltClose` at `0x14006e9b5`
- `FLTMGR!FltClose` at `0x14006eacb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006e6c5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006e709`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006e95b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006eaed`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006eb5e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ebdd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ebf6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ec6d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ec86`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006eca7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ecc0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006e6c5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006e709`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006e95b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006eaed`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006eb5e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ebdd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ebf6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ec6d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ec86`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006eca7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ecc0`
- `FLTMGR!FltQueryInformationFile` at `0x14006e5ff`
- `FLTMGR!FltQueryInformationFile` at `0x14006e5ff`

## string_xrefs

- `0x14006ece1`: `ORIGIN: Allocating file links buffer`
- `0x14006e62b`: `API: Querying hard link info`
- `0x14006e63c`: `UnionFs::Utils::GetHardLinkPaths`
- `0x14006e6e6`: `UnionFs::Utils::GetHardLinkPaths`
- `0x14006ea8d`: `UnionFs::Utils::GetHardLinkPaths`
- `0x14006eb2f`: `UnionFs::Utils::GetHardLinkPaths`
- `0x14006eb87`: `UnionFs::Utils::GetHardLinkPaths`
- `0x14006ec1a`: `UnionFs::Utils::GetHardLinkPaths`
- `0x14006ecf4`: `UnionFs::Utils::GetHardLinkPaths`
- `0x14006e6d5`: `API: Opening parent directory`
- `0x14006eb06`: `API: Opening parent directory`
- `0x14006ec09`: `PUSH: Building hard link name`
- `0x14006eb74`: `ORIGIN: Pushing link name`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::GetHardLinkPaths(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        struct _FILE_OBJECT *a3,
        struct UnionFs::StackEventTracer *a4)
{
  struct _DEVICE_OBJECT *v6; // rdx
  __int64 v9; // r8
  ULONG *v10; // rbx
  int v11; // r15d
  ULONG v12; // edi
  ULONG **v13; // rax
  ULONG *v14; // r14
  NTSTATUS InformationFile; // edi
  ULONG *v16; // rcx
  unsigned int FileNameInformationUnsafe; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v19; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v20; // rcx
  PFILE_OBJECT v21; // r12
  unsigned int *v22; // rbx
  __int64 v23; // r15
  USHORT v24; // ax
  __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  void *v27; // rcx
  struct _UNICODE_STRING *v28; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v29; // rcx
  PFILE_OBJECT v30; // rcx
  struct _UNICODE_STRING *v31; // rdi
  struct _UNICODE_STRING *v32; // rdx
  __int64 v33; // rax
  const char *v34; // rax
  __int64 v35; // r8
  struct _UNICODE_STRING *v36; // rdx
  PFILE_OBJECT v37; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v38; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v39; // rcx
  struct _UNICODE_STRING *v40; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v41; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v42; // rcx
  struct _UNICODE_STRING *v43; // rdx
  struct _UNICODE_STRING *v44; // rdi
  struct _FLT_FILE_NAME_INFORMATION *v45; // rcx
  struct _UNICODE_STRING *v46; // rdx
  struct _UNICODE_STRING *v47; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v48; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v49; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v50; // rcx
  const char *LengthReturned; // [rsp+28h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION v52; // [rsp+80h] [rbp-80h] BYREF
  PFLT_FILE_NAME_INFORMATION v53; // [rsp+88h] [rbp-78h] BYREF
  PVOID P; // [rsp+90h] [rbp-70h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation[2]; // [rsp+98h] [rbp-68h] BYREF
  char v56; // [rsp+A8h] [rbp-58h]
  HANDLE FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING v59; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING v60; // [rsp+D8h] [rbp-28h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+E8h] [rbp-18h] BYREF
  __int64 HostSilo; // [rsp+108h] [rbp+8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+110h] [rbp+10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+140h] [rbp+40h] BYREF
  PFILE_OBJECT FileObjecta; // [rsp+1B0h] [rbp+B0h] BYREF

  FileObjecta = a3;
  v6 = *(struct _DEVICE_OBJECT **)&a3->Type;
  v9 = ((__int64)a3->DeviceObject - *(_QWORD *)&a3->Type) >> 3;
  a3->DeviceObject = v6;
  utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
    Instance,
    v6,
    v9);
  v10 = 0;
  v11 = 0;
  v12 = 32;
  while ( 1 )
  {
    v13 = (ULONG **)utl::make_unique_pool<enum gsl::byte [0],256,1902921301,0>(&P, v12);
    v14 = *v13;
    *v13 = 0;
    if ( v10 )
      ExFreePoolWithTag(v10, 0);
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( !v14 )
    {
      FileNameInformationUnsafe = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x3A1002107E0LL,
        (unsigned __int64)"UnionFs::Utils::GetHardLinkPaths",
        "ORIGIN: Allocating file links buffer",
        LengthReturned);
      return FileNameInformationUnsafe;
    }
    v10 = v14;
    InformationFile = FltQueryInformationFile(Instance, FileObject, v14, v12, FileHardLinkInformation, 0);
    if ( InformationFile != -2147483643 || v11 )
      break;
    v12 = *v14;
    v11 = 1;
  }
  if ( InformationFile < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)InformationFile,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x39E002107F6LL,
      (unsigned __int64)"UnionFs::Utils::GetHardLinkPaths",
      "API: Querying hard link info",
      LengthReturned);
    v16 = v14;
LABEL_12:
    ExFreePoolWithTag(v16, 0);
    return (unsigned int)InformationFile;
  }
  if ( v14[1] <= 1 )
  {
    FileNameInformationUnsafe = 0;
    goto LABEL_21;
  }
  v56 = 1;
  v52 = 0;
  FileNameInformation[0] = (PFLT_FILE_NAME_INFORMATION)&v52;
  FileNameInformation[1] = 0;
  FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, Instance, 0x101u, &FileNameInformation[1]);
  if ( v56 )
  {
    v19 = *(struct _FLT_FILE_NAME_INFORMATION **)FileNameInformation[0];
    *(_QWORD *)FileNameInformation[0] = FileNameInformation[1];
    if ( v19 )
      FltReleaseFileNameInformation(v19);
  }
  if ( (FileNameInformationUnsafe & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)FileNameInformationUnsafe,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x3E60021080FLL,
      (unsigned __int64)"UnionFs::Utils::GetHardLinkPaths",
      "API: Opening parent directory",
      LengthReturned);
    v20 = v52;
    v52 = 0;
    if ( v20 )
      FltReleaseFileNameInformation(v20);
LABEL_21:
    ExFreePoolWithTag(v14, 0);
    return FileNameInformationUnsafe;
  }
  v21 = FileObjecta;
  v22 = v14 + 2;
  v53 = 0;
  v60 = 0;
  v23 = 0;
  while ( v22 )
  {
    v24 = 2 * *((_WORD *)v22 + 8);
    *(_DWORD *)(&v59.MaximumLength + 1) = 0;
    v59.Length = v24;
    v59.MaximumLength = v24;
    v59.Buffer = (PWSTR)(v22 + 5);
    if ( v23 != *((_QWORD *)v22 + 1) )
    {
      FsFltWil::MakeUniqueUnicodeString(&DestinationString, (unsigned __int16)(v52->Volume.Length + 10), 1279685446);
      if ( !DestinationString.Buffer )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x43D0021082CLL,
          (unsigned __int64)"UnionFs::Utils::GetHardLinkPaths",
          "ORIGIN: Allocating parent file ID string",
          LengthReturned);
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v40);
        v41 = v53;
        v53 = 0;
        if ( v41 )
          FltReleaseFileNameInformation(v41);
        v42 = v52;
        v52 = 0;
        goto LABEL_70;
      }
      RtlCopyUnicodeString(&DestinationString, &v52->Volume);
      RtlAppendUnicodeToString(&DestinationString, L"\\");
      v25 = *((_QWORD *)v22 + 1);
      v26 = (unsigned __int64)DestinationString.Length >> 1;
      *(_QWORD *)&DestinationString.Buffer[v26] = v25;
      DestinationString.Length += 8;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      memset(&DriverContext, 0, sizeof(DriverContext));
      HostSilo = 1;
      *(_QWORD *)&ObjectAttributes.Attributes = 512;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      FileHandle = 0;
      FileObjecta = 0;
      IoStatusBlock = 0;
      DriverContext.Size = 40;
      HostSilo = PsGetHostSilo(v25, v26);
      FileNameInformation[0] = (PFLT_FILE_NAME_INFORMATION)&FileObjecta;
      FileNameInformation[1] = 0;
      v56 = 1;
      if ( FileHandle )
        FltClose(FileHandle);
      FileHandle = 0;
      InformationFile = FltCreateFileEx2(
                          *(PFLT_FILTER *)UnionFs::g_FilterState,
                          Instance,
                          &FileHandle,
                          (PFILE_OBJECT *)&FileNameInformation[1],
                          0x80u,
                          &ObjectAttributes,
                          &IoStatusBlock,
                          0,
                          0,
                          7u,
                          1u,
                          0x2021u,
                          0,
                          0,
                          0x800u,
                          &DriverContext);
      if ( v56 )
      {
        v27 = *(void **)FileNameInformation[0];
        *(_QWORD *)FileNameInformation[0] = FileNameInformation[1];
        if ( v27 )
          ObfDereferenceObject(v27);
      }
      if ( InformationFile < 0 )
      {
        v34 = "API: Opening parent directory";
        v35 = 0x39F00210855LL;
LABEL_52:
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)InformationFile,
          (int)a4,
          (struct UnionFs::StackEventTracer *)v35,
          (unsigned __int64)"UnionFs::Utils::GetHardLinkPaths",
          v34,
          LengthReturned);
        v37 = FileObjecta;
        FileObjecta = 0;
        if ( v37 )
          ObfDereferenceObject(v37);
        if ( FileHandle )
          FltClose(FileHandle);
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v36);
        v38 = v53;
        v53 = 0;
        if ( v38 )
          FltReleaseFileNameInformation(v38);
        v39 = v52;
        v52 = 0;
LABEL_80:
        if ( v39 )
          FltReleaseFileNameInformation(v39);
LABEL_82:
        v16 = v14;
        goto LABEL_12;
      }
      FileNameInformation[0] = (PFLT_FILE_NAME_INFORMATION)&v53;
      FileNameInformation[1] = 0;
      v56 = 1;
      InformationFile = FltGetFileNameInformationUnsafe(FileObjecta, Instance, 0x101u, &FileNameInformation[1]);
      if ( v56 )
      {
        v28 = (struct _UNICODE_STRING *)FileNameInformation[1];
        v29 = *(struct _FLT_FILE_NAME_INFORMATION **)FileNameInformation[0];
        *(_QWORD *)FileNameInformation[0] = FileNameInformation[1];
        if ( v29 )
          FltReleaseFileNameInformation(v29);
      }
      if ( InformationFile < 0 )
      {
        v34 = "API: Querying source name";
        v35 = 0x3A00021085ELL;
        goto LABEL_52;
      }
      v60.Length = v53->Name.Length;
      v60.MaximumLength = v60.Length;
      v60.Buffer = v53->Name.Buffer;
      v30 = FileObjecta;
      v23 = *((_QWORD *)v22 + 1);
      FileObjecta = 0;
      if ( v30 )
        ObfDereferenceObject(v30);
      if ( FileHandle )
        FltClose(FileHandle);
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v28);
    }
    P = 0;
    InformationFile = UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(&v60, &v59, a4);
    if ( InformationFile < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)InformationFile,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x3D200210870LL,
        (unsigned __int64)"UnionFs::Utils::GetHardLinkPaths",
        "PUSH: Building hard link name",
        LengthReturned);
      v47 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v47, v46);
        ExFreePoolWithTag(v47, 0);
      }
      v48 = v53;
      v53 = 0;
      if ( v48 )
        FltReleaseFileNameInformation(v48);
      v39 = v52;
      v52 = 0;
      goto LABEL_80;
    }
    v31 = (struct _UNICODE_STRING *)P;
    *(_OWORD *)FileNameInformation = *(_OWORD *)P;
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)FileNameInformation, &v52->Name, 0) )
      goto LABEL_92;
    if ( !(unsigned __int8)utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>::push_back(
                             v21,
                             &P) )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x3A20021087FLL,
        (unsigned __int64)"UnionFs::Utils::GetHardLinkPaths",
        "ORIGIN: Pushing link name",
        LengthReturned);
      v44 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v44, v43);
        ExFreePoolWithTag(v44, 0);
      }
      v45 = v53;
      v53 = 0;
      if ( v45 )
        FltReleaseFileNameInformation(v45);
      v42 = v52;
      v52 = 0;
LABEL_70:
      if ( v42 )
        FltReleaseFileNameInformation(v42);
      InformationFile = -1073741670;
      goto LABEL_82;
    }
    v31 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
LABEL_92:
      if ( !LOBYTE(v31[1].Length) )
        *v31 = 0;
      FsFltWil::Details::FreeUnicodeString(v31, v32);
      ExFreePoolWithTag(v31, 0);
    }
    v33 = *v22;
    if ( (_DWORD)v33 )
      v22 = (unsigned int *)((char *)v22 + v33);
    else
      v22 = 0;
  }
  v49 = v53;
  v53 = 0;
  if ( v49 )
    FltReleaseFileNameInformation(v49);
  v50 = v52;
  v52 = 0;
  if ( v50 )
    FltReleaseFileNameInformation(v50);
  ExFreePoolWithTag(v14, 0);
  return 0;
}

```

## disassembly

```asm
0x14006e54c  mov     [rsp-8+FileObject], r8
0x14006e551  push    rbp
0x14006e552  push    rbx
0x14006e553  push    rsi
0x14006e554  push    rdi
0x14006e555  push    r12
0x14006e557  push    r13
0x14006e559  push    r14
0x14006e55b  push    r15
0x14006e55d  lea     rbp, [rsp-58h]
0x14006e562  sub     rsp, 158h
0x14006e569  mov     rax, r8
0x14006e56c  mov     r12, rdx
0x14006e56f  mov     rdx, [r8]
0x14006e572  mov     rsi, r9
0x14006e575  mov     r8, [r8+8]
0x14006e579  mov     r13, rcx
0x14006e57c  sub     r8, rdx
0x14006e57f  sar     r8, 3
0x14006e583  mov     [rax+8], rdx
0x14006e587  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006e58c  xor     ebx, ebx
0x14006e58e  xor     r15d, r15d
0x14006e591  lea     edi, [rbx+20h]
0x14006e594  mov     edx, edi
0x14006e596  lea     rcx, [rbp+90h+P]
0x14006e59a  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0HBGMEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1902921301,0>(unsigned __int64)
0x14006e59f  mov     r14, [rax]
0x14006e5a2  mov     qword ptr [rax], 0
0x14006e5a9  test    rbx, rbx
0x14006e5ac  jz      short loc_14006E5BF
0x14006e5ae  xor     edx, edx; Tag
0x14006e5b0  mov     rcx, rbx; P
0x14006e5b3  call    cs:__imp_ExFreePoolWithTag
0x14006e5ba  nop     dword ptr [rax+rax+00h]
0x14006e5bf  mov     rcx, [rbp+90h+P]; P
0x14006e5c3  test    rcx, rcx
0x14006e5c6  jz      short loc_14006E5D6
0x14006e5c8  xor     edx, edx; Tag
0x14006e5ca  call    cs:__imp_ExFreePoolWithTag
0x14006e5d1  nop     dword ptr [rax+rax+00h]
0x14006e5d6  test    r14, r14
0x14006e5d9  jz      loc_14006ECE1
0x14006e5df  mov     [rsp+190h+LengthReturned], 0; char *
0x14006e5e8  mov     r9d, edi; Length
0x14006e5eb  mov     r8, r14; FileInformation
0x14006e5ee  mov     [rsp+190h+FileInformationClass], 2Eh ; '.'; FileInformationClass
0x14006e5f6  mov     rdx, r12; FileObject
0x14006e5f9  mov     rcx, r13; Instance
0x14006e5fc  mov     rbx, r14
0x14006e5ff  call    cs:__imp_FltQueryInformationFile
0x14006e606  nop     dword ptr [rax+rax+00h]
0x14006e60b  mov     edi, eax
0x14006e60d  cmp     eax, 80000005h
0x14006e612  jnz     short loc_14006E627
0x14006e614  test    r15d, r15d
0x14006e617  jnz     short loc_14006E627
0x14006e619  mov     edi, [r14]
0x14006e61c  mov     r15d, 1
0x14006e622  jmp     loc_14006E594
0x14006e627  test    edi, edi
0x14006e629  jns     short loc_14006E66A
0x14006e62b  lea     rax, aApiQueryingHar; "API: Querying hard link info"
0x14006e632  mov     r8, 39E002107F6h; struct UnionFs::StackEventTracer *
0x14006e63c  lea     r9, aUnionfsUtilsGe_10; "UnionFs::Utils::GetHardLinkPaths"
0x14006e643  mov     qword ptr [rsp+190h+FileInformationClass], rax; char *
0x14006e648  mov     rdx, rsi; int
0x14006e64b  mov     ecx, edi; this
0x14006e64d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e652  mov     rcx, rbx; P
0x14006e655  xor     edx, edx; Tag
0x14006e657  call    cs:__imp_ExFreePoolWithTag
0x14006e65e  nop     dword ptr [rax+rax+00h]
0x14006e663  mov     eax, edi
0x14006e665  jmp     loc_14006ED0F
0x14006e66a  cmp     dword ptr [r14+4], 1
0x14006e66f  ja      short loc_14006E678
0x14006e671  xor     ebx, ebx
0x14006e673  jmp     loc_14006E715
0x14006e678  xor     edi, edi
0x14006e67a  mov     [rbp+90h+var_E8], 1
0x14006e67e  lea     rax, [rbp+90h+var_110]
0x14006e682  mov     [rbp+90h+var_110], rdi
0x14006e686  lea     r9, [rbp+90h+FileNameInformation+8]; FileNameInformation
0x14006e68a  mov     [rbp+90h+FileNameInformation], rax
0x14006e68e  mov     r8d, 101h; NameOptions
0x14006e694  mov     [rbp+90h+FileNameInformation+8], rdi
0x14006e698  mov     rdx, r13; Instance
0x14006e69b  mov     rcx, r12; FileObject
0x14006e69e  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14006e6a5  nop     dword ptr [rax+rax+00h]
0x14006e6aa  mov     ebx, eax
0x14006e6ac  cmp     [rbp+90h+var_E8], dil
0x14006e6b0  jz      short loc_14006E6D1
0x14006e6b2  mov     r8, [rbp+90h+FileNameInformation]
0x14006e6b6  mov     rdx, [rbp+90h+FileNameInformation+8]
0x14006e6ba  mov     rcx, [r8]; FileNameInformation
0x14006e6bd  mov     [r8], rdx
0x14006e6c0  test    rcx, rcx
0x14006e6c3  jz      short loc_14006E6D1
0x14006e6c5  call    cs:__imp_FltReleaseFileNameInformation
0x14006e6cc  nop     dword ptr [rax+rax+00h]
0x14006e6d1  test    ebx, ebx
0x14006e6d3  jns     short loc_14006E72B
0x14006e6d5  lea     rax, aApiOpeningPare_0; "API: Opening parent directory"
0x14006e6dc  mov     r8, 3E60021080Fh; struct UnionFs::StackEventTracer *
0x14006e6e6  lea     r9, aUnionfsUtilsGe_10; "UnionFs::Utils::GetHardLinkPaths"
0x14006e6ed  mov     qword ptr [rsp+190h+FileInformationClass], rax; char *
0x14006e6f2  mov     rdx, rsi; int
0x14006e6f5  mov     ecx, ebx; this
0x14006e6f7  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e6fc  mov     rcx, [rbp+90h+var_110]; FileNameInformation
0x14006e700  mov     [rbp+90h+var_110], rdi
0x14006e704  test    rcx, rcx
0x14006e707  jz      short loc_14006E715
0x14006e709  call    cs:__imp_FltReleaseFileNameInformation
0x14006e710  nop     dword ptr [rax+rax+00h]
0x14006e715  xor     edx, edx; Tag
0x14006e717  mov     rcx, r14; P
0x14006e71a  call    cs:__imp_ExFreePoolWithTag
0x14006e721  nop     dword ptr [rax+rax+00h]
0x14006e726  jmp     loc_14006ED0D
0x14006e72b  mov     r12, [rbp+90h+FileObject]
0x14006e732  lea     rbx, [r14+8]
0x14006e736  xorps   xmm0, xmm0
0x14006e739  mov     [rbp+90h+var_108], rdi
0x14006e73d  movups  xmmword ptr [rbp+90h+var_B8.Length], xmm0
0x14006e741  mov     r15, rdi
0x14006e744  test    rbx, rbx
0x14006e747  jz      loc_14006EC9A
0x14006e74d  movzx   eax, word ptr [rbx+10h]
0x14006e751  xorps   xmm0, xmm0
0x14006e754  add     ax, ax
0x14006e757  movups  xmmword ptr [rbp+90h+var_C8.Length], xmm0
0x14006e75b  mov     [rbp+90h+var_C8.Length], ax
0x14006e75f  mov     [rbp+90h+var_C8.MaximumLength], ax
0x14006e763  lea     rax, [rbx+14h]
0x14006e767  mov     [rbp+90h+var_C8.Buffer], rax
0x14006e76b  cmp     r15, [rbx+8]
0x14006e76f  jz      loc_14006E9CA
0x14006e775  mov     rax, [rbp+90h+var_110]
0x14006e779  lea     rcx, [rbp+90h+DestinationString]
0x14006e77d  mov     r8d, 4C467346h
0x14006e783  movzx   edx, word ptr [rax+18h]
0x14006e787  add     dx, 0Ah
0x14006e78b  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14006e790  xor     r15d, r15d
0x14006e793  cmp     [rbp+90h+DestinationString.Buffer], r15
0x14006e797  jz      loc_14006EB1C
0x14006e79d  mov     rdx, [rbp+90h+var_110]
0x14006e7a1  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x14006e7a5  add     rdx, 18h; SourceString
0x14006e7a9  call    cs:__imp_RtlCopyUnicodeString
0x14006e7b0  nop     dword ptr [rax+rax+00h]
0x14006e7b5  lea     rdx, Source; "\\"
0x14006e7bc  lea     rcx, [rbp+90h+DestinationString]; Destination
0x14006e7c0  call    cs:__imp_RtlAppendUnicodeToString
0x14006e7c7  nop     dword ptr [rax+rax+00h]
0x14006e7cc  movzx   edx, [rbp+90h+DestinationString.Length]
0x14006e7d0  xorps   xmm1, xmm1
0x14006e7d3  mov     rax, [rbp+90h+DestinationString.Buffer]
0x14006e7d7  xorps   xmm0, xmm0
0x14006e7da  mov     rcx, [rbx+8]
0x14006e7de  shr     rdx, 1
0x14006e7e1  mov     [rax+rdx*2], rcx
0x14006e7e5  lea     rax, [rbp+90h+DestinationString]
0x14006e7e9  add     [rbp+90h+DestinationString.Length], 8
0x14006e7ee  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x14006e7f2  lea     eax, [r15+28h]
0x14006e7f6  lea     edi, [rax-27h]
0x14006e7f9  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x14006e801  movups  xmmword ptr [rbp+90h+var_A8.Size], xmm1
0x14006e805  mov     [rbp+90h+var_88], rdi
0x14006e809  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], 200h
0x14006e811  mov     [rbp+90h+ObjectAttributes.RootDirectory], r15
0x14006e815  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x14006e81a  mov     [rbp+90h+FileHandle], r15
0x14006e81e  mov     [rbp+90h+FileObject], r15
0x14006e825  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x14006e829  mov     [rbp+90h+var_A8.Size], ax
0x14006e82d  movups  xmmword ptr [rbp+90h+var_A8.DeviceObjectHint], xmm1
0x14006e831  call    cs:__imp_PsGetHostSilo
0x14006e838  nop     dword ptr [rax+rax+00h]
0x14006e83d  mov     rcx, [rbp+90h+FileHandle]; FileHandle
0x14006e841  mov     [rbp+90h+var_88], rax
0x14006e845  lea     rax, [rbp+90h+FileObject]
0x14006e84c  mov     [rbp+90h+FileNameInformation], rax
0x14006e850  mov     [rbp+90h+FileNameInformation+8], r15
0x14006e854  mov     [rbp+90h+var_E8], dil
0x14006e858  test    rcx, rcx
0x14006e85b  jz      short loc_14006E869
0x14006e85d  call    cs:__imp_FltClose
0x14006e864  nop     dword ptr [rax+rax+00h]
0x14006e869  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006e870  lea     rax, [rbp+90h+var_A8]
0x14006e874  mov     [rsp+190h+DriverContext], rax; DriverContext
0x14006e879  lea     r9, [rbp+90h+FileNameInformation+8]; FileObject
0x14006e87d  mov     [rsp+190h+Flags], 800h; Flags
0x14006e885  lea     rax, [rbp+90h+var_50]
0x14006e889  mov     [rsp+190h+EaLength], r15d; EaLength
0x14006e88e  lea     r8, [rbp+90h+FileHandle]; FileHandle
0x14006e892  mov     [rsp+190h+EaBuffer], r15; EaBuffer
0x14006e897  mov     rdx, r13; Instance
0x14006e89a  mov     [rsp+190h+CreateOptions], 2021h; CreateOptions
0x14006e8a2  mov     [rsp+190h+CreateDisposition], edi; CreateDisposition
0x14006e8a6  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x14006e8ae  mov     [rsp+190h+FileAttributes], r15d; FileAttributes
0x14006e8b3  mov     [rsp+190h+AllocationSize], r15; AllocationSize
0x14006e8b8  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x14006e8bd  lea     rax, [rbp+90h+ObjectAttributes]
0x14006e8c1  mov     [rbp+90h+FileHandle], r15
0x14006e8c5  mov     rcx, [rcx]; Filter
0x14006e8c8  mov     [rsp+190h+LengthReturned], rax; char *
0x14006e8cd  mov     [rsp+190h+FileInformationClass], 80h; DesiredAccess
0x14006e8d5  call    cs:__imp_FltCreateFileEx2
0x14006e8dc  nop     dword ptr [rax+rax+00h]
0x14006e8e1  mov     edi, eax
0x14006e8e3  cmp     [rbp+90h+var_E8], r15b
0x14006e8e7  jz      short loc_14006E908
0x14006e8e9  mov     r8, [rbp+90h+FileNameInformation]
0x14006e8ed  mov     rdx, [rbp+90h+FileNameInformation+8]
0x14006e8f1  mov     rcx, [r8]; Object
0x14006e8f4  mov     [r8], rdx
0x14006e8f7  test    rcx, rcx
0x14006e8fa  jz      short loc_14006E908
0x14006e8fc  call    cs:__imp_ObfDereferenceObject
0x14006e903  nop     dword ptr [rax+rax+00h]
0x14006e908  test    edi, edi
0x14006e90a  js      loc_14006EB06
0x14006e910  mov     rcx, [rbp+90h+FileObject]; FileObject
0x14006e917  lea     rax, [rbp+90h+var_108]
0x14006e91b  lea     r9, [rbp+90h+FileNameInformation+8]; FileNameInformation
0x14006e91f  mov     [rbp+90h+FileNameInformation], rax
0x14006e923  mov     r8d, 101h; NameOptions
0x14006e929  mov     [rbp+90h+FileNameInformation+8], r15
0x14006e92d  mov     rdx, r13; Instance
0x14006e930  mov     [rbp+90h+var_E8], 1
0x14006e934  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14006e93b  nop     dword ptr [rax+rax+00h]
0x14006e940  mov     edi, eax
0x14006e942  cmp     [rbp+90h+var_E8], r15b
0x14006e946  jz      short loc_14006E967
0x14006e948  mov     r8, [rbp+90h+FileNameInformation]
0x14006e94c  mov     rdx, [rbp+90h+FileNameInformation+8]
0x14006e950  mov     rcx, [r8]; FileNameInformation
0x14006e953  mov     [r8], rdx
0x14006e956  test    rcx, rcx
0x14006e959  jz      short loc_14006E967
0x14006e95b  call    cs:__imp_FltReleaseFileNameInformation
0x14006e962  nop     dword ptr [rax+rax+00h]
0x14006e967  test    edi, edi
0x14006e969  js      loc_14006EA7C
0x14006e96f  mov     rax, [rbp+90h+var_108]
0x14006e973  xor     edi, edi
0x14006e975  movzx   ecx, word ptr [rax+8]
0x14006e979  mov     [rbp+90h+var_B8.Length], cx
0x14006e97d  mov     [rbp+90h+var_B8.MaximumLength], cx
0x14006e981  mov     rcx, [rax+10h]
0x14006e985  mov     [rbp+90h+var_B8.Buffer], rcx
0x14006e989  mov     rcx, [rbp+90h+FileObject]; Object
0x14006e990  mov     r15, [rbx+8]
0x14006e994  mov     [rbp+90h+FileObject], rdi
0x14006e99b  test    rcx, rcx
0x14006e99e  jz      short loc_14006E9AC
0x14006e9a0  call    cs:__imp_ObfDereferenceObject
0x14006e9a7  nop     dword ptr [rax+rax+00h]
0x14006e9ac  mov     rcx, [rbp+90h+FileHandle]; FileHandle
0x14006e9b0  test    rcx, rcx
0x14006e9b3  jz      short loc_14006E9C1
0x14006e9b5  call    cs:__imp_FltClose
0x14006e9bc  nop     dword ptr [rax+rax+00h]
0x14006e9c1  lea     rcx, [rbp+90h+DestinationString]; UnicodeString
0x14006e9c5  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006e9ca  mov     r8, [rbp+90h+var_108]
0x14006e9ce  lea     r9, [rbp+90h+P]
0x14006e9d2  lea     rdx, [rbp+90h+var_C8]; struct _UNICODE_STRING *
0x14006e9d6  mov     [rbp+90h+P], rdi
0x14006e9da  lea     rcx, [rbp+90h+var_B8]; struct _UNICODE_STRING *
0x14006e9de  mov     qword ptr [rsp+190h+FileInformationClass], rsi; struct UnionFs::StackEventTracer *
0x14006e9e3  movzx   r8d, word ptr [r8+18h]
0x14006e9e8  call    ?AllocAndInitWithCombinedPaths@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@0GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithCombinedPaths(_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14006e9ed  mov     edi, eax
0x14006e9ef  test    eax, eax
0x14006e9f1  js      loc_14006EC09
0x14006e9f7  mov     rdx, [rbp+90h+var_110]
0x14006e9fb  lea     rcx, [rbp+90h+FileNameInformation]; String1
0x14006e9ff  mov     rdi, [rbp+90h+P]
0x14006ea03  add     rdx, 8; String2
0x14006ea07  xor     r8d, r8d; CaseInSensitive
0x14006ea0a  movups  xmm0, xmmword ptr [rdi]
0x14006ea0d  movdqu  xmmword ptr [rbp+90h+FileNameInformation], xmm0
0x14006ea12  call    cs:__imp_RtlEqualUnicodeString
0x14006ea19  nop     dword ptr [rax+rax+00h]
0x14006ea1e  test    al, al
0x14006ea20  jnz     short loc_14006EA3F
0x14006ea22  lea     rdx, [rbp+90h+P]
0x14006ea26  mov     rcx, r12
0x14006ea29  call    ?push_back@?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@2@@Z; utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>::push_back(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&)
0x14006ea2e  test    al, al
0x14006ea30  jz      loc_14006EB74
  ... truncated ...
```
