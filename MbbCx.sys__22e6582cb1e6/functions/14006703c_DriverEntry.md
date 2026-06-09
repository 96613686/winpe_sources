# DriverEntry

- ea: `0x14006703c`
- end: `0x14006763d`
- name: `DriverEntry`
- size: `1537`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140042074`

## callees

- `0x140001db8`
- `0x140006aa4`
- `0x140006b60`
- `0x140009104`
- `0x14000d890`
- `0x14001d774`
- `0x140024bf4`
- `0x140024c60`
- `0x1400251e4`
- `0x14002534c`
- `0x140047e50`
- `0x140047e90`
- `0x140048340`
- `0x140065008`
- `0x1400650bc`
- `0x140065184`
- `0x1400661bc`
- `0x140066384`
- `0x14006703c`
- `0x140067644`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140067586`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140067586`
- `ntoskrnl!EtwUnregister` at `0x1400674ee`
- `ntoskrnl!EtwUnregister` at `0x14006750d`
- `ntoskrnl!EtwUnregister` at `0x1400674ee`
- `ntoskrnl!EtwUnregister` at `0x14006750d`
- `ntoskrnl!EtwRegister` at `0x14006710d`
- `ntoskrnl!EtwRegister` at `0x14006717a`
- `ntoskrnl!EtwRegister` at `0x14006710d`
- `ntoskrnl!EtwRegister` at `0x14006717a`
- `ntoskrnl!ZwPowerInformation` at `0x140067461`
- `ntoskrnl!ZwPowerInformation` at `0x140067461`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400670ee`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400670ee`
- `WDFLDR!WdfRegisterClassLibrary` at `0x1400673dc`
- `WDFLDR!WdfRegisterClassLibrary` at `0x1400673dc`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS v4; // eax
  int v5; // edx
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edx
  int v14; // eax
  int v15; // edx
  int v16; // r9d
  int v17; // eax
  int v18; // edx
  int v19; // eax
  int v20; // edx
  void *v21; // rcx
  NTSTATUS MbbSecurityDescriptor; // eax
  int v23; // edx
  int v24; // r9d
  wchar_t *Buffer; // rdx
  int RegistryValues; // eax
  int v27; // edx
  int v28; // r8d
  int v29; // r9d
  int v31; // [rsp+30h] [rbp-D0h]
  _BYTE OutputBuffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  char v33; // [rsp+44h] [rbp-BCh] BYREF
  char v34; // [rsp+45h] [rbp-BBh]
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v37; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v38; // [rsp+68h] [rbp-98h] BYREF
  __int128 v39; // [rsp+78h] [rbp-88h]
  __int64 v40[14]; // [rsp+90h] [rbp-70h] BYREF
  char v41; // [rsp+100h] [rbp+0h] BYREF

  wil_InitializeFeatureStaging();
  v34 = 1;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_WMBCLASS;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  WPP_MAIN_CB.DeviceQueue.Lock = (KSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink = (struct _LIST_ENTRY *)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink;
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
  v4 = EtwRegister(&WmbclassServiceTrace, 0, 0, (PREGHANDLE)&WPP_MAIN_CB.DeviceQueue.32);
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        11,
        10,
        (__int64)WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids,
        v4);
    }
LABEL_46:
    WppCleanupKm(DriverObject);
    goto LABEL_55;
  }
  v7 = EtwRegister(
         &WmbclassServiceTraceOpn,
         EtwOpnEventControlEnableCallback,
         0,
         (PREGHANDLE)&WPP_MAIN_CB.Dpc.DpcListEntry);
  if ( v7 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v9,
      11,
      (__int64)WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids,
      (__int64)L"DriverEntry",
      v7);
  v10 = TlgRegisterAggregateProvider();
  v6 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        11,
        12,
        (__int64)WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids,
        v10);
    }
    goto LABEL_42;
  }
  v38 = 0;
  v39 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x18 )
      LODWORD(v38) = -1;
    else
      LODWORD(v38) = *(_DWORD *)(WdfStructures + 192);
  }
  else
  {
    LODWORD(v38) = 32;
  }
  *((_QWORD *)&v38 + 1) = 0;
  *(_QWORD *)&v39 = EvtDriverUnload;
  DWORD2(v39) = 1;
  v35 = 0;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _DRIVER_OBJECT *, PUNICODE_STRING, _QWORD, __int128 *, __int64 *))(WdfFunctions_01031 + 928))(
          WdfDriverGlobals,
          DriverObject,
          RegistryPath,
          0,
          &v38,
          &v35);
  v6 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        11,
        13,
        (__int64)WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids,
        (char)DriverObject,
        v12);
    }
    goto LABEL_41;
  }
  v36 = 8;
  v14 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64, __int64 *))qword_14005F7A0)(NetDriverGlobals, v35, &v36);
  v6 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_41:
      TlgUnregisterAggregateProvider();
LABEL_42:
      if ( WPP_MAIN_CB.DeviceQueue.1 )
      {
        EtwUnregister(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32);
        WPP_MAIN_CB.DeviceQueue.1 = 0;
      }
      if ( WPP_MAIN_CB.Dpc.DpcListEntry.Next )
      {
        EtwUnregister((REGHANDLE)WPP_MAIN_CB.Dpc.DpcListEntry.Next);
        WPP_MAIN_CB.Dpc.DpcListEntry.Next = 0;
      }
      goto LABEL_46;
    }
    v16 = 14;
LABEL_21:
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      11,
      v16,
      (__int64)WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids,
      v14);
    goto LABEL_41;
  }
  v14 = MbbIpInitialize((struct _MINIPORT_DRIVER_CONTEXT *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext);
  v6 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v16 = 15;
    goto LABEL_21;
  }
  *(_QWORD *)&v37.Length = 13107200;
  v37.Buffer = (wchar_t *)&v41;
  v17 = CreateControlDevice(&v37);
  v6 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        11,
        16,
        (__int64)WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids,
        v17);
    }
LABEL_40:
    MbbIpCleanup((struct _MINIPORT_DRIVER_CONTEXT *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext);
    goto LABEL_41;
  }
  v19 = WdfRegisterClassLibrary(&WdfClassLibraryInfo, RegistryPath, &v37);
  v6 = v19;
  if ( v19 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v20) = 2;
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        v20,
        11,
        17,
        (__int64)WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids,
        v35,
        v19);
    }
    goto LABEL_38;
  }
  MbbSecurityDescriptor = CreateMbbSecurityDescriptor(v21);
  v6 = MbbSecurityDescriptor;
  if ( MbbSecurityDescriptor < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_38;
    v24 = 18;
    goto LABEL_37;
  }
  OutputBuffer[0] = 0;
  MbbSecurityDescriptor = ZwPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, OutputBuffer, 1u);
  v6 = MbbSecurityDescriptor;
  if ( MbbSecurityDescriptor < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_38;
    v24 = 19;
LABEL_37:
    LOBYTE(v23) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      11,
      v24,
      (__int64)WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids,
      MbbSecurityDescriptor);
LABEL_38:
    if ( WPP_MAIN_CB.Queue.Wcb.DeviceRoutine )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 1664))(WdfDriverGlobals);
      WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = 0;
    }
    goto LABEL_40;
  }
  LOBYTE(WPP_MAIN_CB.Dpc.ProcessorHistory) = OutputBuffer[0] != 0;
  memset(v40, 0, sizeof(v40));
  Buffer = RegistryPath->Buffer;
  v40[2] = (__int64)L"MbimExtendedTestVersion";
  LODWORD(v40[1]) = 292;
  v40[3] = (__int64)&WPP_MAIN_CB.Dpc.ProcessorHistory + 4;
  LODWORD(v40[4]) = 0x4000000;
  v40[5] = 0;
  LODWORD(v40[6]) = 0;
  RegistryValues = RtlQueryRegistryValuesEx(0, Buffer, v40, 0);
  if ( RegistryValues >= 0 )
  {
    if ( ((HIDWORD(WPP_MAIN_CB.Dpc.ProcessorHistory) - 256) & 0xFFFFFCFF) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          v28,
          v29,
          0,
          v40[2],
          SBYTE4(WPP_MAIN_CB.Dpc.ProcessorHistory));
      HIDWORD(WPP_MAIN_CB.Dpc.ProcessorHistory) = 0;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_SDd(WPP_GLOBAL_Control->DeviceExtension, v27, v28, v29, 0, v40[2], v31, RegistryValues);
  }
  v34 = 0;
  v6 = 0;
LABEL_55:
  wil::details::lambda_call__DriverEntry_::_2_::_lambda_1___::_lambda_call__DriverEntry_::_2_::_lambda_1___(&v33);
  return v6;
}

```

