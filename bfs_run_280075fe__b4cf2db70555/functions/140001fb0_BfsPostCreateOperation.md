# BfsPostCreateOperation

- ea: `0x140001fb0`
- end: `0x140002750`
- name: `BfsPostCreateOperation`
- size: `1952`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140001870`
- `0x140001fb0`
- `0x1400034e4`
- `0x140006040`
- `0x140006af4`
- `0x14000dadc`
- `0x14001033c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400025b0`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400025b0`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400025ea`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400025ea`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000250e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000252f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000250e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000252f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002607`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002628`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002607`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002628`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400025cf`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400025cf`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000256a`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000256a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140002658`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140002658`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140002486`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140002486`
- `ntoskrnl!SeQuerySessionIdToken` at `0x1400022de`
- `ntoskrnl!SeQuerySessionIdToken` at `0x1400023b0`
- `ntoskrnl!SeQuerySessionIdToken` at `0x1400022de`
- `ntoskrnl!SeQuerySessionIdToken` at `0x1400023b0`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400022b4`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400022b4`
- `ntoskrnl!SeExports` at `0x14000225f`
- `ntoskrnl!RtlCheckTokenCapability` at `0x14000227a`
- `ntoskrnl!RtlCheckTokenCapability` at `0x14000227a`
- `ntoskrnl!ObfDereferenceObject` at `0x140002214`
- `ntoskrnl!ObfDereferenceObject` at `0x140002214`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400026b2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400026b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002693`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002693`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400024f9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000251a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000269f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400024f9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000251a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000269f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002613`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002634`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400026be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002613`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002634`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400026be`
- `ntoskrnl!EtwWriteTransfer` at `0x1400020db`
- `ntoskrnl!EtwWriteTransfer` at `0x140002397`
- `ntoskrnl!EtwWriteTransfer` at `0x140002469`
- `ntoskrnl!EtwWriteTransfer` at `0x1400020db`
- `ntoskrnl!EtwWriteTransfer` at `0x140002397`
- `ntoskrnl!EtwWriteTransfer` at `0x140002469`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000266d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002682`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000266d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002682`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140002147`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140002147`
- `FLTMGR!FltReleaseContext` at `0x1400026d2`
- `FLTMGR!FltReleaseContext` at `0x1400026d2`

## pseudocode

