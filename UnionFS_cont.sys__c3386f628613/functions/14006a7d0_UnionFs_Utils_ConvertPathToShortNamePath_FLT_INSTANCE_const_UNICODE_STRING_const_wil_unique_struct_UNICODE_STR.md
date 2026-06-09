# UnionFs::Utils::ConvertPathToShortNamePath(_FLT_INSTANCE const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x14006a7d0`
- end: `0x14006ae43`
- name: `?ConvertPathToShortNamePath@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `1651`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PCUNICODE_STRING SourceString, PUNICODE_STRING UnicodeString, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400449c0`

## callees

- `0x140056a50`
- `0x140056a88`
- `0x140056ac4`
- `0x140056afc`
- `0x14006a7d0`
- `0x14006de98`
- `0x140075254`
- `0x140079c48`
- `0x140079d0c`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006abee`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006ac57`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006abee`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006ac57`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006ac0c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006ac78`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006ac0c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006ac78`
- `ntoskrnl!PsGetHostSilo` at `0x14006aa9a`
- `ntoskrnl!PsGetHostSilo` at `0x14006aa9a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a875`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a9a8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a875`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006a9a8`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ab6e`
- `ntoskrnl!ObfDereferenceObject` at `0x14006acb4`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ad7b`
- `ntoskrnl!ObfDereferenceObject` at `0x14006adf1`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ab6e`
- `ntoskrnl!ObfDereferenceObject` at `0x14006acb4`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ad7b`
- `ntoskrnl!ObfDereferenceObject` at `0x14006adf1`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006abad`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006abad`
- `FLTMGR!FltCreateFileEx2` at `0x14006ab48`
- `FLTMGR!FltCreateFileEx2` at `0x14006ab48`
- `FLTMGR!FltClose` at `0x14006acc9`
- `FLTMGR!FltClose` at `0x14006ad90`
- `FLTMGR!FltClose` at `0x14006ae06`
- `FLTMGR!FltClose` at `0x14006acc9`
- `FLTMGR!FltClose` at `0x14006ad90`
- `FLTMGR!FltClose` at `0x14006ae06`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006abd3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ac9b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ad62`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006abd3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ac9b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ad62`

## string_xrefs

