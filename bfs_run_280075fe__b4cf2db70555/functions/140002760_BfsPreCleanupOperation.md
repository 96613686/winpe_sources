# BfsPreCleanupOperation

- ea: `0x140002760`
- end: `0x140002a27`
- name: `BfsPreCleanupOperation`
- size: `711`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001270`
- `0x140002760`
- `0x140004998`
- `0x140004b90`
- `0x140013730`
- `0x140013770`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400029a9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400029a9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400027c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002996`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400027c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002996`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400027d4`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400027d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400027e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400029b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400027e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400029b5`
- `ntoskrnl!EtwWriteTransfer` at `0x14000298a`
- `ntoskrnl!EtwWriteTransfer` at `0x14000298a`
- `FLTMGR!FltGetFileNameInformation` at `0x1400028d3`
- `FLTMGR!FltGetFileNameInformation` at `0x1400028d3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002a10`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002a10`
- `FLTMGR!FltReleaseContext` at `0x1400029ca`
- `FLTMGR!FltReleaseContext` at `0x1400029ca`
- `FLTMGR!FltGetFileContext` at `0x140002807`
- `FLTMGR!FltGetFileContext` at `0x140002807`

## pseudocode

```c
__int64 __fastcall BfsPreCleanupOperation(PFLT_CALLBACK_DATA CallbackData, __int64 a2, PFLT_CONTEXT *a3)
{
  PDEVICE_OBJECT DeviceObject; // rax
  BOOLEAN v7; // bl
  __int64 v8; // rbx
  NTSTATUS v9; // eax
  char v11; // [rsp+30h] [rbp-69h]
  int v12; // [rsp+50h] [rbp-49h] BYREF
  __int64 v13; // [rsp+58h] [rbp-41h]
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-39h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-19h] BYREF
  int *v18; // [rsp+90h] [rbp-9h]
  int v19; // [rsp+98h] [rbp-1h]
  int v20; // [rsp+9Ch] [rbp+3h]
  int *v21; // [rsp+A0h] [rbp+7h]
  __int64 v22; // [rsp+A8h] [rbp+Fh]

  Context = 0;
  FileNameInformation = 0;
  if ( (unsigned int)Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline() )
  {
    DeviceObject = CallbackData->Iopb->TargetFileObject->DeviceObject;
    if ( !DeviceObject || DeviceObject->DeviceType == 20 )
      goto LABEL_16;
  }
  KeEnterCriticalRegion();
  v7 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( !v7 )
    goto LABEL_16;
  if ( FltGetFileContext(*(PFLT_INSTANCE *)(a2 + 24), CallbackData->Iopb->TargetFileObject, &Context) >= 0 )
  {
    v13 = (unsigned int)Feature_AppSiloBFSPagePoolCleanup__private_featureState;
    if ( (Feature_AppSiloBFSPagePoolCleanup__private_featureState & 0x10) == 0 )
    {
      LODWORD(v13) = Feature_AppSiloBFSPagePoolCleanup__private_featureState | 1;
      v8 = v13;
      v12 = 3;
      if ( (unsigned int)wil_details_FeatureReporting_ReportUsageToServiceDirect(
                           wil_details_featureDescriptors_a,
                           v13,
                           2)
        && g_wil_details_pfnFeatureLoggingHook )
      {
        v11 = 0;
        g_wil_details_pfnFeatureLoggingHook(
          57751298,
          &Feature_AppSiloBFSPagePoolCleanup_logged_traits,
          0,
          1,
          &v12,
          0,
          v11,
          1);
      }
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v8, 3, wil_details_featureDescriptors_a);
    }
    if ( !*((_QWORD *)Context + 1) )
    {
      v9 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_140019000 > 3 )
        {
          v12 = v9;
          v22 = 4;
          v21 = &v12;
          UserData.Ptr = (ULONGLONG)EventInformation;
          *(_DWORD *)&EventDescriptor.Level = 3;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v18 = &dword_140016D9C;
          UserData.Reserved = 2;
          v19 = 30;
          v20 = 1;
          LODWORD(v13) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        goto LABEL_15;
      }
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)Context + 1, (signed __int64)FileNameInformation, 0) )
        FltReleaseFileNameInformation(FileNameInformation);
    }
    *a3 = Context;
    return 0;
  }
LABEL_15:
  KeEnterCriticalRegion();
  ExReleaseRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
LABEL_16:
  if ( Context )
    FltReleaseContext(Context);
  return 1;
}

```