```c
__int64 __fastcall BfsPostCreateOperation(PFLT_CALLBACK_DATA Data, __int64 a2, char *a3, char a4)
{
  void *v4; // r12
  signed int FileContext; // eax
  __int64 v8; // r14
  char v9; // r13
  int v10; // eax
  ULONG Options; // r15d
  __int64 v12; // rax
  __int64 v13; // rbx
  UNICODE_STRING *FileName; // rax
  int v15; // edx
  int v16; // r9d
  __int64 v17; // rcx
  void *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  void *v21; // rcx
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  __int64 v24; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v25; // r15
  ULONG_PTR v26; // rbx
  unsigned int v27; // esi
  WCHAR v28; // ax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v30; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v31; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v33; // rax
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  _BYTE v36[16]; // [rsp+30h] [rbp-59h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-39h] BYREF
  ULONG v39; // [rsp+54h] [rbp-35h] BYREF
  ULONG SessionId; // [rsp+58h] [rbp-31h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT EventDescriptor; // [rsp+60h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-11h] BYREF
  int *v43; // [rsp+88h] [rbp-1h]
  int v44; // [rsp+90h] [rbp+7h]
  int v45; // [rsp+94h] [rbp+Bh]
  unsigned int *p_SessionId; // [rsp+98h] [rbp+Fh]
  __int64 v47; // [rsp+A0h] [rbp+17h]

  v4 = 0;
  *(_QWORD *)&String1.Length = 0;
  if ( !a3 )
    goto LABEL_71;
  if ( (a4 & 1) == 0 )
  {
    if ( (*(_DWORD *)a3 & 2) != 0 && Data->IoStatus.Status >= 0 && a3[80] )
    {
      FileContext = BfsGetFileContext(a2, Data->Iopb->TargetFileObject, &String1);
      if ( FileContext < 0 )
      {
        if ( (unsigned int)dword_140019000 > 3 )
        {
          SessionId = FileContext;
          v47 = 4;
          p_SessionId = &SessionId;
          UserData.Ptr = (ULONGLONG)EventInformation;
          EventDescriptor.ChainHead = (PLIST_ENTRY)0x30B000000LL;
          EventDescriptor.PrevLinkage = 0;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v43 = &dword_140016D9C;
          UserData.Reserved = 2;
          v44 = 30;
          v45 = 1;
          v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&EventDescriptor, 0, 0, 3u, &UserData);
        }
        v4 = *(void **)&String1.Length;
        goto LABEL_66;
      }
      v4 = *(void **)&String1.Length;
      **(_BYTE **)&String1.Length = 1;
    }
    v8 = 0;
    v9 = 0;
    if ( (*(_DWORD *)a3 & 1) == 0 )
      goto LABEL_51;
    v10 = *((_DWORD *)a3 + 2);
    v8 = *((_QWORD *)a3 + 8);
    *((_QWORD *)a3 + 8) = 0;
    if ( !v10 )
    {
      Options = Data->Iopb->Parameters.Create.Options;
      if ( !(unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline() )
      {
        v12 = *(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8);
        *(_DWORD *)(v12 + 20) &= 0xFFF3FFFF;
        FltSetCallbackDataDirty(Data);
      }
      if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( (Options & 1) != 0 )
        {
          if ( (Data->IoStatus.Information & 2) == 0 || a3[72] )
            goto LABEL_31;
LABEL_18:
          v13 = *((_QWORD *)a3 + 6);
          FileName = (UNICODE_STRING *)BfsGetFileName(&EventDescriptor, v13);
          v15 = 2;
          v16 = 2;
LABEL_30:
          v17 = *(_QWORD *)(v8 + 48);
          String1 = *FileName;
          BfsAddOrModifyEntry(v17, v15, 1, v16, v13 + 24, (__int64)&String1);
          goto LABEL_31;
        }
        if ( (Options & 0x40) == 0 || (Data->IoStatus.Information & 2) == 0 || a3[72] )
          goto LABEL_31;
      }
      else
      {
        if ( (Options & 1) != 0 )
        {
          if ( (Data->IoStatus.Information & 2) == 0 )
          {
LABEL_31:
            v18 = *(void **)(*(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8) + 32LL);
            if ( v18 )
              ObfDereferenceObject(v18);
            v19 = *(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8);
            *(_OWORD *)(v19 + 32) = *((_OWORD *)a3 + 1);
            *(_OWORD *)(v19 + 48) = *((_OWORD *)a3 + 2);
LABEL_51:
            if ( (*(_DWORD *)a3 & 4) != 0 && Data->IoStatus.Status >= 0 && (Data->IoStatus.Information & 2) != 0 )
            {
              v24 = *((_QWORD *)a3 + 11);
              String1 = 0;
              String1.Buffer = *(PWSTR *)(v24 + 16);
              String1.Length = *(_WORD *)(v24 + 8) - *(_WORD *)(v24 + 72);
              String1.MaximumLength = String1.Length;
              KeEnterCriticalRegion();
              ExAcquirePushLockExclusiveEx(&qword_140019178, 0);
              KeEnterCriticalRegion();
              ExAcquirePushLockExclusiveEx(&gBfsGlobalFileTable, 0);
              v25 = P;
              v26 = 0;
              v27 = 0;
              memset(&EventDescriptor, 0, sizeof(EventDescriptor));
              if ( (String1.Length & 0xFFFE) == 0 )
                goto LABEL_57;
              do
              {
                v28 = RtlUpcaseUnicodeChar(String1.Buffer[v27++]);
                v26 = ((unsigned __int64)v28 >> 8) + 37 * ((unsigned __int8)v28 + 37 * v26);
              }
              while ( v27 < String1.Length >> 1 );
              if ( !v26 )
LABEL_57:
                v26 = -1;
              NextEntryHashTable = RtlLookupEntryHashTable(v25, v26, &EventDescriptor);
              if ( NextEntryHashTable )
              {
                while ( !RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)&NextEntryHashTable[2].Signature, 1u) )
                {
                  NextEntryHashTable = RtlGetNextEntryHashTable(v25, &EventDescriptor);
                  if ( !NextEntryHashTable )
                    goto LABEL_61;
                }
                if ( LOBYTE(NextEntryHashTable[1].Signature) )
                {
                  v33 = NextEntryHashTable + 1;
                  LOBYTE(NextEntryHashTable[1].Signature) = 0;
                  Flink = NextEntryHashTable[1].Linkage.Flink;
                  if ( (PRTL_DYNAMIC_HASH_TABLE_ENTRY)Flink->Blink != &NextEntryHashTable[1]
                    || (Blink = NextEntryHashTable[1].Linkage.Blink,
                        (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)Blink->Flink != v33) )
                  {
                    __fastfail(3u);
                  }
                  Blink->Flink = Flink;
                  Flink->Blink = Blink;
                  v33->Linkage.Flink = 0;
                  NextEntryHashTable[1].Linkage.Blink = 0;
                  NextEntryHashTable[2].Linkage.Flink = 0;
                  NextEntryHashTable[2].Linkage.Blink = 0;
                }
              }
LABEL_61:
              ExReleasePushLockExclusiveEx(&gBfsGlobalFileTable, 0);
              KeLeaveCriticalRegion();
              ExReleasePushLockExclusiveEx(&qword_140019178, 0);
              KeLeaveCriticalRegion();
            }
            goto LABEL_62;
          }
          goto LABEL_18;
        }
        if ( (Options & 0x40) == 0 || (Data->IoStatus.Information & 2) == 0 )
          goto LABEL_31;
      }
      v13 = *((_QWORD *)a3 + 6);
      FileName = (UNICODE_STRING *)BfsGetFileName(&EventDescriptor, v13);
      v15 = 1;
      v16 = 0;
      goto LABEL_30;
    }
    if ( v10 != 1 || Data->IoStatus.Status != -1073741790 )
      goto LABEL_51;
    v20 = *(_DWORD *)(v8 + 104);
    if ( v20 )
    {
      if ( v20 != 1 )
        goto LABEL_51;
    }
    else
    {
      v36[0] = 0;
      if ( (int)RtlCheckTokenCapability(0, *(_QWORD *)&SeExports[1].SeIncreaseQuotaPrivilege, v36) < 0 || !v36[0] )
      {
        *(_DWORD *)(v8 + 104) = 2;
        goto LABEL_51;
      }
      *(_DWORD *)(v8 + 104) = 1;
    }
    SeCaptureSubjectContext((PSECURITY_SUBJECT_CONTEXT)(a3 + 16));
    v9 = 1;
    if ( *((_QWORD *)a3 + 2) )
    {
      v21 = (void *)*((_QWORD *)a3 + 4);
      SessionId = 0;
      v39 = 0;
      v22 = SeQuerySessionIdToken(v21, &SessionId);
      if ( v22 < 0 )
      {
        if ( (unsigned int)dword_140019000 > 3 )
        {
          v38 = v22;
          v47 = 4;
          p_SessionId = &v38;
          UserData.Ptr = (ULONGLONG)EventInformation;
          EventDescriptor.ChainHead = (PLIST_ENTRY)0x30B000000LL;
          EventDescriptor.PrevLinkage = 0;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v43 = &dword_140016D9C;
          UserData.Reserved = 2;
          v44 = 30;
          v45 = 1;
          *(_DWORD *)&String1.Length = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&EventDescriptor, 0, 0, 3u, &UserData);
        }
        goto LABEL_62;
      }
      v23 = SeQuerySessionIdToken(*((PACCESS_TOKEN *)a3 + 2), &v39);
      if ( v23 < 0 )
      {
LABEL_47:
        if ( (unsigned int)dword_140019000 > 3 )
        {
          *(_DWORD *)&String1.Length = v23;
          v47 = 4;
          p_SessionId = (unsigned int *)&String1;
          UserData.Ptr = (ULONGLONG)EventInformation;
          EventDescriptor.ChainHead = (PLIST_ENTRY)0x30B000000LL;
          EventDescriptor.PrevLinkage = 0;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v43 = &dword_140016D9C;
          UserData.Reserved = 2;
          v44 = 30;
          v45 = 1;
          v38 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&EventDescriptor, 0, 0, 3u, &UserData);
        }
        goto LABEL_62;
      }
      if ( SessionId != v39 )
      {
LABEL_62:
        if ( v8 )
          BfsDereferencePolicyEntryEx((PVOID)v8);
        if ( v9 )
          SeReleaseSubjectContext((PSECURITY_SUBJECT_CONTEXT)(a3 + 16));
        goto LABEL_66;
      }
    }
    *((_QWORD *)a3 + 7) = PsGetCurrentProcessId();
    v23 = BfsPerformPrompt(Data);
    if ( v23 >= 0 )
      goto LABEL_51;
    goto LABEL_47;
  }
LABEL_66:
  v30 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)a3 + 6);
  if ( v30 )
    FltReleaseFileNameInformation(v30);
  v31 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)a3 + 11);
  if ( v31 )
    FltReleaseFileNameInformation(v31);
  ExFreePoolWithTag(a3, 0);
  KeEnterCriticalRegion();
  ExReleaseRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
LABEL_71:
  if ( v4 )
    FltReleaseContext(v4);
  return 0;
}

```

