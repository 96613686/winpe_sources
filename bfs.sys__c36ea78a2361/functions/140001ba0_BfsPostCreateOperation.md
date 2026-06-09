# BfsPostCreateOperation

- ea: `0x140001ba0`
- end: `0x140002340`
- name: `BfsPostCreateOperation`
- size: `1952`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, char *, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140001460`
- `0x140001ba0`
- `0x140003614`
- `0x1400061d0`
- `0x140006c84`
- `0x14000dc70`
- `0x1400104ec`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400021a0`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400021a0`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400021da`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400021da`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400020fe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000211f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400020fe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000211f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400021f7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002218`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400021f7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140002218`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400021bf`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400021bf`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000215a`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000215a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140002248`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140002248`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140002076`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140002076`
- `ntoskrnl!SeQuerySessionIdToken` at `0x140001ece`
- `ntoskrnl!SeQuerySessionIdToken` at `0x140001fa0`
- `ntoskrnl!SeQuerySessionIdToken` at `0x140001ece`
- `ntoskrnl!SeQuerySessionIdToken` at `0x140001fa0`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140001ea4`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140001ea4`
- `ntoskrnl!SeExports` at `0x140001e4f`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140001e6a`
- `ntoskrnl!RtlCheckTokenCapability` at `0x140001e6a`
- `ntoskrnl!ObfDereferenceObject` at `0x140001e04`
- `ntoskrnl!ObfDereferenceObject` at `0x140001e04`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400022a2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400022a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002283`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002283`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400020e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000210a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000228f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400020e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000210a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000228f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002203`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002224`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400022ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002203`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002224`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400022ae`
- `ntoskrnl!EtwWriteTransfer` at `0x140001ccb`
- `ntoskrnl!EtwWriteTransfer` at `0x140001f87`
- `ntoskrnl!EtwWriteTransfer` at `0x140002059`
- `ntoskrnl!EtwWriteTransfer` at `0x140001ccb`
- `ntoskrnl!EtwWriteTransfer` at `0x140001f87`
- `ntoskrnl!EtwWriteTransfer` at `0x140002059`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000225d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002272`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000225d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002272`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140001d37`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140001d37`
- `FLTMGR!FltReleaseContext` at `0x1400022c2`
- `FLTMGR!FltReleaseContext` at `0x1400022c2`

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
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  UNICODE_STRING *FileName; // rax
  int v16; // edx
  int v17; // r9d
  __int64 v18; // rcx
  void *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  void *v22; // rcx
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  __int64 v25; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v26; // r15
  ULONG_PTR v27; // rbx
  unsigned int v28; // esi
  WCHAR v29; // ax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v31; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v32; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v34; // rax
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  _BYTE v37[16]; // [rsp+30h] [rbp-59h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v39; // [rsp+50h] [rbp-39h] BYREF
  ULONG v40; // [rsp+54h] [rbp-35h] BYREF
  ULONG SessionId; // [rsp+58h] [rbp-31h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT EventDescriptor; // [rsp+60h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-11h] BYREF
  int *v44; // [rsp+88h] [rbp-1h]
  int v45; // [rsp+90h] [rbp+7h]
  int v46; // [rsp+94h] [rbp+Bh]
  unsigned int *p_SessionId; // [rsp+98h] [rbp+Fh]
  __int64 v48; // [rsp+A0h] [rbp+17h]

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
          v48 = 4;
          p_SessionId = &SessionId;
          UserData.Ptr = (ULONGLONG)EventInformation;
          EventDescriptor.ChainHead = (PLIST_ENTRY)0x30B000000LL;
          EventDescriptor.PrevLinkage = 0;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v44 = &dword_140016D9C;
          UserData.Reserved = 2;
          v45 = 30;
          v46 = 1;
          v40 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
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
      if ( !(unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(Data) )
      {
        v13 = *(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8);
        *(_DWORD *)(v13 + 20) &= 0xFFF3FFFF;
        FltSetCallbackDataDirty(Data);
      }
      if ( (unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(v12) )
      {
        if ( (Options & 1) != 0 )
        {
          if ( (Data->IoStatus.Information & 2) == 0 || a3[72] )
            goto LABEL_31;
LABEL_18:
          v14 = *((_QWORD *)a3 + 6);
          FileName = (UNICODE_STRING *)BfsGetFileName(&EventDescriptor, v14);
          v16 = 2;
          v17 = 2;
LABEL_30:
          v18 = *(_QWORD *)(v8 + 48);
          String1 = *FileName;
          BfsAddOrModifyEntry(v18, v16, 1, v17, v14 + 24, (__int64)&String1);
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
            v19 = *(void **)(*(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8) + 32LL);
            if ( v19 )
              ObfDereferenceObject(v19);
            v20 = *(_QWORD *)(Data->Iopb->Parameters.WMI.ProviderId + 8);
            *(_OWORD *)(v20 + 32) = *((_OWORD *)a3 + 1);
            *(_OWORD *)(v20 + 48) = *((_OWORD *)a3 + 2);
LABEL_51:
            if ( (*(_DWORD *)a3 & 4) != 0 && Data->IoStatus.Status >= 0 && (Data->IoStatus.Information & 2) != 0 )
            {
              v25 = *((_QWORD *)a3 + 11);
              String1 = 0;
              String1.Buffer = *(PWSTR *)(v25 + 16);
              String1.Length = *(_WORD *)(v25 + 8) - *(_WORD *)(v25 + 72);
              String1.MaximumLength = String1.Length;
              KeEnterCriticalRegion();
              ExAcquirePushLockExclusiveEx(&qword_140019168, 0);
              KeEnterCriticalRegion();
              ExAcquirePushLockExclusiveEx(&gBfsGlobalFileTable, 0);
              v26 = P;
              v27 = 0;
              v28 = 0;
              memset(&EventDescriptor, 0, sizeof(EventDescriptor));
              if ( (String1.Length & 0xFFFE) == 0 )
                goto LABEL_57;
              do
              {
                v29 = RtlUpcaseUnicodeChar(String1.Buffer[v28++]);
                v27 = ((unsigned __int64)v29 >> 8) + 37 * ((unsigned __int8)v29 + 37 * v27);
              }
              while ( v28 < String1.Length >> 1 );
              if ( !v27 )
LABEL_57:
                v27 = -1;
              NextEntryHashTable = RtlLookupEntryHashTable(v26, v27, &EventDescriptor);
              if ( NextEntryHashTable )
              {
                while ( !RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)&NextEntryHashTable[2].Signature, 1u) )
                {
                  NextEntryHashTable = RtlGetNextEntryHashTable(v26, &EventDescriptor);
                  if ( !NextEntryHashTable )
                    goto LABEL_61;
                }
                if ( LOBYTE(NextEntryHashTable[1].Signature) )
                {
                  v34 = NextEntryHashTable + 1;
                  LOBYTE(NextEntryHashTable[1].Signature) = 0;
                  Flink = NextEntryHashTable[1].Linkage.Flink;
                  if ( (PRTL_DYNAMIC_HASH_TABLE_ENTRY)Flink->Blink != &NextEntryHashTable[1]
                    || (Blink = NextEntryHashTable[1].Linkage.Blink,
                        (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)Blink->Flink != v34) )
                  {
                    __fastfail(3u);
                  }
                  Blink->Flink = Flink;
                  Flink->Blink = Blink;
                  v34->Linkage.Flink = 0;
                  NextEntryHashTable[1].Linkage.Blink = 0;
                  NextEntryHashTable[2].Linkage.Flink = 0;
                  NextEntryHashTable[2].Linkage.Blink = 0;
                }
              }
LABEL_61:
              ExReleasePushLockExclusiveEx(&gBfsGlobalFileTable, 0);
              KeLeaveCriticalRegion();
              ExReleasePushLockExclusiveEx(&qword_140019168, 0);
              KeLeaveCriticalRegion();
            }
            goto LABEL_62;
          }
          goto LABEL_18;
        }
        if ( (Options & 0x40) == 0 || (Data->IoStatus.Information & 2) == 0 )
          goto LABEL_31;
      }
      v14 = *((_QWORD *)a3 + 6);
      FileName = (UNICODE_STRING *)BfsGetFileName(&EventDescriptor, v14);
      v16 = 1;
      v17 = 0;
      goto LABEL_30;
    }
    if ( v10 != 1 || Data->IoStatus.Status != -1073741790 )
      goto LABEL_51;
    v21 = *(_DWORD *)(v8 + 104);
    if ( v21 )
    {
      if ( v21 != 1 )
        goto LABEL_51;
    }
    else
    {
      v37[0] = 0;
      if ( (int)RtlCheckTokenCapability(0, *(_QWORD *)&SeExports[1].SeIncreaseQuotaPrivilege, v37) < 0 || !v37[0] )
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
      v22 = (void *)*((_QWORD *)a3 + 4);
      SessionId = 0;
      v40 = 0;
      v23 = SeQuerySessionIdToken(v22, &SessionId);
      if ( v23 < 0 )
      {
        if ( (unsigned int)dword_140019000 > 3 )
        {
          v39 = v23;
          v48 = 4;
          p_SessionId = &v39;
          UserData.Ptr = (ULONGLONG)EventInformation;
          EventDescriptor.ChainHead = (PLIST_ENTRY)0x30B000000LL;
          EventDescriptor.PrevLinkage = 0;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v44 = &dword_140016D9C;
          UserData.Reserved = 2;
          v45 = 30;
          v46 = 1;
          *(_DWORD *)&String1.Length = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&EventDescriptor, 0, 0, 3u, &UserData);
        }
        goto LABEL_62;
      }
      v24 = SeQuerySessionIdToken(*((PACCESS_TOKEN *)a3 + 2), &v40);
      if ( v24 < 0 )
      {
LABEL_47:
        if ( (unsigned int)dword_140019000 > 3 )
        {
          *(_DWORD *)&String1.Length = v24;
          v48 = 4;
          p_SessionId = (unsigned int *)&String1;
          UserData.Ptr = (ULONGLONG)EventInformation;
          EventDescriptor.ChainHead = (PLIST_ENTRY)0x30B000000LL;
          EventDescriptor.PrevLinkage = 0;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v44 = &dword_140016D9C;
          UserData.Reserved = 2;
          v45 = 30;
          v46 = 1;
          v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&EventDescriptor, 0, 0, 3u, &UserData);
        }
        goto LABEL_62;
      }
      if ( SessionId != v40 )
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
    v24 = BfsPerformPrompt(Data);
    if ( v24 >= 0 )
      goto LABEL_51;
    goto LABEL_47;
  }
