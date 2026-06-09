# BfsPreCreateOperation

- ea: `0x140002620`
- end: `0x140002d28`
- name: `BfsPreCreateOperation`
- size: `1800`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, PVOID *, _QWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140001270`
- `0x1400012b0`
- `0x140002620`
- `0x140003340`
- `0x140005768`
- `0x14000b4c8`
- `0x14000be9c`
- `0x14000bf74`
- `0x14000c344`
- `0x140013860`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x140002cf2`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140002cf2`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000294c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000294c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000291e`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000291e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002893`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400028b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400028c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002893`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400028b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400028c9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002cb2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002cb2`
- `ntoskrnl!SeQueryInformationToken` at `0x140002bf5`
- `ntoskrnl!SeQueryInformationToken` at `0x140002c13`
- `ntoskrnl!SeQueryInformationToken` at `0x140002bf5`
- `ntoskrnl!SeQueryInformationToken` at `0x140002c13`
- `ntoskrnl!IoGetCurrentProcess` at `0x140002b48`
- `ntoskrnl!IoGetCurrentProcess` at `0x140002b48`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140002b57`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140002b57`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140002b34`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140002b34`
- `ntoskrnl!ExAllocatePool2` at `0x1400027b3`
- `ntoskrnl!ExAllocatePool2` at `0x140002a6c`
- `ntoskrnl!ExAllocatePool2` at `0x140002c8c`
- `ntoskrnl!ExAllocatePool2` at `0x1400027b3`
- `ntoskrnl!ExAllocatePool2` at `0x140002a6c`
- `ntoskrnl!ExAllocatePool2` at `0x140002c8c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000269d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000290b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000269d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000290b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400026b0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400026b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400026bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000292a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400026bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000292a`
- `ntoskrnl!EtwWriteTransfer` at `0x140002781`
- `ntoskrnl!EtwWriteTransfer` at `0x14000287d`
- `ntoskrnl!EtwWriteTransfer` at `0x140002781`
- `ntoskrnl!EtwWriteTransfer` at `0x14000287d`
- `FLTMGR!FltGetFileNameInformation` at `0x1400029f7`
- `FLTMGR!FltGetFileNameInformation` at `0x140002c35`
- `FLTMGR!FltGetFileNameInformation` at `0x1400029f7`
- `FLTMGR!FltGetFileNameInformation` at `0x140002c35`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400028f2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002b0a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400028f2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002b0a`
- `FLTMGR!FltGetFileSystemType` at `0x14000296e`
- `FLTMGR!FltGetFileSystemType` at `0x14000296e`

## pseudocode

