# OnDriverLoad

- ea: `0x1402104e4`
- end: `0x140210dca`
- name: `OnDriverLoad`
- size: `2278`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1402102b0`

## callees

- `0x14000113c`
- `0x14000116c`
- `0x140005608`
- `0x140005690`
- `0x14001a420`
- `0x140027874`
- `0x1400278a0`
- `0x14015cba0`
- `0x14015d710`
- `0x140161b40`
- `0x140161b94`
- `0x1401643f0`
- `0x140164520`
- `0x1401646f4`
- `0x1401b3530`
- `0x1401b35b8`
- `0x1401b3a70`
- `0x1401b3af8`
- `0x1401ba368`
- `0x1401ba41c`
- `0x1401ba450`
- `0x1401ba4f8`
- `0x1401ba5c8`
- `0x1401baa40`
- `0x1401f2694`
- `0x140210008`
- `0x140210230`
- `0x1402104e4`
- `0x140211944`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1402107ff`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402107ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210bf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210c37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210bf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210c37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210d47`
- `ntoskrnl!ExAllocatePool2` at `0x140210777`
- `ntoskrnl!ExAllocatePool2` at `0x140210a20`
- `ntoskrnl!ExAllocatePool2` at `0x140210777`
- `ntoskrnl!ExAllocatePool2` at `0x140210a20`
- `ntoskrnl!KeInitializeEvent` at `0x140210531`
- `ntoskrnl!KeInitializeEvent` at `0x140210531`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x140210c70`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x140210d80`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x140210c70`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x140210d80`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x1402106ff`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x1402106ff`
- `WppRecorder!imp_WppRecorderGetTriageInfo` at `0x140210695`
- `WppRecorder!imp_WppRecorderGetTriageInfo` at `0x140210695`

## pseudocode

```c
__int64 __fastcall OnDriverLoad(UNICODE_STRING *SourceString)
{
  __int64 v2; // rcx
  int v3; // edx
  int v4; // r8d
  int TriageInfo; // eax
  int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // edx
  __int64 *v12; // r8
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  __int64 v16; // rdx
  __int64 *v17; // r8
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  int v22; // edx
  int v23; // r8d
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // eax
  int v28; // edx
  int v29; // r8d
  __int64 Pool2; // rax
  int v31; // edx
  int v32; // r8d
  int v33; // eax
  int v34; // edx
  int v35; // r8d
  PDEVICE_OBJECT v36; // r10
  int v37; // eax
  int v38; // eax
  int v39; // edx
  int v40; // r8d
  int Singleton; // eax
  int v42; // edx
  int v43; // r8d
  int v44; // eax
  bool v46; // sf
  int v47; // eax
  __int16 v48; // [rsp+30h] [rbp-30h]
  char v49; // [rsp+40h] [rbp-20h]
  int *v50; // [rsp+50h] [rbp-10h] BYREF
  char v51; // [rsp+58h] [rbp-8h]
  int v52; // [rsp+90h] [rbp+30h] BYREF
  const wchar_t *v53; // [rsp+98h] [rbp+38h] BYREF
  __int64 v54; // [rsp+A0h] [rbp+40h] BYREF

  v52 = 0;
  _security_init_cookie();
  v52 = wil_InitializeFeatureStaging();
  dword_140197C20 = 1;
  qword_140197C28 = 0;
  dword_140197C30 = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  dword_1401980C9 = 0;
  qword_140197C60 = (__int64)&qword_140197C58;
  qword_140197C58 = (__int64)&qword_140197C58;
  qword_1401980C0 = (__int64)&qword_1401980B8;
  qword_1401980B8 = (__int64)&qword_1401980B8;
  WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink = (_LIST_ENTRY *)&Microsoft::Bluetooth::Foundation::KernelSingleton<WppProviderStateObservable>::s_rawStorage;
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)&WPP_ThisDir_CTLGUID_bthport;
  WPP_MAIN_CB.NextDevice = (_DEVICE_OBJECT *)&WPP_MAIN_CB.Queue;
  WPP_MAIN_CB.Queue.ListEntry.Blink = (_LIST_ENTRY *)WPP_ThisDir_CTLGUID_BleConnectionDiagnosticsGuid;
  word_1401980CD = 0;
  byte_1401980CF = 0;
  Microsoft::Bluetooth::Foundation::KernelSingleton<WppProviderStateObservable>::s_rawStorage = 0;
  byte_1401980C8 = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.Queue.ListEntry.Flink = 0;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = 0;
  WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = 1;
  WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc = 0;
  WPP_MAIN_CB.AlignmentRequirement = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(v2, SourceString);
  v4 = v52;
  if ( v52 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v3) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v3) = 0;
    LOBYTE(v4) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      v4,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      6,
      10,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v52);
    v52 = 0;
  }
  TriageInfo = imp_WppRecorderGetTriageInfo(WPP_GLOBAL_Control, &g_bthportWppTriageInfo);
  v52 = TriageInfo;
  if ( TriageInfo < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v6) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v6) = 0;
    LOBYTE(v7) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      6,
      11,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      TriageInfo);
    v52 = 0;
  }
  v8 = SleepstudyHelper_Initialize(&qword_140197C68, "BthPortSleepStudy");
  v52 = v8;
  if ( v8 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v9) = 0;
    LOBYTE(v10) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      v10,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      6,
      12,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v8);
    v52 = 0;
  }
  RefObj_GlobalsInit();
  DestinationString.Buffer = (wchar_t *)ExAllocatePool2(256, SourceString->Length + 2LL, 1346917442);
  if ( !DestinationString.Buffer )
  {
    v52 = -1073741670;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v11) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v11) = 0;
    v12 = WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids;
    LOBYTE(v12) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      (_DWORD)v12,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      6,
      13,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids);
    v13 = v52;
    v14 = v52;
    goto LABEL_91;
  }
  DestinationString.MaximumLength = SourceString->Length + 2;
  RtlCopyUnicodeString(&DestinationString, SourceString);
  v15 = TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140197150);
  v52 = v15;
  if ( v15 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v16) = 0;
    v17 = WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids;
    LOBYTE(v17) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v16,
      (_DWORD)v17,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      6,
      14,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v15);
    v52 = 0;
  }
  v50 = &v52;
  if ( (unsigned int)dword_140197150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140197150, 0x400000000000LL) )
  {
    v54 = 33556480;
    v53 = L"BthPort.sys";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      v18,
      (unsigned int)byte_140189805,
      v19,
      v20,
      (__int64)&v54,
      (__int64)&v53);
  }
  v21 = McGenEventRegister_EtwRegister(
          BTHPORT_ETW_PROVIDER,
          v16,
          &BTHPORT_ETW_PROVIDER_Context,
          &BTHPORT_ETW_PROVIDER_Context);
  v52 = v21;
  if ( v21 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v22) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v22) = 0;
    LOBYTE(v23) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v22,
      v23,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      6,
      15,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v21);
    v52 = 0;
  }
  v24 = TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140197118);
  v52 = v24;
  if ( v24 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v25) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v25) = 0;
    LOBYTE(v26) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v25,
      v26,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      6,
      16,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v24);
    v52 = 0;
  }
  v27 = InitializeTelemetryAssertsKM((const void **)SourceString);
  v52 = v27;
  if ( v27 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v28) = 0;
    LOBYTE(v29) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v28,
      v29,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      6,
      17,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v27);
    v52 = 0;
  }
  DevicePerfCounters::Register();
  RadioPerfCounters::Register();
  Pool2 = ExAllocatePool2(64, 8, 1346917442);
  *(_QWORD *)&Globals = Pool2;
  if ( !Pool2 )
  {
    v52 = -1073741670;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v31) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v31) = 0;
    LOBYTE(v32) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v31,
      v32,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      6,
      18,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids);
    v14 = v52;
    if ( v52 >= 0 )
      goto LABEL_89;
    DevicePerfCounters::Unregister();
    RadioPerfCounters::Unregister();
    if ( v52 >= 0 )
      goto LABEL_89;
    goto LABEL_86;
  }
  *(_DWORD *)Pool2 = 1;
  *(_DWORD *)(Pool2 + 4) = 1;
  v33 = SecDB_Init((struct _SECURITY_DATABASE *)Pool2);
  v52 = v33;
  if ( v33 < 0 )
  {
    v36 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v34) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v34) = 0;
    v49 = v33;
    v48 = 19;
    goto LABEL_50;
  }
  v37 = BthPolicyInitialize();
  v52 = v37;
  if ( v37 < 0 )
  {
    v36 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v34) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v34) = 0;
    v49 = v37;
    v48 = 20;
