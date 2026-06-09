# DriverEntry

- ea: `0x14003c5e0`
- end: `0x14003c926`
- name: `DriverEntry`
- size: `838`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140045134`

## callees

- `0x140001bd8`
- `0x140003530`
- `0x14000700c`
- `0x140014d0c`
- `0x14001bed0`
- `0x14003b244`
- `0x14003baa0`
- `0x14003bc28`
- `0x14003c5e0`
- `0x14003ca34`
- `0x140058710`
- `0x140058e80`
- `0x140084084`
- `0x140084220`
- `0x1400842e8`
- `0x1400846cc`
- `0x14008c03c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003c624`
- `ntoskrnl!ExAllocatePool2` at `0x14003c624`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c69e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c69e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003c667`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003c667`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003c64d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003c64d`
- `ks!KsInitializeDriver` at `0x14003c83c`
- `ks!KsInitializeDriver` at `0x14003c83c`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x14003c887`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x14003c887`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  char v10; // si
  int v11; // edx
  __int64 v12; // rcx
  int v13; // r8d
  __int64 v14; // r8
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // r8d
  __int64 *v19; // rdx
  const wchar_t *v20; // [rsp+90h] [rbp+18h] BYREF
  __int64 v21; // [rsp+98h] [rbp+20h] BYREF

  result = wil_InitializeFeatureStaging();
  if ( result >= 0 )
  {
    DriverParametersRegistryPathName.MaximumLength = RegistryPath->Length + 24;
    DriverParametersRegistryPathName.Buffer = (PWSTR)ExAllocatePool2(
                                                       256,
                                                       DriverParametersRegistryPathName.MaximumLength,
                                                       1346650433);
    if ( !DriverParametersRegistryPathName.Buffer )
    {
      v5 = -1073741670;
LABEL_7:
      wil_UninitializeFeatureStaging();
      return v5;
    }
    RtlCopyUnicodeString(&DriverParametersRegistryPathName, RegistryPath);
    RtlAppendUnicodeToString(&DriverParametersRegistryPathName, L"\\Parameters");
    v10 = 1;
    if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v7, v6, v8, v9) )
    {
      v5 = InitializeWppTracing(DriverObject, RegistryPath);
      if ( v5 < 0 )
      {
        ExFreePoolWithTag(DriverParametersRegistryPathName.Buffer, 0x50444141u);
        DriverParametersRegistryPathName.Buffer = 0;
        goto LABEL_7;
      }
    }
    else
    {
      *(_QWORD *)&WPP_MAIN_CB.Type = 0;
      WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_BthA2DP;
      WPP_MAIN_CB.DeviceType = 0;
      WPP_MAIN_CB.NextDevice = 0;
      WPP_MAIN_CB.CurrentIrp = 0;
      WPP_MAIN_CB.Timer = (PIO_TIMER)1;
      WPP_MAIN_CB.DeviceExtension = 0;
      WppLoadTracingSupport();
      WPP_MAIN_CB.CurrentIrp = 0;
      WppInitKm(DriverObject, RegistryPath);
    }
    InitializeTelemetryAssertsKMByDriverObject(DriverObject);
    McGenEventRegister_EtwRegister();
    if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
      McTemplateK0_EtwWriteTransfer(v12, LoadBthA2dpDriver);
    LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v13,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        28,
        (__int64)WPP_6f32ee2d763d37e41fef735ec7f190b2_Traceguids,
        (char)DriverObject);
    }
    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_14006F0F8);
    if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 0x400000000000LL, v14) )
    {
      v21 = 33556480;
      v20 = L"BthA2dp.sys";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v15,
        (unsigned int)byte_14006A1C9,
        v16,
        v17,
        (__int64)&v21,
        (__int64)&v20);
    }
    v5 = KsInitializeDriver(DriverObject, RegistryPath, &Descriptor);
    dispatchunload = DriverObject->DriverUnload;
    DriverObject->DriverUnload = (PDRIVER_UNLOAD)DriverUnload;
    if ( v5 >= 0 )
    {
      DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)A2dpAudioIrpDispatcher;
      DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)A2dpAudioIrpDispatcher;
      DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)A2dpAudioIrpDispatcher;
    }
    SleepstudyHelper_Initialize(&g_SleepstudyLibraryHandle, DriverObject);
    RefObj_GlobalsInit();
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v10 = 0;
      }
      if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = WPP_6f32ee2d763d37e41fef735ec7f190b2_Traceguids;
        LOBYTE(v19) = v10;
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v19,
          v18,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          29,
          (__int64)WPP_6f32ee2d763d37e41fef735ec7f190b2_Traceguids,
          (char)DriverObject,
          v5);
      }
      DriverUnload(DriverObject);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14003c5e0  mov     [rsp+arg_0], rbx
