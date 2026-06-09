# UnionFs::Utils::ConvertPathToShortNamePath(_FLT_INSTANCE const &,_UNICODE_STRING const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x14006a9c0`
- end: `0x14006b033`
- name: `?ConvertPathToShortNamePath@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `1651`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PCUNICODE_STRING SourceString, PUNICODE_STRING UnicodeString, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140044b40`

## callees

- `0x140056bd0`
- `0x140056c08`
- `0x140056c44`
- `0x140056c7c`
- `0x14006a9c0`
- `0x14006e088`
- `0x140075454`
- `0x140079f68`
- `0x14007a02c`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006adde`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006ae47`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006adde`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006ae47`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006adfc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006ae68`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006adfc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006ae68`
- `ntoskrnl!PsGetHostSilo` at `0x14006ac8a`
- `ntoskrnl!PsGetHostSilo` at `0x14006ac8a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006aa65`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006ab98`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006aa65`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006ab98`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ad5e`
- `ntoskrnl!ObfDereferenceObject` at `0x14006aea4`
- `ntoskrnl!ObfDereferenceObject` at `0x14006af6b`
- `ntoskrnl!ObfDereferenceObject` at `0x14006afe1`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ad5e`
- `ntoskrnl!ObfDereferenceObject` at `0x14006aea4`
- `ntoskrnl!ObfDereferenceObject` at `0x14006af6b`
- `ntoskrnl!ObfDereferenceObject` at `0x14006afe1`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006ad9d`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14006ad9d`
- `FLTMGR!FltCreateFileEx2` at `0x14006ad38`
- `FLTMGR!FltCreateFileEx2` at `0x14006ad38`
- `FLTMGR!FltClose` at `0x14006aeb9`
- `FLTMGR!FltClose` at `0x14006af80`
- `FLTMGR!FltClose` at `0x14006aff6`
- `FLTMGR!FltClose` at `0x14006aeb9`
- `FLTMGR!FltClose` at `0x14006af80`
- `FLTMGR!FltClose` at `0x14006aff6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006adc3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ae8b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006af52`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006adc3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006ae8b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006af52`

## string_xrefs

