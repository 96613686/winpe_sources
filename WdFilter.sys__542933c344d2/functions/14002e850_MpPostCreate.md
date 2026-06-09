# MpPostCreate

- ea: `0x14002e850`
- end: `0x14002f503`
- name: `MpPostCreate`
- size: `3251`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation`

## callees

- `0x140002450`
- `0x1400026c0`
- `0x140003af0`
- `0x1400049dc`
- `0x1400051bc`
- `0x140006234`
- `0x140007c84`
- `0x140009bf0`
- `0x14000a760`
- `0x14000a7d8`
- `0x14000ae58`
- `0x140011890`
- `0x1400118d0`
- `0x140011900`
- `0x14002d450`
- `0x14002d4a0`
- `0x14002e850`
- `0x140030060`
- `0x1400393f0`
- `0x14003a1b0`
- `0x14003f260`
- `0x14003fe70`
- `0x140051af0`
- `0x140054230`
- `0x140066180`
- `0x140084340`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14002eab5`
- `ntoskrnl!PsGetProcessId` at `0x14002eab5`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002edb1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002f190`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002f190`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002eaa2`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002eaa2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002eb59`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f387`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002eb59`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f387`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002eb4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f37b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002eb4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f37b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002eaed`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002eaed`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002f175`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002f175`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002eadb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002eadb`
- `ntoskrnl!IoThreadToProcess` at `0x14002ea53`
- `ntoskrnl!IoThreadToProcess` at `0x14002ea7f`
- `ntoskrnl!IoThreadToProcess` at `0x14002eda5`
- `ntoskrnl!IoThreadToProcess` at `0x14002ea53`
- `ntoskrnl!IoThreadToProcess` at `0x14002ea7f`
- `ntoskrnl!IoThreadToProcess` at `0x14002eda5`
- `ntoskrnl!ExQueryDepthSList` at `0x14002e934`
- `ntoskrnl!ExQueryDepthSList` at `0x14002e934`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002e94e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002e94e`
- `FLTMGR!FltReleaseContext` at `0x14002ec50`
- `FLTMGR!FltReleaseContext` at `0x14002ef8b`
- `FLTMGR!FltReleaseContext` at `0x14002f4de`
- `FLTMGR!FltReleaseContext` at `0x14002ec50`
- `FLTMGR!FltReleaseContext` at `0x14002ef8b`
- `FLTMGR!FltReleaseContext` at `0x14002f4de`
- `FLTMGR!FltGetFileNameInformation` at `0x14002f0ef`
- `FLTMGR!FltGetFileNameInformation` at `0x14002f0ef`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002ed59`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002ed59`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14002efa6`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14002efa6`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14002e9b5`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14002e9b5`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14002e9e9`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14002e9e9`
- `FLTMGR!FltCancelFileOpen` at `0x14002f409`
- `FLTMGR!FltCancelFileOpen` at `0x14002f409`
- `FLTMGR!FltAcknowledgeEcp` at `0x14002f05b`
- `FLTMGR!FltAcknowledgeEcp` at `0x14002f05b`
- `FLTMGR!FltSupportsStreamContexts` at `0x14002ea0c`
- `FLTMGR!FltSupportsStreamContexts` at `0x14002ea0c`
- `FLTMGR!FltParseFileNameInformation` at `0x14002f107`
- `FLTMGR!FltParseFileNameInformation` at `0x14002f107`
- `FLTMGR!FltSupportsStreamHandleContexts` at `0x14002ef33`
- `FLTMGR!FltSupportsStreamHandleContexts` at `0x14002ef33`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f06c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002f06c`

## pseudocode