0x14003c5e5  push    rsi
0x14003c5e6  push    rdi
0x14003c5e7  push    r13
0x14003c5e9  push    r14
0x14003c5eb  push    r15
0x14003c5ed  sub     rsp, 50h
0x14003c5f1  mov     r14, rdx
0x14003c5f4  mov     rbx, rcx
0x14003c5f7  call    wil_InitializeFeatureStaging
0x14003c5fc  test    eax, eax
0x14003c5fe  js      loc_14003C910
0x14003c604  movzx   eax, word ptr [r14]
0x14003c608  mov     r15d, 50444141h
0x14003c60e  add     ax, 18h
0x14003c612  mov     r8d, r15d
0x14003c615  movzx   edx, ax
0x14003c618  mov     ecx, 100h
0x14003c61d  mov     cs:DriverParametersRegistryPathName.MaximumLength, dx
0x14003c624  call    cs:__imp_ExAllocatePool2
0x14003c62b  nop     dword ptr [rax+rax+00h]
0x14003c630  mov     cs:DriverParametersRegistryPathName.Buffer, rax
0x14003c637  test    rax, rax
0x14003c63a  jnz     short loc_14003C643
0x14003c63c  mov     edi, 0C000009Ah
0x14003c641  jmp     short loc_14003C6B5
0x14003c643  mov     rdx, r14; SourceString
0x14003c646  lea     rcx, DriverParametersRegistryPathName; DestinationString
0x14003c64d  call    cs:__imp_RtlCopyUnicodeString
0x14003c654  nop     dword ptr [rax+rax+00h]
0x14003c659  lea     rdx, Source; "\\Parameters"
0x14003c660  lea     rcx, DriverParametersRegistryPathName; Destination
0x14003c667  call    cs:__imp_RtlAppendUnicodeToString
0x14003c66e  nop     dword ptr [rax+rax+00h]
0x14003c673  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14003c678  mov     sil, 1
0x14003c67b  test    eax, eax
0x14003c67d  jz      short loc_14003C6BF
0x14003c67f  mov     rdx, r14
0x14003c682  mov     rcx, rbx
0x14003c685  call    InitializeWppTracing
0x14003c68a  mov     edi, eax
0x14003c68c  test    eax, eax
0x14003c68e  jns     loc_14003C727
0x14003c694  mov     rcx, cs:DriverParametersRegistryPathName.Buffer; P
0x14003c69b  mov     edx, r15d; Tag
0x14003c69e  call    cs:__imp_ExFreePoolWithTag
0x14003c6a5  nop     dword ptr [rax+rax+00h]
0x14003c6aa  mov     cs:DriverParametersRegistryPathName.Buffer, 0
0x14003c6b5  call    wil_UninitializeFeatureStaging
0x14003c6ba  jmp     loc_14003C90E
0x14003c6bf  lea     rax, WPP_ThisDir_CTLGUID_BthA2DP
0x14003c6c6  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14003c6d1  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14003c6d8  xor     eax, eax
0x14003c6da  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x14003c6e0  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14003c6eb  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14003c6f6  mov     cs:WPP_MAIN_CB.Timer, 1
0x14003c701  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x14003c70c  call    WppLoadTracingSupport
0x14003c711  mov     rdx, r14
0x14003c714  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14003c71f  mov     rcx, rbx
0x14003c722  call    WppInitKm
0x14003c727  mov     rcx, rbx
0x14003c72a  call    InitializeTelemetryAssertsKMByDriverObject
0x14003c72f  call    McGenEventRegister_EtwRegister
0x14003c734  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, sil
0x14003c73b  jz      short loc_14003C749
0x14003c73d  lea     rdx, _LoadBthA2dpDriver
0x14003c744  call    McTemplateK0_EtwWriteTransfer
0x14003c749  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c750  lea     r15, WPP_GLOBAL_Control
0x14003c757  cmp     rcx, r15
0x14003c75a  jz      short loc_14003C76E
0x14003c75c  mov     eax, [rcx+2Ch]
0x14003c75f  test    al, 10h
0x14003c761  jz      short loc_14003C76E
0x14003c763  cmp     byte ptr [rcx+29h], 4
0x14003c767  jb      short loc_14003C76E
0x14003c769  mov     dl, sil
0x14003c76c  jmp     short loc_14003C770
0x14003c76e  xor     dl, dl
0x14003c770  lea     r13, WPP_RECORDER_INITIALIZED
0x14003c777  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003c77e  lea     r9, WPP_6f32ee2d763d37e41fef735ec7f190b2_Traceguids
0x14003c785  setnz   r8b
0x14003c789  test    dl, dl
0x14003c78b  jnz     short loc_14003C792
0x14003c78d  test    r8b, r8b
0x14003c790  jz      short loc_14003C7BD
0x14003c792  mov     [rsp+78h+var_38], rbx
0x14003c797  mov     [rsp+78h+var_40], r9
0x14003c79c  mov     r9, [rcx+40h]
0x14003c7a0  mov     rcx, [rcx+18h]
0x14003c7a4  mov     [rsp+78h+var_48], 1Ch
0x14003c7ab  mov     dword ptr [rsp+78h+var_50], 5
0x14003c7b3  mov     byte ptr [rsp+78h+var_58], 4
0x14003c7b8  call    WPP_RECORDER_AND_TRACE_SF_q
0x14003c7bd  lea     rcx, dword_14006F0F8; CallbackContext
0x14003c7c4  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14003c7c9  mov     eax, cs:dword_14006F0F8
0x14003c7cf  cmp     eax, 5
0x14003c7d2  jbe     short loc_14003C82F
0x14003c7d4  mov     rdx, 400000000000h
0x14003c7de  lea     rcx, dword_14006F0F8
0x14003c7e5  call    _tlgKeywordOn
0x14003c7ea  test    al, al
0x14003c7ec  jz      short loc_14003C82F
0x14003c7ee  lea     rax, aBtha2dpSys_0; "BthA2dp.sys"
0x14003c7f5  mov     [rsp+78h+arg_18], 2000800h
0x14003c801  mov     [rsp+78h+arg_10], rax
0x14003c809  lea     rdx, byte_14006A1C9
0x14003c810  lea     rax, [rsp+78h+arg_10]
0x14003c818  mov     [rsp+78h+var_50], rax
0x14003c81d  lea     rax, [rsp+78h+arg_18]
0x14003c825  mov     [rsp+78h+var_58], rax
0x14003c82a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003c82f  lea     r8, Descriptor; Descriptor
0x14003c836  mov     rdx, r14; RegistryPathName
0x14003c839  mov     rcx, rbx; DriverObject
0x14003c83c  call    cs:__imp_KsInitializeDriver
0x14003c843  nop     dword ptr [rax+rax+00h]
0x14003c848  mov     rcx, [rbx+68h]
0x14003c84c  mov     edi, eax
0x14003c84e  mov     cs:?dispatchunload@@3P6AXPEAU_DRIVER_OBJECT@@@ZEA, rcx; void (*dispatchunload)(_DRIVER_OBJECT *)
0x14003c855  lea     rax, ?DriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; DriverUnload(_DRIVER_OBJECT *)
0x14003c85c  mov     [rbx+68h], rax
0x14003c860  test    edi, edi
0x14003c862  js      short loc_14003C87D
0x14003c864  lea     rax, ?A2dpAudioIrpDispatcher@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; A2dpAudioIrpDispatcher(_DEVICE_OBJECT *,_IRP *)
0x14003c86b  mov     [rbx+0E0h], rax
0x14003c872  mov     [rbx+70h], rax
0x14003c876  mov     [rbx+80h], rax
0x14003c87d  mov     rdx, rbx
0x14003c880  lea     rcx, ?g_SleepstudyLibraryHandle@@3PEAUSS_LIBRARY__@@EA; SS_LIBRARY__ * g_SleepstudyLibraryHandle
0x14003c887  call    cs:__imp_SleepstudyHelper_Initialize
0x14003c88e  nop     dword ptr [rax+rax+00h]
0x14003c893  call    RefObj_GlobalsInit
0x14003c898  test    edi, edi
0x14003c89a  jns     short loc_14003C90E
0x14003c89c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c8a3  cmp     rcx, r15
0x14003c8a6  jz      short loc_14003C8B5
0x14003c8a8  mov     eax, [rcx+2Ch]
0x14003c8ab  test    al, 10h
0x14003c8ad  jz      short loc_14003C8B5
0x14003c8af  cmp     byte ptr [rcx+29h], 2
0x14003c8b3  jnb     short loc_14003C8B8
0x14003c8b5  xor     sil, sil
0x14003c8b8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14003c8bf  setnz   r8b
0x14003c8c3  test    sil, sil
0x14003c8c6  jnz     short loc_14003C8CD
0x14003c8c8  test    r8b, r8b
0x14003c8cb  jz      short loc_14003C906
0x14003c8cd  mov     r9, [rcx+40h]
0x14003c8d1  lea     rdx, WPP_6f32ee2d763d37e41fef735ec7f190b2_Traceguids
0x14003c8d8  mov     rcx, [rcx+18h]
0x14003c8dc  mov     [rsp+78h+var_30], edi
0x14003c8e0  mov     [rsp+78h+var_38], rbx
0x14003c8e5  mov     [rsp+78h+var_40], rdx
0x14003c8ea  mov     dl, sil
0x14003c8ed  mov     [rsp+78h+var_48], 1Dh
0x14003c8f4  mov     dword ptr [rsp+78h+var_50], 5
0x14003c8fc  mov     byte ptr [rsp+78h+var_58], 2
0x14003c901  call    WPP_RECORDER_AND_TRACE_SF_qD
0x14003c906  mov     rcx, rbx; struct _DRIVER_OBJECT *
0x14003c909  call    ?DriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; DriverUnload(_DRIVER_OBJECT *)
0x14003c90e  mov     eax, edi
0x14003c910  mov     rbx, [rsp+78h+arg_0]
0x14003c918  add     rsp, 50h
0x14003c91c  pop     r15
0x14003c91e  pop     r14
0x14003c920  pop     r13
0x14003c922  pop     rdi
0x14003c923  pop     rsi
0x14003c924  retn
```