- `0x14006a923`: `ORIGIN: Allocating short path string`
- `0x14006a967`: `ORIGIN: Allocating pathToOpen`
- `0x14006a936`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006a97a`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006a9e8`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006ad3f`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006adc7`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006aa76`: `pathToOpen.Length <= pathToOpen.MaximumLength`
- `0x14006ac1e`: `Couldn't append name component`
- `0x14006ad0f`: `Couldn't append name component`
- `0x14006adce`: `API: Could not open directory`
- `0x14006ac2a`: `API: Appending short component`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::ConvertPathToShortNamePath(
        PFLT_INSTANCE Instance,
        UNICODE_STRING *SourceString,
        PUNICODE_STRING UnicodeString,
        __int64 a4)
{
  USHORT Length; // r9
  struct _UNICODE_STRING *UniqueUnicodeString; // rax
  struct _UNICODE_STRING *v10; // rdx
  struct _UNICODE_STRING v11; // xmm6
  unsigned int v12; // ebx
  __int64 v13; // r8
  struct _UNICODE_STRING *v14; // rdx
  struct _UNICODE_STRING v15; // xmm0
  unsigned __int16 v16; // r9
  unsigned __int16 v17; // dx
  unsigned __int16 i; // r8
  unsigned __int16 v19; // ax
  struct _UNICODE_STRING *v20; // rax
  struct _UNICODE_STRING *v21; // rdx
  struct _UNICODE_STRING v22; // xmm6
  struct _UNICODE_STRING *v23; // rdx
  NTSTATUS FileNameInformationUnsafe; // esi
  unsigned __int16 v25; // r8
  struct _UNICODE_STRING *v26; // rdx
  USHORT v27; // r12
  char v28; // r15
  __int64 v29; // rdx
  __int64 v30; // rcx
  NTSTATUS v31; // esi
  void *v32; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v33; // rcx
  struct _UNICODE_STRING *v34; // rdx
  const char *v35; // rax
  __int64 v36; // r8
  struct _FLT_FILE_NAME_INFORMATION *v37; // rcx
  PFILE_OBJECT v38; // rcx
  struct _UNICODE_STRING v39; // xmm0
  struct _UNICODE_STRING *v40; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v42; // rcx
  PFILE_OBJECT v43; // rcx
  struct _UNICODE_STRING *v44; // rdx
  PFILE_OBJECT v45; // rcx
  struct _UNICODE_STRING *v46; // rdx
  char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  const struct _UNICODE_STRING *IoStatusBlock; // [rsp+30h] [rbp-D0h]
  PFILE_OBJECT v49; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v50; // [rsp+88h] [rbp-78h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING UnicodeStringa; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING FileHandle; // [rsp+C0h] [rbp-40h] BYREF
  void **p_FileNameInformation; // [rsp+D0h] [rbp-30h]
  PFILE_OBJECT FileObject; // [rsp+D8h] [rbp-28h] BYREF
  char v57; // [rsp+E0h] [rbp-20h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+E8h] [rbp-18h] BYREF
  __int64 HostSilo; // [rsp+108h] [rbp+8h]
  struct _OBJECT_ATTRIBUTES v60; // [rsp+110h] [rbp+10h] BYREF
  struct _IO_STATUS_BLOCK v61; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v62; // [rsp+1B8h] [rbp+B8h] BYREF

  FsFltWil::Details::FreeUnicodeString(UnicodeString, SourceString);
  *UnicodeString = 0;
  Length = SourceString->Length;
  DestinationString = 0;
  if ( Length == 2 )
  {
    UniqueUnicodeString = (struct _UNICODE_STRING *)FsFltWil::MakeUniqueUnicodeString(&FileHandle, 2, 1752188501);
    if ( &DestinationString != UniqueUnicodeString )
    {
      v11 = *UniqueUnicodeString;
      *UniqueUnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v10);
      DestinationString = v11;
    }
    FsFltWil::Details::FreeUnicodeString(&FileHandle, v10);
    v12 = 0;
    if ( DestinationString.Buffer )
    {
      RtlCopyUnicodeString(&DestinationString, SourceString);
      v15 = DestinationString;
      DestinationString = *UnicodeString;
      *UnicodeString = v15;
LABEL_58:
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v14);
      return v12;
    }
    v13 = 0x152002101C5LL;
LABEL_16:
    v12 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a4,
      (struct UnionFs::StackEventTracer *)v13,
      (unsigned __int64)"UnionFs::Utils::ConvertPathToShortNamePath",
      "ORIGIN: Allocating short path string",
      ObjectAttributes);
    goto LABEL_58;
  }
  v16 = Length >> 1;
  v17 = 0;
  if ( v16 )
  {
    for ( i = 0; i < v16; ++i )
    {
      v19 = v17 + 1;
      if ( SourceString->Buffer[i] != 92 )
        v19 = v17;
      v17 = v19;
    }
  }
  v20 = (struct _UNICODE_STRING *)FsFltWil::MakeUniqueUnicodeString(&FileHandle, 26 * (unsigned int)v17, 1752188501);
  if ( &DestinationString != v20 )
  {
    v22 = *v20;
    *v20 = 0;
    FsFltWil::Details::FreeUnicodeString(&DestinationString, v21);
    DestinationString = v22;
  }
  FsFltWil::Details::FreeUnicodeString(&FileHandle, v21);
  if ( !DestinationString.Buffer )
  {
    v13 = 0x144002101E3LL;
    goto LABEL_16;
  }
  FsFltWil::MakeUniqueUnicodeString(&UnicodeStringa, (unsigned __int16)(SourceString->MaximumLength + 50), 1752188501);
  if ( !UnicodeStringa.Buffer )
  {
    v12 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a4,
      (struct UnionFs::StackEventTracer *)0x163002101F0LL,
      (unsigned __int64)"UnionFs::Utils::ConvertPathToShortNamePath",
      "ORIGIN: Allocating pathToOpen",
      ObjectAttributes);
    FsFltWil::Details::FreeUnicodeString(&UnicodeStringa, v23);
    goto LABEL_58;
  }
  RtlCopyUnicodeString(&UnicodeStringa, SourceString);
  v62 = 0;
  FileNameInformationUnsafe = UnionFs::Utils::PrependVolumeNameFromInstance(Instance, &UnicodeStringa, a4, &v62);
  if ( FileNameInformationUnsafe < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformationUnsafe,
      a4,
      (struct UnionFs::StackEventTracer *)0x164002101F7LL,
      (unsigned __int64)"UnionFs::Utils::ConvertPathToShortNamePath",
      "PUSH: Prepending volume root",
      ObjectAttributes);
