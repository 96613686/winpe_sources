# DriverEntry

- ea: `0x14007553c`
- end: `0x140075986`
- name: `DriverEntry`
- size: `1098`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140056dc4`

## callees

- `0x140046d4c`
- `0x140057bf4`
- `0x140059970`
- `0x1400599b0`
- `0x14007553c`
- `0x14007598c`
- `0x140075a54`
- `0x14007b3b4`
- `0x14007b49c`
- `0x14007b7ec`
- `0x1400800c8`
- `0x14008503c`

## import_xrefs

- `ntoskrnl!EtwSetInformation` at `0x140075947`
- `ntoskrnl!EtwSetInformation` at `0x140075947`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400755ba`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140075625`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140075653`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400755ba`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140075625`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140075653`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140075852`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140075852`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075615`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075643`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075615`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075643`
- `ntoskrnl!KeInitializeSpinLock` at `0x140075822`
- `ntoskrnl!KeInitializeSpinLock` at `0x140075822`
- `WppRecorder!imp_WppRecorderConfigure` at `0x1400756dc`
- `WppRecorder!imp_WppRecorderConfigure` at `0x1400756dc`
- `WppRecorder!imp_WppRecorderGetTriageInfo` at `0x140075892`
- `WppRecorder!imp_WppRecorderGetTriageInfo` at `0x140075892`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x140075920`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x140075920`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  PVOID SystemRoutineAddress; // rax
  int v5; // ebx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  _BYTE v10[8]; // [rsp+40h] [rbp-69h] BYREF
  __int64 SystemInformation; // [rsp+48h] [rbp-61h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp-59h] BYREF
  __int64 v13; // [rsp+58h] [rbp-51h] BYREF
  struct _UNICODE_STRING v14[2]; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-19h] BYREF
  __int128 v17; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v18; // [rsp+B0h] [rbp+7h]
  __int128 v19; // [rsp+C0h] [rbp+17h]
  __int64 *v20; // [rsp+D0h] [rbp+27h]
  __int128 v21; // [rsp+D8h] [rbp+2Fh] BYREF

  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = DriverObject;
  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  SystemInformation = 0;
  LODWORD(v20) = 0;
  ReturnLength = 0;
  SystemRoutineName.Buffer = L"NtQuerySystemInformation";
  memset(v14, 0, 28);
  v13 = 0;
  v10[0] = 0;
  DestinationString = 0;
  v21 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress
    && ((int (__fastcall *)(__int64, _BYTE *, __int64, _QWORD))SystemRoutineAddress)(227, v10, 1, 0) >= 0
    && v10[0] )
  {
    ExPoolZeroingNativelySupported = 1;
  }
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  wil_InitializeFeatureStaging();
  RtlInitUnicodeString(&DestinationString, L"KseQueryDeviceFlags");
  WPP_MAIN_CB.Queue.Wcb.CurrentIrp = MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"IoTryQueueWorkItem");
  WPP_MAIN_CB.Queue.Wcb.DeviceObject = MmGetSystemRoutineAddress(&DestinationString);
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_USBXHCI;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  LODWORD(v21) = 16;
  *((_QWORD *)&v21 + 1) = 0x200000002LL;
  BYTE4(v21) = 0;
  imp_WppRecorderConfigure(WPP_GLOBAL_Control, &v21);
  v20 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v17) = -1;
    else
      LODWORD(v17) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v17) = 56;
  }
  v20 = off_14006C108;
  *((_QWORD *)&v17 + 1) = DriverCleanup;
  *((_QWORD *)&v18 + 1) = 0x100000001LL;
  memset(v14, 0, sizeof(v14));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x18 )
      *(_DWORD *)&v14[0].Length = -1;
    else
      *(_DWORD *)&v14[0].Length = *(_DWORD *)(WdfStructures + 192);
  }
  else
  {
    *(_DWORD *)&v14[0].Length = 32;
  }
  HIDWORD(v14[1].Buffer) = 1464027224;
  v14[0].Buffer = (wchar_t *)Controller_WdfEvtDeviceAdd;
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _DRIVER_OBJECT *, PUNICODE_STRING, __int128 *, struct _UNICODE_STRING *, __int64 *))(WdfFunctions_01033 + 928))(
         WdfDriverGlobals,
         DriverObject,
         RegistryPath,
         &v17,
         v14,
         &v13);
  if ( v5 >= 0 )
  {
    v6 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                     WdfDriverGlobals,
                     v13,
                     off_14006C108);
    g_WdfDriverUsbXhciContext = (__int64)v6;
    v6[1] = v6;
    *v6 = v6;
    KeInitializeSpinLock(v6 + 2);
    *(_DWORD *)(g_WdfDriverUsbXhciContext + 24) = 0;
    SystemInformation = 8;
    v5 = ZwQuerySystemInformation(SystemCodeIntegrityInformation, &SystemInformation, 8u, &ReturnLength);
    if ( v5 >= 0 && (SystemInformation & 0x200000000LL) != 0 )
    {
      *(_BYTE *)(g_WdfDriverUsbXhciContext + 28) = 1;
    }
    else
    {
      v5 = 0;
      *(_BYTE *)(g_WdfDriverUsbXhciContext + 28) = 0;
    }
    imp_WppRecorderGetTriageInfo(WPP_GLOBAL_Control, &WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
    dword_14006C3B8 = WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey;
    qword_14006C3BC = (__int64)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine;
    dword_14006C3C4 = *((_DWORD *)&WPP_MAIN_CB.Queue.Wcb.1 + 5);
    dword_14006C3C8 = (int)WPP_MAIN_CB.Queue.Wcb.DeviceContext;
    qword_14006C3E0 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01033 + 3448))(WdfDriverGlobals);
    InitializeTelemetryAssertsKMByDriverObject(DriverObject);
    McGenEventRegister_EtwRegister(v8, v7, &MS_USBXHCI_ETW_PROVIDER_Context, &MS_USBXHCI_ETW_PROVIDER_Context);
    SleepstudyHelper_Initialize(g_WdfDriverUsbXhciContext + 32, DriverObject);
    EtwSetInformation(
      MS_USBXHCI_ETW_PROVIDER_Context,
      EventProviderSetTraits,
      &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
      (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_14006C4F0);
    Counter_Register();
  }
  else
  {
    WppCleanupKm(DriverObject);
    wil_UninitializeFeatureStaging();
  }
  return v5;
}

```

