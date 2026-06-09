# DriverEntry

- ea: `0x14003825c`
- end: `0x1400385f6`
- name: `DriverEntry`
- size: `922`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140038010`

## callees

- `0x140001010`
- `0x140001044`
- `0x1400016a8`
- `0x1400016d8`
- `0x140003a54`
- `0x140006a20`
- `0x140021d30`
- `0x140022054`
- `0x140022184`
- `0x140022218`
- `0x140025194`
- `0x1400380c4`
- `0x14003825c`
- `0x1400385fc`
- `0x1400387a4`

## import_xrefs

- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x1400385b0`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x1400385b0`
- `ntoskrnl!ZwCreateEvent` at `0x140038570`
- `ntoskrnl!ZwCreateEvent` at `0x140038570`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400384b1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400384b1`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x140038472`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x140038472`
- `ntoskrnl!IoCreateDevice` at `0x140038390`
- `ntoskrnl!IoCreateDevice` at `0x140038390`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v3; // rdx
  int ProcessNotifyRoutine; // ebx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v12; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+48h] [rbp-41h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+58h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-21h] BYREF
  __int64 v16[6]; // [rsp+98h] [rbp+Fh] BYREF

  *(_QWORD *)&DeviceName.Length = 1835034;
  *(_QWORD *)&SymbolicLinkName.Length = 1310738;
  DeviceName.Buffer = L"\\Device\\AppID";
  WPP_MAIN_CB.NextDevice = 0;
  SymbolicLinkName.Buffer = L"\\??\\AppID";
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_AppIDLog;
  memset(&ObjectAttributes, 0, 44);
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport(DriverObject, RegistryPath);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  SymCryptInitEnvWindowsKernelmodeWin8_1nLater();
  if ( (int)TraceLoggingRegisterEx_EtwRegister_EtwSetInformation() < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
  }
  wil_InitializeFeatureStaging();
  ProcessNotifyRoutine = AipInitializeGlobals();
  if ( ProcessNotifyRoutine < 0 )
    goto LABEL_12;
  ProcessNotifyRoutine = SrpInitialize(DriverObject);
  if ( ProcessNotifyRoutine < 0 )
    goto LABEL_12;
  ProcessNotifyRoutine = IoCreateDevice(
                           DriverObject,
                           0,
                           &DeviceName,
                           0x22u,
                           0x100u,
                           0,
                           (PDEVICE_OBJECT *)&WPP_MAIN_CB.DeviceExtension);
  if ( ProcessNotifyRoutine < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_12;
    v6 = 11;
    goto LABEL_11;
  }
  ProcessNotifyRoutine = ObSetSecurityObjectByPointer(WPP_MAIN_CB.DeviceExtension, 4, qword_14000ACA8);
  if ( ProcessNotifyRoutine < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_12;
    v6 = 12;
    goto LABEL_11;
  }
  ProcessNotifyRoutine = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
  if ( ProcessNotifyRoutine < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_12;
    v6 = 13;
    goto LABEL_11;
  }
  WPP_MAIN_CB.DeviceType = 1;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)AipUnload;
  ObjectAttributes.Length = 48;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)AipCreateDispatch;
  ObjectAttributes.RootDirectory = 0;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&AipCloseDispatch;
  ObjectAttributes.Attributes = 512;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)AipDeviceIoControlDispatch;
  ObjectAttributes.ObjectName = 0;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&AipCleanupDispatch;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ProcessNotifyRoutine = ZwCreateEvent(&Handle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( ProcessNotifyRoutine < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_12;
    v6 = 14;
    goto LABEL_11;
  }
  ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutineEx(AiProcessNotifyRoutine, 0);
  if ( ProcessNotifyRoutine >= 0 )
  {
    *(_DWORD *)&WPP_MAIN_CB.StackSize = 1;
    goto LABEL_15;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v6 = 15;
LABEL_11:
    WPP_SF_D(v5->AttachedDevice, v6, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids);
  }
LABEL_12:
  if ( WPP_MAIN_CB.Queue.ListEntry.Blink )
    AiLogStatusEvent(WPP_MAIN_CB.Queue.ListEntry.Blink, v3, (unsigned int)ProcessNotifyRoutine);
  AipUnload(DriverObject);
LABEL_15:
  if ( (unsigned int)dword_140019000 > 4 && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
  {
    v12 = ProcessNotifyRoutine;
    v16[4] = (__int64)&v12;
    v16[5] = 4;
    tlgWriteTransfer_EtwWriteTransfer(v8, (int)&word_140015E12, v9, v10, 3u, (__int64)v16);
  }
  return ProcessNotifyRoutine;
}

```

## disassembly

```asm
0x14003825c  mov     [rsp-8+arg_8], rbx
0x140038261  mov     [rsp-8+arg_10], rdi
0x140038266  push    rbp
0x140038267  push    r12
0x140038269  push    r15
0x14003826b  lea     rbp, [rsp-47h]
0x140038270  sub     rsp, 0D0h
0x140038277  mov     rax, cs:__security_cookie
0x14003827e  xor     rax, rsp
0x140038281  mov     [rbp+57h+var_18], rax
0x140038285  xorps   xmm0, xmm0
0x140038288  mov     qword ptr [rbp+57h+DeviceName.Length], 1C001Ah
0x140038290  lea     rax, aDeviceAppid; "\\Device\\AppID"
0x140038297  mov     qword ptr [rbp+57h+SymbolicLinkName.Length], 140012h
0x14003829f  mov     [rbp+57h+DeviceName.Buffer], rax
0x1400382a3  mov     rdi, rcx
0x1400382a6  lea     rax, aAppid; "\\??\\AppID"
0x1400382ad  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x1400382b8  mov     [rbp+57h+SymbolicLinkName.Buffer], rax
0x1400382bc  xor     eax, eax
0x1400382be  mov     qword ptr cs:WPP_MAIN_CB.Type, rax
0x1400382c5  lea     rax, WPP_ThisDir_CTLGUID_AppIDLog
0x1400382cc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400382d0  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400382d7  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400382db  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400382e6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400382ea  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400382f5  call    WppLoadTracingSupport
0x1400382fa  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x140038305  call    WppInitKm
0x14003830a  call    SymCryptInitEnvWindowsKernelmodeWin8_1nLater
0x14003830f  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140038314  lea     r12, WPP_30d23e94a4083aaac446a7e141febb9c_Traceguids
0x14003831b  lea     r15, WPP_GLOBAL_Control
0x140038322  test    eax, eax
0x140038324  jns     short loc_14003834A
0x140038326  mov     rcx, cs:WPP_GLOBAL_Control
0x14003832d  cmp     rcx, r15
0x140038330  jz      short loc_14003834A
0x140038332  mov     eax, [rcx+2Ch]
0x140038335  test    al, 1
0x140038337  jz      short loc_14003834A
0x140038339  mov     rcx, [rcx+18h]
0x14003833d  mov     edx, 0Ah
0x140038342  mov     r8, r12
0x140038345  call    WPP_SF_
0x14003834a  call    wil_InitializeFeatureStaging
0x14003834f  call    AipInitializeGlobals
0x140038354  mov     ebx, eax
0x140038356  test    eax, eax
0x140038358  js      short loc_1400383CD
0x14003835a  mov     rcx, rdi; DriverObject
0x14003835d  call    SrpInitialize
0x140038362  mov     ebx, eax
0x140038364  test    eax, eax
0x140038366  js      short loc_1400383CD
0x140038368  lea     rax, WPP_MAIN_CB.DeviceExtension
0x14003836f  mov     r9d, 22h ; '"'; DeviceType
0x140038375  mov     [rsp+0E0h+DeviceObject], rax; DeviceObject
0x14003837a  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x14003837e  mov     [rsp+0E0h+Exclusive], 0; Exclusive
0x140038383  xor     edx, edx; DeviceExtensionSize
0x140038385  mov     rcx, rdi; DriverObject
0x140038388  mov     [rsp+0E0h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140038390  call    cs:__imp_IoCreateDevice
0x140038397  nop     dword ptr [rax+rax+00h]
0x14003839c  mov     ebx, eax
0x14003839e  test    eax, eax
0x1400383a0  jns     loc_14003845F
0x1400383a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400383ad  cmp     rcx, r15
0x1400383b0  jz      short loc_1400383CD
0x1400383b2  mov     eax, [rcx+2Ch]
0x1400383b5  test    al, 1
0x1400383b7  jz      short loc_1400383CD
0x1400383b9  mov     edx, 0Bh
0x1400383be  mov     rcx, [rcx+18h]
0x1400383c2  mov     r9d, ebx
0x1400383c5  mov     r8, r12
0x1400383c8  call    WPP_SF_D
0x1400383cd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400383d4  test    rcx, rcx
0x1400383d7  jz      short loc_1400383E1
0x1400383d9  mov     r8d, ebx
0x1400383dc  call    AiLogStatusEvent
0x1400383e1  mov     rcx, rdi
0x1400383e4  call    AipUnload
0x1400383e9  mov     eax, cs:dword_140019000
0x1400383ef  cmp     eax, 4
0x1400383f2  jbe     short loc_140038437
0x1400383f4  mov     rdx, 400000000000h
0x1400383fe  call    _tlgKeywordOn
0x140038403  test    al, al
0x140038405  jz      short loc_140038437
0x140038407  lea     rax, [rbp+57h+var_A0]
0x14003840b  mov     [rbp+57h+var_A0], ebx
0x14003840e  mov     [rbp+57h+var_28], rax
0x140038412  lea     rdx, word_140015E12; int
0x140038419  lea     rax, [rbp+57h+var_48]
0x14003841d  mov     [rbp+57h+var_20], 4
0x140038425  mov     qword ptr [rsp+0E0h+Exclusive], rax; __int64
0x14003842a  mov     [rsp+0E0h+DeviceCharacteristics], 3; ULONG
0x140038432  call    _tlgWriteTransfer_EtwWriteTransfer
0x140038437  mov     eax, ebx
0x140038439  mov     rcx, [rbp+57h+var_18]
0x14003843d  xor     rcx, rsp; StackCookie
0x140038440  call    __security_check_cookie
0x140038445  lea     r11, [rsp+0E0h+var_10]
0x14003844d  mov     rbx, [r11+28h]
0x140038451  mov     rdi, [r11+30h]
0x140038455  mov     rsp, r11
0x140038458  pop     r15
0x14003845a  pop     r12
0x14003845c  pop     rbp
0x14003845d  retn
0x14003845f  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140038466  lea     r8, qword_14000ACA8
0x14003846d  mov     edx, 4
0x140038472  call    cs:__imp_ObSetSecurityObjectByPointer
0x140038479  nop     dword ptr [rax+rax+00h]
0x14003847e  mov     ebx, eax
0x140038480  test    eax, eax
0x140038482  jns     short loc_1400384A9
0x140038484  mov     rcx, cs:WPP_GLOBAL_Control
0x14003848b  cmp     rcx, r15
0x14003848e  jz      loc_1400383CD
0x140038494  mov     eax, [rcx+2Ch]
0x140038497  test    al, 1
0x140038499  jz      loc_1400383CD
0x14003849f  mov     edx, 0Ch
0x1400384a4  jmp     loc_1400383BE
0x1400384a9  lea     rdx, [rbp+57h+DeviceName]; DeviceName
0x1400384ad  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x1400384b1  call    cs:__imp_IoCreateSymbolicLink
0x1400384b8  nop     dword ptr [rax+rax+00h]
0x1400384bd  mov     ebx, eax
0x1400384bf  test    eax, eax
0x1400384c1  jns     short loc_1400384E8
0x1400384c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400384ca  cmp     rcx, r15
0x1400384cd  jz      loc_1400383CD
0x1400384d3  mov     eax, [rcx+2Ch]
0x1400384d6  test    al, 1
0x1400384d8  jz      loc_1400383CD
0x1400384de  mov     edx, 0Dh
0x1400384e3  jmp     loc_1400383BE
0x1400384e8  mov     cs:WPP_MAIN_CB.DeviceType, 1
0x1400384f2  lea     rax, AipUnload
0x1400384f9  mov     [rdi+68h], rax
0x1400384fd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140038501  lea     rax, AipCreateDispatch
0x140038508  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14003850f  mov     [rdi+70h], rax
0x140038513  lea     rcx, Handle; EventHandle
0x14003851a  lea     rax, AipCloseDispatch
0x140038521  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140038529  mov     [rdi+80h], rax
0x140038530  xorps   xmm0, xmm0
0x140038533  lea     rax, AipDeviceIoControlDispatch
0x14003853a  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140038541  mov     [rdi+0E0h], rax
0x140038548  xor     r9d, r9d; EventType
0x14003854b  lea     rax, AipCleanupDispatch
0x140038552  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x14003855a  mov     edx, 1F0003h; DesiredAccess
0x14003855f  mov     [rdi+100h], rax
0x140038566  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003856b  mov     byte ptr [rsp+0E0h+DeviceCharacteristics], 0; InitialState
0x140038570  call    cs:__imp_ZwCreateEvent
0x140038577  nop     dword ptr [rax+rax+00h]
0x14003857c  mov     ebx, eax
0x14003857e  test    eax, eax
0x140038580  jns     short loc_1400385A7
0x140038582  mov     rcx, cs:WPP_GLOBAL_Control
0x140038589  cmp     rcx, r15
0x14003858c  jz      loc_1400383CD
0x140038592  mov     eax, [rcx+2Ch]
0x140038595  test    al, 1
0x140038597  jz      loc_1400383CD
0x14003859d  mov     edx, 0Eh
0x1400385a2  jmp     loc_1400383BE
0x1400385a7  xor     edx, edx; Remove
0x1400385a9  lea     rcx, AiProcessNotifyRoutine; NotifyRoutine
0x1400385b0  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx
0x1400385b7  nop     dword ptr [rax+rax+00h]
0x1400385bc  mov     ebx, eax
0x1400385be  test    eax, eax
0x1400385c0  jns     short loc_1400385E7
0x1400385c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400385c9  cmp     rcx, r15
0x1400385cc  jz      loc_1400383CD
0x1400385d2  mov     eax, [rcx+2Ch]
0x1400385d5  test    al, 1
0x1400385d7  jz      loc_1400383CD
0x1400385dd  mov     edx, 0Fh
0x1400385e2  jmp     loc_1400383BE
0x1400385e7  mov     dword ptr cs:WPP_MAIN_CB.StackSize, 1
0x1400385f1  jmp     loc_1400383E9
```