## disassembly

```asm
0x140002760  push    rbp
0x140002762  push    rbx
0x140002763  push    rsi
0x140002764  push    rdi
0x140002765  push    r12
0x140002767  push    r14
0x140002769  push    r15
0x14000276b  lea     rbp, [rsp-27h]
0x140002770  sub     rsp, 0C0h
0x140002777  mov     rax, cs:__security_cookie
0x14000277e  xor     rax, rsp
0x140002781  mov     [rbp+57h+var_40], rax
0x140002785  xor     r12d, r12d
0x140002788  mov     r15, r8
0x14000278b  mov     [rbp+57h+Context], r12
0x14000278f  mov     r14, rdx
0x140002792  mov     [rbp+57h+FileNameInformation], r12
0x140002796  mov     rsi, rcx
0x140002799  call    Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline
0x14000279e  test    eax, eax
0x1400027a0  jz      short loc_1400027C1
0x1400027a2  mov     rax, [rsi+10h]
0x1400027a6  mov     rcx, [rax+8]
0x1400027aa  mov     rax, [rcx+8]
0x1400027ae  test    rax, rax
0x1400027b1  jz      loc_1400029C1
0x1400027b7  cmp     dword ptr [rax+48h], 14h
0x1400027bb  jz      loc_1400029C1
0x1400027c1  call    cs:__imp_KeEnterCriticalRegion
0x1400027c8  nop     dword ptr [rax+rax+00h]
0x1400027cd  lea     rcx, gBfsRundownProtection; RunRef
0x1400027d4  call    cs:__imp_ExAcquireRundownProtection
0x1400027db  nop     dword ptr [rax+rax+00h]
0x1400027e0  movzx   ebx, al
0x1400027e3  call    cs:__imp_KeLeaveCriticalRegion
0x1400027ea  nop     dword ptr [rax+rax+00h]
0x1400027ef  test    bl, bl
0x1400027f1  jz      loc_1400029C1
0x1400027f7  mov     rdx, [rsi+10h]
0x1400027fb  lea     r8, [rbp+57h+Context]; Context
0x1400027ff  mov     rcx, [r14+18h]; Instance
0x140002803  mov     rdx, [rdx+8]; FileObject
0x140002807  call    cs:__imp_FltGetFileContext
0x14000280e  nop     dword ptr [rax+rax+00h]
0x140002813  test    eax, eax
0x140002815  js      loc_140002996
0x14000281b  mov     ecx, cs:Feature_AppSiloBFSPagePoolCleanup__private_featureState
0x140002821  mov     [rbp+57h+var_98], r12
0x140002825  mov     dword ptr [rbp+57h+var_98], ecx
0x140002828  test    cl, 10h
0x14000282b  jnz     loc_1400028B9
0x140002831  mov     rax, [rbp+57h+var_98]
0x140002835  or      ecx, 1
0x140002838  mov     [rbp+57h+var_98], rax
0x14000283c  mov     r8d, 2
0x140002842  mov     dword ptr [rbp+57h+var_98], ecx
0x140002845  lea     rcx, wil_details_featureDescriptors_a
0x14000284c  mov     rbx, [rbp+57h+var_98]
0x140002850  mov     rdx, rbx
0x140002853  mov     [rbp+57h+var_A0], 3
0x14000285a  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000285f  test    eax, eax
0x140002861  jz      short loc_1400028A5
0x140002863  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000286a  test    rax, rax
0x14000286d  jz      short loc_1400028A5
0x14000286f  mov     rdx, cs:off_140018058
0x140002876  lea     rcx, [rbp+57h+var_A0]
0x14000287a  mov     [rsp+0F0h+var_B8], 1
0x140002883  mov     r9d, 1
0x140002889  mov     [rsp+0F0h+var_C0], r12b
0x14000288e  xor     r8d, r8d
0x140002891  mov     [rsp+0F0h+UserData], r12
0x140002896  mov     qword ptr [rsp+0F0h+UserDataCount], rcx
0x14000289b  mov     ecx, 3713702h
0x1400028a0  call    _guard_dispatch_icall
0x1400028a5  lea     r8, wil_details_featureDescriptors_a
0x1400028ac  mov     edx, 3
0x1400028b1  mov     rcx, rbx
0x1400028b4  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400028b9  mov     rax, [rbp+57h+Context]
0x1400028bd  cmp     [rax+8], r12
0x1400028c1  jnz     loc_140002A1C
0x1400028c7  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400028cb  mov     edx, 101h; NameOptions
0x1400028d0  mov     rcx, rsi; CallbackData
0x1400028d3  call    cs:__imp_FltGetFileNameInformation
0x1400028da  nop     dword ptr [rax+rax+00h]
0x1400028df  test    eax, eax
0x1400028e1  jns     loc_1400029FA
0x1400028e7  mov     ecx, cs:dword_140019000
0x1400028ed  cmp     ecx, 3
0x1400028f0  jbe     loc_140002996
0x1400028f6  mov     [rbp+57h+var_A0], eax
0x1400028f9  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400028fd  mov     [rbp+57h+var_48], 4
0x140002905  lea     rax, [rbp+57h+var_A0]
0x140002909  mov     [rbp+57h+var_50], rax
0x14000290d  xor     r9d, r9d; RelatedActivityId
0x140002910  mov     rax, cs:qword_140016D92
0x140002917  xor     r8d, r8d; ActivityId
0x14000291a  movzx   ecx, ax
0x14000291d  mov     rax, cs:EventInformation
0x140002924  mov     [rbp+57h+var_70.Ptr], rax
0x140002928  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x14000292b  lea     rcx, _TraceLoggingMetadata
0x140002932  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002939  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x14000293d  movzx   eax, word ptr [rax]
0x140002940  mov     [rbp+57h+var_70.Size], eax
0x140002943  lea     rax, dword_140016D9C
0x14000294a  mov     [rbp+57h+var_60], rax
0x14000294e  lea     rax, _TraceLoggingMetadataEnd
0x140002955  sub     eax, ecx
0x140002957  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x14000295e  mov     [rbp+57h+var_58], 1Eh
0x140002965  mov     [rbp+57h+var_54], 1
0x14000296c  mov     dword ptr [rbp+57h+var_98], eax
0x14000296f  mov     eax, dword ptr [rbp+57h+var_98]
0x140002972  mov     rcx, cs:RegHandle; RegHandle
0x140002979  lea     rax, [rbp+57h+var_70]
0x14000297d  mov     [rsp+0F0h+UserData], rax; UserData
0x140002982  mov     [rsp+0F0h+UserDataCount], 3; UserDataCount
0x14000298a  call    cs:__imp_EtwWriteTransfer
0x140002991  nop     dword ptr [rax+rax+00h]
0x140002996  call    cs:__imp_KeEnterCriticalRegion
0x14000299d  nop     dword ptr [rax+rax+00h]
0x1400029a2  lea     rcx, gBfsRundownProtection; RunRef
0x1400029a9  call    cs:__imp_ExReleaseRundownProtection
0x1400029b0  nop     dword ptr [rax+rax+00h]
0x1400029b5  call    cs:__imp_KeLeaveCriticalRegion
0x1400029bc  nop     dword ptr [rax+rax+00h]
0x1400029c1  mov     rcx, [rbp+57h+Context]; Context
0x1400029c5  test    rcx, rcx
0x1400029c8  jz      short loc_1400029D6
0x1400029ca  call    cs:__imp_FltReleaseContext
0x1400029d1  nop     dword ptr [rax+rax+00h]
0x1400029d6  mov     eax, 1
0x1400029db  mov     rcx, [rbp+57h+var_40]
0x1400029df  xor     rcx, rsp; StackCookie
0x1400029e2  call    __security_check_cookie
0x1400029e7  add     rsp, 0C0h
0x1400029ee  pop     r15
0x1400029f0  pop     r14
0x1400029f2  pop     r12
0x1400029f4  pop     rdi
0x1400029f5  pop     rsi
0x1400029f6  pop     rbx
0x1400029f7  pop     rbp
0x1400029f8  retn
0x1400029fa  mov     rdx, [rbp+57h+Context]
0x1400029fe  xor     eax, eax
0x140002a00  mov     rcx, [rbp+57h+FileNameInformation]
0x140002a04  lock cmpxchg [rdx+8], rcx
0x140002a0a  jz      short loc_140002A1C
0x140002a0c  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140002a10  call    cs:__imp_FltReleaseFileNameInformation
0x140002a17  nop     dword ptr [rax+rax+00h]
0x140002a1c  mov     rax, [rbp+57h+Context]
0x140002a20  mov     [r15], rax
0x140002a23  xor     eax, eax
0x140002a25  jmp     short loc_1400029DB
```
