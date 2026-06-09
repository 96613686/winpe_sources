# Streaming::StagingManager::StageDirectoryInternal(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA *)

- ea: `0x14000a310`
- end: `0x14000abcf`
- name: `?StageDirectoryInternal@StagingManager@Streaming@@CAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `2239`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x140001bc0`
- `0x14000abd8`

## callees

- `0x1400023d8`
- `0x140002a14`
- `0x140002b3c`
- `0x140002cb8`
- `0x140005e3c`
- `0x140005fb8`
- `0x14000a1ac`
- `0x14000a1f0`
- `0x14000a310`
- `0x140011478`
- `0x1400147fc`
- `0x140014934`
- `0x140014b00`
- `0x140014c40`
- `0x1400153c4`
- `0x140015af0`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14000a723`
- `ntoskrnl!EtwActivityIdControl` at `0x14000a723`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a7ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a9d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000aa97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a7ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a9d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000aa97`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a7a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a9cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000aa8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a7a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a9cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000aa8b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a775`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000a775`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a762`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a762`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a356`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a370`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a396`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a356`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a370`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a396`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a450`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a47d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a495`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a6c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a6ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a706`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a7f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a820`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a838`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa20`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aaf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab96`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a450`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a47d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a495`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a6c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a6ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a706`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a7f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a820`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a838`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa20`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aa65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aaf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab96`
- `FLTMGR!FltQueryInformationFile` at `0x14000a3d2`
- `FLTMGR!FltQueryInformationFile` at `0x14000a3d2`
- `FLTMGR!FltGetStreamContext` at `0x14000a575`
- `FLTMGR!FltGetStreamContext` at `0x14000a575`
- `FLTMGR!FltReleaseContext` at `0x14000a466`
- `FLTMGR!FltReleaseContext` at `0x14000a592`
- `FLTMGR!FltReleaseContext` at `0x14000a5ce`
- `FLTMGR!FltReleaseContext` at `0x14000a6a9`
- `FLTMGR!FltReleaseContext` at `0x14000a6d7`
- `FLTMGR!FltReleaseContext` at `0x14000a7db`
- `FLTMGR!FltReleaseContext` at `0x14000a809`
- `FLTMGR!FltReleaseContext` at `0x14000aa08`
- `FLTMGR!FltReleaseContext` at `0x14000aa36`
- `FLTMGR!FltReleaseContext` at `0x14000aad8`
- `FLTMGR!FltReleaseContext` at `0x14000ab06`
- `FLTMGR!FltReleaseContext` at `0x14000ab67`
- `FLTMGR!FltReleaseContext` at `0x14000a466`
- `FLTMGR!FltReleaseContext` at `0x14000a592`
- `FLTMGR!FltReleaseContext` at `0x14000a5ce`
- `FLTMGR!FltReleaseContext` at `0x14000a6a9`
- `FLTMGR!FltReleaseContext` at `0x14000a6d7`
- `FLTMGR!FltReleaseContext` at `0x14000a7db`
- `FLTMGR!FltReleaseContext` at `0x14000a809`
- `FLTMGR!FltReleaseContext` at `0x14000aa08`
- `FLTMGR!FltReleaseContext` at `0x14000aa36`
- `FLTMGR!FltReleaseContext` at `0x14000aad8`
- `FLTMGR!FltReleaseContext` at `0x14000ab06`
- `FLTMGR!FltReleaseContext` at `0x14000ab67`

## string_xrefs