## disassembly

```asm
0x14007553c  mov     [rsp-8+arg_10], rbx
0x140075541  push    rbp
0x140075542  push    rsi
0x140075543  push    rdi
0x140075544  lea     rbp, [rsp-47h]
0x140075549  sub     rsp, 0F0h
0x140075550  mov     rax, cs:__security_cookie
0x140075557  xor     rax, rsp
0x14007555a  mov     [rbp+57h+var_18], rax
0x14007555e  xorps   xmm0, xmm0
0x140075561  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rcx
0x140075568  xor     esi, esi
0x14007556a  mov     qword ptr [rbp+57h+SystemRoutineName.Length], 320030h
0x140075572  xor     eax, eax
0x140075574  mov     [rbp+57h+SystemInformation], rsi
0x140075578  mov     dword ptr [rbp+57h+var_30], eax
0x14007557b  mov     rdi, rcx
0x14007557e  lea     rax, aNtquerysystemi; "NtQuerySystemInformation"
0x140075585  mov     [rbp+57h+ReturnLength], esi
0x140075588  xorps   xmm1, xmm1
0x14007558b  mov     [rbp+57h+SystemRoutineName.Buffer], rax
0x14007558f  movups  [rbp+57h+var_A0], xmm0
0x140075593  lea     rcx, [rbp+57h+SystemRoutineName]; SystemRoutineName
0x140075597  mov     [rbp+57h+var_A8], rsi
0x14007559b  mov     rbx, rdx
0x14007559e  mov     [rbp+57h+var_C0], sil
0x1400755a2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400755a6  movups  [rbp+57h+var_28], xmm1
0x1400755aa  movups  [rbp+57h+var_60], xmm0
0x1400755ae  movups  [rbp+57h+var_50], xmm0
0x1400755b2  movups  [rbp+57h+var_40], xmm0
0x1400755b6  movups  [rbp+57h+var_A0+0Ch], xmm0
0x1400755ba  call    cs:__imp_MmGetSystemRoutineAddress
0x1400755c1  nop     dword ptr [rax+rax+00h]
0x1400755c6  test    rax, rax
0x1400755c9  jz      short loc_1400755F1
0x1400755cb  xor     r9d, r9d
0x1400755ce  lea     r8d, [rsi+1]
0x1400755d2  lea     rdx, [rbp+57h+var_C0]
0x1400755d6  mov     ecx, 0E3h
0x1400755db  call    _guard_dispatch_icall
0x1400755e0  test    eax, eax
0x1400755e2  js      short loc_1400755F1
0x1400755e4  cmp     [rbp+57h+var_C0], sil
0x1400755e8  jz      short loc_1400755F1
0x1400755ea  mov     cs:ExPoolZeroingNativelySupported, 1
0x1400755f1  mov     cs:ExDefaultNonPagedPoolType, 200h
0x1400755fb  mov     cs:ExDefaultMdlProtection, 40000000h
0x140075605  call    wil_InitializeFeatureStaging
0x14007560a  lea     rdx, aKsequerydevice; "KseQueryDeviceFlags"
0x140075611  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140075615  call    cs:__imp_RtlInitUnicodeString
0x14007561c  nop     dword ptr [rax+rax+00h]
0x140075621  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140075625  call    cs:__imp_MmGetSystemRoutineAddress
0x14007562c  nop     dword ptr [rax+rax+00h]
0x140075631  lea     rdx, aIotryqueuework; "IoTryQueueWorkItem"
0x140075638  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, rax
0x14007563f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140075643  call    cs:__imp_RtlInitUnicodeString
0x14007564a  nop     dword ptr [rax+rax+00h]
0x14007564f  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140075653  call    cs:__imp_MmGetSystemRoutineAddress
0x14007565a  nop     dword ptr [rax+rax+00h]
0x14007565f  mov     qword ptr cs:WPP_MAIN_CB.Queue+30h, rax
0x140075666  lea     rax, WPP_ThisDir_CTLGUID_USBXHCI
0x14007566d  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140075674  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x14007567b  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x140075682  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x140075689  mov     cs:WPP_MAIN_CB.Timer, 1
0x140075694  mov     cs:WPP_MAIN_CB.DeviceExtension, rsi
0x14007569b  mov     cs:WPP_MAIN_CB.DeviceType, esi
0x1400756a1  call    WppLoadTracingSupport
0x1400756a6  mov     rdx, rbx; __annotation("TMC:", "9F7711DD-29AD-C1EE-1B1B-B52A0118A54C", "USBXHCI", "General", "Driver", "Device", "Controller", "IoControl", "Register", "Command", "CommonBuffer", "Interrupter", "DeviceSlot", "RootHub", "UsbDevice", "Endpoint", "TransferRing", "Wmi", "CommandFilter", "StateMachine", "DmaEnabler", "SecureChannel", "TimeSync", "PUBLIC_TMF:")
0x1400756a9  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x1400756b0  mov     rcx, rdi
0x1400756b3  call    WppInitKm
0x1400756b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400756bf  lea     rdx, [rbp+57h+var_28]
0x1400756c3  mov     dword ptr [rbp+57h+var_28], 10h
0x1400756ca  mov     dword ptr [rbp+57h+var_28+8], 2
0x1400756d1  mov     dword ptr [rbp+57h+var_28+0Ch], 2
0x1400756d8  mov     byte ptr [rbp+57h+var_28+4], sil
0x1400756dc  call    cs:__imp_imp_WppRecorderConfigure
0x1400756e3  nop     dword ptr [rax+rax+00h]
0x1400756e8  mov     dl, cs:WdfClientVersionHigherThanFramework
0x1400756ee  xorps   xmm0, xmm0
0x1400756f1  xor     eax, eax
0x1400756f3  or      r8d, 0FFFFFFFFh
0x1400756f7  mov     [rbp+57h+var_30], rax
0x1400756fb  movups  [rbp+57h+var_60], xmm0
0x1400756ff  movups  [rbp+57h+var_50], xmm0
0x140075703  movups  [rbp+57h+var_40], xmm0
0x140075707  test    dl, dl
0x140075709  jz      short loc_14007572C
0x14007570b  cmp     cs:WdfStructureCount, 26h ; '&'
0x140075712  jbe     short loc_140075726
0x140075714  mov     rax, cs:WdfStructures
0x14007571b  mov     ecx, [rax+130h]
0x140075721  mov     dword ptr [rbp+57h+var_60], ecx
0x140075724  jmp     short loc_140075733
0x140075726  mov     dword ptr [rbp+57h+var_60], r8d
0x14007572a  jmp     short loc_140075733
0x14007572c  mov     dword ptr [rbp+57h+var_60], 38h ; '8'
0x140075733  mov     rax, cs:off_14006C108
0x14007573a  mov     [rbp+57h+var_30], rax
0x14007573e  lea     rax, DriverCleanup
0x140075745  mov     qword ptr [rbp+57h+var_60+8], rax
0x140075749  mov     dword ptr [rbp+57h+var_50+8], 1
0x140075750  mov     dword ptr [rbp+57h+var_50+0Ch], 1
0x140075757  movups  [rbp+57h+var_A0], xmm0
0x14007575b  movups  [rbp+57h+var_90], xmm0
0x14007575f  test    dl, dl
0x140075761  jz      short loc_140075784
0x140075763  cmp     cs:WdfStructureCount, 18h
0x14007576a  jbe     short loc_14007577E
0x14007576c  mov     rax, cs:WdfStructures
0x140075773  mov     ecx, [rax+0C0h]
0x140075779  mov     dword ptr [rbp+57h+var_A0], ecx
0x14007577c  jmp     short loc_14007578B
0x14007577e  mov     dword ptr [rbp+57h+var_A0], r8d
0x140075782  jmp     short loc_14007578B
0x140075784  mov     dword ptr [rbp+57h+var_A0], 20h ; ' '
0x14007578b  lea     rax, Controller_WdfEvtDeviceAdd
0x140075792  mov     dword ptr [rbp+57h+var_90+0Ch], 57434858h
0x140075799  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14007579d  lea     rcx, [rbp+57h+var_A8]
0x1400757a1  mov     rax, cs:WdfFunctions_01033
0x1400757a8  lea     r9, [rbp+57h+var_60]
0x1400757ac  mov     [rsp+100h+var_D8], rcx
0x1400757b1  mov     r8, rbx
0x1400757b4  lea     rcx, [rbp+57h+var_A0]
0x1400757b8  mov     rdx, rdi
0x1400757bb  mov     [rsp+100h+var_E0], rcx
0x1400757c0  mov     rax, [rax+3A0h]
0x1400757c7  mov     rcx, cs:WdfDriverGlobals
0x1400757ce  call    _guard_dispatch_icall
0x1400757d3  mov     ebx, eax
0x1400757d5  test    eax, eax
0x1400757d7  jns     short loc_1400757EB
0x1400757d9  mov     rcx, rdi
0x1400757dc  call    WppCleanupKm
0x1400757e1  call    wil_UninitializeFeatureStaging
0x1400757e6  jmp     loc_140075964
0x1400757eb  mov     rax, cs:WdfFunctions_01033
0x1400757f2  mov     r8, cs:off_14006C108
0x1400757f9  mov     rdx, [rbp+57h+var_A8]
0x1400757fd  mov     rcx, cs:WdfDriverGlobals
0x140075804  mov     rax, [rax+650h]
0x14007580b  call    _guard_dispatch_icall
0x140075810  mov     cs:g_WdfDriverUsbXhciContext, rax
0x140075817  lea     rcx, [rax+10h]; SpinLock
0x14007581b  mov     [rax+8], rax
0x14007581f  mov     [rax], rax
0x140075822  call    cs:__imp_KeInitializeSpinLock
0x140075829  nop     dword ptr [rax+rax+00h]
0x14007582e  mov     rax, cs:g_WdfDriverUsbXhciContext
0x140075835  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x140075839  mov     r8d, 8; SystemInformationLength
0x14007583f  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x140075843  mov     [rax+18h], esi
0x140075846  mov     [rbp+57h+SystemInformation], rsi
0x14007584a  lea     ecx, [r8+5Fh]; SystemInformationClass
0x14007584e  mov     dword ptr [rbp+57h+SystemInformation], r8d
0x140075852  call    cs:__imp_ZwQuerySystemInformation
0x140075859  nop     dword ptr [rax+rax+00h]
0x14007585e  mov     ebx, eax
0x140075860  test    eax, eax
0x140075862  js      short loc_140075877
0x140075864  test    byte ptr [rbp+57h+SystemInformation+4], 2
0x140075868  jz      short loc_140075877
0x14007586a  mov     rax, cs:g_WdfDriverUsbXhciContext
0x140075871  mov     byte ptr [rax+1Ch], 1
0x140075875  jmp     short loc_140075884
0x140075877  mov     rax, cs:g_WdfDriverUsbXhciContext
0x14007587e  mov     ebx, esi
0x140075880  mov     [rax+1Ch], sil
0x140075884  mov     rcx, cs:WPP_GLOBAL_Control
0x14007588b  lea     rdx, WPP_MAIN_CB.Queue+10h
0x140075892  call    cs:__imp_imp_WppRecorderGetTriageInfo
0x140075899  nop     dword ptr [rax+rax+00h]
0x14007589e  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400758a4  mov     rcx, cs:WdfDriverGlobals
0x1400758ab  mov     cs:dword_14006C3B8, eax
0x1400758b1  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400758b7  mov     dword ptr cs:qword_14006C3BC, eax
0x1400758bd  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+1Ch
0x1400758c3  mov     dword ptr cs:qword_14006C3BC+4, eax
0x1400758c9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+14h
0x1400758cf  mov     cs:dword_14006C3C4, eax
0x1400758d5  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+20h
0x1400758db  mov     cs:dword_14006C3C8, eax
0x1400758e1  mov     rax, cs:WdfFunctions_01033
0x1400758e8  mov     rax, [rax+0D78h]
0x1400758ef  call    _guard_dispatch_icall
0x1400758f4  mov     rcx, rdi
0x1400758f7  mov     cs:qword_14006C3E0, rax
0x1400758fe  call    InitializeTelemetryAssertsKMByDriverObject
0x140075903  lea     r8, MS_USBXHCI_ETW_PROVIDER_Context
0x14007590a  mov     r9, r8
0x14007590d  call    McGenEventRegister_EtwRegister
0x140075912  mov     rcx, cs:g_WdfDriverUsbXhciContext
0x140075919  mov     rdx, rdi
0x14007591c  add     rcx, 20h ; ' '
0x140075920  call    cs:__imp_SleepstudyHelper_Initialize
0x140075927  nop     dword ptr [rax+rax+00h]
0x14007592c  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; InformationLength
0x140075934  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; EventInformation
0x14007593b  mov     rcx, cs:MS_USBXHCI_ETW_PROVIDER_Context; RegHandle
0x140075942  mov     edx, 2; InformationClass
0x140075947  call    cs:__imp_EtwSetInformation
0x14007594e  nop     dword ptr [rax+rax+00h]
0x140075953  lea     rcx, dword_14006C4F0; CallbackContext
0x14007595a  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14007595f  call    Counter_Register
0x140075964  mov     eax, ebx
0x140075966  mov     rcx, [rbp+57h+var_18]
0x14007596a  xor     rcx, rsp; StackCookie
0x14007596d  call    __security_check_cookie
0x140075972  mov     rbx, [rsp+100h+arg_10]
0x14007597a  add     rsp, 0F0h
0x140075981  pop     rdi
0x140075982  pop     rsi
0x140075983  pop     rbp
0x140075984  retn
```