```c
__int64 __fastcall BfsPreCreateOperation(PFLT_CALLBACK_DATA Data, PVOID *a2, _QWORD *a3)
{
  PACCESS_TOKEN v3; // r15
  const UNICODE_STRING *v4; // r14
  _QWORD *v5; // rbx
  _QWORD *v6; // r12
  unsigned int v9; // esi
  __int64 v10; // rax
  ULONG v11; // eax
  NTSTATUS v12; // r14d
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PDEVICE_OBJECT DeviceObject; // rcx
  unsigned int FsInformationClass_high; // ecx
  int v16; // eax
  struct _KPROCESS *CurrentProcess; // rax
  NTSTATUS v18; // ecx
  char v19; // al
  unsigned int v20; // ecx
  __int64 v21; // rax
  USHORT v22; // r12
  unsigned int v24; // [rsp+30h] [rbp-99h] BYREF
  __int64 Pool2; // [rsp+38h] [rbp-91h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-89h] BYREF
  BOOLEAN v27; // [rsp+50h] [rbp-79h]
  char v28; // [rsp+51h] [rbp-78h]
  unsigned __int8 EffectiveOnly; // [rsp+52h] [rbp-77h] BYREF
  unsigned __int8 CopyOnOpen[5]; // [rsp+53h] [rbp-76h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+58h] [rbp-71h] BYREF
  _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+60h] [rbp-69h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+64h] [rbp-65h] BYREF
  const UNICODE_STRING *v34; // [rsp+68h] [rbp-61h]
  PVOID P; // [rsp+70h] [rbp-59h] BYREF
  PVOID TokenInformation; // [rsp+78h] [rbp-51h] BYREF
  _QWORD *v37; // [rsp+80h] [rbp-49h]
  EVENT_DESCRIPTOR v38; // [rsp+90h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-19h] BYREF
  int *v41; // [rsp+C0h] [rbp-9h]
  int v42; // [rsp+C8h] [rbp-1h]
  int v43; // [rsp+CCh] [rbp+3h]
  __int64 *p_Pool2; // [rsp+D0h] [rbp+7h]
  __int64 v45; // [rsp+D8h] [rbp+Fh]

  v37 = a3;
  FileSystemType = FLT_FSTYPE_UNKNOWN;
  ImpersonationLevel = SecurityAnonymous;
  v38 = 0;
  v3 = 0;
  v28 = 0;
  DestinationString = 0;
  FileNameInformation = 0;
  v4 = 0;
  v34 = 0;
  v5 = 0;
  TokenInformation = 0;
  v6 = a3;
  P = 0;
  Pool2 = 0;
  *a3 = 0;
  v9 = 1;
  CopyOnOpen[0] = 0;
  EffectiveOnly = 0;
  KeEnterCriticalRegion();
  v27 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( !v27 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v24 = -1073741823;
      EventDescriptor.Keyword = 0;
      p_Pool2 = (__int64 *)&v24;
      UserData.Ptr = (ULONGLONG)EventInformation;
      *(_DWORD *)&EventDescriptor.Level = 3;
      v45 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)EventInformation;
      v41 = &dword_140016D9C;
      UserData.Reserved = 2;
      v42 = 30;
      v43 = 1;
      LODWORD(Pool2) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    goto LABEL_12;
  }
  if ( (Data->Iopb->Parameters.Create.Options & 0x1000) == 0 )
  {
LABEL_27:
    v12 = FltGetFileSystemType(a2[2], &FileSystemType);
    if ( v12 < 0 )
    {
LABEL_28:
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_9;
      LODWORD(Pool2) = v12;
      goto LABEL_43;
    }
    if ( (unsigned int)Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( FileSystemType == FLT_FSTYPE_NPFS )
        goto LABEL_49;
      Iopb = Data->Iopb;
      DeviceObject = Iopb->TargetFileObject->DeviceObject;
      if ( !DeviceObject || DeviceObject->DeviceType == 20 )
        goto LABEL_49;
      FsInformationClass_high = HIBYTE(Iopb->Parameters.SetVolumeInformation.FsInformationClass);
    }
    else
    {
      if ( FileSystemType == FLT_FSTYPE_NPFS )
        goto LABEL_49;
      FsInformationClass_high = HIBYTE(Data->Iopb->Parameters.SetVolumeInformation.FsInformationClass);
    }
    if ( FsInformationClass_high <= 5 )
    {
      v16 = 45;
      if ( _bittest(&v16, FsInformationClass_high) )
      {
        v12 = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation);
        if ( v12 < 0 )
          goto LABEL_28;
        EventDescriptor = 0;
        EventDescriptor.Keyword = (ULONGLONG)FileNameInformation->Name.Buffer;
        EventDescriptor.Id = FileNameInformation->Name.Length - FileNameInformation->Stream.Length;
        *(_WORD *)&EventDescriptor.Version = EventDescriptor.Id;
        v38 = EventDescriptor;
        if ( BfsIsPathRelevant((__int64)&v38) )
        {
          if ( !v5 )
          {
            Pool2 = ExAllocatePool2(256, 96, 1131636290);
            v5 = (_QWORD *)Pool2;
            if ( !Pool2 )
            {
LABEL_41:
              if ( (unsigned int)dword_140019000 <= 3 )
                goto LABEL_9;
              LODWORD(Pool2) = -1073741801;
              goto LABEL_43;
            }
          }
          *(_DWORD *)v5 |= 4u;
          v9 = 0;
          v5[11] = FileNameInformation;
        }
        else
        {
          FltReleaseFileNameInformation(FileNameInformation);
        }
        FileNameInformation = 0;
      }
    }
LABEL_49:
    if ( Data->RequestorMode )
    {
      v3 = PsReferenceImpersonationToken(Data->Thread, CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
      if ( v3 )
      {
        v28 = 1;
        if ( ImpersonationLevel < SecurityImpersonation )
          goto LABEL_67;
      }
      else
      {
        CurrentProcess = IoGetCurrentProcess();
        v3 = PsReferencePrimaryToken(CurrentProcess);
      }
      if ( BfsIsApplicableToken(v3, 1) )
      {
        if ( FileSystemType == FLT_FSTYPE_NPFS )
        {
          v18 = SeQueryInformationToken(v3, TokenUser, &P);
          if ( v18 < 0 )
            goto LABEL_56;
          v18 = SeQueryInformationToken(v3, TokenAppContainerSid, &TokenInformation);
          if ( v18 < 0 )
            goto LABEL_56;
          v18 = FltGetFileNameInformation(Data, 0x101u, &FileNameInformation);
          if ( v18 < 0 )
            goto LABEL_56;
          v21 = BfsAcquireNamedPipeMapping(
                  &gBfsPipeMappingTable,
                  *(_QWORD *)P,
                  *(_QWORD *)TokenInformation,
                  &FileNameInformation->Name);
          v34 = (const UNICODE_STRING *)v21;
          v4 = (const UNICODE_STRING *)v21;
          if ( v21 )
          {
            v22 = *(_WORD *)(v21 + 64);
            DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v22, 1181967938);
            if ( DestinationString.Buffer )
            {
              DestinationString.MaximumLength = v22;
              RtlCopyUnicodeString(&DestinationString, v4 + 4);
              BfsReparseNamedPipe(Data);
              v9 = 4;
              goto LABEL_9;
            }
            goto LABEL_41;
          }
LABEL_68:
          if ( !v9 )
          {
            *v6 = v5;
            goto LABEL_12;
          }
          goto LABEL_9;
        }
        v18 = BfsCheckDeleteList(a2[1], a2[3]);
        if ( v18 < 0 )
        {
LABEL_56:
          if ( (unsigned int)dword_140019000 <= 3 )
            goto LABEL_9;
          LODWORD(Pool2) = v18;
LABEL_43:
          v45 = 4;
          p_Pool2 = &Pool2;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 3;
          EventDescriptor.Keyword = 0;
          UserData.Ptr = (ULONGLONG)EventInformation;
          v11 = *(unsigned __int16 *)EventInformation;
          v43 = 1;
          goto LABEL_8;
        }
        v19 = BfsCheckAndApplyPolicy(a2[1], a2[3], v3, Data, &Pool2);
        v5 = (_QWORD *)Pool2;
        v20 = 0;
        if ( !v19 )
          v20 = v9;
        v9 = v20;
      }
    }
LABEL_67:
    v4 = v34;
    goto LABEL_68;
  }
  v10 = ExAllocatePool2(256, 96, 1131636290);
  Pool2 = v10;
  v5 = (_QWORD *)v10;
  if ( v10 )
  {
    *(_DWORD *)v10 |= 2u;
    *(_BYTE *)(v10 + 80) = 1;
    v9 = 0;
    goto LABEL_27;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(Pool2) = -1073741801;
    p_Pool2 = &Pool2;
    v45 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 3;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)EventInformation;
    v11 = *(unsigned __int16 *)EventInformation;
    v43 = 1;
LABEL_8:
    UserData.Size = v11;
    v42 = 30;
    v41 = &dword_140016D9C;
    UserData.Reserved = 2;
    v24 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
LABEL_9:
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  v6 = v37;
  v4 = v34;
LABEL_12:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v4 )
    BfsReleaseNamedPipeMapping(&gBfsPipeMappingTable, v4);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v27 && !*v6 )
  {
    KeEnterCriticalRegion();
    ExReleaseRundownProtection(&gBfsRundownProtection);
    KeLeaveCriticalRegion();
  }
  if ( v3 )
  {
    if ( v28 )
      PsDereferenceImpersonationToken(v3);
    else
      PsDereferencePrimaryToken(v3);
  }
  return v9;
}

```