LABEL_57:
    FsFltWil::Details::FreeUnicodeString(&UnicodeStringa, v26);
    v12 = FileNameInformationUnsafe;
    goto LABEL_58;
  }
  v27 = UnicodeStringa.Length;
  v28 = 1;
  UnicodeStringa.Length = v62;
  v50 = v62 + 4;
  while ( 1 )
  {
    v62 = 0;
    if ( UnionFs::Utils::FindCharForward(
           (UnionFs::Utils *)UnicodeStringa.Buffer,
           (const unsigned __int16 *)v27,
           v25,
           (unsigned __int16)&v62,
           &v50,
           (unsigned __int16 *)ObjectAttributes) )
    {
      v29 = 2;
      v30 = v62;
      LOWORD(v30) = v62 - 2;
      v50 = v62 + 2;
    }
    else
    {
      v28 = 0;
      v30 = v27;
    }
    UnicodeStringa.Length = v30;
    if ( (unsigned __int16)v30 > UnicodeStringa.MaximumLength )
      MicrosoftTelemetryAssertTriggeredMsgKM("pathToOpen.Length <= pathToOpen.MaximumLength");
    HostSilo = 1;
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    HostSilo = PsGetHostSilo(v30, v29);
    *(_QWORD *)&v60.Length = 48;
    *(_QWORD *)&v60.Attributes = 576;
    v60.ObjectName = &UnicodeStringa;
    v60.RootDirectory = 0;
    p_FileNameInformation = (void **)&v49;
    *(_OWORD *)&v60.SecurityDescriptor = 0;
    v49 = 0;
    v61 = 0;
    FileObject = 0;
    v57 = 1;
    *(_QWORD *)&FileHandle.Length = 0;
    v31 = FltCreateFileEx2(
            *(PFLT_FILTER *)UnionFs::g_FilterState,
            Instance,
            (PHANDLE)&FileHandle,
            &FileObject,
            1u,
            &v60,
            &v61,
            0,
            0,
            7u,
            1u,
            0x200001u,
            0,
            0,
            0,
            &DriverContext);
    if ( v57 )
    {
      v32 = *p_FileNameInformation;
      *p_FileNameInformation = FileObject;
      if ( v32 )
        ObfDereferenceObject(v32);
    }
    if ( v31 < 0 )
      break;
    p_FileNameInformation = (void **)&FileNameInformation;
    v57 = 1;
    FileNameInformation = 0;
    FileObject = 0;
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(
                                  v49,
                                  Instance,
                                  0x103u,
                                  (PFLT_FILE_NAME_INFORMATION *)&FileObject);
    if ( v57 )
    {
      v33 = (struct _FLT_FILE_NAME_INFORMATION *)*p_FileNameInformation;
      *p_FileNameInformation = FileObject;
      if ( v33 )
        FltReleaseFileNameInformation(v33);
    }
    if ( FileNameInformationUnsafe < 0 )
    {
      if ( FileNameInformationUnsafe != -1073741772 )
      {
        v35 = "API: Querying short name";
        v36 = 0x12C00210283LL;
        goto LABEL_51;
      }
      FileNameInformationUnsafe = RtlAppendUnicodeToString(&DestinationString, L"\\");
      if ( FileNameInformationUnsafe < 0
        || (FileNameInformationUnsafe = RtlAppendUnicodeStringToString(&DestinationString, &UnionFs::g_NoShortComponent),
            FileNameInformationUnsafe < 0) )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("Couldn't append name component");
        v35 = "API: Appending no-short-name marker";
        v36 = 0x210021027FLL;
        goto LABEL_51;
      }
    }
    else
    {
      FileNameInformationUnsafe = RtlAppendUnicodeToString(&DestinationString, L"\\");
      if ( FileNameInformationUnsafe < 0
        || (FileNameInformationUnsafe = RtlAppendUnicodeStringToString(&DestinationString, &FileNameInformation->Name),
            FileNameInformationUnsafe < 0) )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("Couldn't append name component");
        v35 = "API: Appending short component";
        v36 = 0x200021026FLL;
LABEL_51:
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)FileNameInformationUnsafe,
          a4,
          (struct UnionFs::StackEventTracer *)v36,
          (unsigned __int64)"UnionFs::Utils::ConvertPathToShortNamePath",
          v35,
          ObjectAttributes);
        v42 = FileNameInformation;
        FileNameInformation = 0;
        if ( v42 )
          FltReleaseFileNameInformation(v42);
        v43 = v49;
        v49 = 0;
        if ( v43 )
          ObfDereferenceObject(v43);
        if ( *(_QWORD *)&FileHandle.Length )
          FltClose(*(HANDLE *)&FileHandle.Length);
        goto LABEL_57;
      }
    }
    v37 = FileNameInformation;
    FileNameInformation = 0;
    if ( v37 )
      FltReleaseFileNameInformation(v37);
    v38 = v49;
    v49 = 0;
    if ( v38 )
      ObfDereferenceObject(v38);
    if ( *(_QWORD *)&FileHandle.Length )
      FltClose(*(HANDLE *)&FileHandle.Length);
    if ( !v28 )
    {
      v39 = DestinationString;
      DestinationString = *UnicodeString;
      *UnicodeString = v39;
      FsFltWil::Details::FreeUnicodeString(&UnicodeStringa, v34);
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v40);
      return 0;
    }
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)v31,
    a4,
    (struct UnionFs::StackEventTracer *)0x1F00210259LL,
    (unsigned __int64)"UnionFs::Utils::ConvertPathToShortNamePath",
    "API: Could not open directory",
    (const char *)&UnicodeStringa,
    IoStatusBlock);
  v45 = v49;
  v49 = 0;
  if ( v45 )
    ObfDereferenceObject(v45);
  if ( *(_QWORD *)&FileHandle.Length )
    FltClose(*(HANDLE *)&FileHandle.Length);
  FsFltWil::Details::FreeUnicodeString(&UnicodeStringa, v44);
  FsFltWil::Details::FreeUnicodeString(&DestinationString, v46);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x14006a7d0  mov     rax, rsp