- `0x14000a529`: `StagingManager::StageDirectoryInternal() - Failed to retrieve directory context. Directory path %s, error code 0x%08X.`
- `0x14000a610`: `StagingManager::StageDirectoryInternal() - Failed to retrieve directory context. Directory path %s, error code 0x%08X.`
- `0x14000a929`: `StagingManager::StageDirectoryInternal() - Failed to stage file %s, error code 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::StagingManager::StageDirectoryInternal(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CALLBACK_DATA CallbackData)
{
  Streaming::InstanceContextFactory *v6; // rcx
  int DosName; // ebx
  _QWORD *v9; // rbx
  NTSTATUS StreamContext; // r14d
  NTSTATUS v11; // eax
  __int64 v12; // rdi
  __int64 *v13; // rax
  volatile signed __int32 *v14; // rdi
  volatile signed __int32 *v15; // rdi
  __int64 v16; // r15
  bool v17; // r14
  struct _ERESOURCE *v18; // rcx
  const wchar_t *v19; // rdi
  Streaming::staging_operations **NullTerminated; // rax
  int v21; // eax
  volatile signed __int32 *v22; // rdi
  volatile signed __int32 *v23; // rdi
  __int64 v24; // rdi
  __int64 *CurrentActivityID; // rax
  unsigned int v26; // r12d
  volatile signed __int32 *v27; // rdi
  volatile signed __int32 *v28; // rdi
  struct _ERESOURCE *v29; // rcx
  struct _ERESOURCE *v30; // rcx
  unsigned int v31; // edi
  unsigned int *FileInformationClass; // [rsp+20h] [rbp-E0h]
  const struct _GUID *FileInformationClassa; // [rsp+20h] [rbp-E0h]
  const struct _GUID *FileInformationClassb; // [rsp+20h] [rbp-E0h]
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v36[24]; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  PFLT_CONTEXT v38; // [rsp+60h] [rbp-A0h] BYREF
  volatile signed __int32 *v39; // [rsp+68h] [rbp-98h]
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  PVOID P; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING v42; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v43; // [rsp+90h] [rbp-70h] BYREF
  volatile signed __int32 *v44; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h] BYREF
  PVOID v46; // [rsp+A8h] [rbp-58h]
  struct _UNICODE_STRING v47; // [rsp+B0h] [rbp-50h] BYREF
  __int128 FileInformation; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+E0h] [rbp-20h]
  GUID ActivityId; // [rsp+F0h] [rbp-10h] BYREF

  *(_OWORD *)&v36[8] = 0u;
  RtlInitUnicodeString(&DestinationString, 0);
  v45 = 0;
  v46 = 0;
  RtlInitUnicodeString(&v47, 0);
  v38 = 0;
  Context = 0;
  v40 = 0;
  P = 0;
  RtlInitUnicodeString(&v42, 0);
  v43 = 0;
  v50 = 0;
  FileInformation = 0;
  v49 = 0;
  if ( FltQueryInformationFile(Instance, FileObject, &FileInformation, 0x28u, FileBasicInformation, 0) >= 0
    && (v50 & 0x1000) != 0
    && (*(_QWORD *)&FileInformation = 1114128,
        *((_QWORD *)&FileInformation + 1) = &strmDirectoryEaName,
        *(_DWORD *)v36 = 0,
        Streaming::FileOperations::GetEA(
          Instance,
          (struct _FLT_INSTANCE *)FileObject,
          (struct _FILE_OBJECT *)&FileInformation,
          (const struct _STRING *)v36,
          FileInformationClass) >= 0)
    && *(_DWORD *)v36 )
  {
    DosName = Streaming::InstanceContextFactory::GetContext(v6, Instance, (struct Streaming::InstanceContext *)&Context);
    if ( DosName < 0 )
      goto LABEL_6;
    DosName = Streaming::InstanceContext::GetDosName(
                (Streaming::InstanceContext *)&Context,
                (const struct _UNICODE_STRING **)&v38);
    if ( DosName < 0 )
      goto LABEL_6;
    if ( CallbackData )
    {
      DosName = Streaming::FileOperations::GetFilePathFromCallback(CallbackData, v38, &v36[8], &v45);
      if ( DosName < 0 )
        goto LABEL_6;
      DosName = Streaming::Utils::GetProcessAndUserNotSystem(CallbackData, (__int64)&v40, (HANDLE *)&v43);
      if ( DosName < 0 )
        goto LABEL_6;
    }
    else
    {
      DosName = Streaming::FileOperations::GetDosFilePathUnsafe(Instance, FileObject);
      if ( DosName < 0
        || (DosName = Streaming::Utils::GetCurrentProcessAndUserNotSystem((__int64)&v40, &v43), DosName < 0) )
      {
        LODWORD(FileInformationClassa) = DosName;
        FileInformation = *(_OWORD *)&v36[8];
        v49 = DestinationString;
        LogWrite(
          2,
          0,
          L"StagingManager::StageDirectoryInternal() - Failed to retrieve directory context. Directory path %s, error code 0x%08X.",
          &FileInformation,
          FileInformationClassa);
LABEL_6:
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( Context )
          FltReleaseContext(Context);
        if ( v46 )
          ExFreePoolWithTag(v46, 0);
        if ( *(_QWORD *)&v36[16] )
          ExFreePoolWithTag(*(PVOID *)&v36[16], 0);
        return (unsigned int)DosName;
      }
    }
    v9 = 0;
    v38 = 0;
    *(_QWORD *)v36 = 0;
    StreamContext = FltGetStreamContext(Instance, FileObject, &v38);
    if ( StreamContext >= 0 )
    {
      if ( *(_BYTE *)v38 )
      {
        v9 = v38;
      }
      else
      {
        FltReleaseContext(v38);
        StreamContext = -1073741637;
      }
    }
    else
    {
      if ( v38 )
        FltReleaseContext(v38);
      if ( StreamContext == -1073741275 )
      {
        v11 = Streaming::Context::DirectoryContextFactory::CreateStreamContext(Instance, FileObject);
        v9 = *(_QWORD **)v36;
        StreamContext = v11;
      }
    }
    if ( StreamContext >= 0 )
    {
      EtwActivityIdControl(3u, &ActivityId);
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0_EtwWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
          StrmFlt_STAGE_DIRECTORY_START,
          &ActivityId);
      v16 = v9[1];
      v17 = 0;
      if ( *(_QWORD *)(v16 + 8) )
      {
        KeEnterCriticalRegion();
        v17 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v16 + 8), 1u) == 1;
      }
      if ( *((_BYTE *)v9 + 24) )
      {
        if ( v17 )
        {
          v18 = *(struct _ERESOURCE **)(v16 + 8);
          if ( v18 )
          {
            ExReleaseResourceLite(v18);
            KeLeaveCriticalRegion();
          }
        }
        if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
          McTemplateK0_EtwWriteTransfer(
            PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
            StrmFlt_STAGE_DIRECTORY_STOP,
            &ActivityId);
        FltReleaseContext(v9);
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( Context )
          FltReleaseContext(Context);
        if ( v46 )
          ExFreePoolWithTag(v46, 0);
        if ( *(_QWORD *)&v36[16] )
          ExFreePoolWithTag(*(PVOID *)&v36[16], 0);
        return 0;
      }
      else
      {
        v19 = *(const wchar_t **)Streaming::Utils::GetNullTerminated(&v38, &v42);
        NullTerminated = (Streaming::staging_operations **)Streaming::Utils::GetNullTerminated(
                                                             &FileInformation,
                                                             &DestinationString);
        v21 = Streaming::staging_operations::stage_directory(
                *NullTerminated,
                v19,
                v43,
                &ActivityId,
                FileInformationClassa);
        v22 = (volatile signed __int32 *)*((_QWORD *)&FileInformation + 1);
        *(_DWORD *)v36 = v21;
        if ( *((_QWORD *)&FileInformation + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&FileInformation + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 16LL))(v22);
          }
        }
        v23 = v39;
        if ( v39 )
        {
          if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
            if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 16LL))(v23);
          }
        }
        if ( *(int *)v36 >= 0 )
        {
          *((_BYTE *)v9 + 24) = 1;
          if ( v17 )
          {
            v30 = *(struct _ERESOURCE **)(v16 + 8);
            if ( v30 )
            {
              ExReleaseResourceLite(v30);
              KeLeaveCriticalRegion();
            }
          }
          v31 = Streaming::StagingManager::RemoveOfflineDirectory(Instance, FileObject);
          if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
            McTemplateK0_EtwWriteTransfer(
              PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
              StrmFlt_STAGE_DIRECTORY_STOP,
              &ActivityId);
          FltReleaseContext(v9);
          if ( P )
            ExFreePoolWithTag(P, 0);
          if ( Context )
            FltReleaseContext(Context);
          if ( v46 )
            ExFreePoolWithTag(v46, 0);
          if ( *(_QWORD *)&v36[16] )
            ExFreePoolWithTag(*(PVOID *)&v36[16], 0);
          return v31;
        }
        else
        {
          v24 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&v43, &DestinationString);
          CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&FileInformation);
          v26 = *(_DWORD *)v36;
          LODWORD(FileInformationClassb) = *(_DWORD *)v36;
          LogWrite(
            1,
            *CurrentActivityID,
            L"StagingManager::StageDirectoryInternal() - Failed to stage file %s, error code 0x%08X.",
            v24,
            FileInformationClassb);
          v27 = (volatile signed __int32 *)*((_QWORD *)&FileInformation + 1);
          if ( *((_QWORD *)&FileInformation + 1) )
          {
            if ( _InterlockedExchangeAdd(
                   (volatile signed __int32 *)(*((_QWORD *)&FileInformation + 1) + 8LL),
                   0xFFFFFFFF) == 1 )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
              if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 16LL))(v27);
            }
          }
          v28 = v44;
          if ( v44 )
          {
            if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
              if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
            }
          }
          if ( v17 )
          {
            v29 = *(struct _ERESOURCE **)(v16 + 8);
            if ( v29 )
            {
              ExReleaseResourceLite(v29);
              KeLeaveCriticalRegion();
            }
          }
          if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
            McTemplateK0_EtwWriteTransfer(
              PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
              StrmFlt_STAGE_DIRECTORY_STOP,
              &ActivityId);
          FltReleaseContext(v9);
          if ( P )
            ExFreePoolWithTag(P, 0);
          if ( Context )
            FltReleaseContext(Context);
          if ( v46 )
            ExFreePoolWithTag(v46, 0);
          if ( *(_QWORD *)&v36[16] )
            ExFreePoolWithTag(*(PVOID *)&v36[16], 0);
          return v26;
        }
      }
    }
    else
    {
      v12 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&v43, &DestinationString);
      v13 = (__int64 *)Streaming::Utils::GetCurrentActivityID(&FileInformation);
      LODWORD(FileInformationClassa) = StreamContext;
      LogWrite(
        2,
        *v13,
        L"StagingManager::StageDirectoryInternal() - Failed to retrieve directory context. Directory path %s, error code 0x%08X.",
        v12,
        FileInformationClassa);
      v14 = (volatile signed __int32 *)*((_QWORD *)&FileInformation + 1);
      if ( *((_QWORD *)&FileInformation + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&FileInformation + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
      v15 = v44;
      if ( v44 )
      {
        if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
      if ( v9 )
        FltReleaseContext(v9);
      if ( P )
        ExFreePoolWithTag(P, 0);
      if ( Context )
        FltReleaseContext(Context);
      if ( v46 )
        ExFreePoolWithTag(v46, 0);
      if ( *(_QWORD *)&v36[16] )
        ExFreePoolWithTag(*(PVOID *)&v36[16], 0);
      return (unsigned int)StreamContext;
    }
  }
  else
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v46 )
      ExFreePoolWithTag(v46, 0);
    if ( *(_QWORD *)&v36[16] )
      ExFreePoolWithTag(*(PVOID *)&v36[16], 0);
    return 3221225524LL;
  }
}

```