## disassembly

```asm
0x140001fb0  mov     [rsp-8+arg_18], rbx
0x140001fb5  push    rbp
0x140001fb6  push    rsi
0x140001fb7  push    rdi
0x140001fb8  push    r12
0x140001fba  push    r13
0x140001fbc  push    r14
0x140001fbe  push    r15
0x140001fc0  lea     rbp, [rsp-27h]
0x140001fc5  sub     rsp, 0B0h
0x140001fcc  mov     rax, cs:__security_cookie
0x140001fd3  xor     rax, rsp
0x140001fd6  mov     [rbp+57h+var_38], rax
0x140001fda  xor     r12d, r12d
0x140001fdd  mov     rdi, r8
0x140001fe0  mov     qword ptr [rbp+57h+String1.Length], r12
0x140001fe4  mov     r15, rdx
0x140001fe7  mov     rsi, rcx
0x140001fea  test    r8, r8
0x140001fed  jz      loc_1400026CA
0x140001ff3  test    r9b, 1
0x140001ff7  jnz     loc_140002664
0x140001ffd  mov     eax, [r8]
0x140002000  test    al, 2
0x140002002  jz      loc_1400020F9
0x140002008  cmp     [rcx+18h], r12d
0x14000200c  jl      loc_1400020F9
0x140002012  cmp     [r8+50h], r12b
0x140002016  jz      loc_1400020F9
0x14000201c  mov     rdx, [rcx+10h]
0x140002020  lea     r8, [rbp+57h+String1]
0x140002024  mov     rcx, r15
0x140002027  mov     rdx, [rdx+8]
0x14000202b  call    BfsGetFileContext
0x140002030  test    eax, eax
0x140002032  jns     loc_1400020F0
0x140002038  mov     ecx, cs:dword_140019000
0x14000203e  cmp     ecx, 3
0x140002041  jbe     loc_1400020E7
0x140002047  mov     [rbp+57h+SessionId], eax
0x14000204a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x14000204e  mov     [rbp+57h+var_40], 4
0x140002056  lea     rax, [rbp+57h+SessionId]
0x14000205a  mov     [rbp+57h+var_48], rax
0x14000205e  xor     r9d, r9d; RelatedActivityId
0x140002061  mov     rax, cs:qword_140016D92
0x140002068  xor     r8d, r8d; ActivityId
0x14000206b  movzx   ecx, ax
0x14000206e  mov     rax, cs:EventInformation
0x140002075  mov     [rbp+57h+var_68.Ptr], rax
0x140002079  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x14000207c  lea     rcx, _TraceLoggingMetadata
0x140002083  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x14000208a  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x14000208e  movzx   eax, word ptr [rax]
0x140002091  mov     [rbp+57h+var_68.Size], eax
0x140002094  lea     rax, dword_140016D9C
0x14000209b  mov     [rbp+57h+var_58], rax
0x14000209f  lea     rax, _TraceLoggingMetadataEnd
0x1400020a6  sub     eax, ecx
0x1400020a8  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x1400020af  mov     [rbp+57h+var_50], 1Eh
0x1400020b6  mov     [rbp+57h+var_4C], 1
0x1400020bd  mov     [rbp+57h+var_8C], eax
0x1400020c0  mov     eax, [rbp+57h+var_8C]
0x1400020c3  mov     rcx, cs:RegHandle; RegHandle
0x1400020ca  lea     rax, [rbp+57h+var_68]
0x1400020ce  mov     [rsp+0E0h+UserData], rax; UserData
0x1400020d3  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x1400020db  call    cs:__imp_EtwWriteTransfer
0x1400020e2  nop     dword ptr [rax+rax+00h]
0x1400020e7  mov     r12, qword ptr [rbp+57h+String1.Length]
0x1400020eb  jmp     loc_140002664
0x1400020f0  mov     r12, qword ptr [rbp+57h+String1.Length]
0x1400020f4  mov     byte ptr [r12], 1
0x1400020f9  mov     eax, [rdi]
0x1400020fb  xor     r14d, r14d
0x1400020fe  xor     r13b, r13b
0x140002101  test    al, 1
0x140002103  jz      loc_1400024AC
0x140002109  mov     eax, [rdi+8]
0x14000210c  mov     r14, [rdi+40h]
0x140002110  mov     qword ptr [rdi+40h], 0
0x140002118  test    eax, eax
0x14000211a  jnz     loc_140002241
0x140002120  mov     rax, [rsi+10h]
0x140002124  mov     r15d, [rax+20h]
0x140002128  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14000212d  test    eax, eax
0x14000212f  jnz     short loc_140002153
0x140002131  mov     rax, [rsi+10h]
0x140002135  mov     rcx, [rax+18h]
0x140002139  mov     rax, [rcx+8]
0x14000213d  mov     rcx, rsi; Data
0x140002140  and     dword ptr [rax+14h], 0FFF3FFFFh
0x140002147  call    cs:__imp_FltSetCallbackDataDirty
0x14000214e  nop     dword ptr [rax+rax+00h]
0x140002153  mov     ebx, r15d
0x140002156  and     ebx, 1
0x140002159  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14000215e  test    eax, eax
0x140002160  jnz     short loc_14000219E
0x140002162  test    ebx, ebx
0x140002164  jz      short loc_140002190
0x140002166  test    byte ptr [rsi+20h], 2
0x14000216a  jz      loc_1400021FF
0x140002170  mov     rbx, [rdi+30h]
0x140002174  lea     rcx, [rbp+57h+EventDescriptor]
0x140002178  mov     rdx, rbx
0x14000217b  call    BfsGetFileName
0x140002180  mov     edx, 2
0x140002185  mov     r8d, 1
0x14000218b  mov     r9d, edx
0x14000218e  jmp     short loc_1400021DD
0x140002190  test    r15b, 40h
0x140002194  jz      short loc_1400021FF
0x140002196  test    byte ptr [rsi+20h], 2
0x14000219a  jz      short loc_1400021FF
0x14000219c  jmp     short loc_1400021C2
0x14000219e  test    ebx, ebx
0x1400021a0  jz      short loc_1400021B0
0x1400021a2  test    byte ptr [rsi+20h], 2
0x1400021a6  jz      short loc_1400021FF
0x1400021a8  cmp     [rdi+48h], r13b
0x1400021ac  jnz     short loc_1400021FF
0x1400021ae  jmp     short loc_140002170
0x1400021b0  test    r15b, 40h
0x1400021b4  jz      short loc_1400021FF
0x1400021b6  test    byte ptr [rsi+20h], 2
0x1400021ba  jz      short loc_1400021FF
0x1400021bc  cmp     [rdi+48h], r13b
0x1400021c0  jnz     short loc_1400021FF
0x1400021c2  mov     rbx, [rdi+30h]
0x1400021c6  lea     rcx, [rbp+57h+EventDescriptor]
0x1400021ca  mov     rdx, rbx
0x1400021cd  call    BfsGetFileName
0x1400021d2  mov     edx, 1
0x1400021d7  xor     r9d, r9d
0x1400021da  mov     r8d, edx
0x1400021dd  movups  xmm1, xmmword ptr [rax]
0x1400021e0  lea     rcx, [rbp+57h+String1]
0x1400021e4  mov     [rsp+0E0h+UserData], rcx
0x1400021e9  lea     rax, [rbx+18h]
0x1400021ed  mov     rcx, [r14+30h]
0x1400021f1  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x1400021f5  mov     qword ptr [rsp+0E0h+UserDataCount], rax
0x1400021fa  call    BfsAddOrModifyEntry
0x1400021ff  mov     rax, [rsi+10h]
0x140002203  mov     rcx, [rax+18h]
0x140002207  mov     rax, [rcx+8]
0x14000220b  mov     rcx, [rax+20h]; Object
0x14000220f  test    rcx, rcx
0x140002212  jz      short loc_140002220
0x140002214  call    cs:__imp_ObfDereferenceObject
0x14000221b  nop     dword ptr [rax+rax+00h]
0x140002220  mov     rax, [rsi+10h]
0x140002224  movups  xmm0, xmmword ptr [rdi+10h]
0x140002228  mov     rcx, [rax+18h]
0x14000222c  mov     rax, [rcx+8]
0x140002230  movups  xmmword ptr [rax+20h], xmm0
0x140002234  movups  xmm1, xmmword ptr [rdi+20h]
0x140002238  movups  xmmword ptr [rax+30h], xmm1
0x14000223c  jmp     loc_1400024AC
0x140002241  cmp     eax, 1
0x140002244  jnz     loc_1400024AC
0x14000224a  cmp     dword ptr [rsi+18h], 0C0000022h
0x140002251  jnz     loc_1400024AC
0x140002257  mov     eax, [r14+68h]
0x14000225b  test    eax, eax
0x14000225d  jnz     short loc_1400022A7
0x14000225f  mov     rax, cs:__imp_SeExports
0x140002266  lea     r8, [rbp+57h+var_B0]
0x14000226a  mov     [rbp+57h+var_B0], r13b
0x14000226e  xor     ecx, ecx
0x140002270  mov     rdx, [rax]
0x140002273  mov     rdx, [rdx+248h]
0x14000227a  call    cs:__imp_RtlCheckTokenCapability
0x140002281  nop     dword ptr [rax+rax+00h]
0x140002286  test    eax, eax
0x140002288  js      short loc_14000229A
0x14000228a  cmp     [rbp+57h+var_B0], r13b
0x14000228e  jz      short loc_14000229A
0x140002290  mov     dword ptr [r14+68h], 1
0x140002298  jmp     short loc_1400022B0
0x14000229a  mov     dword ptr [r14+68h], 2
0x1400022a2  jmp     loc_1400024AC
0x1400022a7  cmp     eax, 1
0x1400022aa  jnz     loc_1400024AC
0x1400022b0  lea     rcx, [rdi+10h]; SubjectContext
0x1400022b4  call    cs:__imp_SeCaptureSubjectContext
0x1400022bb  nop     dword ptr [rax+rax+00h]
0x1400022c0  cmp     qword ptr [rdi+10h], 0
0x1400022c5  mov     r13b, 1
0x1400022c8  jz      loc_140002486
0x1400022ce  mov     rcx, [rdi+20h]; Token
0x1400022d2  lea     rdx, [rbp+57h+SessionId]; SessionId
0x1400022d6  xor     eax, eax
0x1400022d8  mov     [rbp+57h+SessionId], eax
0x1400022db  mov     [rbp+57h+var_8C], eax
0x1400022de  call    cs:__imp_SeQuerySessionIdToken
0x1400022e5  nop     dword ptr [rax+rax+00h]
0x1400022ea  test    eax, eax
0x1400022ec  jns     loc_1400023A8
0x1400022f2  mov     ecx, cs:dword_140019000
0x1400022f8  cmp     ecx, 3
0x1400022fb  jbe     loc_140002640
0x140002301  mov     [rbp+57h+var_90], eax
0x140002304  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140002308  mov     [rbp+57h+var_40], 4
0x140002310  lea     rax, [rbp+57h+var_90]
0x140002314  mov     [rbp+57h+var_48], rax
0x140002318  xor     esi, esi
0x14000231a  mov     rax, cs:qword_140016D92
0x140002321  xor     r9d, r9d; RelatedActivityId
0x140002324  movzx   ecx, ax
0x140002327  xor     r8d, r8d; ActivityId
0x14000232a  mov     rax, cs:EventInformation
0x140002331  mov     [rbp+57h+var_68.Ptr], rax
0x140002335  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140002338  lea     rcx, _TraceLoggingMetadata
0x14000233f  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002346  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x14000234a  movzx   eax, word ptr [rax]
0x14000234d  mov     [rbp+57h+var_68.Size], eax
0x140002350  lea     rax, dword_140016D9C
0x140002357  mov     [rbp+57h+var_58], rax
0x14000235b  lea     rax, _TraceLoggingMetadataEnd
0x140002362  sub     eax, ecx
0x140002364  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x14000236b  mov     [rbp+57h+var_50], 1Eh
0x140002372  mov     [rbp+57h+var_4C], 1
0x140002379  mov     dword ptr [rbp+57h+String1.Length], eax
0x14000237c  mov     eax, dword ptr [rbp+57h+String1.Length]
0x14000237f  mov     rcx, cs:RegHandle; RegHandle
0x140002386  lea     rax, [rbp+57h+var_68]
0x14000238a  mov     [rsp+0E0h+UserData], rax; UserData
0x14000238f  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x140002397  call    cs:__imp_EtwWriteTransfer
0x14000239e  nop     dword ptr [rax+rax+00h]
0x1400023a3  jmp     loc_140002640
0x1400023a8  mov     rcx, [rdi+10h]; Token
0x1400023ac  lea     rdx, [rbp+57h+var_8C]; SessionId
0x1400023b0  call    cs:__imp_SeQuerySessionIdToken
0x1400023b7  nop     dword ptr [rax+rax+00h]
0x1400023bc  test    eax, eax
0x1400023be  jns     loc_14000247A
0x1400023c4  mov     ecx, cs:dword_140019000
0x1400023ca  cmp     ecx, 3
0x1400023cd  jbe     loc_140002640
0x1400023d3  mov     dword ptr [rbp+57h+String1.Length], eax
0x1400023d6  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400023da  mov     [rbp+57h+var_40], 4
0x1400023e2  lea     rax, [rbp+57h+String1]
0x1400023e6  mov     [rbp+57h+var_48], rax
0x1400023ea  xor     esi, esi
0x1400023ec  mov     rax, cs:qword_140016D92
0x1400023f3  xor     r9d, r9d; RelatedActivityId
0x1400023f6  movzx   ecx, ax
0x1400023f9  xor     r8d, r8d; ActivityId
0x1400023fc  mov     rax, cs:EventInformation
0x140002403  mov     [rbp+57h+var_68.Ptr], rax
0x140002407  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x14000240a  lea     rcx, _TraceLoggingMetadata
0x140002411  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002418  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x14000241c  movzx   eax, word ptr [rax]
0x14000241f  mov     [rbp+57h+var_68.Size], eax
0x140002422  lea     rax, dword_140016D9C
0x140002429  mov     [rbp+57h+var_58], rax
0x14000242d  lea     rax, _TraceLoggingMetadataEnd
0x140002434  sub     eax, ecx
0x140002436  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x14000243d  mov     [rbp+57h+var_50], 1Eh
0x140002444  mov     [rbp+57h+var_4C], 1
0x14000244b  mov     [rbp+57h+var_90], eax
0x14000244e  mov     eax, [rbp+57h+var_90]
0x140002451  mov     rcx, cs:RegHandle; RegHandle
0x140002458  lea     rax, [rbp+57h+var_68]
0x14000245c  mov     [rsp+0E0h+UserData], rax; UserData
0x140002461  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x140002469  call    cs:__imp_EtwWriteTransfer
0x140002470  nop     dword ptr [rax+rax+00h]
0x140002475  jmp     loc_140002640
0x14000247a  mov     eax, [rbp+57h+var_8C]
0x14000247d  cmp     [rbp+57h+SessionId], eax
0x140002480  jnz     loc_140002640
0x140002486  call    cs:__imp_PsGetCurrentProcessId
0x14000248d  nop     dword ptr [rax+rax+00h]
0x140002492  mov     r8, rdi
0x140002495  mov     rdx, r15
0x140002498  mov     rcx, rsi; Data
0x14000249b  mov     [rdi+38h], rax
0x14000249f  call    BfsPerformPrompt
0x1400024a4  test    eax, eax
0x1400024a6  js      loc_1400023C4
0x1400024ac  mov     eax, [rdi]
0x1400024ae  test    al, 4
0x1400024b0  jz      loc_140002640
0x1400024b6  cmp     dword ptr [rsi+18h], 0
0x1400024ba  jl      loc_140002640
  ... truncated ...
```
