# BfsPreCreateOperation

- ea: `0x140002a30`
- end: `0x140003138`
- name: `BfsPreCreateOperation`
- size: `1800`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140001270`
- `0x1400012b0`
- `0x140002a30`
- `0x140003210`
- `0x1400055d8`
- `0x14000b338`
- `0x14000bd0c`
- `0x14000bde4`
- `0x14000c1b4`
- `0x140013730`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x140003102`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140003102`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140002d5c`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140002d5c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002d2e`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002d2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ca3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002cc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002cd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ca3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002cc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002cd9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400030c2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400030c2`
- `ntoskrnl!SeQueryInformationToken` at `0x140003005`
- `ntoskrnl!SeQueryInformationToken` at `0x140003023`
- `ntoskrnl!SeQueryInformationToken` at `0x140003005`
- `ntoskrnl!SeQueryInformationToken` at `0x140003023`
- `ntoskrnl!IoGetCurrentProcess` at `0x140002f58`
- `ntoskrnl!IoGetCurrentProcess` at `0x140002f58`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140002f67`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140002f67`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140002f44`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140002f44`
- `ntoskrnl!ExAllocatePool2` at `0x140002bc3`
- `ntoskrnl!ExAllocatePool2` at `0x140002e7c`
- `ntoskrnl!ExAllocatePool2` at `0x14000309c`
- `ntoskrnl!ExAllocatePool2` at `0x140002bc3`
- `ntoskrnl!ExAllocatePool2` at `0x140002e7c`
- `ntoskrnl!ExAllocatePool2` at `0x14000309c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002aad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002d1b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002aad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002d1b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002ac0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002ac0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002acf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002d3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002acf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002d3a`
- `ntoskrnl!EtwWriteTransfer` at `0x140002b91`
- `ntoskrnl!EtwWriteTransfer` at `0x140002c8d`
- `ntoskrnl!EtwWriteTransfer` at `0x140002b91`
- `ntoskrnl!EtwWriteTransfer` at `0x140002c8d`
- `FLTMGR!FltGetFileNameInformation` at `0x140002e07`
- `FLTMGR!FltGetFileNameInformation` at `0x140003045`
- `FLTMGR!FltGetFileNameInformation` at `0x140002e07`
- `FLTMGR!FltGetFileNameInformation` at `0x140003045`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002d02`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002f1a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002d02`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002f1a`
- `FLTMGR!FltGetFileSystemType` at `0x140002d7e`
- `FLTMGR!FltGetFileSystemType` at `0x140002d7e`

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
  CopyOnOpen[0] = 0;
  v9 = 1;
  EffectiveOnly = 0;
  *a3 = 0;
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
        if ( (unsigned __int8)BfsIsPathRelevant(&v38) )
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
      if ( (unsigned __int8)BfsIsApplicableToken(v3) )
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
        v19 = BfsCheckAndApplyPolicy(a2[1], a2[3], v3, Data, (__int64)&Pool2);
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
0x140002a30  mov     [rsp-8+arg_18], rbx
0x140002a35  push    rbp
0x140002a36  push    rsi
0x140002a37  push    rdi
0x140002a38  push    r12
0x140002a3a  push    r13
0x140002a3c  push    r14
0x140002a3e  push    r15
0x140002a40  lea     rbp, [rsp-27h]
0x140002a45  sub     rsp, 0F0h
0x140002a4c  mov     rax, cs:__security_cookie
0x140002a53  xor     rax, rsp
0x140002a56  mov     [rbp+57h+var_40], rax
0x140002a5a  xor     eax, eax
0x140002a5c  mov     [rbp+57h+var_A0], r8
0x140002a60  xorps   xmm0, xmm0
0x140002a63  mov     [rbp+57h+FileSystemType], eax
0x140002a66  xorps   xmm1, xmm1
0x140002a69  mov     [rbp+57h+ImpersonationLevel], eax
0x140002a6c  movups  [rbp+57h+var_90], xmm0
0x140002a70  mov     r15d, eax
0x140002a73  mov     [rbp+57h+var_CF], al
0x140002a76  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140002a7a  mov     [rbp+57h+FileNameInformation], rax
0x140002a7e  mov     r14d, eax
0x140002a81  mov     [rbp+57h+var_B8], rax
0x140002a85  mov     ebx, eax
0x140002a87  mov     [rbp+57h+TokenInformation], rax
0x140002a8b  mov     r12, r8
0x140002a8e  mov     [rbp+57h+P], rax
0x140002a92  mov     r13, rdx
0x140002a95  mov     [rsp+120h+var_E8], rax
0x140002a9a  mov     rdi, rcx
0x140002a9d  mov     [rbp+57h+CopyOnOpen], 0
0x140002aa1  mov     esi, 1
0x140002aa6  mov     [rbp+57h+EffectiveOnly], 0
0x140002aaa  mov     [r8], rax
0x140002aad  call    cs:__imp_KeEnterCriticalRegion
0x140002ab4  nop     dword ptr [rax+rax+00h]
0x140002ab9  lea     rcx, gBfsRundownProtection; RunRef
0x140002ac0  call    cs:__imp_ExAcquireRundownProtection
0x140002ac7  nop     dword ptr [rax+rax+00h]
0x140002acc  mov     [rbp+57h+var_D0], al
0x140002acf  call    cs:__imp_KeLeaveCriticalRegion
0x140002ad6  nop     dword ptr [rax+rax+00h]
0x140002adb  cmp     [rbp+57h+var_D0], bl
0x140002ade  jnz     loc_140002BA2
0x140002ae4  mov     eax, cs:dword_140019000
0x140002aea  cmp     eax, 3
0x140002aed  jbe     loc_140002CB7
0x140002af3  xor     edx, edx
0x140002af5  mov     [rsp+120h+var_F0], 0C0000001h
0x140002afd  mov     [rsp+120h+EventDescriptor.Keyword], rdx
0x140002b02  lea     rax, [rsp+120h+var_F0]
0x140002b07  mov     [rbp+57h+var_50], rax
0x140002b0b  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x140002b10  mov     rax, cs:qword_140016D92
0x140002b17  xor     r9d, r9d; RelatedActivityId
0x140002b1a  movzx   ecx, ax
0x140002b1d  xor     r8d, r8d; ActivityId
0x140002b20  mov     rax, cs:EventInformation
0x140002b27  mov     [rbp+57h+var_70.Ptr], rax
0x140002b2b  mov     dword ptr [rsp+120h+EventDescriptor.Level], ecx
0x140002b2f  lea     rcx, _TraceLoggingMetadata
0x140002b36  mov     [rbp+57h+var_48], 4
0x140002b3e  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x140002b46  movzx   eax, word ptr [rax]
0x140002b49  mov     [rbp+57h+var_70.Size], eax
0x140002b4c  lea     rax, dword_140016D9C
0x140002b53  mov     [rbp+57h+var_60], rax
0x140002b57  lea     rax, _TraceLoggingMetadataEnd
0x140002b5e  sub     eax, ecx
0x140002b60  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140002b67  mov     [rbp+57h+var_58], 1Eh
0x140002b6e  mov     [rbp+57h+var_54], esi
0x140002b71  mov     dword ptr [rsp+120h+var_E8], eax
0x140002b75  mov     eax, dword ptr [rsp+120h+var_E8]
0x140002b79  mov     rcx, cs:RegHandle; RegHandle
0x140002b80  lea     rax, [rbp+57h+var_70]
0x140002b84  mov     [rsp+120h+UserData], rax; UserData
0x140002b89  mov     [rsp+120h+UserDataCount], 3; UserDataCount
0x140002b91  call    cs:__imp_EtwWriteTransfer
0x140002b98  nop     dword ptr [rax+rax+00h]
0x140002b9d  jmp     loc_140002CB7
0x140002ba2  mov     rax, [rdi+10h]
0x140002ba6  test    dword ptr [rax+20h], 1000h
0x140002bad  jz      loc_140002D76
0x140002bb3  mov     edx, 60h ; '`'
0x140002bb8  mov     ecx, 100h
0x140002bbd  mov     r8d, 43736642h
0x140002bc3  call    cs:__imp_ExAllocatePool2
0x140002bca  nop     dword ptr [rax+rax+00h]
0x140002bcf  mov     [rsp+120h+var_E8], rax
0x140002bd4  mov     rbx, rax
0x140002bd7  test    rax, rax
0x140002bda  jnz     loc_140002D6D
0x140002be0  mov     eax, cs:dword_140019000
0x140002be6  cmp     eax, 3
0x140002be9  jbe     loc_140002C99
0x140002bef  lea     rax, [rsp+120h+var_E8]
0x140002bf4  mov     dword ptr [rsp+120h+var_E8], 0C0000017h
0x140002bfc  mov     [rbp+57h+var_50], rax
0x140002c00  xor     edx, edx
0x140002c02  mov     rax, cs:qword_140016D92
0x140002c09  movzx   ecx, ax
0x140002c0c  mov     rax, cs:EventInformation
0x140002c13  mov     [rbp+57h+var_48], 4
0x140002c1b  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x140002c23  mov     dword ptr [rsp+120h+EventDescriptor.Level], ecx
0x140002c27  mov     [rsp+120h+EventDescriptor.Keyword], rdx
0x140002c2c  mov     [rbp+57h+var_70.Ptr], rax
0x140002c30  movzx   eax, word ptr [rax]
0x140002c33  mov     [rbp+57h+var_54], esi
0x140002c36  mov     [rbp+57h+var_70.Size], eax
0x140002c39  lea     rcx, _TraceLoggingMetadata
0x140002c40  lea     rax, dword_140016D9C
0x140002c47  mov     [rbp+57h+var_58], 1Eh
0x140002c4e  mov     [rbp+57h+var_60], rax
0x140002c52  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x140002c57  lea     rax, _TraceLoggingMetadataEnd
0x140002c5e  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x140002c65  sub     eax, ecx
0x140002c67  xor     r9d, r9d; RelatedActivityId
0x140002c6a  mov     [rsp+120h+var_F0], eax
0x140002c6e  xor     r8d, r8d; ActivityId
0x140002c71  mov     eax, [rsp+120h+var_F0]
0x140002c75  mov     rcx, cs:RegHandle; RegHandle
0x140002c7c  lea     rax, [rbp+57h+var_70]
0x140002c80  mov     [rsp+120h+UserData], rax; UserData
0x140002c85  mov     [rsp+120h+UserDataCount], 3; UserDataCount
0x140002c8d  call    cs:__imp_EtwWriteTransfer
0x140002c94  nop     dword ptr [rax+rax+00h]
0x140002c99  test    rbx, rbx
0x140002c9c  jz      short loc_140002CAF
0x140002c9e  xor     edx, edx; Tag
0x140002ca0  mov     rcx, rbx; P
0x140002ca3  call    cs:__imp_ExFreePoolWithTag
0x140002caa  nop     dword ptr [rax+rax+00h]
0x140002caf  mov     r12, [rbp+57h+var_A0]
0x140002cb3  mov     r14, [rbp+57h+var_B8]
0x140002cb7  mov     rcx, [rbp+57h+P]; P
0x140002cbb  test    rcx, rcx
0x140002cbe  jz      short loc_140002CCE
0x140002cc0  xor     edx, edx; Tag
0x140002cc2  call    cs:__imp_ExFreePoolWithTag
0x140002cc9  nop     dword ptr [rax+rax+00h]
0x140002cce  mov     rcx, [rbp+57h+TokenInformation]; P
0x140002cd2  test    rcx, rcx
0x140002cd5  jz      short loc_140002CE5
0x140002cd7  xor     edx, edx; Tag
0x140002cd9  call    cs:__imp_ExFreePoolWithTag
0x140002ce0  nop     dword ptr [rax+rax+00h]
0x140002ce5  test    r14, r14
0x140002ce8  jz      short loc_140002CF9
0x140002cea  mov     rdx, r14
0x140002ced  lea     rcx, gBfsPipeMappingTable
0x140002cf4  call    BfsReleaseNamedPipeMapping
0x140002cf9  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140002cfd  test    rcx, rcx
0x140002d00  jz      short loc_140002D0E
0x140002d02  call    cs:__imp_FltReleaseFileNameInformation
0x140002d09  nop     dword ptr [rax+rax+00h]
0x140002d0e  cmp     [rbp+57h+var_D0], 0
0x140002d12  jz      short loc_140002D46
0x140002d14  cmp     qword ptr [r12], 0
0x140002d19  jnz     short loc_140002D46
0x140002d1b  call    cs:__imp_KeEnterCriticalRegion
0x140002d22  nop     dword ptr [rax+rax+00h]
0x140002d27  lea     rcx, gBfsRundownProtection; RunRef
0x140002d2e  call    cs:__imp_ExReleaseRundownProtection
0x140002d35  nop     dword ptr [rax+rax+00h]
0x140002d3a  call    cs:__imp_KeLeaveCriticalRegion
0x140002d41  nop     dword ptr [rax+rax+00h]
0x140002d46  test    r15, r15
0x140002d49  jz      loc_14000310E
0x140002d4f  cmp     [rbp+57h+var_CF], 0
0x140002d53  mov     rcx, r15; PrimaryToken
0x140002d56  jz      loc_140003102
0x140002d5c  call    cs:__imp_PsDereferenceImpersonationToken
0x140002d63  nop     dword ptr [rax+rax+00h]
0x140002d68  jmp     loc_14000310E
0x140002d6d  or      dword ptr [rax], 2
0x140002d70  mov     [rax+50h], sil
0x140002d74  xor     esi, esi
0x140002d76  mov     rcx, [r13+10h]; FltObject
0x140002d7a  lea     rdx, [rbp+57h+FileSystemType]; FileSystemType
0x140002d7e  call    cs:__imp_FltGetFileSystemType
0x140002d85  nop     dword ptr [rax+rax+00h]
0x140002d8a  mov     r14d, eax
0x140002d8d  test    eax, eax
0x140002d8f  jns     short loc_140002DAA
0x140002d91  mov     eax, cs:dword_140019000
0x140002d97  cmp     eax, 3
0x140002d9a  jbe     loc_140002C99
0x140002da0  mov     dword ptr [rsp+120h+var_E8], r14d
0x140002da5  jmp     loc_140002EAC
0x140002daa  call    Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline
0x140002daf  test    eax, eax
0x140002db1  jz      loc_140002EF4
0x140002db7  cmp     [rbp+57h+FileSystemType], 19h
0x140002dbb  jz      loc_140002F2A
0x140002dc1  mov     rdx, [rdi+10h]
0x140002dc5  mov     rax, [rdx+8]
0x140002dc9  mov     rcx, [rax+8]
0x140002dcd  test    rcx, rcx
0x140002dd0  jz      loc_140002F2A
0x140002dd6  cmp     dword ptr [rcx+48h], 14h
0x140002dda  jz      loc_140002F2A
0x140002de0  movzx   ecx, byte ptr [rdx+23h]
0x140002de4  cmp     ecx, 5
0x140002de7  ja      loc_140002F2A
0x140002ded  mov     eax, 2Dh ; '-'
0x140002df2  bt      eax, ecx
0x140002df5  jnb     loc_140002F2A
0x140002dfb  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x140002dff  mov     edx, 101h; NameOptions
0x140002e04  mov     rcx, rdi; CallbackData
0x140002e07  call    cs:__imp_FltGetFileNameInformation
0x140002e0e  nop     dword ptr [rax+rax+00h]
0x140002e13  mov     r14d, eax
0x140002e16  test    eax, eax
0x140002e18  js      loc_140002D91
0x140002e1e  mov     rcx, [rbp+57h+FileNameInformation]
0x140002e22  xorps   xmm0, xmm0
0x140002e25  movups  xmmword ptr [rsp+120h+EventDescriptor.Id], xmm0
0x140002e2a  mov     rax, [rcx+10h]
0x140002e2e  mov     [rsp+120h+EventDescriptor.Keyword], rax
0x140002e33  movzx   eax, word ptr [rcx+48h]
0x140002e37  movzx   ecx, word ptr [rcx+8]
0x140002e3b  sub     cx, ax
0x140002e3e  mov     [rsp+120h+EventDescriptor.Id], cx
0x140002e43  mov     word ptr [rsp+120h+EventDescriptor.Version], cx
0x140002e48  lea     rcx, [rbp+57h+var_90]
0x140002e4c  movaps  xmm0, xmmword ptr [rsp+120h+EventDescriptor.Id]
0x140002e51  movdqa  [rbp+57h+var_90], xmm0
0x140002e56  call    BfsIsPathRelevant
0x140002e5b  test    al, al
0x140002e5d  jz      loc_140002F16
0x140002e63  test    rbx, rbx
0x140002e66  jnz     loc_140002F07
0x140002e6c  mov     edx, 60h ; '`'
0x140002e71  mov     ecx, 100h
0x140002e76  mov     r8d, 43736642h
0x140002e7c  call    cs:__imp_ExAllocatePool2
0x140002e83  nop     dword ptr [rax+rax+00h]
0x140002e88  mov     [rsp+120h+var_E8], rax
0x140002e8d  mov     rbx, rax
0x140002e90  test    rax, rax
0x140002e93  jnz     short loc_140002F07
0x140002e95  mov     eax, cs:dword_140019000
0x140002e9b  cmp     eax, 3
0x140002e9e  jbe     loc_140002C99
0x140002ea4  mov     dword ptr [rsp+120h+var_E8], 0C0000017h
0x140002eac  lea     rax, [rsp+120h+var_E8]
0x140002eb1  mov     [rbp+57h+var_48], 4
0x140002eb9  mov     [rbp+57h+var_50], rax
0x140002ebd  xor     edx, edx
0x140002ebf  mov     rax, cs:qword_140016D92
0x140002ec6  movzx   ecx, ax
0x140002ec9  mov     rax, cs:EventInformation
0x140002ed0  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x140002ed8  mov     dword ptr [rsp+120h+EventDescriptor.Level], ecx
0x140002edc  mov     [rsp+120h+EventDescriptor.Keyword], rdx
0x140002ee1  mov     [rbp+57h+var_70.Ptr], rax
0x140002ee5  movzx   eax, word ptr [rax]
0x140002ee8  mov     [rbp+57h+var_54], 1
0x140002eef  jmp     loc_140002C36
0x140002ef4  cmp     [rbp+57h+FileSystemType], 19h
0x140002ef8  jz      short loc_140002F2A
0x140002efa  mov     rax, [rdi+10h]
0x140002efe  movzx   ecx, byte ptr [rax+23h]
0x140002f02  jmp     loc_140002DE4
0x140002f07  or      dword ptr [rbx], 4
0x140002f0a  mov     rax, [rbp+57h+FileNameInformation]
0x140002f0e  xor     esi, esi
0x140002f10  mov     [rbx+58h], rax
0x140002f14  jmp     short loc_140002F26
0x140002f16  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140002f1a  call    cs:__imp_FltReleaseFileNameInformation
0x140002f21  nop     dword ptr [rax+rax+00h]
0x140002f26  mov     [rbp+57h+FileNameInformation], r15
0x140002f2a  cmp     [rdi+50h], r15b
0x140002f2e  jz      loc_1400030E4
0x140002f34  mov     rcx, [rdi+8]; Thread
0x140002f38  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x140002f3c  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x140002f40  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x140002f44  call    cs:__imp_PsReferenceImpersonationToken
0x140002f4b  nop     dword ptr [rax+rax+00h]
0x140002f50  mov     r15, rax
0x140002f53  test    rax, rax
0x140002f56  jnz     short loc_140002F78
0x140002f58  call    cs:__imp_IoGetCurrentProcess
0x140002f5f  nop     dword ptr [rax+rax+00h]
0x140002f64  mov     rcx, rax; Process
0x140002f67  call    cs:__imp_PsReferencePrimaryToken
0x140002f6e  nop     dword ptr [rax+rax+00h]
0x140002f73  mov     r15, rax
0x140002f76  jmp     short loc_140002F86
0x140002f78  cmp     [rbp+57h+ImpersonationLevel], 2
  ... truncated ...
```