## disassembly

```asm
0x140002620  mov     [rsp-8+arg_18], rbx
0x140002625  push    rbp
0x140002626  push    rsi
0x140002627  push    rdi
0x140002628  push    r12
0x14000262a  push    r13
0x14000262c  push    r14
0x14000262e  push    r15
0x140002630  lea     rbp, [rsp-27h]
0x140002635  sub     rsp, 0F0h
0x14000263c  mov     rax, cs:__security_cookie
0x140002643  xor     rax, rsp
0x140002646  mov     [rbp+57h+var_40], rax
0x14000264a  xor     eax, eax
0x14000264c  mov     [rbp+57h+var_A0], r8
0x140002650  xorps   xmm0, xmm0
0x140002653  mov     [rbp+57h+FileSystemType], eax
0x140002656  xorps   xmm1, xmm1
0x140002659  mov     [rbp+57h+ImpersonationLevel], eax
0x14000265c  movups  [rbp+57h+var_90], xmm0
0x140002660  mov     r15d, eax
0x140002663  mov     [rbp+57h+var_CF], al
0x140002666  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14000266a  mov     [rbp+57h+FileNameInformation], rax
0x14000266e  mov     r14d, eax
0x140002671  mov     [rbp+57h+var_B8], rax
0x140002675  mov     ebx, eax
0x140002677  mov     [rbp+57h+TokenInformation], rax
0x14000267b  mov     r12, r8
0x14000267e  mov     [rbp+57h+P], rax
0x140002682  mov     r13, rdx
0x140002685  mov     [rsp+120h+var_E8], rax
0x14000268a  mov     rdi, rcx
0x14000268d  mov     [r8], rax
0x140002690  mov     esi, 1
0x140002695  mov     [rbp+57h+CopyOnOpen], 0
0x140002699  mov     [rbp+57h+EffectiveOnly], 0
0x14000269d  call    cs:__imp_KeEnterCriticalRegion
0x1400026a4  nop     dword ptr [rax+rax+00h]
0x1400026a9  lea     rcx, gBfsRundownProtection; RunRef
0x1400026b0  call    cs:__imp_ExAcquireRundownProtection
0x1400026b7  nop     dword ptr [rax+rax+00h]
0x1400026bc  mov     [rbp+57h+var_D0], al
0x1400026bf  call    cs:__imp_KeLeaveCriticalRegion
0x1400026c6  nop     dword ptr [rax+rax+00h]
0x1400026cb  cmp     [rbp+57h+var_D0], bl
0x1400026ce  jnz     loc_140002792
0x1400026d4  mov     eax, cs:dword_140019000
0x1400026da  cmp     eax, 3
0x1400026dd  jbe     loc_1400028A7
0x1400026e3  xor     edx, edx
0x1400026e5  mov     [rsp+120h+var_F0], 0C0000001h
0x1400026ed  mov     [rsp+120h+EventDescriptor.Keyword], rdx
0x1400026f2  lea     rax, [rsp+120h+var_F0]
0x1400026f7  mov     [rbp+57h+var_50], rax
0x1400026fb  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x140002700  mov     rax, cs:qword_140016D92
0x140002707  xor     r9d, r9d; RelatedActivityId
0x14000270a  movzx   ecx, ax
0x14000270d  xor     r8d, r8d; ActivityId
0x140002710  mov     rax, cs:EventInformation
0x140002717  mov     [rbp+57h+var_70.Ptr], rax
0x14000271b  mov     dword ptr [rsp+120h+EventDescriptor.Level], ecx
0x14000271f  lea     rcx, _TraceLoggingMetadata
0x140002726  mov     [rbp+57h+var_48], 4
0x14000272e  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x140002736  movzx   eax, word ptr [rax]
0x140002739  mov     [rbp+57h+var_70.Size], eax
0x14000273c  lea     rax, dword_140016D9C
0x140002743  mov     [rbp+57h+var_60], rax
0x140002747  lea     rax, _TraceLoggingMetadataEnd
0x14000274e  sub     eax, ecx
0x140002750  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140002757  mov     [rbp+57h+var_58], 1Eh
0x14000275e  mov     [rbp+57h+var_54], esi
0x140002761  mov     dword ptr [rsp+120h+var_E8], eax
0x140002765  mov     eax, dword ptr [rsp+120h+var_E8]
0x140002769  mov     rcx, cs:RegHandle; RegHandle
0x140002770  lea     rax, [rbp+57h+var_70]
0x140002774  mov     [rsp+120h+UserData], rax; UserData
0x140002779  mov     [rsp+120h+UserDataCount], 3; UserDataCount
0x140002781  call    cs:__imp_EtwWriteTransfer
0x140002788  nop     dword ptr [rax+rax+00h]
0x14000278d  jmp     loc_1400028A7
0x140002792  mov     rax, [rdi+10h]
0x140002796  test    dword ptr [rax+20h], 1000h
0x14000279d  jz      loc_140002966
0x1400027a3  mov     edx, 60h ; '`'
0x1400027a8  mov     ecx, 100h
0x1400027ad  mov     r8d, 43736642h
0x1400027b3  call    cs:__imp_ExAllocatePool2
0x1400027ba  nop     dword ptr [rax+rax+00h]
0x1400027bf  mov     [rsp+120h+var_E8], rax
0x1400027c4  mov     rbx, rax
0x1400027c7  test    rax, rax
0x1400027ca  jnz     loc_14000295D
0x1400027d0  mov     eax, cs:dword_140019000
0x1400027d6  cmp     eax, 3
0x1400027d9  jbe     loc_140002889
0x1400027df  lea     rax, [rsp+120h+var_E8]
0x1400027e4  mov     dword ptr [rsp+120h+var_E8], 0C0000017h
0x1400027ec  mov     [rbp+57h+var_50], rax
0x1400027f0  xor     edx, edx
0x1400027f2  mov     rax, cs:qword_140016D92
0x1400027f9  movzx   ecx, ax
0x1400027fc  mov     rax, cs:EventInformation
0x140002803  mov     [rbp+57h+var_48], 4
0x14000280b  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x140002813  mov     dword ptr [rsp+120h+EventDescriptor.Level], ecx
0x140002817  mov     [rsp+120h+EventDescriptor.Keyword], rdx
0x14000281c  mov     [rbp+57h+var_70.Ptr], rax
0x140002820  movzx   eax, word ptr [rax]
0x140002823  mov     [rbp+57h+var_54], esi
0x140002826  mov     [rbp+57h+var_70.Size], eax
0x140002829  lea     rcx, _TraceLoggingMetadata
0x140002830  lea     rax, dword_140016D9C
0x140002837  mov     [rbp+57h+var_58], 1Eh
0x14000283e  mov     [rbp+57h+var_60], rax
0x140002842  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x140002847  lea     rax, _TraceLoggingMetadataEnd
0x14000284e  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140002855  sub     eax, ecx
0x140002857  xor     r9d, r9d; RelatedActivityId
0x14000285a  mov     [rsp+120h+var_F0], eax
0x14000285e  xor     r8d, r8d; ActivityId
0x140002861  mov     eax, [rsp+120h+var_F0]
0x140002865  mov     rcx, cs:RegHandle; RegHandle
0x14000286c  lea     rax, [rbp+57h+var_70]
0x140002870  mov     [rsp+120h+UserData], rax; UserData
0x140002875  mov     [rsp+120h+UserDataCount], 3; UserDataCount
0x14000287d  call    cs:__imp_EtwWriteTransfer
0x140002884  nop     dword ptr [rax+rax+00h]
0x140002889  test    rbx, rbx
0x14000288c  jz      short loc_14000289F
0x14000288e  xor     edx, edx; Tag
0x140002890  mov     rcx, rbx; P
0x140002893  call    cs:__imp_ExFreePoolWithTag
0x14000289a  nop     dword ptr [rax+rax+00h]
0x14000289f  mov     r12, [rbp+57h+var_A0]
0x1400028a3  mov     r14, [rbp+57h+var_B8]
0x1400028a7  mov     rcx, [rbp+57h+P]; P
0x1400028ab  test    rcx, rcx
0x1400028ae  jz      short loc_1400028BE
0x1400028b0  xor     edx, edx; Tag
0x1400028b2  call    cs:__imp_ExFreePoolWithTag
0x1400028b9  nop     dword ptr [rax+rax+00h]
0x1400028be  mov     rcx, [rbp+57h+TokenInformation]; P
0x1400028c2  test    rcx, rcx
0x1400028c5  jz      short loc_1400028D5
0x1400028c7  xor     edx, edx; Tag
0x1400028c9  call    cs:__imp_ExFreePoolWithTag
0x1400028d0  nop     dword ptr [rax+rax+00h]
0x1400028d5  test    r14, r14
0x1400028d8  jz      short loc_1400028E9
0x1400028da  mov     rdx, r14
0x1400028dd  lea     rcx, gBfsPipeMappingTable
0x1400028e4  call    BfsReleaseNamedPipeMapping
0x1400028e9  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400028ed  test    rcx, rcx
0x1400028f0  jz      short loc_1400028FE
0x1400028f2  call    cs:__imp_FltReleaseFileNameInformation
0x1400028f9  nop     dword ptr [rax+rax+00h]
0x1400028fe  cmp     [rbp+57h+var_D0], 0
0x140002902  jz      short loc_140002936
0x140002904  cmp     qword ptr [r12], 0
0x140002909  jnz     short loc_140002936
0x14000290b  call    cs:__imp_KeEnterCriticalRegion
0x140002912  nop     dword ptr [rax+rax+00h]
0x140002917  lea     rcx, gBfsRundownProtection; RunRef
0x14000291e  call    cs:__imp_ExReleaseRundownProtection
0x140002925  nop     dword ptr [rax+rax+00h]
0x14000292a  call    cs:__imp_KeLeaveCriticalRegion
0x140002931  nop     dword ptr [rax+rax+00h]
0x140002936  test    r15, r15
0x140002939  jz      loc_140002CFE
0x14000293f  cmp     [rbp+57h+var_CF], 0
0x140002943  mov     rcx, r15; PrimaryToken
0x140002946  jz      loc_140002CF2
0x14000294c  call    cs:__imp_PsDereferenceImpersonationToken
0x140002953  nop     dword ptr [rax+rax+00h]
0x140002958  jmp     loc_140002CFE
0x14000295d  or      dword ptr [rax], 2
0x140002960  mov     [rax+50h], sil
0x140002964  xor     esi, esi
0x140002966  mov     rcx, [r13+10h]; FltObject
0x14000296a  lea     rdx, [rbp+57h+FileSystemType]; FileSystemType
0x14000296e  call    cs:__imp_FltGetFileSystemType
0x140002975  nop     dword ptr [rax+rax+00h]
0x14000297a  mov     r14d, eax
0x14000297d  test    eax, eax
0x14000297f  jns     short loc_14000299A
0x140002981  mov     eax, cs:dword_140019000
0x140002987  cmp     eax, 3
0x14000298a  jbe     loc_140002889
0x140002990  mov     dword ptr [rsp+120h+var_E8], r14d
0x140002995  jmp     loc_140002A9C
0x14000299a  call    Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline
0x14000299f  test    eax, eax
0x1400029a1  jz      loc_140002AE4
0x1400029a7  cmp     [rbp+57h+FileSystemType], 19h
0x1400029ab  jz      loc_140002B1A
0x1400029b1  mov     rdx, [rdi+10h]
0x1400029b5  mov     rax, [rdx+8]
0x1400029b9  mov     rcx, [rax+8]
0x1400029bd  test    rcx, rcx
0x1400029c0  jz      loc_140002B1A
0x1400029c6  cmp     dword ptr [rcx+48h], 14h
0x1400029ca  jz      loc_140002B1A
0x1400029d0  movzx   ecx, byte ptr [rdx+23h]
0x1400029d4  cmp     ecx, 5
0x1400029d7  ja      loc_140002B1A
0x1400029dd  mov     eax, 2Dh ; '-'
0x1400029e2  bt      eax, ecx
0x1400029e5  jnb     loc_140002B1A
0x1400029eb  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400029ef  mov     edx, 101h; NameOptions
0x1400029f4  mov     rcx, rdi; CallbackData
0x1400029f7  call    cs:__imp_FltGetFileNameInformation
0x1400029fe  nop     dword ptr [rax+rax+00h]
0x140002a03  mov     r14d, eax
0x140002a06  test    eax, eax
0x140002a08  js      loc_140002981
0x140002a0e  mov     rcx, [rbp+57h+FileNameInformation]
0x140002a12  xorps   xmm0, xmm0
0x140002a15  movups  xmmword ptr [rsp+120h+EventDescriptor.Id], xmm0
0x140002a1a  mov     rax, [rcx+10h]
0x140002a1e  mov     [rsp+120h+EventDescriptor.Keyword], rax
0x140002a23  movzx   eax, word ptr [rcx+48h]
0x140002a27  movzx   ecx, word ptr [rcx+8]
0x140002a2b  sub     cx, ax
0x140002a2e  mov     [rsp+120h+EventDescriptor.Id], cx
0x140002a33  mov     word ptr [rsp+120h+EventDescriptor.Version], cx
0x140002a38  lea     rcx, [rbp+57h+var_90]
0x140002a3c  movaps  xmm0, xmmword ptr [rsp+120h+EventDescriptor.Id]
0x140002a41  movdqa  [rbp+57h+var_90], xmm0
0x140002a46  call    BfsIsPathRelevant
0x140002a4b  test    al, al
0x140002a4d  jz      loc_140002B06
0x140002a53  test    rbx, rbx
0x140002a56  jnz     loc_140002AF7
0x140002a5c  mov     edx, 60h ; '`'
0x140002a61  mov     ecx, 100h
0x140002a66  mov     r8d, 43736642h
0x140002a6c  call    cs:__imp_ExAllocatePool2
0x140002a73  nop     dword ptr [rax+rax+00h]
0x140002a78  mov     [rsp+120h+var_E8], rax
0x140002a7d  mov     rbx, rax
0x140002a80  test    rax, rax
0x140002a83  jnz     short loc_140002AF7
0x140002a85  mov     eax, cs:dword_140019000
0x140002a8b  cmp     eax, 3
0x140002a8e  jbe     loc_140002889
0x140002a94  mov     dword ptr [rsp+120h+var_E8], 0C0000017h
0x140002a9c  lea     rax, [rsp+120h+var_E8]
0x140002aa1  mov     [rbp+57h+var_48], 4
0x140002aa9  mov     [rbp+57h+var_50], rax
0x140002aad  xor     edx, edx
0x140002aaf  mov     rax, cs:qword_140016D92
0x140002ab6  movzx   ecx, ax
0x140002ab9  mov     rax, cs:EventInformation
0x140002ac0  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x140002ac8  mov     dword ptr [rsp+120h+EventDescriptor.Level], ecx
0x140002acc  mov     [rsp+120h+EventDescriptor.Keyword], rdx
0x140002ad1  mov     [rbp+57h+var_70.Ptr], rax
0x140002ad5  movzx   eax, word ptr [rax]
0x140002ad8  mov     [rbp+57h+var_54], 1
0x140002adf  jmp     loc_140002826
0x140002ae4  cmp     [rbp+57h+FileSystemType], 19h
0x140002ae8  jz      short loc_140002B1A
0x140002aea  mov     rax, [rdi+10h]
0x140002aee  movzx   ecx, byte ptr [rax+23h]
0x140002af2  jmp     loc_1400029D4
0x140002af7  or      dword ptr [rbx], 4
0x140002afa  mov     rax, [rbp+57h+FileNameInformation]
0x140002afe  xor     esi, esi
0x140002b00  mov     [rbx+58h], rax
0x140002b04  jmp     short loc_140002B16
0x140002b06  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140002b0a  call    cs:__imp_FltReleaseFileNameInformation
0x140002b11  nop     dword ptr [rax+rax+00h]
0x140002b16  mov     [rbp+57h+FileNameInformation], r15
0x140002b1a  cmp     [rdi+50h], r15b
0x140002b1e  jz      loc_140002CD4
0x140002b24  mov     rcx, [rdi+8]; Thread
0x140002b28  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x140002b2c  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x140002b30  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x140002b34  call    cs:__imp_PsReferenceImpersonationToken
0x140002b3b  nop     dword ptr [rax+rax+00h]
0x140002b40  mov     r15, rax
0x140002b43  test    rax, rax
0x140002b46  jnz     short loc_140002B68
0x140002b48  call    cs:__imp_IoGetCurrentProcess
0x140002b4f  nop     dword ptr [rax+rax+00h]
0x140002b54  mov     rcx, rax; Process
0x140002b57  call    cs:__imp_PsReferencePrimaryToken
0x140002b5e  nop     dword ptr [rax+rax+00h]
0x140002b63  mov     r15, rax
0x140002b66  jmp     short loc_140002B76
0x140002b68  cmp     [rbp+57h+ImpersonationLevel], 2
  ... truncated ...
```