0x14006a7d3  push    rbp
0x14006a7d4  push    rbx
0x14006a7d5  push    rsi
0x14006a7d6  push    rdi
0x14006a7d7  push    r12
0x14006a7d9  push    r13
0x14006a7db  push    r14
0x14006a7dd  push    r15
0x14006a7df  lea     rbp, [rsp-68h]
0x14006a7e4  sub     rsp, 168h
0x14006a7eb  mov     r13, rcx
0x14006a7ee  movaps  xmmword ptr [rax-58h], xmm6
0x14006a7f2  mov     rcx, r8; UnicodeString
0x14006a7f5  mov     rdi, r9
0x14006a7f8  mov     r14, r8
0x14006a7fb  mov     rsi, rdx
0x14006a7fe  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006a803  xorps   xmm0, xmm0
0x14006a806  mov     eax, 2
0x14006a80b  movups  xmmword ptr [r14], xmm0
0x14006a80f  movzx   r9d, word ptr [rsi]
0x14006a813  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x14006a817  cmp     r9w, ax
0x14006a81b  jnz     short loc_14006A898
0x14006a81d  mov     edx, eax
0x14006a81f  lea     rcx, [rbp+0A0h+FileHandle]
0x14006a823  mov     r8d, 68704655h
0x14006a829  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14006a82e  lea     rcx, [rbp+0A0h+DestinationString]
0x14006a832  cmp     rcx, rax
0x14006a835  jz      short loc_14006A84E
0x14006a837  movups  xmm6, xmmword ptr [rax]
0x14006a83a  lea     rcx, [rbp+0A0h+DestinationString]; UnicodeString
0x14006a83e  xorps   xmm0, xmm0
0x14006a841  movups  xmmword ptr [rax], xmm0
0x14006a844  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006a849  movdqa  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm6
0x14006a84e  lea     rcx, [rbp+0A0h+FileHandle]; UnicodeString
0x14006a852  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006a857  xor     ebx, ebx
0x14006a859  cmp     [rbp+0A0h+DestinationString.Buffer], rbx
0x14006a85d  jnz     short loc_14006A86E
0x14006a85f  mov     r8, 152002101C5h
0x14006a869  jmp     loc_14006A923
0x14006a86e  mov     rdx, rsi; SourceString
0x14006a871  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x14006a875  call    cs:__imp_RtlCopyUnicodeString
0x14006a87c  nop     dword ptr [rax+rax+00h]
0x14006a881  movups  xmm1, xmmword ptr [r14]
0x14006a885  movaps  xmm0, xmmword ptr [rbp+0A0h+DestinationString.Length]
0x14006a889  movdqa  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm1
0x14006a88e  movdqu  xmmword ptr [r14], xmm0
0x14006a893  jmp     loc_14006ADA7
0x14006a898  xor     ebx, ebx
0x14006a89a  shr     r9w, 1
0x14006a89e  movzx   edx, bx
0x14006a8a1  lea     r11d, [rbx+1]
0x14006a8a5  cmp     bx, r9w
0x14006a8a9  jnb     short loc_14006A8D5
0x14006a8ab  mov     r10, [rsi+8]
0x14006a8af  movzx   r8d, bx
0x14006a8b3  movzx   eax, r8w
0x14006a8b7  movzx   ecx, word ptr [r10+rax*2]
0x14006a8bc  lea     eax, [r11+rdx]
0x14006a8c0  cmp     cx, 5Ch ; '\'
0x14006a8c4  cmovnz  ax, dx
0x14006a8c8  add     r8w, r11w
0x14006a8cc  movzx   edx, ax
0x14006a8cf  cmp     r8w, r9w
0x14006a8d3  jb      short loc_14006A8B3
0x14006a8d5  movzx   eax, dx
0x14006a8d8  lea     rcx, [rbp+0A0h+FileHandle]
0x14006a8dc  imul    edx, eax, 1Ah
0x14006a8df  mov     r8d, 68704655h
0x14006a8e5  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14006a8ea  lea     rcx, [rbp+0A0h+DestinationString]
0x14006a8ee  cmp     rcx, rax
0x14006a8f1  jz      short loc_14006A90A
0x14006a8f3  movups  xmm6, xmmword ptr [rax]
0x14006a8f6  lea     rcx, [rbp+0A0h+DestinationString]; UnicodeString
0x14006a8fa  xorps   xmm0, xmm0
0x14006a8fd  movups  xmmword ptr [rax], xmm0
0x14006a900  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006a905  movdqa  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm6
0x14006a90a  lea     rcx, [rbp+0A0h+FileHandle]; UnicodeString
0x14006a90e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006a913  cmp     [rbp+0A0h+DestinationString.Buffer], rbx
0x14006a917  jnz     short loc_14006A94A
0x14006a919  mov     r8, 144002101E3h; struct UnionFs::StackEventTracer *
0x14006a923  lea     rax, aOriginAllocati_29; "ORIGIN: Allocating short path string"
0x14006a92a  mov     ebx, 0C000009Ah
0x14006a92f  mov     ecx, ebx; this
0x14006a931  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14006a936  lea     r9, aUnionfsUtilsCo_0; "UnionFs::Utils::ConvertPathToShortNameP"...
0x14006a93d  mov     rdx, rdi; int
0x14006a940  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a945  jmp     loc_14006ADA7
0x14006a94a  movzx   edx, word ptr [rsi+2]
0x14006a94e  lea     rcx, [rbp+0A0h+UnicodeString]
0x14006a952  add     dx, 32h ; '2'
0x14006a956  mov     r8d, 68704655h
0x14006a95c  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14006a961  cmp     [rbp+0A0h+UnicodeString.Buffer], rbx
0x14006a965  jnz     short loc_14006A9A1
0x14006a967  lea     rax, aOriginAllocati_67; "ORIGIN: Allocating pathToOpen"
0x14006a96e  mov     ebx, 0C000009Ah
0x14006a973  mov     ecx, ebx; this
0x14006a975  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14006a97a  lea     r9, aUnionfsUtilsCo_0; "UnionFs::Utils::ConvertPathToShortNameP"...
0x14006a981  mov     r8, 163002101F0h; struct UnionFs::StackEventTracer *
0x14006a98b  mov     rdx, rdi; int
0x14006a98e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a993  lea     rcx, [rbp+0A0h+UnicodeString]; UnicodeString
0x14006a997  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006a99c  jmp     loc_14006ADA7
0x14006a9a1  mov     rdx, rsi; SourceString
0x14006a9a4  lea     rcx, [rbp+0A0h+UnicodeString]; DestinationString
0x14006a9a8  call    cs:__imp_RtlCopyUnicodeString
0x14006a9af  nop     dword ptr [rax+rax+00h]
0x14006a9b4  lea     r9, [rbp+0A0h+arg_8]
0x14006a9bb  mov     [rbp+0A0h+arg_8], bx
0x14006a9c2  mov     r8, rdi
0x14006a9c5  lea     rdx, [rbp+0A0h+UnicodeString]
0x14006a9c9  mov     rcx, r13
0x14006a9cc  call    ?PrependVolumeNameFromInstance@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEAG@Z; UnionFs::Utils::PrependVolumeNameFromInstance(_FLT_INSTANCE const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort *)
0x14006a9d1  mov     esi, eax
0x14006a9d3  test    eax, eax
0x14006a9d5  jns     short loc_14006AA03
0x14006a9d7  lea     rax, aPushPrepending; "PUSH: Prepending volume root"
0x14006a9de  mov     r8, 164002101F7h; struct UnionFs::StackEventTracer *
0x14006a9e8  lea     r9, aUnionfsUtilsCo_0; "UnionFs::Utils::ConvertPathToShortNameP"...
0x14006a9ef  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14006a9f4  mov     rdx, rdi; int
0x14006a9f7  mov     ecx, esi; this
0x14006a9f9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a9fe  jmp     loc_14006AD9C
0x14006aa03  movzx   ecx, [rbp+0A0h+arg_8]
0x14006aa0a  mov     esi, 1
0x14006aa0f  movzx   r12d, [rbp+0A0h+UnicodeString.Length]
0x14006aa14  mov     r15b, sil
0x14006aa17  mov     [rbp+0A0h+UnicodeString.Length], cx
0x14006aa1b  lea     eax, [rcx+4]
0x14006aa1e  mov     [rbp+0A0h+var_118], ax
0x14006aa22  mov     rcx, [rbp+0A0h+UnicodeString.Buffer]; this
0x14006aa26  lea     rax, [rbp+0A0h+var_118]
0x14006aa2a  lea     r9, [rbp+0A0h+arg_8]; unsigned __int16
0x14006aa31  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; unsigned __int16 *
0x14006aa36  movzx   edx, r12w; unsigned __int16 *
0x14006aa3a  mov     [rbp+0A0h+arg_8], bx
0x14006aa41  call    ?FindCharForward@Utils@UnionFs@@YA_NPEBGGGPEAG1@Z; UnionFs::Utils::FindCharForward(ushort const *,ushort,ushort,ushort *,ushort *)
0x14006aa46  test    al, al
0x14006aa48  jnz     short loc_14006AA53
0x14006aa4a  mov     r15b, bl
0x14006aa4d  movzx   ecx, r12w
0x14006aa51  jmp     short loc_14006AA6C
0x14006aa53  movzx   eax, [rbp+0A0h+arg_8]
0x14006aa5a  mov     edx, 2
0x14006aa5f  movzx   ecx, ax
0x14006aa62  sub     cx, dx
0x14006aa65  add     ax, dx
0x14006aa68  mov     [rbp+0A0h+var_118], ax
0x14006aa6c  mov     [rbp+0A0h+UnicodeString.Length], cx
0x14006aa70  cmp     cx, [rbp+0A0h+UnicodeString.MaximumLength]
0x14006aa74  jbe     short loc_14006AA82
0x14006aa76  lea     rcx, aPathtoopenLeng; "pathToOpen.Length <= pathToOpen.Maximum"...
0x14006aa7d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006aa82  xorps   xmm0, xmm0
0x14006aa85  mov     [rbp+0A0h+var_98], rsi
0x14006aa89  mov     eax, 28h ; '('
0x14006aa8e  movups  xmmword ptr [rbp+0A0h+var_B8.Size], xmm0
0x14006aa92  mov     [rbp+0A0h+var_B8.Size], ax
0x14006aa96  movups  xmmword ptr [rbp+0A0h+var_B8.DeviceObjectHint], xmm0
0x14006aa9a  call    cs:__imp_PsGetHostSilo
0x14006aaa1  nop     dword ptr [rax+rax+00h]
0x14006aaa6  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006aaad  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x14006aab1  mov     [rbp+0A0h+var_98], rax
0x14006aab5  lea     r8, [rbp+0A0h+FileHandle]; FileHandle
0x14006aab9  xorps   xmm0, xmm0
0x14006aabc  mov     qword ptr [rbp+0A0h+var_90.Length], 30h ; '0'
0x14006aac4  lea     rax, [rbp+0A0h+UnicodeString]
0x14006aac8  mov     qword ptr [rbp+0A0h+var_90.Attributes], 240h
0x14006aad0  mov     [rbp+0A0h+var_90.ObjectName], rax
0x14006aad4  mov     rdx, r13; Instance
0x14006aad7  lea     rax, [rbp+0A0h+var_120]
0x14006aadb  mov     [rbp+0A0h+var_90.RootDirectory], rbx
0x14006aadf  mov     [rbp+0A0h+var_D0], rax
0x14006aae3  lea     rax, [rbp+0A0h+var_B8]
0x14006aae7  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x14006aaec  lea     rax, [rbp+0A0h+var_60]
0x14006aaf0  mov     [rsp+1A0h+Flags], ebx; Flags
0x14006aaf4  mov     [rsp+1A0h+EaLength], ebx; EaLength
0x14006aaf8  mov     [rsp+1A0h+EaBuffer], rbx; EaBuffer
0x14006aafd  mov     [rsp+1A0h+CreateOptions], 200001h; CreateOptions
0x14006ab05  mov     [rsp+1A0h+CreateDisposition], esi; CreateDisposition
0x14006ab09  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x14006ab11  mov     [rsp+1A0h+FileAttributes], ebx; FileAttributes
0x14006ab15  mov     [rsp+1A0h+AllocationSize], rbx; AllocationSize
0x14006ab1a  mov     [rsp+1A0h+IoStatusBlock], rax; struct _UNICODE_STRING *
0x14006ab1f  lea     rax, [rbp+0A0h+var_90]
0x14006ab23  movdqu  xmmword ptr [rbp+0A0h+var_90.SecurityDescriptor], xmm0
0x14006ab28  mov     [rbp+0A0h+var_120], rbx
0x14006ab2c  movups  xmmword ptr [rbp+0A0h+var_60], xmm0
0x14006ab30  mov     [rbp+0A0h+FileObject], rbx
0x14006ab34  mov     [rbp+0A0h+var_C0], sil
0x14006ab38  mov     qword ptr [rbp+0A0h+FileHandle], rbx
0x14006ab3c  mov     rcx, [rcx]; Filter
0x14006ab3f  mov     [rsp+1A0h+ObjectAttributes], rax; char *
0x14006ab44  mov     [rsp+1A0h+DesiredAccess], esi; DesiredAccess
0x14006ab48  call    cs:__imp_FltCreateFileEx2
0x14006ab4f  nop     dword ptr [rax+rax+00h]
0x14006ab54  mov     esi, eax
0x14006ab56  cmp     [rbp+0A0h+var_C0], bl
0x14006ab59  jz      short loc_14006AB7A
0x14006ab5b  mov     r8, [rbp+0A0h+var_D0]
0x14006ab5f  mov     rdx, [rbp+0A0h+FileObject]
0x14006ab63  mov     rcx, [r8]; Object
0x14006ab66  mov     [r8], rdx
0x14006ab69  test    rcx, rcx
0x14006ab6c  jz      short loc_14006AB7A
0x14006ab6e  call    cs:__imp_ObfDereferenceObject
0x14006ab75  nop     dword ptr [rax+rax+00h]
0x14006ab7a  test    esi, esi
0x14006ab7c  js      loc_14006ADB4
0x14006ab82  mov     rcx, [rbp+0A0h+var_120]; FileObject
0x14006ab86  lea     rax, [rbp+0A0h+FileNameInformation]
0x14006ab8a  mov     r11d, 1
0x14006ab90  mov     [rbp+0A0h+var_D0], rax
0x14006ab94  lea     r9, [rbp+0A0h+FileObject]; FileNameInformation
0x14006ab98  mov     [rbp+0A0h+var_C0], r11b
0x14006ab9c  mov     r8d, 103h; NameOptions
0x14006aba2  mov     [rbp+0A0h+FileNameInformation], rbx
0x14006aba6  mov     rdx, r13; Instance
0x14006aba9  mov     [rbp+0A0h+FileObject], rbx
0x14006abad  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14006abb4  nop     dword ptr [rax+rax+00h]
0x14006abb9  mov     esi, eax
0x14006abbb  cmp     [rbp+0A0h+var_C0], bl
0x14006abbe  jz      short loc_14006ABDF
0x14006abc0  mov     r8, [rbp+0A0h+var_D0]
0x14006abc4  mov     rdx, [rbp+0A0h+FileObject]
0x14006abc8  mov     rcx, [r8]; FileNameInformation
0x14006abcb  mov     [r8], rdx
0x14006abce  test    rcx, rcx
0x14006abd1  jz      short loc_14006ABDF
0x14006abd3  call    cs:__imp_FltReleaseFileNameInformation
0x14006abda  nop     dword ptr [rax+rax+00h]
0x14006abdf  test    esi, esi
0x14006abe1  js      short loc_14006AC40
0x14006abe3  lea     rdx, Source; "\\"
0x14006abea  lea     rcx, [rbp+0A0h+DestinationString]; Destination
0x14006abee  call    cs:__imp_RtlAppendUnicodeToString
0x14006abf5  nop     dword ptr [rax+rax+00h]
0x14006abfa  mov     esi, eax
0x14006abfc  test    eax, eax
0x14006abfe  js      short loc_14006AC1E
0x14006ac00  mov     rdx, [rbp+0A0h+FileNameInformation]
0x14006ac04  lea     rcx, [rbp+0A0h+DestinationString]; Destination
0x14006ac08  add     rdx, 8; Source
0x14006ac0c  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006ac13  nop     dword ptr [rax+rax+00h]
0x14006ac18  mov     esi, eax
0x14006ac1a  test    eax, eax
0x14006ac1c  jns     short loc_14006AC8E
0x14006ac1e  lea     rcx, aCouldnTAppendN; "Couldn't append name component"
0x14006ac25  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006ac2a  lea     rax, aApiAppendingSh; "API: Appending short component"
0x14006ac31  mov     r8, 200021026Fh
0x14006ac3b  jmp     loc_14006AD3F
0x14006ac40  cmp     esi, 0C0000034h
0x14006ac46  jnz     loc_14006AD2E
0x14006ac4c  lea     rdx, Source; "\\"
0x14006ac53  lea     rcx, [rbp+0A0h+DestinationString]; Destination
0x14006ac57  call    cs:__imp_RtlAppendUnicodeToString
0x14006ac5e  nop     dword ptr [rax+rax+00h]
0x14006ac63  mov     esi, eax
0x14006ac65  test    eax, eax
0x14006ac67  js      loc_14006AD0F
0x14006ac6d  lea     rdx, ?g_NoShortComponent@UnionFs@@3U_UNICODE_STRING@@B; Source
0x14006ac74  lea     rcx, [rbp+0A0h+DestinationString]; Destination
0x14006ac78  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006ac7f  nop     dword ptr [rax+rax+00h]
0x14006ac84  mov     esi, eax
0x14006ac86  test    eax, eax
0x14006ac88  js      loc_14006AD0F
0x14006ac8e  mov     rcx, [rbp+0A0h+FileNameInformation]; FileNameInformation
0x14006ac92  mov     [rbp+0A0h+FileNameInformation], rbx
0x14006ac96  test    rcx, rcx
0x14006ac99  jz      short loc_14006ACA7
0x14006ac9b  call    cs:__imp_FltReleaseFileNameInformation
0x14006aca2  nop     dword ptr [rax+rax+00h]
0x14006aca7  mov     rcx, [rbp+0A0h+var_120]; Object
0x14006acab  mov     [rbp+0A0h+var_120], rbx
0x14006acaf  test    rcx, rcx
0x14006acb2  jz      short loc_14006ACC0
0x14006acb4  call    cs:__imp_ObfDereferenceObject
0x14006acbb  nop     dword ptr [rax+rax+00h]
0x14006acc0  mov     rcx, qword ptr [rbp+0A0h+FileHandle]; FileHandle
0x14006acc4  test    rcx, rcx
  ... truncated ...
```
