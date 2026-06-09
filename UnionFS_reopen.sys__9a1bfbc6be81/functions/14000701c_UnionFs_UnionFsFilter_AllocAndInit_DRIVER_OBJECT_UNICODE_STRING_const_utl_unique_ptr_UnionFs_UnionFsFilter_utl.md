# UnionFs::UnionFsFilter::AllocAndInit(_DRIVER_OBJECT &,_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UnionFsFilter,utl::default_delete<UnionFs::UnionFsFilter>> &,UnionFs::StackEventTracer &)

- ea: `0x14000701c`
- end: `0x140008062`
- name: `?AllocAndInit@UnionFsFilter@UnionFs@@SAJAEAU_DRIVER_OBJECT@@AEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUnionFsFilter@UnionFs@@U?$default_delete@VUnionFsFilter@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `4166`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT Driver, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140079f58`

## callees

- `0x140001008`
- `0x140005820`
- `0x140006390`
- `0x14000701c`
- `0x14000bf40`
- `0x140010148`
- `0x1400102a8`
- `0x14001f978`
- `0x14003e10c`
- `0x140056a50`
- `0x140056afc`
- `0x14005b298`
- `0x140079c48`
- `0x140079d0c`
- `0x14007adc0`
- `0x14007af90`
- `0x1400a7ecc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007ff0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008030`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ff0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008030`
- `ntoskrnl!ExAllocatePool2` at `0x14000705d`
- `ntoskrnl!ExAllocatePool2` at `0x14000705d`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x140007651`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x140007651`
- `ntoskrnl!ZwClose` at `0x1400075ed`
- `ntoskrnl!ZwClose` at `0x1400075ed`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140007f7f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140007f7f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400076d5`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007732`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000778f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400077ec`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007849`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400078a6`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007903`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007960`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400079bd`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007a1a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007a77`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007ad4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007b31`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007b8e`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007beb`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007c48`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007ca5`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007d02`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007e17`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007e74`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007ed1`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400076d5`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007732`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14000778f`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400077ec`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007849`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400078a6`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007903`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007960`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400079bd`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007a1a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007a77`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007ad4`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007b31`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007b8e`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007beb`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007c48`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007ca5`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007d02`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007e17`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007e74`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140007ed1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140007161`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140007161`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140007623`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140007623`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400070d7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400070d7`
- `ntoskrnl!PsInitialSystemProcess` at `0x1400075f9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400074b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400074b4`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140007d4c`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140007d7a`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140007da8`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140007dd6`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140007d4c`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140007d7a`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140007da8`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140007dd6`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14000750a`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x140007fd7`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x140008012`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14000750a`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x140007fd7`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x140008012`
- `FLTMGR!FltCreateCommunicationPort` at `0x1400075b2`
- `FLTMGR!FltCreateCommunicationPort` at `0x1400075b2`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x1400074e3`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x1400074e3`
- `FLTMGR!FltGetRoutineAddress` at `0x1400071eb`
- `FLTMGR!FltGetRoutineAddress` at `0x140007274`
- `FLTMGR!FltGetRoutineAddress` at `0x1400072f0`
- `FLTMGR!FltGetRoutineAddress` at `0x14000736c`
- `FLTMGR!FltGetRoutineAddress` at `0x1400071eb`
- `FLTMGR!FltGetRoutineAddress` at `0x140007274`
- `FLTMGR!FltGetRoutineAddress` at `0x1400072f0`
- `FLTMGR!FltGetRoutineAddress` at `0x14000736c`
- `FLTMGR!FltRegisterFilter` at `0x14000746d`
- `FLTMGR!FltRegisterFilter` at `0x14000746d`

## string_xrefs

- `0x14000720e`: `Could not import FltQueryInformationByName2. Creates targeting layer files with symlink ancestors may fail.`
- `0x140007527`: `API: Building security descriptor`
- `0x1400075c4`: `API: Creating communication port`
- `0x140007635`: `API: Opening System process`
- `0x140007691`: `PUSH: loading boot config`
- `0x1400076e7`: `API: Initializing m_CreateContextLookaside`
- `0x140007744`: `API: Initializing m_RenameContextLookaside`
- `0x1400077a1`: `API: Initializing m_LinkContextLookaside`
- `0x1400077fe`: `API: Initializing m_SetFileSizeContextLookaside`
- `0x14000785b`: `API: Initializing m_QueryInfoContextLookaside`
- `0x1400078b8`: `API: Initializing m_QueryUsnContextLookaside`
- `0x140007915`: `API: Initializing m_CleanupContextLookaside`
- `0x140007972`: `API: Initializing m_IoSyncContextLookaside`
- `0x1400079cf`: `API: Initializing m_PathCacheListItemLookaside`
- `0x140007a2c`: `API: Initializing m_CollapseContextLookaside`
- `0x140007a89`: `API: Initializing m_EnumContextLookaside`
- `0x140007ae6`: `API: Initializing m_EnumBufferSmallLookaside`
- `0x140007b43`: `API: Initializing m_EnumBufferMidLookaside`
- `0x140007ba0`: `API: Initializing m_EnumBufferLargeLookaside`
- `0x140007bfd`: `API: Initializing m_PathCachePayloadNPLookaside`
- `0x140007c5a`: `API: Initializing m_PathCachePayloadLookaside`
- `0x140007cb7`: `API: Initializing m_PathTreeLookaside`
- `0x140007d14`: `API: Initializing m_PathTierNodeLookaside`
- `0x140007e29`: `API: Initializing m_OpenReparseListEntryLookaside`
- `0x140007e86`: `API: Initializing m_RequestOplockContextLookaside`
- `0x140007ee6`: `API: Initializing m_CheckOplockContextLookaside`
- `0x140007faa`: `PUSH: Setting up path cache manager`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::AllocAndInit(
        PDRIVER_OBJECT Driver,
        PCUNICODE_STRING SourceString,
        UnionFs::UnionFsFilter **a3,
        struct UnionFs::StackEventTracer *a4)
{
  UnionFs::UnionFsFilter **v4; // r12
  UnionFs::UnionFsFilter *Pool2; // rax
  __int64 v9; // rdi
  __int128 *UniqueUnicodeString; // rax
  struct _UNICODE_STRING *v11; // rdx
  __int128 v12; // xmm6
  NTSTATUS BootConfiguration; // ebx
  const char *v14; // rax
  __int64 v15; // r8
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  PWSTR *v31; // r15
  PWSTR Buffer; // r12
  const char *v33; // rax
  __int64 v34; // r8
  int v35; // edx
  void *v36; // rcx
  const char *v37; // rax
  __int64 v38; // r8
  int v39; // edx
  PSECURITY_DESCRIPTOR v41; // rcx
  UnionFs::UnionFsFilter *v42; // rbx
  const char *DisconnectNotifyCallback; // [rsp+28h] [rbp-D8h]
  PSECURITY_DESCRIPTOR v44; // [rsp+40h] [rbp-C0h] BYREF
  int v45; // [rsp+48h] [rbp-B8h] BYREF
  const char *v46; // [rsp+50h] [rbp-B0h] BYREF
  char v47[8]; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING Parameter; // [rsp+60h] [rbp-A0h] BYREF
  char v49; // [rsp+70h] [rbp-90h]
  _UNICODE_STRING SystemRoutineName; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  FLT_REGISTRATION Registration; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v54; // [rsp+138h] [rbp+38h]
  _UNKNOWN *retaddr; // [rsp+198h] [rbp+98h]

  v4 = a3;
  Pool2 = (UnionFs::UnionFsFilter *)ExAllocatePool2(66, 2816, 1852261973);
  if ( !Pool2 )
    return 3221225626LL;
  v9 = UnionFs::UnionFsFilter::UnionFsFilter(Pool2);
  if ( !v9 )
    return 3221225626LL;
  UniqueUnicodeString = (__int128 *)FsFltWil::MakeUniqueUnicodeString(
                                      &Parameter,
                                      SourceString->MaximumLength,
                                      1852261973);
  if ( (__int128 *)(v9 + 8) != UniqueUnicodeString )
  {
    v12 = *UniqueUnicodeString;
    *UniqueUnicodeString = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)(v9 + 8), v11);
    *(_OWORD *)(v9 + 8) = v12;
  }
  FsFltWil::Details::FreeUnicodeString(&Parameter, v11);
  if ( !*(_QWORD *)(v9 + 16) )
  {
    BootConfiguration = -1073741670;
LABEL_98:
    UnionFs::UnionFsFilter::~UnionFsFilter((UnionFs::UnionFsFilter *)v9);
    ExFreePoolWithTag((PVOID)v9, 0);
    return (unsigned int)BootConfiguration;
  }
  RtlCopyUnicodeString((PUNICODE_STRING)(v9 + 8), SourceString);
  InitializeTelemetryAssertsKMByDriverObject(Driver);
  *(_BYTE *)(v9 + 2784) = 1;
  BootConfiguration = TlgRegisterAggregateProvider();
  if ( BootConfiguration < 0 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("Could not register TraceLogging!");
    v14 = "API: Could not register TraceLogging";
    v15 = 0x22400010223LL;
LABEL_9:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)BootConfiguration,
      (int)a4,
      (struct UnionFs::StackEventTracer *)v15,
      (unsigned __int64)"UnionFs::UnionFsFilter::AllocAndInit",
      v14,
      DisconnectNotifyCallback);
    goto LABEL_98;
  }
  *(_BYTE *)(v9 + 2785) = 1;
  McGenEventRegister_EtwRegister();
  *(_BYTE *)(v9 + 2786) = 1;
  SystemRoutineName.Buffer = L"ObCloseHandleWithResult";
  *(_QWORD *)&SystemRoutineName.Length = 3145774;
  UnionFs::CloseHandleWithResult = (int (*)(void *, char, unsigned int, struct UnionFs::_OBJECT_CLOSE_RESULT *))MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( !UnionFs::CloseHandleWithResult && (unsigned int)dword_14009E178 > 3 )
  {
    v45 = 569;
    *(_QWORD *)&Parameter.Length = "Could not import ObCloseHandleWithResult. Shadow file objects not fully functional.";
    v46 = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
    *(_QWORD *)v47 = "UnionFs::UnionFsFilter::AllocAndInit";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)&word_14009546E,
      v17,
      v18,
      (__int64)&Parameter,
      (__int64)v47,
      (__int64)&v46,
      (__int64)&v45);
  }
  UnionFs::QueryInformationByName2 = (int (*)(struct _FLT_FILTER *, struct _FLT_INSTANCE *, struct _OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, void *, unsigned int, enum _FILE_INFORMATION_CLASS, unsigned int, struct _IO_DRIVER_CREATE_CONTEXT *))FltGetRoutineAddress("FltQueryInformationByName2");
  if ( !UnionFs::QueryInformationByName2 && (unsigned int)dword_14009E178 > 3 )
  {
    v45 = 578;
    v46 = "Could not import FltQueryInformationByName2. Creates targeting layer files with symlink ancestors may fail.";
    *(_QWORD *)&Parameter.Length = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
    *(_QWORD *)v47 = "UnionFs::UnionFsFilter::AllocAndInit";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)byte_1400955AD,
      v20,
      v21,
      (__int64)&v46,
      (__int64)v47,
      (__int64)&Parameter,
      (__int64)&v45);
  }
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    UnionFs::Flt_UpperOplockFsctrl = (enum _FLT_PREOP_CALLBACK_STATUS (*)(void **, struct _FLT_CALLBACK_DATA *, unsigned int, unsigned int, unsigned int))FltGetRoutineAddress("FltUpperOplockFsctrl");
    if ( !UnionFs::Flt_UpperOplockFsctrl && (unsigned int)dword_14009E178 > 3 )
    {
      v45 = 594;
      v46 = "Could not import FltUpperOplockFsctrl. Cannot request oplocks on scratch-backed SFOs.";
      *(_QWORD *)&Parameter.Length = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
      *(_QWORD *)v47 = "UnionFs::UnionFsFilter::AllocAndInit";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1400953D5,
        v23,
        v24,
        (__int64)&v46,
        (__int64)v47,
        (__int64)&Parameter,
        (__int64)&v45);
    }
    UnionFs::Flt_CheckUpperOplock = (int (*)(void **, unsigned int, void *, void (*)(struct _FLT_CALLBACK_DATA *, void *), void (*)(struct _FLT_CALLBACK_DATA *, void *), unsigned int))FltGetRoutineAddress("FltCheckUpperOplock");
    if ( !UnionFs::Flt_CheckUpperOplock && (unsigned int)dword_14009E178 > 3 )
    {
      v45 = 603;
      v46 = "Could not import FltCheckUpperOplock. Cannot check for oplocks on scratch-backed SFOs.";
      *(_QWORD *)&Parameter.Length = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
      *(_QWORD *)v47 = "UnionFs::UnionFsFilter::AllocAndInit";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v25,
        (unsigned int)&word_140095856,
        v26,
        v27,
        (__int64)&v46,
        (__int64)v47,
        (__int64)&Parameter,
        (__int64)&v45);
    }
    UnionFs::Flt_OplockBreakH2 = (enum _FLT_PREOP_CALLBACK_STATUS (*)(void **, struct _FLT_CALLBACK_DATA *, unsigned int, void *, void (*)(struct _FLT_CALLBACK_DATA *, void *), void (*)(struct _FLT_CALLBACK_DATA *, void *), unsigned int *, unsigned __int16 *))FltGetRoutineAddress("FltOplockBreakH2");
    if ( !UnionFs::Flt_OplockBreakH2 && (unsigned int)dword_14009E178 > 3 )
    {
      v45 = 612;
      v46 = "Could not import FltOplockBreakH2. Reduced functionality for breaking H oplocks.";
      *(_QWORD *)&Parameter.Length = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
      *(_QWORD *)v47 = "UnionFs::UnionFsFilter::AllocAndInit";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v28,
        (unsigned int)&byte_14009574F,
        v29,
        v30,
        (__int64)&v46,
        (__int64)v47,
        (__int64)&Parameter,
        (__int64)&v45);
    }
  }
  *(_DWORD *)&Registration.Size = 33751152;
  v54 = 0;
  Registration.Flags = 5;
  Registration.ContextRegistration = (const FLT_CONTEXT_REGISTRATION *)&UnionFs::ContextRegistration;
  Registration.OperationRegistration = (const FLT_OPERATION_REGISTRATION *)&qword_14007E1C0;
  Registration.FilterUnloadCallback = (PFLT_FILTER_UNLOAD_CALLBACK)UnionFs::UnionFsFilter::UnloadFilter;
  Registration.InstanceSetupCallback = (PFLT_INSTANCE_SETUP_CALLBACK)UnionFs::UnionFsFilter::InstanceSetup;
  Registration.InstanceQueryTeardownCallback = (PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK)UnionFs::UnionFsFilter::InstanceQueryTeardown;
  Registration.InstanceTeardownStartCallback = (PFLT_INSTANCE_TEARDOWN_CALLBACK)UnionFs::UnionFsFilter::InstanceTeardownStart;
  Registration.InstanceTeardownCompleteCallback = (PFLT_INSTANCE_TEARDOWN_CALLBACK)UnionFs::UnionFsFilter::InstanceTeardownComplete;
  Registration.GenerateFileNameCallback = (PFLT_GENERATE_FILE_NAME)UnionFs::UnionFsFilter::GenerateFileNameCallback;
  Registration.NormalizeNameComponentExCallback = (PFLT_NORMALIZE_NAME_COMPONENT_EX)UnionFs::UnionFsFilter::NormalizeNameComponentExCallback;
  memset(&Registration.NormalizeNameComponentCallback, 0, 24);
  BootConfiguration = FltRegisterFilter(Driver, &Registration, (PFLT_FILTER *)v9);
  if ( BootConfiguration < 0 )
  {
    v14 = "API: FltRegisterFilter";
    v15 = 0x200010284LL;
    goto LABEL_9;
  }
  *(_BYTE *)(v9 + 2787) = 1;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\UnionfsPort");
  v44 = 0;
  *(_QWORD *)&Parameter.Length = &v44;
  Parameter.Buffer = 0;
  v49 = 1;
  BootConfiguration = FltBuildDefaultSecurityDescriptor((PSECURITY_DESCRIPTOR *)&Parameter.Buffer, 0x1F0001u);
  if ( v49 )
  {
    v31 = *(PWSTR **)&Parameter.Length;
    Buffer = Parameter.Buffer;
    if ( **(_QWORD **)&Parameter.Length )
      FltFreeSecurityDescriptor(**(PSECURITY_DESCRIPTOR **)&Parameter.Length);
    *v31 = Buffer;
    v4 = a3;
  }
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Building security descriptor";
    v34 = 0x4200010291LL;
LABEL_34:
    v35 = (int)a4;
LABEL_35:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)BootConfiguration,
      v35,
      (struct UnionFs::StackEventTracer *)v34,
      (unsigned __int64)"UnionFs::UnionFsFilter::AllocAndInit",
      v33,
      DisconnectNotifyCallback);
    goto LABEL_96;
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityDescriptor = v44;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.SecurityQualityOfService = 0;
  BootConfiguration = FltCreateCommunicationPort(
                        *(PFLT_FILTER *)v9,
                        (PFLT_PORT *)(v9 + 24),
                        &ObjectAttributes,
                        0,
                        UnionFs::UnionFsFilter::PortConnect,
                        UnionFs::UnionFsFilter::PortDisconnect,
                        UnionFs::UnionFsFilter::PortMessage,
                        1000);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Creating communication port";
    v34 = 0x43000102A0LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2788) = 1;
  v36 = *(void **)(v9 + 104);
  if ( v36 )
    ZwClose(v36);
  *(_QWORD *)(v9 + 104) = 0;
  BootConfiguration = ObOpenObjectByPointer(PsInitialSystemProcess, 0x200u, 0, 0x20000u, 0, 0, (PHANDLE)(v9 + 104));
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Opening System process";
    v34 = 0x23B000102AELL;
    goto LABEL_34;
  }
  BootConfiguration = PsAllocSiloContextSlot(0, v9 + 112);
  v35 = (int)a4;
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Registering silo context slot";
    v34 = 0x65A000102B4LL;
    goto LABEL_35;
  }
  *(_BYTE *)(v9 + 2789) = 1;
  BootConfiguration = UnionFs::UnionFsFilter::LoadBootConfiguration((UnionFs::UnionFsFilter *)v9, a4);
  if ( BootConfiguration < 0 )
  {
    v37 = "PUSH: loading boot config";
    v38 = 0xBA000102BBLL;
LABEL_94:
    v39 = (int)a4;
    goto LABEL_95;
  }
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 224),
                        0,
                        0,
                        PagedPool,
                        0,
                        0xD0u,
                        0x63634655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_CreateContextLookaside";
    v34 = 0xFD000102C8LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2790) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 320),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x188u,
                        0x63634655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_RenameContextLookaside";
    v34 = 0x151000102D7LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2791) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 416),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x18u,
                        0x63634655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_LinkContextLookaside";
    v34 = 0x3CF000102E6LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2792) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 512),
                        0,
                        0,
                        (POOL_TYPE)512,
                        0,
                        0x90u,
                        0x63634655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_SetFileSizeContextLookaside";
    v34 = 0x32F000102F5LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2793) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 608),
                        0,
                        0,
                        PagedPool,
                        0,
                        0xA0u,
                        0x63634655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_QueryInfoContextLookaside";
    v34 = 0x62C00010304LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2794) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 704),
                        0,
                        0,
                        PagedPool,
                        0,
                        0xA8u,
                        0x63634655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_QueryUsnContextLookaside";
    v34 = 0x6A800010313LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2795) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 800),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x20u,
                        0x63634655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_CleanupContextLookaside";
    v34 = 0x2E000010322LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2796) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 896),
                        0,
                        0,
                        (POOL_TYPE)512,
                        0,
                        0x88u,
                        0x6F694655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_IoSyncContextLookaside";
    v34 = 0x4A700010331LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2797) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 992),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x40u,
                        0x63704655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_PathCacheListItemLookaside";
    v34 = 0x4D900010340LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2798) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 1088),
                        0,
                        0,
                        (POOL_TYPE)512,
                        0,
                        0x30u,
                        0x63634655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_CollapseContextLookaside";
    v34 = 0x22300010350LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2799) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 1184),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x50u,
                        0x6E654655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_EnumContextLookaside";
    v34 = 0x1A000010360LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2800) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 1280),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x27Cu,
                        0x6E654655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_EnumBufferSmallLookaside";
    v34 = 0x1A10001036ELL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2801) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 1376),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x1014u,
                        0x6E654655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_EnumBufferMidLookaside";
    v34 = 0x1A20001037CLL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2802) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 1472),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x10014u,
                        0x6E654655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_EnumBufferLargeLookaside";
    v34 = 0x1A30001038ALL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2803) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 1568),
                        0,
                        0,
                        (POOL_TYPE)512,
                        0,
                        0x120u,
                        0x63704655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_PathCachePayloadNPLookaside";
    v34 = 0x10300010399LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2804) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 1664),
                        0,
                        0,
                        PagedPool,
                        0,
                        0xD8u,
                        0x63704655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_PathCachePayloadLookaside";
    v34 = 0x204000103A8LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2805) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 1760),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x20u,
                        0x74704655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_PathTreeLookaside";
    v34 = 0x205000103B8LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2806) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 1856),
                        0,
                        0,
                        PagedPool,
                        0,
                        0xA0u,
                        0x6E704655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_PathTierNodeLookaside";
    v34 = 0x206000103C6LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2807) = 1;
  FltInitExtraCreateParameterLookasideList(*(PFLT_FILTER *)v9, (PVOID)(v9 + 1984), 0, 0x58u, 0x63614655u);
  *(_BYTE *)(v9 + 2808) = 1;
  FltInitExtraCreateParameterLookasideList(*(PFLT_FILTER *)v9, (PVOID)(v9 + 2112), 0, 0x10u, 0x726F4655u);
  *(_BYTE *)(v9 + 2809) = 1;
  FltInitExtraCreateParameterLookasideList(*(PFLT_FILTER *)v9, (PVOID)(v9 + 2240), 0, 0xC8u, 0x63714655u);
  *(_BYTE *)(v9 + 2810) = 1;
  FltInitExtraCreateParameterLookasideList(*(PFLT_FILTER *)v9, (PVOID)(v9 + 2368), 0, 0x14u, 0x6B6F4655u);
  *(_BYTE *)(v9 + 2811) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 2496),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x30u,
                        0x6E704655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_OpenReparseListEntryLookaside";
    v34 = 0x25A000103F4LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2812) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 2592),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x30u,
                        0x706F4655u,
                        0);
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_RequestOplockContextLookaside";
    v34 = 0x6B000010402LL;
    goto LABEL_34;
  }
  *(_BYTE *)(v9 + 2813) = 1;
  BootConfiguration = ExInitializeLookasideListEx(
                        (PLOOKASIDE_LIST_EX)(v9 + 2688),
                        0,
                        0,
                        PagedPool,
                        0,
                        0x10u,
                        0x636F4655u,
                        0);
  v35 = (int)a4;
  if ( BootConfiguration < 0 )
  {
    v33 = "API: Initializing m_CheckOplockContextLookaside";
    v34 = 0x70500010410LL;
    goto LABEL_35;
  }
  *(_BYTE *)(v9 + 2814) = 1;
  BootConfiguration = UnionFs::UfsTombstoneManager::AllocAndInit(v9 + 120, a4);
  v39 = (int)a4;
  if ( BootConfiguration < 0 )
  {
    v37 = "PUSH: Setting up tombstone persistence manager";
    v38 = 0x32600010418LL;
LABEL_95:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)BootConfiguration,
      v39,
      (struct UnionFs::StackEventTracer *)v38,
      (unsigned __int64)"UnionFs::UnionFsFilter::AllocAndInit",
      v37,
      DisconnectNotifyCallback);
LABEL_96:
    if ( v44 )
      FltFreeSecurityDescriptor(v44);
    goto LABEL_98;
  }
  BootConfiguration = UnionFs::UfsEaManager::AllocAndInit(v9 + 128, a4);
  if ( BootConfiguration < 0 )
  {
    v37 = "PUSH: Setting up EA persistence manager";
    v38 = 0x6780001041ELL;
    goto LABEL_94;
  }
  *(_QWORD *)&Parameter.Length = retaddr;
  Parameter.Buffer = 0;
  KeExpandKernelStackAndCalloutEx(
    UnionFs::UnionFsFilter::MeasureExpandedStackCalloutDepthCallout,
    &Parameter,
    0x6000u,
    0,
    0);
  *(_DWORD *)(v9 + 196) = Parameter.Buffer;
  BootConfiguration = UnionFs::UfsPathCacheManager::AllocAndInit(SourceString, v9 + 96, a4);
  if ( BootConfiguration < 0 )
  {
    v37 = "PUSH: Setting up path cache manager";
    v38 = 0x41200010428LL;
    goto LABEL_94;
  }
  v41 = v44;
  v42 = *v4;
  *v4 = (UnionFs::UnionFsFilter *)v9;
  if ( v41 )
    FltFreeSecurityDescriptor(v41);
  if ( v42 )
  {
    UnionFs::UnionFsFilter::~UnionFsFilter(v42);
    ExFreePoolWithTag(v42, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14000701c  mov     rax, rsp
0x14000701f  mov     [rax+18h], r8
0x140007023  push    rbp
0x140007024  push    rbx
0x140007025  push    rsi
0x140007026  push    rdi
0x140007027  push    r12
0x140007029  push    r13
0x14000702b  push    r14
0x14000702d  push    r15
0x14000702f  lea     rbp, [rsp-58h]
0x140007034  sub     rsp, 158h
0x14000703b  mov     r12, r8
0x14000703e  movaps  xmmword ptr [rax-58h], xmm6
0x140007042  mov     r13, rdx
0x140007045  mov     r15, rcx
0x140007048  mov     ebx, 6E674655h
0x14000704d  mov     edx, 0B00h
0x140007052  mov     r8d, ebx
0x140007055  mov     ecx, 42h ; 'B'
0x14000705a  mov     r14, r9
0x14000705d  call    cs:__imp_ExAllocatePool2
0x140007064  nop     dword ptr [rax+rax+00h]
0x140007069  test    rax, rax
0x14000706c  jz      loc_140008040
0x140007072  mov     rcx, rax; this
0x140007075  call    ??0UnionFsFilter@UnionFs@@AEAA@XZ; UnionFs::UnionFsFilter::UnionFsFilter(void)
0x14000707a  mov     rdi, rax
0x14000707d  test    rax, rax
0x140007080  jz      loc_140008040
0x140007086  movzx   edx, word ptr [r13+2]
0x14000708b  lea     rcx, [rsp+190h+Parameter]
0x140007090  mov     r8d, ebx
0x140007093  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140007098  lea     rbx, [rdi+8]
0x14000709c  cmp     rbx, rax
0x14000709f  jz      short loc_1400070B6
0x1400070a1  movups  xmm6, xmmword ptr [rax]
0x1400070a4  mov     rcx, rbx; UnicodeString
0x1400070a7  xorps   xmm0, xmm0
0x1400070aa  movups  xmmword ptr [rax], xmm0
0x1400070ad  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400070b2  movdqu  xmmword ptr [rbx], xmm6
0x1400070b6  lea     rcx, [rsp+190h+Parameter]; UnicodeString
0x1400070bb  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400070c0  cmp     qword ptr [rdi+10h], 0
0x1400070c5  jnz     short loc_1400070D1
0x1400070c7  mov     ebx, 0C000009Ah
0x1400070cc  jmp     loc_140007FE3
0x1400070d1  mov     rdx, r13; SourceString
0x1400070d4  mov     rcx, rbx; DestinationString
0x1400070d7  call    cs:__imp_RtlCopyUnicodeString
0x1400070de  nop     dword ptr [rax+rax+00h]
0x1400070e3  mov     rcx, r15
0x1400070e6  call    InitializeTelemetryAssertsKMByDriverObject
0x1400070eb  mov     byte ptr [rdi+0AE0h], 1
0x1400070f2  call    TlgRegisterAggregateProvider
0x1400070f7  mov     ebx, eax
0x1400070f9  test    eax, eax
0x1400070fb  jns     short loc_140007135
0x1400070fd  lea     rcx, aCouldNotRegist; "Could not register TraceLogging!"
0x140007104  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140007109  lea     rax, aApiCouldNotReg; "API: Could not register TraceLogging"
0x140007110  mov     r8, 22400010223h; struct UnionFs::StackEventTracer *
0x14000711a  lea     r9, aUnionfsUnionfs_35; "UnionFs::UnionFsFilter::AllocAndInit"
0x140007121  mov     rdx, r14; int
0x140007124  mov     [rsp+190h+ConnectNotifyCallback], rax; char *
0x140007129  mov     ecx, ebx; this
0x14000712b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140007130  jmp     loc_140007FE3
0x140007135  mov     byte ptr [rdi+0AE1h], 1
0x14000713c  call    McGenEventRegister_EtwRegister
0x140007141  mov     byte ptr [rdi+0AE2h], 1
0x140007148  lea     rax, aObclosehandlew; "ObCloseHandleWithResult"
0x14000714f  lea     rcx, [rsp+190h+SystemRoutineName]; SystemRoutineName
0x140007154  mov     [rbp+90h+SystemRoutineName.Buffer], rax
0x140007158  mov     qword ptr [rsp+190h+SystemRoutineName.Length], 30002Eh
0x140007161  call    cs:__imp_MmGetSystemRoutineAddress
0x140007168  nop     dword ptr [rax+rax+00h]
0x14000716d  mov     cs:?CloseHandleWithResult@UnionFs@@3P6AJPEAXDKPEAU_OBJECT_CLOSE_RESULT@1@@ZEA, rax; long (*UnionFs::CloseHandleWithResult)(void *,char,ulong,UnionFs::_OBJECT_CLOSE_RESULT *)
0x140007174  lea     rsi, aUnionfsUnionfs_35; "UnionFs::UnionFsFilter::AllocAndInit"
0x14000717b  lea     rbx, aOnecoreBaseFsU_4; "onecore\\base\\fs\\unionfs\\sys\\unionf"...
0x140007182  test    rax, rax
0x140007185  jnz     short loc_1400071E4
0x140007187  mov     eax, cs:dword_14009E178
0x14000718d  cmp     eax, 3
0x140007190  jbe     short loc_1400071E4
0x140007192  lea     rax, aCouldNotImport_3; "Could not import ObCloseHandleWithResul"...
0x140007199  mov     [rsp+190h+var_148], 239h
0x1400071a1  mov     [rsp+190h+Parameter], rax
0x1400071a6  lea     rdx, word_14009546E
0x1400071ad  lea     rax, [rsp+190h+var_148]
0x1400071b2  mov     [rsp+190h+var_140], rbx
0x1400071b7  mov     qword ptr [rsp+190h+MaxConnections], rax
0x1400071bc  lea     rax, [rsp+190h+var_140]
0x1400071c1  mov     [rsp+190h+MessageNotifyCallback], rax
0x1400071c6  lea     rax, [rsp+190h+var_138]
0x1400071cb  mov     [rsp+190h+DisconnectNotifyCallback], rax
0x1400071d0  lea     rax, [rsp+190h+Parameter]
0x1400071d5  mov     [rsp+190h+ConnectNotifyCallback], rax
0x1400071da  mov     qword ptr [rsp+190h+var_138], rsi
0x1400071df  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400071e4  lea     rcx, FltMgrRoutineName; "FltQueryInformationByName2"
0x1400071eb  call    cs:__imp_FltGetRoutineAddress
0x1400071f2  nop     dword ptr [rax+rax+00h]
0x1400071f7  mov     cs:?QueryInformationByName2@UnionFs@@3P6AJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAXKW4_FILE_INFORMATION_CLASS@@KPEAU_IO_DRIVER_CREATE_CONTEXT@@@ZEA, rax; long (*UnionFs::QueryInformationByName2)(_FLT_FILTER *,_FLT_INSTANCE *,_OBJECT_ATTRIBUTES *,_IO_STATUS_BLOCK *,void *,ulong,_FILE_INFORMATION_CLASS,ulong,_IO_DRIVER_CREATE_CONTEXT *)
0x1400071fe  test    rax, rax
0x140007201  jnz     short loc_140007260
0x140007203  mov     eax, cs:dword_14009E178
0x140007209  cmp     eax, 3
0x14000720c  jbe     short loc_140007260
0x14000720e  lea     rax, aCouldNotImport_0; "Could not import FltQueryInformationByN"...
0x140007215  mov     [rsp+190h+var_148], 242h
0x14000721d  mov     [rsp+190h+var_140], rax
0x140007222  lea     rdx, byte_1400955AD
0x140007229  lea     rax, [rsp+190h+var_148]
0x14000722e  mov     [rsp+190h+Parameter], rbx
0x140007233  mov     qword ptr [rsp+190h+MaxConnections], rax
0x140007238  lea     rax, [rsp+190h+Parameter]
0x14000723d  mov     [rsp+190h+MessageNotifyCallback], rax
0x140007242  lea     rax, [rsp+190h+var_138]
0x140007247  mov     [rsp+190h+DisconnectNotifyCallback], rax
0x14000724c  lea     rax, [rsp+190h+var_140]
0x140007251  mov     [rsp+190h+ConnectNotifyCallback], rax
0x140007256  mov     qword ptr [rsp+190h+var_138], rsi
0x14000725b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140007260  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140007265  test    eax, eax
0x140007267  jz      loc_1400073E1
0x14000726d  lea     rcx, aFltupperoplock; "FltUpperOplockFsctrl"
0x140007274  call    cs:__imp_FltGetRoutineAddress
0x14000727b  nop     dword ptr [rax+rax+00h]
0x140007280  mov     cs:?Flt_UpperOplockFsctrl@UnionFs@@3P6A?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAPEAXPEAU_FLT_CALLBACK_DATA@@KKK@ZEA, rax; _FLT_PREOP_CALLBACK_STATUS (*UnionFs::Flt_UpperOplockFsctrl)(void * *,_FLT_CALLBACK_DATA *,ulong,ulong,ulong)
0x140007287  test    rax, rax
0x14000728a  jnz     short loc_1400072E9
0x14000728c  mov     eax, cs:dword_14009E178
0x140007292  cmp     eax, 3
0x140007295  jbe     short loc_1400072E9
0x140007297  lea     rax, aCouldNotImport_2; "Could not import FltUpperOplockFsctrl. "...
0x14000729e  mov     [rsp+190h+var_148], 252h
0x1400072a6  mov     [rsp+190h+var_140], rax
0x1400072ab  lea     rdx, byte_1400953D5
0x1400072b2  lea     rax, [rsp+190h+var_148]
0x1400072b7  mov     [rsp+190h+Parameter], rbx
0x1400072bc  mov     qword ptr [rsp+190h+MaxConnections], rax
0x1400072c1  lea     rax, [rsp+190h+Parameter]
0x1400072c6  mov     [rsp+190h+MessageNotifyCallback], rax
0x1400072cb  lea     rax, [rsp+190h+var_138]
0x1400072d0  mov     [rsp+190h+DisconnectNotifyCallback], rax
0x1400072d5  lea     rax, [rsp+190h+var_140]
0x1400072da  mov     [rsp+190h+ConnectNotifyCallback], rax
0x1400072df  mov     qword ptr [rsp+190h+var_138], rsi
0x1400072e4  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400072e9  lea     rcx, aFltcheckuppero; "FltCheckUpperOplock"
0x1400072f0  call    cs:__imp_FltGetRoutineAddress
0x1400072f7  nop     dword ptr [rax+rax+00h]
0x1400072fc  mov     cs:?Flt_CheckUpperOplock@UnionFs@@3P6AJPEAPEAXKPEAXP6AXPEAU_FLT_CALLBACK_DATA@@1@Z3K@ZEA, rax; long (*UnionFs::Flt_CheckUpperOplock)(void * *,ulong,void *,void (*)(_FLT_CALLBACK_DATA *,void *),void (*)(_FLT_CALLBACK_DATA *,void *),ulong)
0x140007303  test    rax, rax
0x140007306  jnz     short loc_140007365
0x140007308  mov     eax, cs:dword_14009E178
0x14000730e  cmp     eax, 3
0x140007311  jbe     short loc_140007365
0x140007313  lea     rax, aCouldNotImport; "Could not import FltCheckUpperOplock. C"...
0x14000731a  mov     [rsp+190h+var_148], 25Bh
0x140007322  mov     [rsp+190h+var_140], rax
0x140007327  lea     rdx, word_140095856
0x14000732e  lea     rax, [rsp+190h+var_148]
0x140007333  mov     [rsp+190h+Parameter], rbx
0x140007338  mov     qword ptr [rsp+190h+MaxConnections], rax
0x14000733d  lea     rax, [rsp+190h+Parameter]
0x140007342  mov     [rsp+190h+MessageNotifyCallback], rax
0x140007347  lea     rax, [rsp+190h+var_138]
0x14000734c  mov     [rsp+190h+DisconnectNotifyCallback], rax
0x140007351  lea     rax, [rsp+190h+var_140]
0x140007356  mov     [rsp+190h+ConnectNotifyCallback], rax
0x14000735b  mov     qword ptr [rsp+190h+var_138], rsi
0x140007360  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140007365  lea     rcx, aFltoplockbreak; "FltOplockBreakH2"
0x14000736c  call    cs:__imp_FltGetRoutineAddress
0x140007373  nop     dword ptr [rax+rax+00h]
0x140007378  mov     cs:?Flt_OplockBreakH2@UnionFs@@3P6A?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAPEAXPEAU_FLT_CALLBACK_DATA@@KPEAXP6AX12@Z3PEAKPEAG@ZEA, rax; _FLT_PREOP_CALLBACK_STATUS (*UnionFs::Flt_OplockBreakH2)(void * *,_FLT_CALLBACK_DATA *,ulong,void *,void (*)(_FLT_CALLBACK_DATA *,void *),void (*)(_FLT_CALLBACK_DATA *,void *),ulong *,ushort *)
0x14000737f  test    rax, rax
0x140007382  jnz     short loc_1400073E1
0x140007384  mov     eax, cs:dword_14009E178
0x14000738a  cmp     eax, 3
0x14000738d  jbe     short loc_1400073E1
0x14000738f  lea     rax, aCouldNotImport_1; "Could not import FltOplockBreakH2. Redu"...
0x140007396  mov     [rsp+190h+var_148], 264h
0x14000739e  mov     [rsp+190h+var_140], rax
0x1400073a3  lea     rdx, byte_14009574F
0x1400073aa  lea     rax, [rsp+190h+var_148]
0x1400073af  mov     [rsp+190h+Parameter], rbx
0x1400073b4  mov     qword ptr [rsp+190h+MaxConnections], rax
0x1400073b9  lea     rax, [rsp+190h+Parameter]
0x1400073be  mov     [rsp+190h+MessageNotifyCallback], rax
0x1400073c3  lea     rax, [rsp+190h+var_138]
0x1400073c8  mov     [rsp+190h+DisconnectNotifyCallback], rax; char *
0x1400073cd  lea     rax, [rsp+190h+var_140]
0x1400073d2  mov     [rsp+190h+ConnectNotifyCallback], rax
0x1400073d7  mov     qword ptr [rsp+190h+var_138], rsi
0x1400073dc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400073e1  xor     eax, eax
0x1400073e3  mov     dword ptr [rbp+90h+Registration.Size], 2030070h
0x1400073ea  mov     [rbp+90h+Registration.TransactionNotificationCallback], rax
0x1400073ee  lea     rdx, [rbp+90h+Registration]; Registration
0x1400073f2  mov     [rbp+90h+var_58], rax
0x1400073f6  xorps   xmm0, xmm0
0x1400073f9  lea     rax, ?ContextRegistration@UnionFs@@3PAU_FLT_CONTEXT_REGISTRATION@@A; _FLT_CONTEXT_REGISTRATION near * UnionFs::ContextRegistration
0x140007400  mov     [rbp+90h+Registration.Flags], 5
0x140007407  mov     [rbp+90h+Registration.ContextRegistration], rax
0x14000740b  mov     r8, rdi; RetFilter
0x14000740e  lea     rax, qword_14007E1C0
0x140007415  mov     rcx, r15; Driver
0x140007418  mov     [rbp+90h+Registration.OperationRegistration], rax
0x14000741c  lea     rax, ?UnloadFilter@UnionFsFilter@UnionFs@@SAJK@Z; UnionFs::UnionFsFilter::UnloadFilter(ulong)
0x140007423  mov     [rbp+90h+Registration.FilterUnloadCallback], rax
0x140007427  lea     rax, ?InstanceSetup@UnionFsFilter@UnionFs@@SAJPEBU_FLT_RELATED_OBJECTS@@KKW4_FLT_FILESYSTEM_TYPE@@@Z; UnionFs::UnionFsFilter::InstanceSetup(_FLT_RELATED_OBJECTS const *,ulong,ulong,_FLT_FILESYSTEM_TYPE)
0x14000742e  mov     [rbp+90h+Registration.InstanceSetupCallback], rax
0x140007432  lea     rax, ?InstanceQueryTeardown@UnionFsFilter@UnionFs@@SAJPEBU_FLT_RELATED_OBJECTS@@K@Z; UnionFs::UnionFsFilter::InstanceQueryTeardown(_FLT_RELATED_OBJECTS const *,ulong)
0x140007439  mov     [rbp+90h+Registration.InstanceQueryTeardownCallback], rax
0x14000743d  lea     rax, ?InstanceTeardownStart@UnionFsFilter@UnionFs@@SAXPEBU_FLT_RELATED_OBJECTS@@K@Z; UnionFs::UnionFsFilter::InstanceTeardownStart(_FLT_RELATED_OBJECTS const *,ulong)
0x140007444  mov     [rbp+90h+Registration.InstanceTeardownStartCallback], rax
0x140007448  lea     rax, ?InstanceTeardownComplete@UnionFsFilter@UnionFs@@SAXPEBU_FLT_RELATED_OBJECTS@@K@Z; UnionFs::UnionFsFilter::InstanceTeardownComplete(_FLT_RELATED_OBJECTS const *,ulong)
0x14000744f  mov     [rbp+90h+Registration.InstanceTeardownCompleteCallback], rax
0x140007453  lea     rax, ?GenerateFileNameCallback@UnionFsFilter@UnionFs@@SAJPEAU_FLT_INSTANCE@@PEAU_FILE_OBJECT@@PEAU_FLT_CALLBACK_DATA@@KPEAEPEAU_FLT_NAME_CONTROL@@@Z; UnionFs::UnionFsFilter::GenerateFileNameCallback(_FLT_INSTANCE *,_FILE_OBJECT *,_FLT_CALLBACK_DATA *,ulong,uchar *,_FLT_NAME_CONTROL *)
0x14000745a  mov     [rbp+90h+Registration.GenerateFileNameCallback], rax
0x14000745e  lea     rax, ?NormalizeNameComponentExCallback@UnionFsFilter@UnionFs@@SAJPEAU_FLT_INSTANCE@@PEAU_FILE_OBJECT@@PEBU_UNICODE_STRING@@G2PEAU_FILE_NAMES_INFORMATION@@KKPEAPEAX@Z; UnionFs::UnionFsFilter::NormalizeNameComponentExCallback(_FLT_INSTANCE *,_FILE_OBJECT *,_UNICODE_STRING const *,ushort,_UNICODE_STRING const *,_FILE_NAMES_INFORMATION *,ulong,ulong,void * *)
0x140007465  mov     [rbp+90h+Registration.NormalizeNameComponentExCallback], rax
0x140007469  movups  xmmword ptr [rbp+90h+Registration.NormalizeNameComponentCallback], xmm0
0x14000746d  call    cs:__imp_FltRegisterFilter
0x140007474  nop     dword ptr [rax+rax+00h]
0x140007479  xor     r15d, r15d
0x14000747c  mov     ebx, eax
0x14000747e  test    eax, eax
0x140007480  jns     short loc_14000749B
0x140007482  lea     rax, aApiFltregister; "API: FltRegisterFilter"
0x140007489  mov     r9, rsi
0x14000748c  mov     r8, 200010284h
0x140007496  jmp     loc_140007121
0x14000749b  xorps   xmm0, xmm0
0x14000749e  mov     byte ptr [rdi+0AE3h], 1
0x1400074a5  lea     rdx, SourceString; "\\UnionfsPort"
0x1400074ac  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1400074b0  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x1400074b4  call    cs:__imp_RtlInitUnicodeString
0x1400074bb  nop     dword ptr [rax+rax+00h]
0x1400074c0  lea     rax, [rsp+190h+var_150]
0x1400074c5  mov     [rsp+190h+var_150], r15
0x1400074ca  mov     edx, 1F0001h; DesiredAccess
0x1400074cf  mov     [rsp+190h+Parameter], rax
0x1400074d4  lea     rcx, [rsp+190h+SecurityDescriptor]; SecurityDescriptor
0x1400074d9  mov     [rsp+190h+SecurityDescriptor], r15
0x1400074de  mov     [rsp+190h+var_120], 1
0x1400074e3  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x1400074ea  nop     dword ptr [rax+rax+00h]
0x1400074ef  mov     ebx, eax
0x1400074f1  cmp     [rsp+190h+var_120], r15b
0x1400074f6  jz      short loc_140007523
0x1400074f8  mov     r15, [rsp+190h+Parameter]
0x1400074fd  mov     r12, [rsp+190h+SecurityDescriptor]
0x140007502  mov     rcx, [r15]; SecurityDescriptor
0x140007505  test    rcx, rcx
0x140007508  jz      short loc_140007516
0x14000750a  call    cs:__imp_FltFreeSecurityDescriptor
0x140007511  nop     dword ptr [rax+rax+00h]
0x140007516  mov     [r15], r12
0x140007519  xor     r15d, r15d
0x14000751c  mov     r12, [rbp+90h+arg_10]
0x140007523  test    ebx, ebx
0x140007525  jns     short loc_14000754F
0x140007527  lea     rax, aApiBuildingSec; "API: Building security descriptor"
0x14000752e  mov     r8, 4200010291h; struct UnionFs::StackEventTracer *
0x140007538  mov     rdx, r14; int
0x14000753b  mov     r9, rsi; unsigned __int64
0x14000753e  mov     [rsp+190h+ConnectNotifyCallback], rax; char *
0x140007543  mov     ecx, ebx; this
0x140007545  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000754a  jmp     loc_140007FCD
0x14000754f  mov     [rsp+190h+MaxConnections], 3E8h; MaxConnections
0x140007557  lea     rax, [rbp+90h+DestinationString]
0x14000755b  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x14000755f  lea     rdx, [rdi+18h]; ServerPort
0x140007563  mov     rax, [rsp+190h+var_150]
0x140007568  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x14000756c  mov     [rbp+90h+ObjectAttributes.SecurityDescriptor], rax
0x140007570  xor     r9d, r9d; ServerPortCookie
0x140007573  lea     rax, ?PortMessage@UnionFsFilter@UnionFs@@SAJPEAX0K0KPEAK@Z; UnionFs::UnionFsFilter::PortMessage(void *,void *,ulong,void *,ulong,ulong *)
0x14000757a  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x140007582  mov     [rsp+190h+MessageNotifyCallback], rax; MessageNotifyCallback
0x140007587  lea     rax, ?PortDisconnect@UnionFsFilter@UnionFs@@SAXPEAX@Z; UnionFs::UnionFsFilter::PortDisconnect(void *)
0x14000758e  mov     [rsp+190h+DisconnectNotifyCallback], rax; DisconnectNotifyCallback
0x140007593  lea     rax, ?PortConnect@UnionFsFilter@UnionFs@@SAJPEAU_FLT_PORT@@PEAX1KPEAPEAX@Z; UnionFs::UnionFsFilter::PortConnect(_FLT_PORT *,void *,void *,ulong,void * *)
0x14000759a  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], 240h
0x1400075a2  mov     [rbp+90h+ObjectAttributes.RootDirectory], r15
0x1400075a6  mov     [rbp+90h+ObjectAttributes.SecurityQualityOfService], r15
0x1400075aa  mov     rcx, [rdi]; Filter
0x1400075ad  mov     [rsp+190h+ConnectNotifyCallback], rax; ConnectNotifyCallback
0x1400075b2  call    cs:__imp_FltCreateCommunicationPort
0x1400075b9  nop     dword ptr [rax+rax+00h]
0x1400075be  mov     ebx, eax
  ... truncated ...
```