## disassembly

```asm
0x14000a310  mov     [rsp-8+arg_18], rbx
0x14000a315  push    rbp
0x14000a316  push    rsi
0x14000a317  push    rdi
0x14000a318  push    r12
0x14000a31a  push    r13
0x14000a31c  push    r14
0x14000a31e  push    r15
0x14000a320  lea     rbp, [rsp-10h]
0x14000a325  sub     rsp, 110h
0x14000a32c  mov     rax, cs:__security_cookie
0x14000a333  xor     rax, rsp
0x14000a336  mov     [rbp+40h+var_40], rax
0x14000a33a  mov     r13, rdx
0x14000a33d  mov     r12, rcx
0x14000a340  xor     esi, esi
0x14000a342  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x14000a347  xor     edx, edx; SourceString
0x14000a349  mov     qword ptr [rsp+140h+var_108+8], rsi
0x14000a34e  mov     qword ptr [rsp+140h+var_108+10h], rsi
0x14000a353  mov     rdi, r8
0x14000a356  call    cs:__imp_RtlInitUnicodeString
0x14000a35d  nop     dword ptr [rax+rax+00h]
0x14000a362  xor     edx, edx; SourceString
0x14000a364  mov     [rbp+40h+var_A0], rsi
0x14000a368  lea     rcx, [rbp+40h+var_90]; DestinationString
0x14000a36c  mov     [rbp+40h+var_98], rsi
0x14000a370  call    cs:__imp_RtlInitUnicodeString
0x14000a377  nop     dword ptr [rax+rax+00h]
0x14000a37c  xor     edx, edx; SourceString
0x14000a37e  mov     [rsp+140h+var_E0], rsi
0x14000a383  lea     rcx, [rbp+40h+var_C0]; DestinationString
0x14000a387  mov     [rsp+140h+Context], rsi
0x14000a38c  mov     [rsp+140h+var_D0], rsi
0x14000a391  mov     [rsp+140h+P], rsi
0x14000a396  call    cs:__imp_RtlInitUnicodeString
0x14000a39d  nop     dword ptr [rax+rax+00h]
0x14000a3a2  xorps   xmm0, xmm0
0x14000a3a5  mov     [rsp+140h+LengthReturned], rsi; LengthReturned
0x14000a3aa  xor     eax, eax
0x14000a3ac  mov     [rbp+40h+var_B0], rsi
0x14000a3b0  lea     r9d, [rsi+28h]; Length
0x14000a3b4  mov     [rbp+40h+var_60], rax
0x14000a3b8  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x14000a3bc  mov     dword ptr [rsp+140h+FileInformationClass], 4; struct _GUID *
0x14000a3c4  mov     rdx, r13; FileObject
0x14000a3c7  mov     rcx, r12; Instance
0x14000a3ca  movups  [rbp+40h+FileInformation], xmm0
0x14000a3ce  movups  [rbp+40h+var_70], xmm0
0x14000a3d2  call    cs:__imp_FltQueryInformationFile
0x14000a3d9  nop     dword ptr [rax+rax+00h]
0x14000a3de  test    eax, eax
0x14000a3e0  js      loc_14000AB45
0x14000a3e6  mov     eax, dword ptr [rbp+40h+var_60]
0x14000a3e9  shr     eax, 0Ch
0x14000a3ec  test    al, 1
0x14000a3ee  jz      loc_14000AB45
0x14000a3f4  lea     rax, ?strmDirectoryEaName@@3PADA; "appvstrmstagedir"
0x14000a3fb  mov     qword ptr [rbp+40h+FileInformation], 110010h
0x14000a403  lea     r9, [rsp+140h+var_108]; struct _STRING *
0x14000a408  mov     qword ptr [rbp+40h+FileInformation+8], rax
0x14000a40c  lea     r8, [rbp+40h+FileInformation]; struct _FILE_OBJECT *
0x14000a410  mov     dword ptr [rsp+140h+var_108], esi
0x14000a414  mov     rdx, r13; struct _FLT_INSTANCE *
0x14000a417  mov     rcx, r12; this
0x14000a41a  call    ?GetEA@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEBU_STRING@@AEAK@Z; Streaming::FileOperations::GetEA(_FLT_INSTANCE *,_FILE_OBJECT &,_STRING const &,ulong &)
0x14000a41f  test    eax, eax
0x14000a421  js      loc_14000AB45
0x14000a427  cmp     dword ptr [rsp+140h+var_108], esi
0x14000a42b  jz      loc_14000AB45
0x14000a431  lea     r8, [rsp+140h+Context]; struct Streaming::InstanceContext *
0x14000a436  mov     rdx, r12; struct _FLT_INSTANCE *
0x14000a439  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x14000a43e  mov     ebx, eax
0x14000a440  test    eax, eax
0x14000a442  jns     short loc_14000A4A8
0x14000a444  mov     rcx, [rsp+140h+P]; P
0x14000a449  test    rcx, rcx
0x14000a44c  jz      short loc_14000A45C
0x14000a44e  xor     edx, edx; Tag
0x14000a450  call    cs:__imp_ExFreePoolWithTag
0x14000a457  nop     dword ptr [rax+rax+00h]
0x14000a45c  mov     rcx, [rsp+140h+Context]; Context
0x14000a461  test    rcx, rcx
0x14000a464  jz      short loc_14000A472
0x14000a466  call    cs:__imp_FltReleaseContext
0x14000a46d  nop     dword ptr [rax+rax+00h]
0x14000a472  mov     rcx, [rbp+40h+var_98]; P
0x14000a476  test    rcx, rcx
0x14000a479  jz      short loc_14000A489
0x14000a47b  xor     edx, edx; Tag
0x14000a47d  call    cs:__imp_ExFreePoolWithTag
0x14000a484  nop     dword ptr [rax+rax+00h]
0x14000a489  mov     rcx, qword ptr [rsp+140h+var_108+10h]; P
0x14000a48e  test    rcx, rcx
0x14000a491  jz      short loc_14000A4A1
0x14000a493  xor     edx, edx; Tag
0x14000a495  call    cs:__imp_ExFreePoolWithTag
0x14000a49c  nop     dword ptr [rax+rax+00h]
0x14000a4a1  mov     eax, ebx
0x14000a4a3  jmp     loc_14000ABA7
0x14000a4a8  lea     rdx, [rsp+140h+var_E0]; struct _UNICODE_STRING **
0x14000a4ad  lea     rcx, [rsp+140h+Context]; this
0x14000a4b2  call    ?GetDosName@InstanceContext@Streaming@@QEAAJAEAPEBU_UNICODE_STRING@@@Z; Streaming::InstanceContext::GetDosName(_UNICODE_STRING const * &)
0x14000a4b7  mov     ebx, eax
0x14000a4b9  test    eax, eax
0x14000a4bb  js      short loc_14000A444
0x14000a4bd  test    rdi, rdi
0x14000a4c0  jz      short loc_14000A4FE
0x14000a4c2  mov     rdx, [rsp+140h+var_E0]
0x14000a4c7  lea     r9, [rbp+40h+var_A0]
0x14000a4cb  lea     r8, [rsp+140h+var_108+8]
0x14000a4d0  mov     rcx, rdi
0x14000a4d3  call    ?GetFilePathFromCallback@FileOperations@Streaming@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_UNICODE_STRING@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@2@Z; Streaming::FileOperations::GetFilePathFromCallback(_FLT_CALLBACK_DATA &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x14000a4d8  mov     ebx, eax
0x14000a4da  test    eax, eax
0x14000a4dc  js      loc_14000A444
0x14000a4e2  lea     r8, [rbp+40h+var_B0]
0x14000a4e6  mov     rcx, rdi; CallbackData
0x14000a4e9  lea     rdx, [rsp+140h+var_D0]
0x14000a4ee  call    ?GetProcessAndUserNotSystem@Utils@Streaming@@YAJAEAU_FLT_CALLBACK_DATA@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@AEAPEAX@Z; Streaming::Utils::GetProcessAndUserNotSystem(_FLT_CALLBACK_DATA &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,void * &)
0x14000a4f3  mov     ebx, eax
0x14000a4f5  test    eax, eax
0x14000a4f7  jns     short loc_14000A55D
0x14000a4f9  jmp     loc_14000A444
0x14000a4fe  mov     r8, [rsp+140h+var_E0]
0x14000a503  lea     r9, [rsp+140h+var_108+8]
0x14000a508  mov     rdx, r13; FileObject
0x14000a50b  mov     rcx, r12; Instance
0x14000a50e  call    ?GetDosFilePathUnsafe@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEBU_UNICODE_STRING@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::FileOperations::GetDosFilePathUnsafe(_FLT_INSTANCE *,_FILE_OBJECT &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x14000a513  mov     ebx, eax
0x14000a515  test    eax, eax
0x14000a517  jns     short loc_14000A549
0x14000a519  movups  xmm0, xmmword ptr [rsp+140h+var_108+8]
0x14000a51e  xor     edx, edx
0x14000a520  lea     r9, [rbp+40h+FileInformation]
0x14000a524  movups  xmm1, xmmword ptr [rsp+140h+DestinationString.Length]
0x14000a529  lea     r8, aStagingmanager_1; "StagingManager::StageDirectoryInternal("...
0x14000a530  mov     dword ptr [rsp+140h+FileInformationClass], ebx
0x14000a534  movaps  [rbp+40h+FileInformation], xmm0
0x14000a538  lea     ecx, [rdx+2]
0x14000a53b  movaps  [rbp+40h+var_70], xmm1
0x14000a53f  call    LogWrite
0x14000a544  jmp     loc_14000A444
0x14000a549  lea     rdx, [rbp+40h+var_B0]
0x14000a54d  lea     rcx, [rsp+140h+var_D0]
0x14000a552  call    ?GetCurrentProcessAndUserNotSystem@Utils@Streaming@@YAJAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@AEAPEAX@Z; Streaming::Utils::GetCurrentProcessAndUserNotSystem(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,void * &)
0x14000a557  mov     ebx, eax
0x14000a559  test    eax, eax
0x14000a55b  js      short loc_14000A519
0x14000a55d  mov     rbx, rsi
0x14000a560  mov     [rsp+140h+var_E0], rsi
0x14000a565  lea     r8, [rsp+140h+var_E0]; Context
0x14000a56a  mov     qword ptr [rsp+140h+var_108], rbx
0x14000a56f  mov     rdx, r13; FileObject
0x14000a572  mov     rcx, r12; Instance
0x14000a575  call    cs:__imp_FltGetStreamContext
0x14000a57c  nop     dword ptr [rax+rax+00h]
0x14000a581  mov     r14d, eax
0x14000a584  test    eax, eax
0x14000a586  jns     short loc_14000A5C1
0x14000a588  mov     rcx, [rsp+140h+var_E0]; Context
0x14000a58d  test    rcx, rcx
0x14000a590  jz      short loc_14000A59E
0x14000a592  call    cs:__imp_FltReleaseContext
0x14000a599  nop     dword ptr [rax+rax+00h]
0x14000a59e  cmp     r14d, 0C0000225h
0x14000a5a5  jnz     short loc_14000A5E5
0x14000a5a7  lea     r8, [rsp+140h+var_108]
0x14000a5ac  mov     rdx, r13; FileObject
0x14000a5af  mov     rcx, r12; Instance
0x14000a5b2  call    ?CreateStreamContext@DirectoryContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UDirectoryContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::DirectoryContextFactory::CreateStreamContext(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::DirectoryContext,Streaming::Context::ContextDelete> &)
0x14000a5b7  mov     rbx, qword ptr [rsp+140h+var_108]
0x14000a5bc  mov     r14d, eax
0x14000a5bf  jmp     short loc_14000A5E5
0x14000a5c1  mov     rax, [rsp+140h+var_E0]
0x14000a5c6  cmp     [rax], sil
0x14000a5c9  jnz     short loc_14000A5E2
0x14000a5cb  mov     rcx, rax; Context
0x14000a5ce  call    cs:__imp_FltReleaseContext
0x14000a5d5  nop     dword ptr [rax+rax+00h]
0x14000a5da  mov     r14d, 0C00000BBh
0x14000a5e0  jmp     short loc_14000A5E5
0x14000a5e2  mov     rbx, rax
0x14000a5e5  test    r14d, r14d
0x14000a5e8  jns     loc_14000A71A
0x14000a5ee  lea     rdx, [rsp+140h+DestinationString]
0x14000a5f3  lea     rcx, [rbp+40h+var_B0]
0x14000a5f7  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000a5fc  lea     rcx, [rbp+40h+FileInformation]
0x14000a600  mov     rdi, [rax]
0x14000a603  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000a608  mov     r9, rdi
0x14000a60b  mov     dword ptr [rsp+140h+FileInformationClass], r14d
0x14000a610  lea     r8, aStagingmanager_1; "StagingManager::StageDirectoryInternal("...
0x14000a617  mov     ecx, 2
0x14000a61c  mov     rdx, [rax]
0x14000a61f  call    LogWrite
0x14000a624  mov     rdi, qword ptr [rbp+40h+FileInformation+8]
0x14000a628  or      esi, 0FFFFFFFFh
0x14000a62b  test    rdi, rdi
0x14000a62e  jz      short loc_14000A664
0x14000a630  mov     eax, esi
0x14000a632  lock xadd [rdi+8], eax
0x14000a637  add     eax, esi
0x14000a639  jnz     short loc_14000A664
0x14000a63b  mov     rax, [rdi]
0x14000a63e  mov     rcx, rdi
0x14000a641  mov     rax, [rax+8]
0x14000a645  call    _guard_dispatch_icall
0x14000a64a  mov     eax, esi
0x14000a64c  lock xadd [rdi+0Ch], eax
0x14000a651  add     eax, esi
0x14000a653  jnz     short loc_14000A664
0x14000a655  mov     rax, [rdi]
0x14000a658  mov     rcx, rdi
0x14000a65b  mov     rax, [rax+10h]
0x14000a65f  call    _guard_dispatch_icall
0x14000a664  mov     rdi, [rbp+40h+var_A8]
0x14000a668  test    rdi, rdi
0x14000a66b  jz      short loc_14000A6A1
0x14000a66d  mov     eax, esi
0x14000a66f  lock xadd [rdi+8], eax
0x14000a674  add     eax, esi
0x14000a676  jnz     short loc_14000A6A1
0x14000a678  mov     rax, [rdi]
0x14000a67b  mov     rcx, rdi
0x14000a67e  mov     rax, [rax+8]
0x14000a682  call    _guard_dispatch_icall
0x14000a687  mov     eax, esi
0x14000a689  lock xadd [rdi+0Ch], eax
0x14000a68e  add     eax, esi
0x14000a690  jnz     short loc_14000A6A1
0x14000a692  mov     rax, [rdi]
0x14000a695  mov     rcx, rdi
0x14000a698  mov     rax, [rax+10h]
0x14000a69c  call    _guard_dispatch_icall
0x14000a6a1  test    rbx, rbx
0x14000a6a4  jz      short loc_14000A6B5
0x14000a6a6  mov     rcx, rbx; Context
0x14000a6a9  call    cs:__imp_FltReleaseContext
0x14000a6b0  nop     dword ptr [rax+rax+00h]
0x14000a6b5  mov     rcx, [rsp+140h+P]; P
0x14000a6ba  test    rcx, rcx
0x14000a6bd  jz      short loc_14000A6CD
0x14000a6bf  xor     edx, edx; Tag
0x14000a6c1  call    cs:__imp_ExFreePoolWithTag
0x14000a6c8  nop     dword ptr [rax+rax+00h]
0x14000a6cd  mov     rcx, [rsp+140h+Context]; Context
0x14000a6d2  test    rcx, rcx
0x14000a6d5  jz      short loc_14000A6E3
0x14000a6d7  call    cs:__imp_FltReleaseContext
0x14000a6de  nop     dword ptr [rax+rax+00h]
0x14000a6e3  mov     rcx, [rbp+40h+var_98]; P
0x14000a6e7  test    rcx, rcx
0x14000a6ea  jz      short loc_14000A6FA
0x14000a6ec  xor     edx, edx; Tag
0x14000a6ee  call    cs:__imp_ExFreePoolWithTag
0x14000a6f5  nop     dword ptr [rax+rax+00h]
0x14000a6fa  mov     rcx, qword ptr [rsp+140h+var_108+10h]; P
0x14000a6ff  test    rcx, rcx
0x14000a702  jz      short loc_14000A712
0x14000a704  xor     edx, edx; Tag
0x14000a706  call    cs:__imp_ExFreePoolWithTag
0x14000a70d  nop     dword ptr [rax+rax+00h]
0x14000a712  mov     eax, r14d
0x14000a715  jmp     loc_14000ABA7
0x14000a71a  lea     rdx, [rbp+40h+ActivityId]; ActivityId
0x14000a71e  mov     ecx, 3; ControlCode
0x14000a723  call    cs:__imp_EtwActivityIdControl
0x14000a72a  nop     dword ptr [rax+rax+00h]
0x14000a72f  mov     edi, 1
0x14000a734  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, dil
0x14000a73b  jz      short loc_14000A754
0x14000a73d  lea     r8, [rbp+40h+ActivityId]
0x14000a741  lea     rdx, StrmFlt_STAGE_DIRECTORY_START
0x14000a748  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x14000a74f  call    McTemplateK0_EtwWriteTransfer
0x14000a754  mov     r15, [rbx+8]
0x14000a758  movzx   r14d, sil
0x14000a75c  cmp     [r15+8], rsi
0x14000a760  jz      short loc_14000A788
0x14000a762  call    cs:__imp_KeEnterCriticalRegion
0x14000a769  nop     dword ptr [rax+rax+00h]
0x14000a76e  mov     rcx, [r15+8]; Resource
0x14000a772  mov     dl, dil; Wait
0x14000a775  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000a77c  nop     dword ptr [rax+rax+00h]
0x14000a781  cmp     al, dil
0x14000a784  cmovz   r14d, edi
0x14000a788  cmp     [rbx+18h], sil
0x14000a78c  jz      loc_14000A84B
0x14000a792  test    r14b, r14b
0x14000a795  jz      short loc_14000A7B8
0x14000a797  mov     rcx, [r15+8]; Resource
0x14000a79b  test    rcx, rcx
0x14000a79e  jz      short loc_14000A7B8
0x14000a7a0  call    cs:__imp_ExReleaseResourceLite
0x14000a7a7  nop     dword ptr [rax+rax+00h]
0x14000a7ac  call    cs:__imp_KeLeaveCriticalRegion
  ... truncated ...
```