LABEL_66:
  v31 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)a3 + 6);
  if ( v31 )
    FltReleaseFileNameInformation(v31);
  v32 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)a3 + 11);
  if ( v32 )
    FltReleaseFileNameInformation(v32);
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
0x140001ba0  mov     [rsp-8+arg_18], rbx
0x140001ba5  push    rbp
0x140001ba6  push    rsi
0x140001ba7  push    rdi
0x140001ba8  push    r12
0x140001baa  push    r13
0x140001bac  push    r14
0x140001bae  push    r15
0x140001bb0  lea     rbp, [rsp-27h]
0x140001bb5  sub     rsp, 0B0h
0x140001bbc  mov     rax, cs:__security_cookie
0x140001bc3  xor     rax, rsp
0x140001bc6  mov     [rbp+57h+var_38], rax
0x140001bca  xor     r12d, r12d
0x140001bcd  mov     rdi, r8
0x140001bd0  mov     qword ptr [rbp+57h+String1.Length], r12
0x140001bd4  mov     r15, rdx
0x140001bd7  mov     rsi, rcx
0x140001bda  test    r8, r8
0x140001bdd  jz      loc_1400022BA
0x140001be3  test    r9b, 1
0x140001be7  jnz     loc_140002254
0x140001bed  mov     eax, [r8]
0x140001bf0  test    al, 2
0x140001bf2  jz      loc_140001CE9
0x140001bf8  cmp     [rcx+18h], r12d
0x140001bfc  jl      loc_140001CE9
0x140001c02  cmp     [r8+50h], r12b
0x140001c06  jz      loc_140001CE9
0x140001c0c  mov     rdx, [rcx+10h]
0x140001c10  lea     r8, [rbp+57h+String1]
0x140001c14  mov     rcx, r15
0x140001c17  mov     rdx, [rdx+8]
0x140001c1b  call    BfsGetFileContext
0x140001c20  test    eax, eax
0x140001c22  jns     loc_140001CE0
0x140001c28  mov     ecx, cs:dword_140019000
0x140001c2e  cmp     ecx, 3
0x140001c31  jbe     loc_140001CD7
0x140001c37  mov     [rbp+57h+SessionId], eax
0x140001c3a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140001c3e  mov     [rbp+57h+var_40], 4
0x140001c46  lea     rax, [rbp+57h+SessionId]
0x140001c4a  mov     [rbp+57h+var_48], rax
0x140001c4e  xor     r9d, r9d; RelatedActivityId
0x140001c51  mov     rax, cs:qword_140016D92
0x140001c58  xor     r8d, r8d; ActivityId
0x140001c5b  movzx   ecx, ax
0x140001c5e  mov     rax, cs:EventInformation
0x140001c65  mov     [rbp+57h+var_68.Ptr], rax
0x140001c69  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140001c6c  lea     rcx, _TraceLoggingMetadata
0x140001c73  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140001c7a  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x140001c7e  movzx   eax, word ptr [rax]
0x140001c81  mov     [rbp+57h+var_68.Size], eax
0x140001c84  lea     rax, dword_140016D9C
0x140001c8b  mov     [rbp+57h+var_58], rax
0x140001c8f  lea     rax, _TraceLoggingMetadataEnd
0x140001c96  sub     eax, ecx
0x140001c98  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x140001c9f  mov     [rbp+57h+var_50], 1Eh
0x140001ca6  mov     [rbp+57h+var_4C], 1
0x140001cad  mov     [rbp+57h+var_8C], eax
0x140001cb0  mov     eax, [rbp+57h+var_8C]
0x140001cb3  mov     rcx, cs:RegHandle; RegHandle
0x140001cba  lea     rax, [rbp+57h+var_68]
0x140001cbe  mov     [rsp+0E0h+UserData], rax; UserData
0x140001cc3  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x140001ccb  call    cs:__imp_EtwWriteTransfer
0x140001cd2  nop     dword ptr [rax+rax+00h]
0x140001cd7  mov     r12, qword ptr [rbp+57h+String1.Length]
0x140001cdb  jmp     loc_140002254
0x140001ce0  mov     r12, qword ptr [rbp+57h+String1.Length]
0x140001ce4  mov     byte ptr [r12], 1
0x140001ce9  mov     eax, [rdi]
0x140001ceb  xor     r14d, r14d
0x140001cee  xor     r13b, r13b
0x140001cf1  test    al, 1
0x140001cf3  jz      loc_14000209C
0x140001cf9  mov     eax, [rdi+8]
0x140001cfc  mov     r14, [rdi+40h]
0x140001d00  mov     qword ptr [rdi+40h], 0
0x140001d08  test    eax, eax
0x140001d0a  jnz     loc_140001E31
0x140001d10  mov     rax, [rsi+10h]
0x140001d14  mov     r15d, [rax+20h]
0x140001d18  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140001d1d  test    eax, eax
0x140001d1f  jnz     short loc_140001D43
0x140001d21  mov     rax, [rsi+10h]
0x140001d25  mov     rcx, [rax+18h]
0x140001d29  mov     rax, [rcx+8]
0x140001d2d  mov     rcx, rsi; Data
0x140001d30  and     dword ptr [rax+14h], 0FFF3FFFFh
0x140001d37  call    cs:__imp_FltSetCallbackDataDirty
0x140001d3e  nop     dword ptr [rax+rax+00h]
0x140001d43  mov     ebx, r15d
0x140001d46  and     ebx, 1
0x140001d49  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x140001d4e  test    eax, eax
0x140001d50  jnz     short loc_140001D8E
0x140001d52  test    ebx, ebx
0x140001d54  jz      short loc_140001D80
0x140001d56  test    byte ptr [rsi+20h], 2
0x140001d5a  jz      loc_140001DEF
0x140001d60  mov     rbx, [rdi+30h]
0x140001d64  lea     rcx, [rbp+57h+EventDescriptor]
0x140001d68  mov     rdx, rbx
0x140001d6b  call    BfsGetFileName
0x140001d70  mov     edx, 2
0x140001d75  mov     r8d, 1
0x140001d7b  mov     r9d, edx
0x140001d7e  jmp     short loc_140001DCD
0x140001d80  test    r15b, 40h
0x140001d84  jz      short loc_140001DEF
0x140001d86  test    byte ptr [rsi+20h], 2
0x140001d8a  jz      short loc_140001DEF
0x140001d8c  jmp     short loc_140001DB2
0x140001d8e  test    ebx, ebx
0x140001d90  jz      short loc_140001DA0
0x140001d92  test    byte ptr [rsi+20h], 2
0x140001d96  jz      short loc_140001DEF
0x140001d98  cmp     [rdi+48h], r13b
0x140001d9c  jnz     short loc_140001DEF
0x140001d9e  jmp     short loc_140001D60
0x140001da0  test    r15b, 40h
0x140001da4  jz      short loc_140001DEF
0x140001da6  test    byte ptr [rsi+20h], 2
0x140001daa  jz      short loc_140001DEF
0x140001dac  cmp     [rdi+48h], r13b
0x140001db0  jnz     short loc_140001DEF
0x140001db2  mov     rbx, [rdi+30h]
0x140001db6  lea     rcx, [rbp+57h+EventDescriptor]
0x140001dba  mov     rdx, rbx
0x140001dbd  call    BfsGetFileName
0x140001dc2  mov     edx, 1
0x140001dc7  xor     r9d, r9d
0x140001dca  mov     r8d, edx
0x140001dcd  movups  xmm1, xmmword ptr [rax]
0x140001dd0  lea     rcx, [rbp+57h+String1]
0x140001dd4  mov     [rsp+0E0h+UserData], rcx
0x140001dd9  lea     rax, [rbx+18h]
0x140001ddd  mov     rcx, [r14+30h]
0x140001de1  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x140001de5  mov     qword ptr [rsp+0E0h+UserDataCount], rax
0x140001dea  call    BfsAddOrModifyEntry
0x140001def  mov     rax, [rsi+10h]
0x140001df3  mov     rcx, [rax+18h]
0x140001df7  mov     rax, [rcx+8]
0x140001dfb  mov     rcx, [rax+20h]; Object
0x140001dff  test    rcx, rcx
0x140001e02  jz      short loc_140001E10
0x140001e04  call    cs:__imp_ObfDereferenceObject
0x140001e0b  nop     dword ptr [rax+rax+00h]
0x140001e10  mov     rax, [rsi+10h]
0x140001e14  movups  xmm0, xmmword ptr [rdi+10h]
0x140001e18  mov     rcx, [rax+18h]
0x140001e1c  mov     rax, [rcx+8]
0x140001e20  movups  xmmword ptr [rax+20h], xmm0
0x140001e24  movups  xmm1, xmmword ptr [rdi+20h]
0x140001e28  movups  xmmword ptr [rax+30h], xmm1
0x140001e2c  jmp     loc_14000209C
0x140001e31  cmp     eax, 1
0x140001e34  jnz     loc_14000209C
0x140001e3a  cmp     dword ptr [rsi+18h], 0C0000022h
0x140001e41  jnz     loc_14000209C
0x140001e47  mov     eax, [r14+68h]
0x140001e4b  test    eax, eax
0x140001e4d  jnz     short loc_140001E97
0x140001e4f  mov     rax, cs:__imp_SeExports
0x140001e56  lea     r8, [rbp+57h+var_B0]
0x140001e5a  mov     [rbp+57h+var_B0], r13b
0x140001e5e  xor     ecx, ecx
0x140001e60  mov     rdx, [rax]
0x140001e63  mov     rdx, [rdx+248h]
0x140001e6a  call    cs:__imp_RtlCheckTokenCapability
0x140001e71  nop     dword ptr [rax+rax+00h]
0x140001e76  test    eax, eax
0x140001e78  js      short loc_140001E8A
0x140001e7a  cmp     [rbp+57h+var_B0], r13b
0x140001e7e  jz      short loc_140001E8A
0x140001e80  mov     dword ptr [r14+68h], 1
0x140001e88  jmp     short loc_140001EA0
0x140001e8a  mov     dword ptr [r14+68h], 2
0x140001e92  jmp     loc_14000209C
0x140001e97  cmp     eax, 1
0x140001e9a  jnz     loc_14000209C
0x140001ea0  lea     rcx, [rdi+10h]; SubjectContext
0x140001ea4  call    cs:__imp_SeCaptureSubjectContext
0x140001eab  nop     dword ptr [rax+rax+00h]
0x140001eb0  cmp     qword ptr [rdi+10h], 0
0x140001eb5  mov     r13b, 1
0x140001eb8  jz      loc_140002076
0x140001ebe  mov     rcx, [rdi+20h]; Token
0x140001ec2  lea     rdx, [rbp+57h+SessionId]; SessionId
0x140001ec6  xor     eax, eax
0x140001ec8  mov     [rbp+57h+SessionId], eax
0x140001ecb  mov     [rbp+57h+var_8C], eax
0x140001ece  call    cs:__imp_SeQuerySessionIdToken
0x140001ed5  nop     dword ptr [rax+rax+00h]
0x140001eda  test    eax, eax
0x140001edc  jns     loc_140001F98
0x140001ee2  mov     ecx, cs:dword_140019000
0x140001ee8  cmp     ecx, 3
0x140001eeb  jbe     loc_140002230
0x140001ef1  mov     [rbp+57h+var_90], eax
0x140001ef4  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140001ef8  mov     [rbp+57h+var_40], 4
0x140001f00  lea     rax, [rbp+57h+var_90]
0x140001f04  mov     [rbp+57h+var_48], rax
0x140001f08  xor     esi, esi
0x140001f0a  mov     rax, cs:qword_140016D92
0x140001f11  xor     r9d, r9d; RelatedActivityId
0x140001f14  movzx   ecx, ax
0x140001f17  xor     r8d, r8d; ActivityId
0x140001f1a  mov     rax, cs:EventInformation
0x140001f21  mov     [rbp+57h+var_68.Ptr], rax
0x140001f25  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140001f28  lea     rcx, _TraceLoggingMetadata
0x140001f2f  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140001f36  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x140001f3a  movzx   eax, word ptr [rax]
0x140001f3d  mov     [rbp+57h+var_68.Size], eax
0x140001f40  lea     rax, dword_140016D9C
0x140001f47  mov     [rbp+57h+var_58], rax
0x140001f4b  lea     rax, _TraceLoggingMetadataEnd
0x140001f52  sub     eax, ecx
0x140001f54  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x140001f5b  mov     [rbp+57h+var_50], 1Eh
0x140001f62  mov     [rbp+57h+var_4C], 1
0x140001f69  mov     dword ptr [rbp+57h+String1.Length], eax
0x140001f6c  mov     eax, dword ptr [rbp+57h+String1.Length]
0x140001f6f  mov     rcx, cs:RegHandle; RegHandle
0x140001f76  lea     rax, [rbp+57h+var_68]
0x140001f7a  mov     [rsp+0E0h+UserData], rax; UserData
0x140001f7f  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x140001f87  call    cs:__imp_EtwWriteTransfer
0x140001f8e  nop     dword ptr [rax+rax+00h]
0x140001f93  jmp     loc_140002230
0x140001f98  mov     rcx, [rdi+10h]; Token
0x140001f9c  lea     rdx, [rbp+57h+var_8C]; SessionId
0x140001fa0  call    cs:__imp_SeQuerySessionIdToken
0x140001fa7  nop     dword ptr [rax+rax+00h]
0x140001fac  test    eax, eax
0x140001fae  jns     loc_14000206A
0x140001fb4  mov     ecx, cs:dword_140019000
0x140001fba  cmp     ecx, 3
0x140001fbd  jbe     loc_140002230
0x140001fc3  mov     dword ptr [rbp+57h+String1.Length], eax
0x140001fc6  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140001fca  mov     [rbp+57h+var_40], 4
0x140001fd2  lea     rax, [rbp+57h+String1]
0x140001fd6  mov     [rbp+57h+var_48], rax
0x140001fda  xor     esi, esi
0x140001fdc  mov     rax, cs:qword_140016D92
0x140001fe3  xor     r9d, r9d; RelatedActivityId
0x140001fe6  movzx   ecx, ax
0x140001fe9  xor     r8d, r8d; ActivityId
0x140001fec  mov     rax, cs:EventInformation
0x140001ff3  mov     [rbp+57h+var_68.Ptr], rax
0x140001ff7  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140001ffa  lea     rcx, _TraceLoggingMetadata
0x140002001  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002008  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x14000200c  movzx   eax, word ptr [rax]
0x14000200f  mov     [rbp+57h+var_68.Size], eax
0x140002012  lea     rax, dword_140016D9C
0x140002019  mov     [rbp+57h+var_58], rax
0x14000201d  lea     rax, _TraceLoggingMetadataEnd
0x140002024  sub     eax, ecx
0x140002026  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x14000202d  mov     [rbp+57h+var_50], 1Eh
0x140002034  mov     [rbp+57h+var_4C], 1
0x14000203b  mov     [rbp+57h+var_90], eax
0x14000203e  mov     eax, [rbp+57h+var_90]
0x140002041  mov     rcx, cs:RegHandle; RegHandle
0x140002048  lea     rax, [rbp+57h+var_68]
0x14000204c  mov     [rsp+0E0h+UserData], rax; UserData
0x140002051  mov     [rsp+0E0h+UserDataCount], 3; UserDataCount
0x140002059  call    cs:__imp_EtwWriteTransfer
0x140002060  nop     dword ptr [rax+rax+00h]
0x140002065  jmp     loc_140002230
0x14000206a  mov     eax, [rbp+57h+var_8C]
0x14000206d  cmp     [rbp+57h+SessionId], eax
0x140002070  jnz     loc_140002230
0x140002076  call    cs:__imp_PsGetCurrentProcessId
0x14000207d  nop     dword ptr [rax+rax+00h]
0x140002082  mov     r8, rdi
0x140002085  mov     rdx, r15
0x140002088  mov     rcx, rsi; Data
0x14000208b  mov     [rdi+38h], rax
0x14000208f  call    BfsPerformPrompt
0x140002094  test    eax, eax
0x140002096  js      loc_140001FB4
0x14000209c  mov     eax, [rdi]
0x14000209e  test    al, 4
0x1400020a0  jz      loc_140002230
0x1400020a6  cmp     dword ptr [rsi+18h], 0
0x1400020aa  jl      loc_140002230
  ... truncated ...
```