## disassembly

```asm
0x14006703c  mov     [rsp-8+arg_10], rbx
0x140067041  push    rbp
0x140067042  push    rsi
0x140067043  push    rdi
0x140067044  push    r12
0x140067046  push    r13
0x140067048  push    r14
0x14006704a  push    r15
0x14006704c  lea     rbp, [rsp-0E0h]
0x140067054  sub     rsp, 1E0h
0x14006705b  mov     rax, cs:__security_cookie
0x140067062  xor     rax, rsp
0x140067065  mov     [rbp+110h+var_40], rax
0x14006706c  mov     r15, rdx
0x14006706f  mov     r12, rcx
0x140067072  call    wil_InitializeFeatureStaging
0x140067077  xor     r13d, r13d
0x14006707a  mov     [rsp+210h+var_1CB], 1
0x14006707f  lea     rax, WPP_ThisDir_CTLGUID_WMBCLASS
0x140067086  mov     qword ptr cs:WPP_MAIN_CB.Type, r13
0x14006708d  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140067094  mov     cs:WPP_MAIN_CB.NextDevice, r13
0x14006709b  mov     cs:WPP_MAIN_CB.CurrentIrp, r13
0x1400670a2  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400670ad  mov     cs:WPP_MAIN_CB.DeviceExtension, r13
0x1400670b4  mov     cs:WPP_MAIN_CB.DeviceType, r13d
0x1400670bb  call    WppLoadTracingSupport
0x1400670c0  mov     rdx, r15
0x1400670c3  mov     cs:WPP_MAIN_CB.CurrentIrp, r13
0x1400670ca  mov     rcx, r12
0x1400670cd  call    WppInitKm
0x1400670d2  lea     rax, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x1400670d9  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x1400670e0  mov     cs:WPP_MAIN_CB.DeviceQueue.Lock, rax
0x1400670e7  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, rax
0x1400670ee  call    cs:__imp_KeInitializeSpinLock
0x1400670f5  nop     dword ptr [rax+rax+00h]
0x1400670fa  lea     r9, WPP_MAIN_CB.DeviceQueue.20h; RegHandle
0x140067101  xor     r8d, r8d; CallbackContext
0x140067104  xor     edx, edx; EnableCallback
0x140067106  lea     rcx, WmbclassServiceTrace; ProviderId
0x14006710d  call    cs:__imp_EtwRegister
0x140067114  nop     dword ptr [rax+rax+00h]
0x140067119  mov     ebx, eax
0x14006711b  test    eax, eax
0x14006711d  jns     short loc_140067162
0x14006711f  lea     rdi, WPP_RECORDER_INITIALIZED
0x140067126  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006712d  jz      loc_140067520
0x140067133  mov     rcx, cs:WPP_GLOBAL_Control
0x14006713a  lea     r14, WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids
0x140067141  mov     dword ptr [rsp+210h+var_1E8], eax
0x140067145  lea     r9d, [r13+0Ah]
0x140067149  lea     r8d, [r13+0Bh]
0x14006714d  mov     qword ptr [rsp+210h+OutputBufferLength], r14
0x140067152  mov     dl, 2
0x140067154  mov     rcx, [rcx+40h]
0x140067158  call    WPP_RECORDER_SF_d
0x14006715d  jmp     loc_140067520
0x140067162  lea     r9, WPP_MAIN_CB.Dpc.DpcListEntry; RegHandle
0x140067169  xor     r8d, r8d; CallbackContext
0x14006716c  lea     rdx, ?EtwOpnEventControlEnableCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; EnableCallback
0x140067173  lea     rcx, WmbclassServiceTraceOpn; ProviderId
0x14006717a  call    cs:__imp_EtwRegister
0x140067181  nop     dword ptr [rax+rax+00h]
0x140067186  lea     r14, WPP_fcd6e86913ab3e04c4e3cdd5cd23eaeb_Traceguids
0x14006718d  mov     esi, 0Bh
0x140067192  lea     rdi, WPP_RECORDER_INITIALIZED
0x140067199  test    eax, eax
0x14006719b  jns     short loc_1400671CE
0x14006719d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400671a4  jz      short loc_1400671CE
0x1400671a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400671ad  mov     r9d, esi
0x1400671b0  mov     [rsp+210h+var_1E0], eax
0x1400671b4  lea     rax, aDriverentry; "DriverEntry"
0x1400671bb  mov     [rsp+210h+var_1E8], rax
0x1400671c0  mov     qword ptr [rsp+210h+OutputBufferLength], r14
0x1400671c5  mov     rcx, [rcx+40h]
0x1400671c9  call    WPP_RECORDER_SF_Sd
0x1400671ce  call    TlgRegisterAggregateProvider
0x1400671d3  mov     ebx, eax
0x1400671d5  test    eax, eax
0x1400671d7  jns     short loc_14006720F
0x1400671d9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400671e0  jz      loc_1400674E2
0x1400671e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400671ed  mov     r9d, 0Ch
0x1400671f3  mov     dword ptr [rsp+210h+var_1E8], eax
0x1400671f7  mov     r8d, esi
0x1400671fa  mov     dl, 2
0x1400671fc  mov     qword ptr [rsp+210h+OutputBufferLength], r14
0x140067201  mov     rcx, [rcx+40h]
0x140067205  call    WPP_RECORDER_SF_d
0x14006720a  jmp     loc_1400674E2
0x14006720f  cmp     cs:WdfClientVersionHigherThanFramework, r13b
0x140067216  xorps   xmm0, xmm0
0x140067219  movups  [rsp+210h+var_1A8], xmm0
0x14006721e  movups  [rsp+210h+var_198], xmm0
0x140067223  jz      short loc_14006724B
0x140067225  cmp     cs:WdfStructureCount, 18h
0x14006722c  jbe     short loc_140067241
0x14006722e  mov     rax, cs:WdfStructures
0x140067235  mov     ecx, [rax+0C0h]
0x14006723b  mov     dword ptr [rsp+210h+var_1A8], ecx
0x14006723f  jmp     short loc_140067253
0x140067241  mov     dword ptr [rsp+210h+var_1A8], 0FFFFFFFFh
0x140067249  jmp     short loc_140067253
0x14006724b  mov     dword ptr [rsp+210h+var_1A8], 20h ; ' '
0x140067253  lea     rax, EvtDriverUnload
0x14006725a  mov     qword ptr [rsp+210h+var_1A8+8], r13
0x14006725f  mov     qword ptr [rsp+210h+var_198], rax
0x140067264  lea     rcx, [rsp+210h+var_1C8]
0x140067269  mov     rax, cs:WdfFunctions_01031
0x140067270  xor     r9d, r9d
0x140067273  mov     [rsp+210h+var_1E8], rcx
0x140067278  mov     r8, r15
0x14006727b  lea     rcx, [rsp+210h+var_1A8]
0x140067280  mov     dword ptr [rbp+110h+var_198+8], 1
0x140067287  mov     [rsp+210h+var_1C8], r13
0x14006728c  mov     rdx, r12
0x14006728f  mov     rax, [rax+3A0h]
0x140067296  mov     qword ptr [rsp+210h+OutputBufferLength], rcx
0x14006729b  mov     rcx, cs:WdfDriverGlobals
0x1400672a2  call    _guard_dispatch_icall
0x1400672a7  mov     ebx, eax
0x1400672a9  test    eax, eax
0x1400672ab  jns     short loc_1400672E8
0x1400672ad  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400672b4  jz      loc_1400674DD
0x1400672ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400672c1  mov     r9d, 0Dh
0x1400672c7  mov     [rsp+210h+var_1E0], eax
0x1400672cb  mov     r8d, esi
0x1400672ce  mov     [rsp+210h+var_1E8], r12
0x1400672d3  mov     dl, 2
0x1400672d5  mov     qword ptr [rsp+210h+OutputBufferLength], r14
0x1400672da  mov     rcx, [rcx+40h]
0x1400672de  call    WPP_RECORDER_SF_qd
0x1400672e3  jmp     loc_1400674DD
0x1400672e8  mov     rax, cs:qword_14005F7A0
0x1400672ef  lea     r8, [rsp+210h+var_1C0]
0x1400672f4  mov     rdx, [rsp+210h+var_1C8]
0x1400672f9  mov     rcx, cs:NetDriverGlobals
0x140067300  mov     [rsp+210h+var_1C0], r13
0x140067305  mov     dword ptr [rsp+210h+var_1C0], 8
0x14006730d  call    _guard_dispatch_icall
0x140067312  mov     ebx, eax
0x140067314  test    eax, eax
0x140067316  jns     short loc_14006734E
0x140067318  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006731f  jz      loc_1400674DD
0x140067325  mov     r9d, 0Eh
0x14006732b  mov     rcx, cs:WPP_GLOBAL_Control
0x140067332  mov     r8d, esi
0x140067335  mov     dword ptr [rsp+210h+var_1E8], eax
0x140067339  mov     dl, 2
0x14006733b  mov     qword ptr [rsp+210h+OutputBufferLength], r14
0x140067340  mov     rcx, [rcx+40h]
0x140067344  call    WPP_RECORDER_SF_d
0x140067349  jmp     loc_1400674DD
0x14006734e  lea     rcx, WPP_MAIN_CB.Queue+20h; struct _MINIPORT_DRIVER_CONTEXT *
0x140067355  call    ?MbbIpInitialize@@YAHPEAU_MINIPORT_DRIVER_CONTEXT@@@Z; MbbIpInitialize(_MINIPORT_DRIVER_CONTEXT *)
0x14006735a  mov     ebx, eax
0x14006735c  test    eax, eax
0x14006735e  jns     short loc_140067375
0x140067360  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140067367  jz      loc_1400674DD
0x14006736d  mov     r9d, 0Fh
0x140067373  jmp     short loc_14006732B
0x140067375  lea     rax, [rbp+110h+var_110]
0x140067379  mov     qword ptr [rsp+210h+var_1B8.Length], 0C80000h
0x140067382  lea     rcx, [rsp+210h+var_1B8]; struct _UNICODE_STRING *
0x140067387  mov     [rsp+210h+var_1B8.Buffer], rax
0x14006738c  call    ?CreateControlDevice@@YAJPEAU_UNICODE_STRING@@@Z; CreateControlDevice(_UNICODE_STRING *)
0x140067391  mov     ebx, eax
0x140067393  test    eax, eax
0x140067395  jns     short loc_1400673CD
0x140067397  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006739e  jz      loc_1400674D1
0x1400673a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400673ab  mov     r9d, 10h
0x1400673b1  mov     dword ptr [rsp+210h+var_1E8], eax
0x1400673b5  mov     r8d, esi
0x1400673b8  mov     dl, 2
0x1400673ba  mov     qword ptr [rsp+210h+OutputBufferLength], r14
0x1400673bf  mov     rcx, [rcx+40h]
0x1400673c3  call    WPP_RECORDER_SF_d
0x1400673c8  jmp     loc_1400674D1
0x1400673cd  lea     r8, [rsp+210h+var_1B8]
0x1400673d2  mov     rdx, r15
0x1400673d5  lea     rcx, ?WdfClassLibraryInfo@@3U_WDF_CLASS_LIBRARY_INFO@@A; _WDF_CLASS_LIBRARY_INFO WdfClassLibraryInfo
0x1400673dc  call    cs:__imp_WdfRegisterClassLibrary
0x1400673e3  nop     dword ptr [rax+rax+00h]
0x1400673e8  mov     ebx, eax
0x1400673ea  test    eax, eax
0x1400673ec  jns     short loc_14006742B
0x1400673ee  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400673f5  jz      loc_1400674A4
0x1400673fb  mov     rcx, [rsp+210h+var_1C8]
0x140067400  mov     r9d, 11h
0x140067406  mov     [rsp+210h+var_1E0], eax
0x14006740a  mov     r8d, esi
0x14006740d  mov     [rsp+210h+var_1E8], rcx
0x140067412  mov     dl, 2
0x140067414  mov     rcx, cs:WPP_GLOBAL_Control
0x14006741b  mov     qword ptr [rsp+210h+OutputBufferLength], r14
0x140067420  mov     rcx, [rcx+40h]
0x140067424  call    WPP_RECORDER_SF_qd
0x140067429  jmp     short loc_1400674A4
0x14006742b  call    ?CreateMbbSecurityDescriptor@@YAJPEAX@Z; CreateMbbSecurityDescriptor(void *)
0x140067430  mov     ebx, eax
0x140067432  test    eax, eax
0x140067434  jns     short loc_140067447
0x140067436  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006743d  jz      short loc_1400674A4
0x14006743f  mov     r9d, 12h
0x140067445  jmp     short loc_140067486
0x140067447  xor     edx, edx; InputBuffer
0x140067449  mov     [rsp+210h+OutputBuffer], r13b
0x14006744e  lea     r9, [rsp+210h+OutputBuffer]; OutputBuffer
0x140067453  mov     [rsp+210h+OutputBufferLength], 1; OutputBufferLength
0x14006745b  xor     r8d, r8d; InputBufferLength
0x14006745e  lea     ecx, [rdx+42h]; InformationLevel
0x140067461  call    cs:__imp_ZwPowerInformation
0x140067468  nop     dword ptr [rax+rax+00h]
0x14006746d  mov     ebx, eax
0x14006746f  test    eax, eax
0x140067471  jns     loc_14006752D
0x140067477  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006747e  jz      short loc_1400674A4
0x140067480  mov     r9d, 13h
0x140067486  mov     rcx, cs:WPP_GLOBAL_Control
0x14006748d  mov     r8d, esi
0x140067490  mov     dword ptr [rsp+210h+var_1E8], eax
0x140067494  mov     dl, 2
0x140067496  mov     qword ptr [rsp+210h+OutputBufferLength], r14
0x14006749b  mov     rcx, [rcx+40h]
0x14006749f  call    WPP_RECORDER_SF_d
0x1400674a4  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400674ab  test    rdx, rdx
0x1400674ae  jz      short loc_1400674D1
0x1400674b0  mov     rax, cs:WdfFunctions_01031
0x1400674b7  mov     rcx, cs:WdfDriverGlobals
0x1400674be  mov     rax, [rax+680h]
0x1400674c5  call    _guard_dispatch_icall
0x1400674ca  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, r13
0x1400674d1  lea     rcx, WPP_MAIN_CB.Queue+20h; struct _MINIPORT_DRIVER_CONTEXT *
0x1400674d8  call    ?MbbIpCleanup@@YAXPEAU_MINIPORT_DRIVER_CONTEXT@@@Z; MbbIpCleanup(_MINIPORT_DRIVER_CONTEXT *)
0x1400674dd  call    TlgUnregisterAggregateProvider
0x1400674e2  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h; RegHandle
0x1400674e9  test    rcx, rcx
0x1400674ec  jz      short loc_140067501
0x1400674ee  call    cs:__imp_EtwUnregister
0x1400674f5  nop     dword ptr [rax+rax+00h]
0x1400674fa  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, r13
0x140067501  mov     rcx, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next; RegHandle
0x140067508  test    rcx, rcx
0x14006750b  jz      short loc_140067520
0x14006750d  call    cs:__imp_EtwUnregister
0x140067514  nop     dword ptr [rax+rax+00h]
0x140067519  mov     cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, r13
0x140067520  mov     rcx, r12
0x140067523  call    WppCleanupKm
0x140067528  jmp     loc_140067606
0x14006752d  cmp     [rsp+210h+OutputBuffer], r13b
0x140067532  lea     rcx, [rbp+110h+var_180]; void *
0x140067536  setnz   byte ptr cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x14006753d  xor     edx, edx; Val
0x14006753f  lea     r8d, [rdx+70h]; Size
0x140067543  call    memset
0x140067548  mov     rdx, [r15+8]
0x14006754c  lea     rax, aMbimextendedte; "MbimExtendedTestVersion"
0x140067553  mov     [rbp+110h+var_170], rax
0x140067557  lea     r8, [rbp+110h+var_180]
0x14006755b  lea     rax, WPP_MAIN_CB.Dpc.ProcessorHistory+4
0x140067562  mov     [rbp+110h+var_178], 124h
0x140067569  xor     r9d, r9d
0x14006756c  mov     [rbp+110h+var_168], rax
0x140067570  xor     ecx, ecx
0x140067572  mov     [rbp+110h+var_160], 4000000h
0x140067579  mov     [rbp+110h+var_158], r13
0x14006757d  mov     [rbp+110h+var_150], r13d
0x140067581  mov     qword ptr [rsp+210h+OutputBufferLength], r13
0x140067586  call    cs:__imp_RtlQueryRegistryValuesEx
0x14006758d  nop     dword ptr [rax+rax+00h]
0x140067592  test    eax, eax
0x140067594  jns     short loc_1400675BE
0x140067596  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006759d  jz      short loc_1400675FE
0x14006759f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400675a6  mov     [rsp+210h+var_1D8], eax
0x1400675aa  mov     rax, [rbp+110h+var_170]
0x1400675ae  mov     [rsp+210h+var_1E8], rax
0x1400675b3  mov     rcx, [rcx+40h]
0x1400675b7  call    WPP_RECORDER_SF_SDd
0x1400675bc  jmp     short loc_1400675FE
0x1400675be  mov     ecx, dword ptr cs:WPP_MAIN_CB.Dpc.ProcessorHistory+4
0x1400675c4  lea     eax, [rcx-100h]
0x1400675ca  test    eax, 0FFFFFCFFh
  ... truncated ...
```