```c
__int64 __fastcall MpPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, struct _SLIST_ENTRY *a3, char a4)
{
  volatile signed __int32 *v5; // rsi
  struct _SLIST_ENTRY *Next; // r15
  __int64 v10; // rcx
  struct _SLIST_ENTRY *v11; // rcx
  ULONG_PTR v12; // rdi
  USHORT v13; // bx
  __int64 v14; // rdx
  NTSTATUS Status; // r9d
  struct _FLT_FILTER *v16; // rbx
  struct _FILE_OBJECT *v17; // rcx
  __int64 v18; // rcx
  struct _KPROCESS *v19; // rbx
  struct _KPROCESS *v20; // rbx
  struct _KPROCESS *RequestorProcess; // rbx
  unsigned __int64 ProcessId; // rdi
  char *v23; // rbx
  _QWORD *v24; // r8
  _QWORD *i; // rax
  int v26; // ecx
  _QWORD *DocOpenRule; // rbx
  __int64 (__fastcall *v28)(_QWORD, PFLT_CALLBACK_DATA, __int64, ULONG *); // rax
  __int64 v29; // rax
  unsigned __int8 (__fastcall *v30)(_QWORD); // rax
  int v31; // ebx
  struct _FILE_OBJECT *v32; // rdx
  struct _FLT_INSTANCE *v33; // rcx
  NTSTATUS StreamHandleContext; // eax
  PECP_LIST v35; // rcx
  int v36; // eax
  struct _KPROCESS *v37; // rax
  PVOID v38; // rbx
  char v39; // di
  int v40; // eax
  int HandleContext; // eax
  PVOID v42; // rdx
  _DWORD *v43; // rbx
  const void **v44; // rax
  const void **v45; // rdi
  void *PoolWithTag; // rax
  const wchar_t *v47; // rdi
  __int16 v48; // cx
  void *v49; // rax
  int v50; // eax
  PETHREAD Thread; // rbx
  struct _DEVICE_OBJECT *AttachedDevice; // rdi
  int RequestorProcessId; // eax
  char v54[8]; // [rsp+38h] [rbp-29h] BYREF
  ULONG EcpContextSize[2]; // [rsp+40h] [rbp-21h] BYREF
  PECP_LIST EcpList; // [rsp+48h] [rbp-19h] BYREF
  PVOID EcpContext[2]; // [rsp+50h] [rbp-11h] BYREF
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+7h] BYREF

  v5 = 0;
  LOWORD(Next) = 0;
  Context = 0;
  if ( a3 )
    Next = a3->Next;
  if ( (a4 & 1) == 0 )
  {
    v14 = *(_QWORD *)(a2 + 32);
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_4;
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids);
      goto LABEL_52;
    }
    Status = CallbackData->IoStatus.Status;
    if ( Status < 0 || Status == 260 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
        goto LABEL_4;
      WPP_SF_DZ(
        WPP_GLOBAL_Control->AttachedDevice,
        79,
        (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        Status,
        v14 + 88);
      goto LABEL_52;
    }
    v16 = *(struct _FLT_FILTER **)(a2 + 8);
    EcpList = 0;
    EcpContext[0] = 0;
    EcpContextSize[0] = 0;
    if ( FltGetEcpListFromCallbackData(v16, CallbackData, &EcpList) >= 0 )
    {
      if ( EcpList )
      {
        _mm_lfence();
        if ( FltFindExtraCreateParameter(v16, EcpList, &GUID_MP_ECP_QUERY_EA, EcpContext, EcpContextSize) >= 0 )
        {
          _mm_lfence();
          if ( !FltIsEcpFromUserMode(v16, EcpContext[0]) )
          {
            v43 = EcpContext[0];
            if ( EcpContext[0] )
            {
              if ( EcpContextSize[0] )
              {
                if ( *(_QWORD *)(MpData + 96) )
                {
                  if ( (*(_DWORD *)(MpData + 864) & 0x800) != 0 )
                  {
                    EcpContextSize[0] = 0;
                    v44 = (const void **)(*(__int64 (__fastcall **)(_QWORD, PFLT_CALLBACK_DATA, __int64, ULONG *))(MpData + 96))(
                                           *(_QWORD *)(MpData + 16),
                                           CallbackData,
                                           4,
                                           EcpContextSize);
                    v45 = v44;
                    if ( v44 )
                    {
                      PoolWithTag = (void *)MpAllocatePoolWithTag(1, *(unsigned int *)v44, 1634029645);
                      *(_QWORD *)v43 = PoolWithTag;
                      if ( PoolWithTag )
                      {
                        memmove(PoolWithTag, v45[1], *(unsigned int *)v45);
                        v43[2] = *(_DWORD *)v45;
                        FltAcknowledgeEcp(*(PFLT_FILTER *)(MpData + 16), v43);
                      }
                    }
                  }
                }
              }
            }
            goto LABEL_52;
          }
        }
      }
    }
    v17 = *(struct _FILE_OBJECT **)(a2 + 32);
    if ( ((unsigned __int8)Next & 0x20) != 0 )
    {
      EcpContext[0] = 0;
      v54[0] = 0;
      if ( FltSupportsStreamHandleContexts(v17) )
      {
        HandleContext = MpCreateHandleContext(a2, EcpContext, v54);
        if ( HandleContext >= 0 && (v42 = EcpContext[0]) != 0 )
        {
          *((_DWORD *)EcpContext[0] + 10) |= 4u;
          if ( _InterlockedAdd64((volatile signed __int64 *)(MpData + 3640), 1u) < 0 )
            *(_BYTE *)(MpData + 3632) = 0;
          FltReleaseContext(v42);
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_qLZ(
            WPP_GLOBAL_Control->AttachedDevice,
            82,
            (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
            CallbackData->Thread,
            HandleContext,
            *(_QWORD *)(a2 + 32) + 88LL);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          81,
          (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          CallbackData->Thread,
          *(_QWORD *)(a2 + 32) + 88LL);
      }
      goto LABEL_52;
    }
    if ( !FltSupportsStreamContexts(v17) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          83,
          (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          CallbackData->Thread,
          *(_QWORD *)(a2 + 32) + 88LL);
      goto LABEL_52;
    }
    v18 = *(_QWORD *)(a2 + 32);
    if ( !*(_QWORD *)(v18 + 32) && ((unsigned __int8)Next & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          84,
          (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          CallbackData->Thread,
          v18 + 88);
      goto LABEL_52;
    }
    if ( (*(_DWORD *)(v18 + 80) & 0x280) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          85,
          (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          CallbackData->Thread,
          v18 + 88);
      goto LABEL_52;
    }
    v19 = *(struct _KPROCESS **)(MpData + 232);
    if ( IoThreadToProcess(KeGetCurrentThread()) != v19 )
    {
      v20 = *(struct _KPROCESS **)(MpData + 256);
      if ( IoThreadToProcess(KeGetCurrentThread()) != v20 )
      {
        RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(CallbackData);
        EcpContext[0] = (PVOID)PsGetProcessCreateTimeQuadPart(RequestorProcess);
        ProcessId = (unsigned __int64)PsGetProcessId(RequestorProcess);
        if ( ProcessId )
        {
          v23 = (char *)MpProcessTable;
          KeEnterCriticalRegion();
          ExAcquireResourceSharedLite((PERESOURCE)(v23 + 8), 1u);
          v24 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
          for ( i = (_QWORD *)*v24; i != v24; i = (_QWORD *)*i )
          {
            v5 = (volatile signed __int32 *)(i - 1);
            if ( ProcessId == i[2] && EcpContext[0] == *((PVOID *)v5 + 4) )
            {
              _InterlockedIncrement(v5 + 12);
              ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
              KeLeaveCriticalRegion();
              goto LABEL_32;
            }
          }
          ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
          KeLeaveCriticalRegion();
          v5 = 0;
        }
        EcpContextSize[0] = -1073741275;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          _mm_lfence();
          Thread = CallbackData->Thread;
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          RequestorProcessId = MpGetRequestorProcessId(CallbackData);
          WPP_SF_qDD(
            AttachedDevice,
            86,
            WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
            Thread,
            RequestorProcessId,
            EcpContextSize[0]);
        }
LABEL_32:
        if ( ((unsigned __int16)Next & 0x8010) != 0 && v5 )
        {
          v40 = MpHardenPathOnPostCreate(CallbackData);
          if ( v40 == 1835009 )
          {
            FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
            goto LABEL_51;
          }
          if ( v40 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              87,
              WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
              CallbackData->Thread,
              v40);
          }
        }
        if ( ((unsigned __int16)Next & 0x400) != 0 )
          goto LABEL_50;
        if ( ((unsigned __int8)Next & 8) == 0 )
        {
          if ( !v5 )
            goto LABEL_36;
          v36 = *((_DWORD *)v5 + 13);
          if ( (v36 & 1) == 0 )
          {
            if ( (v36 & 0x4000) == 0 )
              goto LABEL_36;
            v37 = IoThreadToProcess(KeGetCurrentThread());
            if ( v37 == PsInitialSystemProcess )
              goto LABEL_36;
            EcpContext[0] = 0;
            if ( (int)MpGetProcessContextByObject(v37) < 0 )
              goto LABEL_36;
            v38 = EcpContext[0];
            v39 = 0;
            if ( (*((_DWORD *)EcpContext[0] + 13) & 1) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  17,
                  WPP_db2fd61d15993f86af8f90e44cbbfca9_Traceguids,
                  KeGetCurrentThread(),
                  *((_DWORD *)EcpContext[0] + 6));
              }
              v39 = 1;
            }
            MpReleaseProcessContext(v38);
            if ( !v39 )
            {
LABEL_36:
              MpAmPostCreate(CallbackData, (__int64)&Context);
              if ( ((unsigned __int8)Next & 0x40) != 0 && CallbackData->IoStatus.Status >= 0 )
              {
                if ( v5 )
                {
                  v26 = *((_DWORD *)v5 + 13);
                  *(_QWORD *)EcpContextSize = 0;
                  EcpList = 0;
                  *(_OWORD *)EcpContext = 0;
                  if ( ((v26 & 8) == 0 || (v5[14] & 0x4000) == 0)
                    && ((v26 & 1) == 0 || (v5[14] & 0x4000) != 0)
                    && (v5[14] & 4) == 0 )
                  {
                    DocOpenRule = (_QWORD *)MpGetDocOpenRule(v5);
                    if ( DocOpenRule )
                    {
                      if ( FltGetFileNameInformation(CallbackData, 0x102u, (PFLT_FILE_NAME_INFORMATION *)EcpContextSize) >= 0
                        && FltParseFileNameInformation(*(PFLT_FILE_NAME_INFORMATION *)EcpContextSize) >= 0 )
                      {
                        v47 = (const wchar_t *)DocOpenRule[68];
                        if ( v47 )
                        {
                          if ( *(_WORD *)(*(_QWORD *)EcpContextSize + 56LL) )
                          {
                            while ( 1 )
                            {
                              DestinationString = 0;
                              if ( !v47 || RtlStringLengthWorkerW(v47, 0x105u, (size_t *)&EcpList) < 0 )
                              {
                                EcpList = 0;
                                goto LABEL_44;
                              }
                              if ( !EcpList )
                                goto LABEL_44;
                              RtlInitUnicodeString(&DestinationString, v47);
                              if ( RtlEqualUnicodeString(
                                     &DestinationString,
                                     (PCUNICODE_STRING)(*(_QWORD *)EcpContextSize + 56LL),
                                     1u) )
                              {
                                break;
                              }
                              v47 += (_QWORD)EcpList + 1;
                            }
                            _mm_lfence();
                            v48 = *(_WORD *)(*(_QWORD *)EcpContextSize + 8LL)
                                - *(_WORD *)(*(_QWORD *)EcpContextSize + 72LL);
                            WORD1(EcpContext[0]) = *(_WORD *)(*(_QWORD *)EcpContextSize + 10LL);
                            v49 = *(void **)(*(_QWORD *)EcpContextSize + 16LL);
                            LOWORD(EcpContext[0]) = v48;
                            EcpContext[1] = v49;
                            v50 = MpSendDocOpenMessage(CallbackData, DocOpenRule + 2, EcpContext, v5);
                            if ( v50 < 0
                              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                            {
                              _mm_lfence();
                              WPP_SF_qD(
                                WPP_GLOBAL_Control->AttachedDevice,
                                40,
                                WPP_52d92c1823383785ccf1919561da03b4_Traceguids,
                                KeGetCurrentThread(),
                                v50);
                            }
                          }
                        }
                      }
                    }
LABEL_44:
                    if ( *(_QWORD *)EcpContextSize )
                      FltReleaseFileNameInformation(*(PFLT_FILE_NAME_INFORMATION *)EcpContextSize);
                    if ( DocOpenRule )
                      MpReleaseDocOpenRule(DocOpenRule);
                  }
                }
              }
            }
          }
        }
        if ( Context )
        {
          v28 = *(__int64 (__fastcall **)(_QWORD, PFLT_CALLBACK_DATA, __int64, ULONG *))(MpData + 96);
          if ( v28 )
          {
            EcpContextSize[0] = 0;
            v29 = v28(*(_QWORD *)(MpData + 16), CallbackData, 1, EcpContextSize);
            if ( v29 )
              *((_DWORD *)Context + 159) = *(_DWORD *)(v29 + 60);
          }
        }
        if ( CallbackData->IoStatus.Status < 0 )
          goto LABEL_50;
        if ( v5 )
          MpDlpPostCreate(CallbackData, (__int64)Context);
        if ( CallbackData->IoStatus.Status < 0 )
        {
LABEL_50:
          if ( !v5 )
            goto LABEL_52;
          goto LABEL_51;
        }
        if ( v5 )
        {
          MpCopyCacheOnPostCreate(CallbackData);
          if ( !*(_QWORD *)(a2 + 32) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 130, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids);
            }
            goto LABEL_51;
          }
          v30 = *(unsigned __int8 (__fastcall **)(_QWORD))(MpData + 184);
          if ( v30 )
          {
            if ( *(_QWORD *)(MpData + 104) )
            {
              v31 = *(_DWORD *)(MpData + 4132);
              if ( (v31 & 1) != 0 && v30(*(_QWORD *)(a2 + 32)) == 1 && ((v31 & 2) == 0 || *((_DWORD *)v5 + 60) == 20) )
              {
                v32 = *(struct _FILE_OBJECT **)(a2 + 32);
                v33 = *(struct _FLT_INSTANCE **)(a2 + 24);
                EcpList = 0;
                StreamHandleContext = FltGetStreamHandleContext(v33, v32, (PFLT_CONTEXT *)&EcpList);
                v35 = EcpList;
                if ( StreamHandleContext >= 0 && EcpList )
                {
                  _InterlockedOr((volatile signed __int32 *)EcpList + 10, 0x800u);
                }
                else
                {
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
                  {
LABEL_152:
                    if ( v35 )
                      FltReleaseContext(v35);
                    goto LABEL_51;
                  }
                  WPP_SF_Z(
                    WPP_GLOBAL_Control->AttachedDevice,
                    131,
                    WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
                    *(_QWORD *)(a2 + 32) + 88LL);
                }
                v35 = EcpList;
                goto LABEL_152;
              }
            }
          }
LABEL_51:
          MpReleaseProcessContext(v5);
        }
      }
    }
LABEL_52:
    if ( Context )
      FltReleaseContext(Context);
  }
LABEL_4:
  if ( a3 )
  {
    v10 = *((_QWORD *)&a3->Next + 1);
    if ( v10 )
      MpFreeString(v10);
    v11 = a3[1].Next;
    if ( v11 )
      MpFreeString(v11);
    v12 = MpData + 896;
    ++*(_DWORD *)(MpData + 924);
    v13 = *(_WORD *)(v12 + 16);
    if ( ExQueryDepthSList((PSLIST_HEADER)v12) >= v13 )
    {
      ++*(_DWORD *)(v12 + 32);
      (*(void (__fastcall **)(struct _SLIST_ENTRY *))(v12 + 56))(a3);
    }
    else
    {
      _mm_lfence();
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v12, a3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002e850  mov     r11, rsp
0x14002e853  push    rbp
0x14002e854  push    r14
0x14002e856  lea     rbp, [r11-5Fh]
0x14002e85a  sub     rsp, 0A8h
0x14002e861  mov     rax, cs:__security_cookie
0x14002e868  xor     rax, rsp
0x14002e86b  mov     [rbp+57h+var_40], rax
0x14002e86f  mov     [r11-18h], rsi
0x14002e873  mov     r14, r8
0x14002e876  mov     [r11-28h], r12
0x14002e87a  xor     esi, esi
0x14002e87c  mov     [r11-30h], r13
0x14002e880  mov     r12, rdx
0x14002e883  mov     [r11-38h], r15
0x14002e887  mov     r15d, esi
0x14002e88a  mov     [rbp+57h+Context], rsi
0x14002e88e  mov     r13, rcx
0x14002e891  test    r8, r8
0x14002e894  jz      short loc_14002E899
0x14002e896  mov     r15, [r8]
0x14002e899  mov     [rsp+0B0h+arg_18], rbx
0x14002e8a1  mov     [rsp+0B0h+var_18], rdi
0x14002e8a9  test    r9b, 1
0x14002e8ad  jz      loc_14002E974
0x14002e8b3  mov     r15, [rsp+0B0h+var_30]
0x14002e8bb  mov     r13, [rsp+0B0h+var_28]
0x14002e8c3  mov     r12, [rsp+0B0h+var_20]
0x14002e8cb  mov     rsi, [rsp+0A0h]
0x14002e8d3  test    r14, r14
0x14002e8d6  jnz     short loc_14002E902
0x14002e8d8  mov     rdi, [rsp+0B0h+var_18]
0x14002e8e0  xor     eax, eax
0x14002e8e2  mov     rbx, [rsp+0B0h+arg_18]
0x14002e8ea  mov     rcx, [rbp+57h+var_40]
0x14002e8ee  xor     rcx, rsp; StackCookie
0x14002e8f1  call    __security_check_cookie
0x14002e8f6  add     rsp, 0A8h
0x14002e8fd  pop     r14
0x14002e8ff  pop     rbp
0x14002e900  retn
0x14002e902  mov     rcx, [r14+8]
0x14002e906  test    rcx, rcx
0x14002e909  jnz     loc_14002F4EF
0x14002e90f  mov     rcx, [r14+10h]
0x14002e913  test    rcx, rcx
0x14002e916  jnz     loc_14002F4F9
0x14002e91c  mov     rdi, cs:MpData
0x14002e923  add     rdi, 380h
0x14002e92a  mov     rcx, rdi; SListHead
0x14002e92d  inc     dword ptr [rdi+1Ch]
0x14002e930  movzx   ebx, word ptr [rdi+10h]
0x14002e934  call    cs:__imp_ExQueryDepthSList
0x14002e93b  nop     dword ptr [rax+rax+00h]
0x14002e940  cmp     ax, bx
0x14002e943  jnb     short loc_14002E95F
0x14002e945  lfence
0x14002e948  mov     rdx, r14; ListEntry
0x14002e94b  mov     rcx, rdi; ListHead
0x14002e94e  call    cs:__imp_ExpInterlockedPushEntrySList
0x14002e955  nop     dword ptr [rax+rax+00h]
0x14002e95a  jmp     loc_14002E8D8
0x14002e95f  inc     dword ptr [rdi+20h]
0x14002e962  mov     rcx, r14
0x14002e965  mov     rax, [rdi+38h]
0x14002e969  call    cs:__guard_dispatch_icall_fptr
0x14002e96f  jmp     loc_14002E8D8
0x14002e974  mov     rdx, [rdx+20h]
0x14002e978  test    rdx, rdx
0x14002e97b  jz      loc_14002F236
0x14002e981  mov     r9d, [rcx+18h]
0x14002e985  test    r9d, r9d
0x14002e988  js      loc_14002EE22
0x14002e98e  cmp     r9d, 104h
0x14002e995  jz      loc_14002EE22
0x14002e99b  mov     rbx, [r12+8]
0x14002e9a0  lea     r8, [rbp+57h+EcpList]; EcpList
0x14002e9a4  mov     rcx, rbx; Filter
0x14002e9a7  mov     [rbp+57h+EcpList], rsi
0x14002e9ab  mov     rdx, r13; CallbackData
0x14002e9ae  mov     [rbp+57h+EcpContext], rsi
0x14002e9b2  mov     [rbp+57h+var_78], esi
0x14002e9b5  call    cs:__imp_FltGetEcpListFromCallbackData
0x14002e9bc  nop     dword ptr [rax+rax+00h]
0x14002e9c1  test    eax, eax
0x14002e9c3  js      short loc_14002E9FD
0x14002e9c5  cmp     [rbp+57h+EcpList], rsi
0x14002e9c9  jz      short loc_14002E9FD
0x14002e9cb  lfence
0x14002e9ce  mov     rdx, [rbp+57h+EcpList]; EcpList
0x14002e9d2  lea     rax, [rbp+57h+var_78]
0x14002e9d6  lea     r9, [rbp+57h+EcpContext]; EcpContext
0x14002e9da  mov     [rsp+0B0h+EcpContextSize], rax; EcpContextSize
0x14002e9df  lea     r8, GUID_MP_ECP_QUERY_EA; EcpType
0x14002e9e6  mov     rcx, rbx; Filter
0x14002e9e9  call    cs:__imp_FltFindExtraCreateParameter
0x14002e9f0  nop     dword ptr [rax+rax+00h]
0x14002e9f5  test    eax, eax
0x14002e9f7  jns     loc_14002EF9C
0x14002e9fd  mov     rcx, [r12+20h]; FileObject
0x14002ea02  test    r15b, 20h
0x14002ea06  jnz     loc_14002EF2B
0x14002ea0c  call    cs:__imp_FltSupportsStreamContexts
0x14002ea13  nop     dword ptr [rax+rax+00h]
0x14002ea18  test    al, al
0x14002ea1a  jz      loc_14002EE67
0x14002ea20  mov     rcx, [r12+20h]
0x14002ea25  cmp     [rcx+20h], rsi
0x14002ea29  jz      loc_14002F07D
0x14002ea2f  test    dword ptr [rcx+50h], 280h
0x14002ea36  jnz     loc_14002F326
0x14002ea3c  mov     rcx, gs:188h; Thread
0x14002ea45  mov     rax, cs:MpData
0x14002ea4c  mov     rbx, [rax+0E8h]
0x14002ea53  call    cs:__imp_IoThreadToProcess
0x14002ea5a  nop     dword ptr [rax+rax+00h]
0x14002ea5f  cmp     rax, rbx
0x14002ea62  jz      loc_14002EC43
0x14002ea68  mov     rcx, gs:188h; Thread
0x14002ea71  mov     rax, cs:MpData
0x14002ea78  mov     rbx, [rax+100h]
0x14002ea7f  call    cs:__imp_IoThreadToProcess
0x14002ea86  nop     dword ptr [rax+rax+00h]
0x14002ea8b  cmp     rax, rbx
0x14002ea8e  jz      loc_14002EC43
0x14002ea94  mov     rcx, r13
0x14002ea97  call    MpGetRequestorProcess
0x14002ea9c  mov     rcx, rax; Process
0x14002ea9f  mov     rbx, rax
0x14002eaa2  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002eaa9  nop     dword ptr [rax+rax+00h]
0x14002eaae  mov     rcx, rbx; Process
0x14002eab1  mov     [rbp+57h+EcpContext], rax
0x14002eab5  call    cs:__imp_PsGetProcessId
0x14002eabc  nop     dword ptr [rax+rax+00h]
0x14002eac1  lea     rbx, WPP_GLOBAL_Control
0x14002eac8  mov     rdi, rax
0x14002eacb  test    rax, rax
0x14002eace  jz      loc_14002F39C
0x14002ead4  mov     rbx, cs:MpProcessTable
0x14002eadb  call    cs:__imp_KeEnterCriticalRegion
0x14002eae2  nop     dword ptr [rax+rax+00h]
0x14002eae7  mov     dl, 1; Wait
0x14002eae9  lea     rcx, [rbx+8]; Resource
0x14002eaed  call    cs:__imp_ExAcquireResourceSharedLite
0x14002eaf4  nop     dword ptr [rax+rax+00h]
0x14002eaf9  mov     rax, cs:MpProcessTable
0x14002eb00  mov     r8, rdi
0x14002eb03  mov     rcx, [rbp+57h+EcpContext]
0x14002eb07  shr     r8, 2
0x14002eb0b  and     r8d, 7Fh
0x14002eb0f  shl     r8, 4
0x14002eb13  add     r8, [rax+180h]
0x14002eb1a  mov     rax, [r8]
0x14002eb1d  nop     dword ptr [rax]
0x14002eb20  cmp     rax, r8
0x14002eb23  jz      loc_14002F370
0x14002eb29  cmp     rdi, [rax+10h]
0x14002eb2d  lea     rsi, [rax-8]
0x14002eb31  jz      short loc_14002EB38
0x14002eb33  mov     rax, [rax]
0x14002eb36  jmp     short loc_14002EB20
0x14002eb38  cmp     rcx, [rsi+20h]
0x14002eb3c  jnz     short loc_14002EB33
0x14002eb3e  lock inc dword ptr [rsi+30h]
0x14002eb42  mov     rcx, cs:MpProcessTable
0x14002eb49  add     rcx, 8; Resource
0x14002eb4d  call    cs:__imp_ExReleaseResourceLite
0x14002eb54  nop     dword ptr [rax+rax+00h]
0x14002eb59  call    cs:__imp_KeLeaveCriticalRegion
0x14002eb60  nop     dword ptr [rax+rax+00h]
0x14002eb65  lea     rbx, WPP_GLOBAL_Control
0x14002eb6c  test    r15, 8010h
0x14002eb73  jnz     loc_14002EEB5
0x14002eb79  bt      r15, 0Ah
0x14002eb7e  jb      loc_14002EC36
0x14002eb84  test    r15b, 8
0x14002eb88  jnz     loc_14002EC25
0x14002eb8e  test    rsi, rsi
0x14002eb91  jnz     loc_14002ED87
0x14002eb97  lea     rax, [rbp+57h+Context]
0x14002eb9b  mov     r9, rsi
0x14002eb9e  mov     r8, r14
0x14002eba1  mov     [rsp+0B0h+EcpContextSize], rax; __int64
0x14002eba6  mov     rdx, r12
0x14002eba9  mov     rcx, r13; CallbackData
0x14002ebac  call    MpAmPostCreate
0x14002ebb1  test    r15b, 40h
0x14002ebb5  jz      short loc_14002EC25
0x14002ebb7  xor     r15d, r15d
0x14002ebba  cmp     [r13+18h], r15d
0x14002ebbe  jl      short loc_14002EC28
0x14002ebc0  test    rsi, rsi
0x14002ebc3  jz      short loc_14002EC28
0x14002ebc5  mov     ecx, [rsi+34h]
0x14002ebc8  xorps   xmm0, xmm0
0x14002ebcb  mov     qword ptr [rbp+57h+var_78], r15
0x14002ebcf  mov     [rbp+57h+EcpList], r15
0x14002ebd3  movups  xmmword ptr [rbp+57h+EcpContext], xmm0
0x14002ebd7  test    cl, 8
0x14002ebda  jz      short loc_14002EBE5
0x14002ebdc  test    dword ptr [rsi+38h], 4000h
0x14002ebe3  jnz     short loc_14002EC28
0x14002ebe5  test    cl, 1
0x14002ebe8  jnz     loc_14002F0D1
0x14002ebee  mov     eax, [rsi+38h]
0x14002ebf1  test    al, 4
0x14002ebf3  jnz     short loc_14002EC28
0x14002ebf5  mov     rcx, rsi
0x14002ebf8  call    MpGetDocOpenRule
0x14002ebfd  mov     rbx, rax
0x14002ec00  test    rax, rax
0x14002ec03  jnz     loc_14002F0E3
0x14002ec09  mov     rcx, qword ptr [rbp+57h+var_78]; FileNameInformation
0x14002ec0d  test    rcx, rcx
0x14002ec10  jnz     loc_14002F06C
0x14002ec16  test    rbx, rbx
0x14002ec19  jz      short loc_14002EC28
0x14002ec1b  mov     rcx, rbx; Entry
0x14002ec1e  call    MpReleaseDocOpenRule
0x14002ec23  jmp     short loc_14002EC28
0x14002ec25  xor     r15d, r15d
0x14002ec28  cmp     [rbp+57h+Context], 0
0x14002ec2d  jnz     short loc_14002EC61
0x14002ec2f  cmp     dword ptr [r13+18h], 0
0x14002ec34  jge     short loc_14002ECA0
0x14002ec36  test    rsi, rsi
0x14002ec39  jz      short loc_14002EC43
0x14002ec3b  mov     rcx, rsi
0x14002ec3e  call    MpReleaseProcessContext
0x14002ec43  mov     rcx, [rbp+57h+Context]; Context
0x14002ec47  test    rcx, rcx
0x14002ec4a  jz      loc_14002E8B3
0x14002ec50  call    cs:__imp_FltReleaseContext
0x14002ec57  nop     dword ptr [rax+rax+00h]
0x14002ec5c  jmp     loc_14002E8B3
0x14002ec61  mov     r10, cs:MpData
0x14002ec68  mov     rax, [r10+60h]
0x14002ec6c  test    rax, rax
0x14002ec6f  jz      short loc_14002EC2F
0x14002ec71  mov     [rbp+57h+var_78], r15d
0x14002ec75  lea     r9, [rbp+57h+var_78]
0x14002ec79  mov     rcx, [r10+10h]
0x14002ec7d  mov     r8d, 1
0x14002ec83  mov     rdx, r13
0x14002ec86  call    cs:__guard_dispatch_icall_fptr
0x14002ec8c  test    rax, rax
0x14002ec8f  jz      short loc_14002EC2F
0x14002ec91  mov     ecx, [rax+3Ch]
0x14002ec94  mov     rax, [rbp+57h+Context]
0x14002ec98  mov     [rax+27Ch], ecx
0x14002ec9e  jmp     short loc_14002EC2F
0x14002eca0  test    rsi, rsi
0x14002eca3  jz      short loc_14002ECBF
0x14002eca5  mov     rax, [rbp+57h+Context]
0x14002eca9  mov     r9, r14
0x14002ecac  mov     r8, rsi
0x14002ecaf  mov     [rsp+0B0h+EcpContextSize], rax; __int64
0x14002ecb4  mov     rdx, r12
0x14002ecb7  mov     rcx, r13; CallbackData
0x14002ecba  call    MpDlpPostCreate
0x14002ecbf  cmp     dword ptr [r13+18h], 0
0x14002ecc4  jl      loc_14002EC36
0x14002ecca  test    rsi, rsi
0x14002eccd  jz      loc_14002EC43
0x14002ecd3  mov     r9, [rbp+57h+Context]
0x14002ecd7  mov     r8, rsi
0x14002ecda  mov     rdx, r12
0x14002ecdd  mov     rcx, r13; CallbackData
0x14002ece0  call    MpCopyCacheOnPostCreate
0x14002ece5  mov     rdx, [r12+20h]
0x14002ecea  test    rdx, rdx
0x14002eced  jz      loc_14002F45C
0x14002ecf3  mov     rcx, cs:MpData
0x14002ecfa  mov     rax, [rcx+0B8h]
0x14002ed01  test    rax, rax
0x14002ed04  jz      loc_14002EC3B
0x14002ed0a  cmp     qword ptr [rcx+68h], 0
0x14002ed0f  jz      loc_14002EC3B
0x14002ed15  mov     ebx, [rcx+1024h]
0x14002ed1b  test    bl, 1
0x14002ed1e  jz      loc_14002EC3B
0x14002ed24  mov     rcx, rdx
0x14002ed27  call    cs:__guard_dispatch_icall_fptr
0x14002ed2d  cmp     al, 1
0x14002ed2f  jnz     loc_14002EC3B
0x14002ed35  test    bl, 2
0x14002ed38  jz      short loc_14002ED47
0x14002ed3a  cmp     dword ptr [rsi+0F0h], 14h
0x14002ed41  jnz     loc_14002EC3B
0x14002ed47  mov     rdx, [r12+20h]; FileObject
0x14002ed4c  lea     r8, [rbp+57h+EcpList]; Context
0x14002ed50  mov     rcx, [r12+18h]; Instance
0x14002ed55  mov     [rbp+57h+EcpList], r15
0x14002ed59  call    cs:__imp_FltGetStreamHandleContext
0x14002ed60  nop     dword ptr [rax+rax+00h]
0x14002ed65  mov     rcx, [rbp+57h+EcpList]
0x14002ed69  test    eax, eax
0x14002ed6b  js      loc_14002F498
0x14002ed71  test    rcx, rcx
  ... truncated ...
```