- `0x14006ab26`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006ab6a`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006abd8`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006af2f`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006afb7`: `UnionFs::Utils::ConvertPathToShortNamePath`
- `0x14006ab13`: `ORIGIN: Allocating short path string`
- `0x14006ab57`: `ORIGIN: Allocating pathToOpen`
- `0x14006afbe`: `API: Could not open directory`
- `0x14006ac66`: `pathToOpen.Length <= pathToOpen.MaximumLength`
- `0x14006ae1a`: `API: Appending short component`
- `0x14006ae0e`: `Couldn't append name component`
- `0x14006aeff`: `Couldn't append name component`

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
0x14006a9c0  mov     rax, rsp
0x14006a9c3  push    rbp
0x14006a9c4  push    rbx
0x14006a9c5  push    rsi
0x14006a9c6  push    rdi
0x14006a9c7  push    r12
0x14006a9c9  push    r13
0x14006a9cb  push    r14
0x14006a9cd  push    r15
0x14006a9cf  lea     rbp, [rsp-68h]
0x14006a9d4  sub     rsp, 168h
0x14006a9db  mov     r13, rcx
0x14006a9de  movaps  xmmword ptr [rax-58h], xmm6
0x14006a9e2  mov     rcx, r8; UnicodeString
0x14006a9e5  mov     rdi, r9
0x14006a9e8  mov     r14, r8
0x14006a9eb  mov     rsi, rdx
0x14006a9ee  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006a9f3  xorps   xmm0, xmm0
0x14006a9f6  mov     eax, 2
0x14006a9fb  movups  xmmword ptr [r14], xmm0
0x14006a9ff  movzx   r9d, word ptr [rsi]
0x14006aa03  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x14006aa07  cmp     r9w, ax
0x14006aa0b  jnz     short loc_14006AA88
0x14006aa0d  mov     edx, eax
0x14006aa0f  lea     rcx, [rbp+0A0h+FileHandle]
0x14006aa13  mov     r8d, 68704655h
0x14006aa19  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14006aa1e  lea     rcx, [rbp+0A0h+DestinationString]
0x14006aa22  cmp     rcx, rax
0x14006aa25  jz      short loc_14006AA3E
0x14006aa27  movups  xmm6, xmmword ptr [rax]
0x14006aa2a  lea     rcx, [rbp+0A0h+DestinationString]; UnicodeString
0x14006aa2e  xorps   xmm0, xmm0
0x14006aa31  movups  xmmword ptr [rax], xmm0
0x14006aa34  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006aa39  movdqa  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm6
0x14006aa3e  lea     rcx, [rbp+0A0h+FileHandle]; UnicodeString
0x14006aa42  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006aa47  xor     ebx, ebx
0x14006aa49  cmp     [rbp+0A0h+DestinationString.Buffer], rbx
0x14006aa4d  jnz     short loc_14006AA5E
0x14006aa4f  mov     r8, 152002101C5h
0x14006aa59  jmp     loc_14006AB13
0x14006aa5e  mov     rdx, rsi; SourceString
0x14006aa61  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x14006aa65  call    cs:__imp_RtlCopyUnicodeString
0x14006aa6c  nop     dword ptr [rax+rax+00h]
0x14006aa71  movups  xmm1, xmmword ptr [r14]
0x14006aa75  movaps  xmm0, xmmword ptr [rbp+0A0h+DestinationString.Length]
0x14006aa79  movdqa  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm1
0x14006aa7e  movdqu  xmmword ptr [r14], xmm0
0x14006aa83  jmp     loc_14006AF97
0x14006aa88  xor     ebx, ebx
0x14006aa8a  shr     r9w, 1
0x14006aa8e  movzx   edx, bx
0x14006aa91  lea     r11d, [rbx+1]
0x14006aa95  cmp     bx, r9w
0x14006aa99  jnb     short loc_14006AAC5
0x14006aa9b  mov     r10, [rsi+8]
0x14006aa9f  movzx   r8d, bx
0x14006aaa3  movzx   eax, r8w
0x14006aaa7  movzx   ecx, word ptr [r10+rax*2]
0x14006aaac  lea     eax, [r11+rdx]
0x14006aab0  cmp     cx, 5Ch ; '\'
0x14006aab4  cmovnz  ax, dx
0x14006aab8  add     r8w, r11w
0x14006aabc  movzx   edx, ax
0x14006aabf  cmp     r8w, r9w
0x14006aac3  jb      short loc_14006AAA3
0x14006aac5  movzx   eax, dx
0x14006aac8  lea     rcx, [rbp+0A0h+FileHandle]
0x14006aacc  imul    edx, eax, 1Ah
0x14006aacf  mov     r8d, 68704655h
0x14006aad5  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14006aada  lea     rcx, [rbp+0A0h+DestinationString]
0x14006aade  cmp     rcx, rax
0x14006aae1  jz      short loc_14006AAFA
0x14006aae3  movups  xmm6, xmmword ptr [rax]
0x14006aae6  lea     rcx, [rbp+0A0h+DestinationString]; UnicodeString
0x14006aaea  xorps   xmm0, xmm0
0x14006aaed  movups  xmmword ptr [rax], xmm0
0x14006aaf0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006aaf5  movdqa  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm6
0x14006aafa  lea     rcx, [rbp+0A0h+FileHandle]; UnicodeString
0x14006aafe  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006ab03  cmp     [rbp+0A0h+DestinationString.Buffer], rbx
0x14006ab07  jnz     short loc_14006AB3A
0x14006ab09  mov     r8, 144002101E3h; struct UnionFs::StackEventTracer *
0x14006ab13  lea     rax, aOriginAllocati_29; "ORIGIN: Allocating short path string"
0x14006ab1a  mov     ebx, 0C000009Ah
0x14006ab1f  mov     ecx, ebx; this
0x14006ab21  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14006ab26  lea     r9, aUnionfsUtilsCo; "UnionFs::Utils::ConvertPathToShortNameP"...
0x14006ab2d  mov     rdx, rdi; int
0x14006ab30  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006ab35  jmp     loc_14006AF97
0x14006ab3a  movzx   edx, word ptr [rsi+2]
0x14006ab3e  lea     rcx, [rbp+0A0h+UnicodeString]
0x14006ab42  add     dx, 32h ; '2'
0x14006ab46  mov     r8d, 68704655h
0x14006ab4c  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14006ab51  cmp     [rbp+0A0h+UnicodeString.Buffer], rbx
0x14006ab55  jnz     short loc_14006AB91
0x14006ab57  lea     rax, aOriginAllocati_68; "ORIGIN: Allocating pathToOpen"
0x14006ab5e  mov     ebx, 0C000009Ah
0x14006ab63  mov     ecx, ebx; this
0x14006ab65  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14006ab6a  lea     r9, aUnionfsUtilsCo; "UnionFs::Utils::ConvertPathToShortNameP"...
0x14006ab71  mov     r8, 163002101F0h; struct UnionFs::StackEventTracer *
0x14006ab7b  mov     rdx, rdi; int
0x14006ab7e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006ab83  lea     rcx, [rbp+0A0h+UnicodeString]; UnicodeString
0x14006ab87  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006ab8c  jmp     loc_14006AF97
0x14006ab91  mov     rdx, rsi; SourceString
0x14006ab94  lea     rcx, [rbp+0A0h+UnicodeString]; DestinationString
0x14006ab98  call    cs:__imp_RtlCopyUnicodeString
0x14006ab9f  nop     dword ptr [rax+rax+00h]
0x14006aba4  lea     r9, [rbp+0A0h+arg_8]
0x14006abab  mov     [rbp+0A0h+arg_8], bx
0x14006abb2  mov     r8, rdi
0x14006abb5  lea     rdx, [rbp+0A0h+UnicodeString]
0x14006abb9  mov     rcx, r13
0x14006abbc  call    ?PrependVolumeNameFromInstance@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEAG@Z; UnionFs::Utils::PrependVolumeNameFromInstance(_FLT_INSTANCE const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort *)
0x14006abc1  mov     esi, eax
0x14006abc3  test    eax, eax
0x14006abc5  jns     short loc_14006ABF3
0x14006abc7  lea     rax, aPushPrepending; "PUSH: Prepending volume root"
0x14006abce  mov     r8, 164002101F7h; struct UnionFs::StackEventTracer *
0x14006abd8  lea     r9, aUnionfsUtilsCo; "UnionFs::Utils::ConvertPathToShortNameP"...
0x14006abdf  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; char *
0x14006abe4  mov     rdx, rdi; int
0x14006abe7  mov     ecx, esi; this
0x14006abe9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006abee  jmp     loc_14006AF8C
0x14006abf3  movzx   ecx, [rbp+0A0h+arg_8]
0x14006abfa  mov     esi, 1
0x14006abff  movzx   r12d, [rbp+0A0h+UnicodeString.Length]
0x14006ac04  mov     r15b, sil
0x14006ac07  mov     [rbp+0A0h+UnicodeString.Length], cx
0x14006ac0b  lea     eax, [rcx+4]
0x14006ac0e  mov     [rbp+0A0h+var_118], ax
0x14006ac12  mov     rcx, [rbp+0A0h+UnicodeString.Buffer]; this
0x14006ac16  lea     rax, [rbp+0A0h+var_118]
0x14006ac1a  lea     r9, [rbp+0A0h+arg_8]; unsigned __int16
0x14006ac21  mov     qword ptr [rsp+1A0h+DesiredAccess], rax; unsigned __int16 *
0x14006ac26  movzx   edx, r12w; unsigned __int16 *
0x14006ac2a  mov     [rbp+0A0h+arg_8], bx
0x14006ac31  call    ?FindCharForward@Utils@UnionFs@@YA_NPEBGGGPEAG1@Z; UnionFs::Utils::FindCharForward(ushort const *,ushort,ushort,ushort *,ushort *)
0x14006ac36  test    al, al
0x14006ac38  jnz     short loc_14006AC43
0x14006ac3a  mov     r15b, bl
0x14006ac3d  movzx   ecx, r12w
0x14006ac41  jmp     short loc_14006AC5C
0x14006ac43  movzx   eax, [rbp+0A0h+arg_8]
0x14006ac4a  mov     edx, 2
0x14006ac4f  movzx   ecx, ax
0x14006ac52  sub     cx, dx
0x14006ac55  add     ax, dx
0x14006ac58  mov     [rbp+0A0h+var_118], ax
0x14006ac5c  mov     [rbp+0A0h+UnicodeString.Length], cx
0x14006ac60  cmp     cx, [rbp+0A0h+UnicodeString.MaximumLength]
0x14006ac64  jbe     short loc_14006AC72
0x14006ac66  lea     rcx, aPathtoopenLeng; "pathToOpen.Length <= pathToOpen.Maximum"...
0x14006ac6d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006ac72  xorps   xmm0, xmm0
0x14006ac75  mov     [rbp+0A0h+var_98], rsi
0x14006ac79  mov     eax, 28h ; '('
0x14006ac7e  movups  xmmword ptr [rbp+0A0h+var_B8.Size], xmm0
0x14006ac82  mov     [rbp+0A0h+var_B8.Size], ax
0x14006ac86  movups  xmmword ptr [rbp+0A0h+var_B8.DeviceObjectHint], xmm0
0x14006ac8a  call    cs:__imp_PsGetHostSilo
0x14006ac91  nop     dword ptr [rax+rax+00h]
0x14006ac96  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006ac9d  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x14006aca1  mov     [rbp+0A0h+var_98], rax
0x14006aca5  lea     r8, [rbp+0A0h+FileHandle]; FileHandle
0x14006aca9  xorps   xmm0, xmm0
0x14006acac  mov     qword ptr [rbp+0A0h+var_90.Length], 30h ; '0'
0x14006acb4  lea     rax, [rbp+0A0h+UnicodeString]
0x14006acb8  mov     qword ptr [rbp+0A0h+var_90.Attributes], 240h
0x14006acc0  mov     [rbp+0A0h+var_90.ObjectName], rax
0x14006acc4  mov     rdx, r13; Instance
0x14006acc7  lea     rax, [rbp+0A0h+var_120]
0x14006accb  mov     [rbp+0A0h+var_90.RootDirectory], rbx
0x14006accf  mov     [rbp+0A0h+var_D0], rax
0x14006acd3  lea     rax, [rbp+0A0h+var_B8]
0x14006acd7  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x14006acdc  lea     rax, [rbp+0A0h+var_60]
0x14006ace0  mov     [rsp+1A0h+Flags], ebx; Flags
0x14006ace4  mov     [rsp+1A0h+EaLength], ebx; EaLength
0x14006ace8  mov     [rsp+1A0h+EaBuffer], rbx; EaBuffer
0x14006aced  mov     [rsp+1A0h+CreateOptions], 200001h; CreateOptions
0x14006acf5  mov     [rsp+1A0h+CreateDisposition], esi; CreateDisposition
0x14006acf9  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x14006ad01  mov     [rsp+1A0h+FileAttributes], ebx; FileAttributes
0x14006ad05  mov     [rsp+1A0h+AllocationSize], rbx; AllocationSize
0x14006ad0a  mov     [rsp+1A0h+IoStatusBlock], rax; struct _UNICODE_STRING *
0x14006ad0f  lea     rax, [rbp+0A0h+var_90]
0x14006ad13  movdqu  xmmword ptr [rbp+0A0h+var_90.SecurityDescriptor], xmm0
0x14006ad18  mov     [rbp+0A0h+var_120], rbx
0x14006ad1c  movups  xmmword ptr [rbp+0A0h+var_60], xmm0
0x14006ad20  mov     [rbp+0A0h+FileObject], rbx
0x14006ad24  mov     [rbp+0A0h+var_C0], sil
0x14006ad28  mov     qword ptr [rbp+0A0h+FileHandle], rbx
0x14006ad2c  mov     rcx, [rcx]; Filter
0x14006ad2f  mov     [rsp+1A0h+ObjectAttributes], rax; char *
0x14006ad34  mov     [rsp+1A0h+DesiredAccess], esi; DesiredAccess
0x14006ad38  call    cs:__imp_FltCreateFileEx2
0x14006ad3f  nop     dword ptr [rax+rax+00h]
0x14006ad44  mov     esi, eax
0x14006ad46  cmp     [rbp+0A0h+var_C0], bl
0x14006ad49  jz      short loc_14006AD6A
0x14006ad4b  mov     r8, [rbp+0A0h+var_D0]
0x14006ad4f  mov     rdx, [rbp+0A0h+FileObject]
0x14006ad53  mov     rcx, [r8]; Object
0x14006ad56  mov     [r8], rdx
0x14006ad59  test    rcx, rcx
0x14006ad5c  jz      short loc_14006AD6A
0x14006ad5e  call    cs:__imp_ObfDereferenceObject
0x14006ad65  nop     dword ptr [rax+rax+00h]
0x14006ad6a  test    esi, esi
0x14006ad6c  js      loc_14006AFA4
0x14006ad72  mov     rcx, [rbp+0A0h+var_120]; FileObject
0x14006ad76  lea     rax, [rbp+0A0h+FileNameInformation]
0x14006ad7a  mov     r11d, 1
0x14006ad80  mov     [rbp+0A0h+var_D0], rax
0x14006ad84  lea     r9, [rbp+0A0h+FileObject]; FileNameInformation
0x14006ad88  mov     [rbp+0A0h+var_C0], r11b
0x14006ad8c  mov     r8d, 103h; NameOptions
0x14006ad92  mov     [rbp+0A0h+FileNameInformation], rbx
0x14006ad96  mov     rdx, r13; Instance
0x14006ad99  mov     [rbp+0A0h+FileObject], rbx
0x14006ad9d  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14006ada4  nop     dword ptr [rax+rax+00h]
0x14006ada9  mov     esi, eax
0x14006adab  cmp     [rbp+0A0h+var_C0], bl
0x14006adae  jz      short loc_14006ADCF
0x14006adb0  mov     r8, [rbp+0A0h+var_D0]
0x14006adb4  mov     rdx, [rbp+0A0h+FileObject]
0x14006adb8  mov     rcx, [r8]; FileNameInformation
0x14006adbb  mov     [r8], rdx
0x14006adbe  test    rcx, rcx
0x14006adc1  jz      short loc_14006ADCF
0x14006adc3  call    cs:__imp_FltReleaseFileNameInformation
0x14006adca  nop     dword ptr [rax+rax+00h]
0x14006adcf  test    esi, esi
0x14006add1  js      short loc_14006AE30
0x14006add3  lea     rdx, Source; "\\"
0x14006adda  lea     rcx, [rbp+0A0h+DestinationString]; Destination
0x14006adde  call    cs:__imp_RtlAppendUnicodeToString
0x14006ade5  nop     dword ptr [rax+rax+00h]
0x14006adea  mov     esi, eax
0x14006adec  test    eax, eax
0x14006adee  js      short loc_14006AE0E
0x14006adf0  mov     rdx, [rbp+0A0h+FileNameInformation]
0x14006adf4  lea     rcx, [rbp+0A0h+DestinationString]; Destination
0x14006adf8  add     rdx, 8; Source
0x14006adfc  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006ae03  nop     dword ptr [rax+rax+00h]
0x14006ae08  mov     esi, eax
0x14006ae0a  test    eax, eax
0x14006ae0c  jns     short loc_14006AE7E
0x14006ae0e  lea     rcx, aCouldnTAppendN; "Couldn't append name component"
0x14006ae15  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006ae1a  lea     rax, aApiAppendingSh; "API: Appending short component"
0x14006ae21  mov     r8, 200021026Fh
0x14006ae2b  jmp     loc_14006AF2F
0x14006ae30  cmp     esi, 0C0000034h
0x14006ae36  jnz     loc_14006AF1E
0x14006ae3c  lea     rdx, Source; "\\"
0x14006ae43  lea     rcx, [rbp+0A0h+DestinationString]; Destination
0x14006ae47  call    cs:__imp_RtlAppendUnicodeToString
0x14006ae4e  nop     dword ptr [rax+rax+00h]
0x14006ae53  mov     esi, eax
0x14006ae55  test    eax, eax
0x14006ae57  js      loc_14006AEFF
0x14006ae5d  lea     rdx, ?g_NoShortComponent@UnionFs@@3U_UNICODE_STRING@@B; Source
0x14006ae64  lea     rcx, [rbp+0A0h+DestinationString]; Destination
0x14006ae68  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006ae6f  nop     dword ptr [rax+rax+00h]
0x14006ae74  mov     esi, eax
0x14006ae76  test    eax, eax
0x14006ae78  js      loc_14006AEFF
0x14006ae7e  mov     rcx, [rbp+0A0h+FileNameInformation]; FileNameInformation
0x14006ae82  mov     [rbp+0A0h+FileNameInformation], rbx
0x14006ae86  test    rcx, rcx
0x14006ae89  jz      short loc_14006AE97
0x14006ae8b  call    cs:__imp_FltReleaseFileNameInformation
0x14006ae92  nop     dword ptr [rax+rax+00h]
0x14006ae97  mov     rcx, [rbp+0A0h+var_120]; Object
0x14006ae9b  mov     [rbp+0A0h+var_120], rbx
0x14006ae9f  test    rcx, rcx
0x14006aea2  jz      short loc_14006AEB0
0x14006aea4  call    cs:__imp_ObfDereferenceObject
0x14006aeab  nop     dword ptr [rax+rax+00h]
0x14006aeb0  mov     rcx, qword ptr [rbp+0A0h+FileHandle]; FileHandle
0x14006aeb4  test    rcx, rcx
  ... truncated ...
```