LABEL_50:
    LOBYTE(v35) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      v36->AttachedDevice,
      v34,
      v35,
      v36->DeviceExtension,
      2,
      6,
      v48,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v49);
    v14 = v52;
    if ( v52 >= 0 )
      goto LABEL_89;
    ExFreePoolWithTag(*(PVOID *)&Globals, 0);
    *(_QWORD *)&Globals = 0;
    if ( v52 >= 0 )
      goto LABEL_89;
    goto LABEL_52;
  }
  v38 = BthSyncWithPolicyStore();
  v52 = v38;
  if ( v38 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v39) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v39) = 0;
    LOBYTE(v40) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v39,
      v40,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      6,
      21,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      v38);
    v52 = 0;
  }
  Singleton = CrashDump::MakeSingleton();
  v52 = Singleton;
  if ( Singleton < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 || (LOBYTE(v42) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v42) = 0;
    LOBYTE(v43) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v42,
      v43,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      6,
      22,
      (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids,
      Singleton);
    v14 = v52;
    if ( v52 >= 0 )
      goto LABEL_89;
    BthPolicyDestroy();
    if ( v52 >= 0 )
      goto LABEL_89;
    ExFreePoolWithTag(*(PVOID *)&Globals, 0);
    *(_QWORD *)&Globals = 0;
    if ( v52 >= 0 )
      goto LABEL_89;
LABEL_52:
    DevicePerfCounters::Unregister();
    RadioPerfCounters::Unregister();
    if ( v52 < 0 )
    {
LABEL_86:
      UninitializeTelemetryAssertsKM();
      if ( v52 < 0 )
      {
        TraceLoggingUnregister_EtwUnregister(&dword_140197118);
        if ( v52 < 0 )
          McGenEventUnregister_EtwUnregister(&BTHPORT_ETW_PROVIDER_Context);
      }
    }
LABEL_89:
    v51 = 0;
    lambda_4d9c19cb87df6cfae12a11f73006a252_::operator()(&v50);
    v46 = v52 < 0;
    if ( v52 >= 0 )
    {
LABEL_97:
      WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink = 0;
      if ( v46 )
        wil_UninitializeFeatureStaging();
      return v14;
    }
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    v13 = v52;
    DestinationString.MaximumLength = 0;
    DestinationString.Buffer = 0;
LABEL_91:
    v46 = v13 < 0;
    if ( v13 < 0 )
    {
      RefObj_GlobalsUnload();
      v47 = v52;
      v46 = v52 < 0;
      if ( v52 < 0 )
      {
        if ( qword_140197C68 )
        {
          SleepstudyHelper_Uninitialize();
          v47 = v52;
          qword_140197C68 = 0;
        }
        v46 = v47 < 0;
        if ( v47 < 0 )
        {
          WppCleanupKm();
          v46 = v52 < 0;
        }
      }
    }
    goto LABEL_97;
  }
  v51 = 0;
  lambda_4d9c19cb87df6cfae12a11f73006a252_::operator()(&v50);
  if ( v52 < 0 )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    DestinationString.Buffer = 0;
    DestinationString.MaximumLength = 0;
    if ( v52 < 0 )
    {
      RefObj_GlobalsUnload();
      v44 = v52;
      if ( v52 < 0 )
      {
        if ( qword_140197C68 )
        {
          SleepstudyHelper_Uninitialize();
          v44 = v52;
          qword_140197C68 = 0;
        }
        if ( v44 < 0 )
        {
          WppCleanupKm();
          if ( v52 < 0 )
            wil_UninitializeFeatureStaging();
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1402104e4  mov     [rsp-28h+arg_18], rbx
0x1402104e9  push    rbp
0x1402104ea  push    rdi
0x1402104eb  push    r12
0x1402104ed  push    r13
0x1402104ef  push    r15
0x1402104f1  mov     rbp, rsp
0x1402104f4  sub     rsp, 60h
0x1402104f8  xor     edi, edi
0x1402104fa  mov     rbx, rcx
0x1402104fd  mov     [rbp+arg_0], edi
0x140210500  call    __security_init_cookie
0x140210505  call    wil_InitializeFeatureStaging
0x14021050a  xor     r8d, r8d; State
0x14021050d  mov     [rbp+arg_0], eax
0x140210510  lea     edx, [rdi+1]; Type
0x140210513  mov     cs:dword_140197C20, 1
0x14021051d  lea     rcx, Event; Event
0x140210524  mov     cs:qword_140197C28, rdi
0x14021052b  mov     cs:dword_140197C30, edi
0x140210531  call    cs:__imp_KeInitializeEvent
0x140210538  nop     dword ptr [rax+rax+00h]
0x14021053d  lea     rax, qword_140197C58
0x140210544  mov     cs:dword_1401980C9, edi
0x14021054a  mov     cs:qword_140197C60, rax
0x140210551  mov     cs:qword_140197C58, rax
0x140210558  lea     rax, qword_1401980B8
0x14021055f  mov     cs:qword_1401980C0, rax
0x140210566  mov     cs:qword_1401980B8, rax
0x14021056d  lea     rax, ?s_rawStorage@?$KernelSingleton@VWppProviderStateObservable@@@Foundation@Bluetooth@Microsoft@@0PAEA; uchar near * Microsoft::Bluetooth::Foundation::KernelSingleton<WppProviderStateObservable>::s_rawStorage
0x140210574  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, rax
0x14021057b  lea     rax, WPP_ThisDir_CTLGUID_bthport
0x140210582  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140210589  lea     rax, WPP_MAIN_CB.Queue
0x140210590  mov     cs:WPP_MAIN_CB.NextDevice, rax
0x140210597  lea     rax, WPP_ThisDir_CTLGUID_BleConnectionDiagnosticsGuid
0x14021059e  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x1402105a5  mov     cs:word_1401980CD, di
0x1402105ac  mov     cs:byte_1401980CF, dil
0x1402105b3  mov     cs:?s_rawStorage@?$KernelSingleton@VWppProviderStateObservable@@@Foundation@Bluetooth@Microsoft@@0PAEA, rdi; uchar near * Microsoft::Bluetooth::Foundation::KernelSingleton<WppProviderStateObservable>::s_rawStorage
0x1402105ba  mov     cs:byte_1401980C8, dil
0x1402105c1  mov     qword ptr cs:WPP_MAIN_CB.Type, rdi
0x1402105c8  mov     cs:WPP_MAIN_CB.CurrentIrp, rdi
0x1402105cf  mov     cs:WPP_MAIN_CB.Timer, 1
0x1402105da  mov     cs:WPP_MAIN_CB.DeviceExtension, rdi
0x1402105e1  mov     cs:WPP_MAIN_CB.DeviceType, edi
0x1402105e7  mov     qword ptr cs:WPP_MAIN_CB.Queue, rdi
0x1402105ee  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rdi
0x1402105f5  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rdi
0x1402105fc  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, 1
0x140210607  mov     qword ptr cs:WPP_MAIN_CB.Queue+40h, rdi
0x14021060e  mov     cs:WPP_MAIN_CB.AlignmentRequirement, edi
0x140210614  call    WppLoadTracingSupport
0x140210619  mov     rdx, rbx
0x14021061c  mov     cs:WPP_MAIN_CB.CurrentIrp, rdi
0x140210623  call    WppInitKm
0x140210628  mov     r8d, [rbp+arg_0]
0x14021062c  lea     r12, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x140210633  lea     r13d, [rdi+6]
0x140210637  mov     r15b, 20h ; ' '
0x14021063a  test    r8d, r8d
0x14021063d  jns     short loc_140210687
0x14021063f  mov     rcx, cs:WPP_GLOBAL_Control
0x140210646  mov     eax, [rcx+2Ch]
0x140210649  test    r15b, al
0x14021064c  jz      short loc_140210656
0x14021064e  cmp     byte ptr [rcx+29h], 3
0x140210652  mov     dl, 1
0x140210654  jnb     short loc_140210659
0x140210656  mov     dl, dil
0x140210659  mov     r9, [rcx+40h]
0x14021065d  mov     rcx, [rcx+18h]
0x140210661  mov     dword ptr [rsp+60h+var_20], r8d
0x140210666  mov     r8b, 1
0x140210669  mov     [rsp+60h+var_28], r12
0x14021066e  mov     [rsp+60h+var_30], 0Ah
0x140210675  mov     dword ptr [rsp+60h+var_38], r13d
0x14021067a  mov     byte ptr [rsp+60h+var_40], 3
0x14021067f  call    WPP_RECORDER_AND_TRACE_SF_d
0x140210684  mov     [rbp+arg_0], edi
0x140210687  mov     rcx, cs:WPP_GLOBAL_Control
0x14021068e  lea     rdx, ?g_bthportWppTriageInfo@@3U_WPP_TRIAGE_INFO@@A; _WPP_TRIAGE_INFO g_bthportWppTriageInfo
0x140210695  call    cs:__imp_imp_WppRecorderGetTriageInfo
0x14021069c  nop     dword ptr [rax+rax+00h]
0x1402106a1  mov     [rbp+arg_0], eax
0x1402106a4  test    eax, eax
0x1402106a6  jns     short loc_1402106F1
0x1402106a8  mov     r10, cs:WPP_GLOBAL_Control
0x1402106af  mov     ecx, [r10+2Ch]
0x1402106b3  test    r15b, cl
0x1402106b6  jz      short loc_1402106C1
0x1402106b8  cmp     byte ptr [r10+29h], 3
0x1402106bd  mov     dl, 1
0x1402106bf  jnb     short loc_1402106C4
0x1402106c1  mov     dl, dil
0x1402106c4  mov     r9, [r10+40h]
0x1402106c8  mov     r8b, 1
0x1402106cb  mov     rcx, [r10+18h]
0x1402106cf  mov     dword ptr [rsp+60h+var_20], eax
0x1402106d3  mov     [rsp+60h+var_28], r12
0x1402106d8  mov     [rsp+60h+var_30], 0Bh
0x1402106df  mov     dword ptr [rsp+60h+var_38], r13d
0x1402106e4  mov     byte ptr [rsp+60h+var_40], 3
0x1402106e9  call    WPP_RECORDER_AND_TRACE_SF_d
0x1402106ee  mov     [rbp+arg_0], edi
0x1402106f1  lea     rdx, aBthportsleepst; "BthPortSleepStudy"
0x1402106f8  lea     rcx, qword_140197C68
0x1402106ff  call    cs:__imp_SleepstudyHelper_Initialize
0x140210706  nop     dword ptr [rax+rax+00h]
0x14021070b  mov     [rbp+arg_0], eax
0x14021070e  test    eax, eax
0x140210710  jns     short loc_14021075B
0x140210712  mov     r10, cs:WPP_GLOBAL_Control
0x140210719  mov     ecx, [r10+2Ch]
0x14021071d  test    r15b, cl
0x140210720  jz      short loc_14021072B
0x140210722  cmp     byte ptr [r10+29h], 3
0x140210727  mov     dl, 1
0x140210729  jnb     short loc_14021072E
0x14021072b  mov     dl, dil
0x14021072e  mov     r9, [r10+40h]
0x140210732  mov     r8b, 1
0x140210735  mov     rcx, [r10+18h]
0x140210739  mov     dword ptr [rsp+60h+var_20], eax
0x14021073d  mov     [rsp+60h+var_28], r12
0x140210742  mov     [rsp+60h+var_30], 0Ch
0x140210749  mov     dword ptr [rsp+60h+var_38], r13d
0x14021074e  mov     byte ptr [rsp+60h+var_40], 3
0x140210753  call    WPP_RECORDER_AND_TRACE_SF_d
0x140210758  mov     [rbp+arg_0], edi
0x14021075b  call    RefObj_GlobalsInit
0x140210760  movzx   edx, word ptr [rbx]
0x140210763  mov     r12d, 2
0x140210769  add     rdx, r12
0x14021076c  mov     ecx, 100h
0x140210771  mov     r8d, 50485442h
0x140210777  call    cs:__imp_ExAllocatePool2
0x14021077e  nop     dword ptr [rax+rax+00h]
0x140210783  mov     cs:DestinationString.Buffer, rax
0x14021078a  test    rax, rax
0x14021078d  jnz     short loc_1402107E7
0x14021078f  mov     [rbp+arg_0], 0C000009Ah
0x140210796  mov     rcx, cs:WPP_GLOBAL_Control
0x14021079d  mov     eax, [rcx+2Ch]
0x1402107a0  test    r15b, al
0x1402107a3  jz      short loc_1402107AD
0x1402107a5  mov     dl, 1
0x1402107a7  cmp     [rcx+29h], r12b
0x1402107ab  jnb     short loc_1402107B0
0x1402107ad  mov     dl, dil
0x1402107b0  mov     r9, [rcx+40h]
0x1402107b4  lea     r8, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x1402107bb  mov     rcx, [rcx+18h]
0x1402107bf  mov     [rsp+60h+var_28], r8
0x1402107c4  mov     r8b, 1
0x1402107c7  mov     [rsp+60h+var_30], 0Dh
0x1402107ce  mov     dword ptr [rsp+60h+var_38], r13d
0x1402107d3  mov     byte ptr [rsp+60h+var_40], r12b
0x1402107d8  call    WPP_RECORDER_AND_TRACE_SF_
0x1402107dd  mov     eax, [rbp+arg_0]
0x1402107e0  mov     ebx, eax
0x1402107e2  jmp     loc_140210D64
0x1402107e7  movzx   eax, word ptr [rbx]
0x1402107ea  lea     rcx, DestinationString; DestinationString
0x1402107f1  add     ax, r12w
0x1402107f5  mov     rdx, rbx; SourceString
0x1402107f8  mov     cs:DestinationString.MaximumLength, ax
0x1402107ff  call    cs:__imp_RtlCopyUnicodeString
0x140210806  nop     dword ptr [rax+rax+00h]
0x14021080b  lea     rcx, dword_140197150; CallbackContext
0x140210812  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140210817  mov     [rbp+arg_0], eax
0x14021081a  test    eax, eax
0x14021081c  jns     short loc_14021086E
0x14021081e  mov     r10, cs:WPP_GLOBAL_Control
0x140210825  mov     ecx, [r10+2Ch]
0x140210829  test    r15b, cl
0x14021082c  jz      short loc_140210837
0x14021082e  cmp     byte ptr [r10+29h], 3
0x140210833  mov     dl, 1
0x140210835  jnb     short loc_14021083A
0x140210837  mov     dl, dil
0x14021083a  mov     r9, [r10+40h]
0x14021083e  lea     r8, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x140210845  mov     rcx, [r10+18h]
0x140210849  mov     dword ptr [rsp+60h+var_20], eax
0x14021084d  mov     [rsp+60h+var_28], r8
0x140210852  mov     r8b, 1
0x140210855  mov     [rsp+60h+var_30], 0Eh
0x14021085c  mov     dword ptr [rsp+60h+var_38], r13d
0x140210861  mov     byte ptr [rsp+60h+var_40], 3
0x140210866  call    WPP_RECORDER_AND_TRACE_SF_d
0x14021086b  mov     [rbp+arg_0], edi
0x14021086e  lea     rax, [rbp+arg_0]
0x140210872  mov     [rbp+var_10], rax
0x140210876  mov     eax, cs:dword_140197150
0x14021087c  cmp     eax, 5
0x14021087f  jbe     short loc_1402108CC
0x140210881  mov     rdx, 400000000000h
0x14021088b  lea     rcx, dword_140197150
0x140210892  call    _tlgKeywordOn
0x140210897  test    al, al
0x140210899  jz      short loc_1402108CC
0x14021089b  lea     rax, aBthportSys_0; "BthPort.sys"
0x1402108a2  mov     [rbp+arg_10], 2000800h
0x1402108aa  mov     [rbp+arg_8], rax
0x1402108ae  lea     rdx, byte_140189805
0x1402108b5  lea     rax, [rbp+arg_8]
0x1402108b9  mov     [rsp+60h+var_38], rax
0x1402108be  lea     rax, [rbp+arg_10]
0x1402108c2  mov     [rsp+60h+var_40], rax
0x1402108c7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1402108cc  lea     r9, BTHPORT_ETW_PROVIDER_Context
0x1402108d3  lea     r8, BTHPORT_ETW_PROVIDER_Context
0x1402108da  lea     rcx, BTHPORT_ETW_PROVIDER
0x1402108e1  call    McGenEventRegister_EtwRegister
0x1402108e6  mov     [rbp+arg_0], eax
0x1402108e9  test    eax, eax
0x1402108eb  jns     short loc_14021093D
0x1402108ed  mov     r10, cs:WPP_GLOBAL_Control
0x1402108f4  mov     ecx, [r10+2Ch]
0x1402108f8  test    r15b, cl
0x1402108fb  jz      short loc_140210906
0x1402108fd  cmp     byte ptr [r10+29h], 3
0x140210902  mov     dl, 1
0x140210904  jnb     short loc_140210909
0x140210906  mov     dl, dil
0x140210909  mov     r9, [r10+40h]
0x14021090d  mov     r8b, 1
0x140210910  mov     rcx, [r10+18h]
0x140210914  mov     dword ptr [rsp+60h+var_20], eax
0x140210918  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x14021091f  mov     [rsp+60h+var_28], rax
0x140210924  mov     [rsp+60h+var_30], 0Fh
0x14021092b  mov     dword ptr [rsp+60h+var_38], r13d
0x140210930  mov     byte ptr [rsp+60h+var_40], 3
0x140210935  call    WPP_RECORDER_AND_TRACE_SF_d
0x14021093a  mov     [rbp+arg_0], edi
0x14021093d  lea     rcx, dword_140197118; CallbackContext
0x140210944  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140210949  mov     [rbp+arg_0], eax
0x14021094c  test    eax, eax
0x14021094e  jns     short loc_1402109A0
0x140210950  mov     r10, cs:WPP_GLOBAL_Control
0x140210957  mov     ecx, [r10+2Ch]
0x14021095b  test    r15b, cl
0x14021095e  jz      short loc_140210969
0x140210960  cmp     byte ptr [r10+29h], 3
0x140210965  mov     dl, 1
0x140210967  jnb     short loc_14021096C
0x140210969  mov     dl, dil
0x14021096c  mov     r9, [r10+40h]
0x140210970  mov     r8b, 1
0x140210973  mov     rcx, [r10+18h]
0x140210977  mov     dword ptr [rsp+60h+var_20], eax
0x14021097b  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x140210982  mov     [rsp+60h+var_28], rax
0x140210987  mov     [rsp+60h+var_30], 10h
0x14021098e  mov     dword ptr [rsp+60h+var_38], r13d
0x140210993  mov     byte ptr [rsp+60h+var_40], 3
0x140210998  call    WPP_RECORDER_AND_TRACE_SF_d
0x14021099d  mov     [rbp+arg_0], edi
0x1402109a0  mov     rcx, rbx
0x1402109a3  call    InitializeTelemetryAssertsKM
0x1402109a8  mov     [rbp+arg_0], eax
0x1402109ab  test    eax, eax
0x1402109ad  jns     short loc_140210A01
0x1402109af  mov     r10, cs:WPP_GLOBAL_Control
0x1402109b6  mov     ecx, [r10+2Ch]
0x1402109ba  test    r15b, cl
0x1402109bd  jz      short loc_1402109C8
0x1402109bf  cmp     byte ptr [r10+29h], 3
0x1402109c4  mov     dl, 1
0x1402109c6  jnb     short loc_1402109CB
0x1402109c8  mov     dl, dil
0x1402109cb  mov     r9, [r10+40h]
0x1402109cf  lea     rbx, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x1402109d6  mov     rcx, [r10+18h]
0x1402109da  mov     r8b, 1
0x1402109dd  mov     dword ptr [rsp+60h+var_20], eax
0x1402109e1  mov     [rsp+60h+var_28], rbx
0x1402109e6  mov     [rsp+60h+var_30], 11h
0x1402109ed  mov     dword ptr [rsp+60h+var_38], r13d
0x1402109f2  mov     byte ptr [rsp+60h+var_40], 3
0x1402109f7  call    WPP_RECORDER_AND_TRACE_SF_d
0x1402109fc  mov     [rbp+arg_0], edi
0x1402109ff  jmp     short loc_140210A08
0x140210a01  lea     rbx, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x140210a08  call    ?Register@DevicePerfCounters@@SAXXZ; DevicePerfCounters::Register(void)
0x140210a0d  call    ?Register@RadioPerfCounters@@SAXXZ; RadioPerfCounters::Register(void)
0x140210a12  mov     edx, 8
0x140210a17  mov     r8d, 50485442h
0x140210a1d  lea     ecx, [rdx+38h]
0x140210a20  call    cs:__imp_ExAllocatePool2
0x140210a27  nop     dword ptr [rax+rax+00h]
0x140210a2c  mov     cs:?Globals@@3U_GLOBALS@@A, rax; _GLOBALS Globals
0x140210a33  test    rax, rax
0x140210a36  jz      loc_140210CA2
0x140210a3c  mov     rcx, rax; struct _SECURITY_DATABASE *
0x140210a3f  mov     dword ptr [rax], 1
  ... truncated ...
```
