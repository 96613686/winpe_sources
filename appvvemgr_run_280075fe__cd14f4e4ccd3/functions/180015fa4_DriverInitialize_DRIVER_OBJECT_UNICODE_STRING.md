# DriverInitialize(_DRIVER_OBJECT *,_UNICODE_STRING *)

- ea: `0x180015fa4`
- end: `0x1800161fc`
- name: `?DriverInitialize@@YAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT Driver, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016204`

## callees

- `0x180009ef0`
- `0x18000a050`
- `0x18000fd14`
- `0x180015fa4`
- `0x180016338`
- `0x180017334`
- `0x18001948c`
- `0x18001b3cc`
- `0x18002b090`
- `0x18002e078`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x180016099`
- `ntoskrnl!IoDeleteDevice` at `0x180016140`
- `ntoskrnl!IoDeleteDevice` at `0x1800161c0`
- `ntoskrnl!IoDeleteDevice` at `0x180016099`
- `ntoskrnl!IoDeleteDevice` at `0x180016140`
- `ntoskrnl!IoDeleteDevice` at `0x1800161c0`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18001607a`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18001607a`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x180016178`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x180016178`
- `ntoskrnl!DbgPrint` at `0x180016193`
- `ntoskrnl!DbgPrint` at `0x180016193`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001602c`
- `ntoskrnl!RtlInitUnicodeString` at `0x180016044`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001602c`
- `ntoskrnl!RtlInitUnicodeString` at `0x180016044`

## string_xrefs

- `0x18001618c`: `PsSetCreateProcessNotifyRoutine failed with error %x\n`

## pseudocode

```c
__int64 __fastcall DriverInitialize(PDRIVER_OBJECT Driver, struct _DEVICE_OBJECT *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rcx
  ULONG v6; // edx
  ULONG v7; // r9d
  NTSTATUS v8; // ebx
  PDEVICE_OBJECT v10; // rdi
  int v11; // eax
  vemgr *v12; // rcx
  NTSTATUS ProcessNotifyRoutine; // eax
  __int64 v14; // rcx
  vemgr *v15; // rcx
  ULONG v16; // [rsp+20h] [rbp-58h]
  BOOLEAN v17; // [rsp+28h] [rbp-50h]
  const UNICODE_STRING *v18; // [rsp+30h] [rbp-48h]
  const GUID *v19; // [rsp+38h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+60h] [rbp-18h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+88h] [rbp+10h] BYREF

  DeviceObject = a2;
  LogInitialize();
  McGenEventRegister_EtwRegister(
    PROVIDER_MICROSOFT_APPV_CLIENT,
    v3,
    PROVIDER_MICROSOFT_APPV_CLIENT_Context,
    PROVIDER_MICROSOFT_APPV_CLIENT_Context);
  McGenEventRegister_EtwRegister(
    PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS,
    v4,
    PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
    PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v5, VEMGR_Driver_Load_Start, 0);
  DeviceObject = 0;
  DestinationString = 0;
  SymbolicLinkName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\AppvVemgr");
  RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\AppvVemgr");
  v8 = WdmlibIoCreateDeviceSecure(Driver, v6, &DestinationString, v7, v16, v17, v18, v19, &DeviceObject);
  if ( v8 < 0 )
    goto LABEL_7;
  v8 = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
  if ( v8 < 0 )
  {
    if ( DeviceObject )
      IoDeleteDevice(DeviceObject);
LABEL_7:
    LogWrite(1, 0, L"DriverInitialize() - AppvVemgr.sys failed to initialize. Error %d.", (unsigned int)v8);
    return (unsigned int)v8;
  }
  v10 = DeviceObject;
  Driver->MajorFunction[16] = (PDRIVER_DISPATCH)VEManagerShutdown;
  vemgr::g_pDeviceExtn = 0;
  Driver->MajorFunction[0] = VEManagerCreate;
  Driver->MajorFunction[2] = VEManagerClose;
  Driver->MajorFunction[14] = VEManagerDispatch;
  v11 = VeMgrFilterStart(Driver);
  v8 = v11;
  if ( v11 < 0 )
  {
    LogWrite(1, 0, L"DriverInitialize() - AppvVemgr.sys failed to initialize. Error %d.", (unsigned int)v11);
    VeMgrFilterCleanup();
    IoDeleteDevice(v10);
    return (unsigned int)v8;
  }
  vemgr::g_pDeviceExtn = v10->DeviceExtension;
  *((_QWORD *)vemgr::g_pDeviceExtn + 1) = 0;
  v8 = vemgr::DevExtnInit(v12);
  if ( v8 < 0 )
    goto LABEL_14;
  ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutineEx(vemgr::ProcessNotifyCallbackEx, 0);
  v8 = ProcessNotifyRoutine;
  if ( ProcessNotifyRoutine < 0 )
  {
    DbgPrint("PsSetCreateProcessNotifyRoutine failed with error %x\n", ProcessNotifyRoutine);
LABEL_14:
    LogWrite(1, 0, L"DriverInitialize() - AppvVemgr.sys failed to initialize. Error %d.", (unsigned int)v8);
    VeMgrFilterCleanup();
    vemgr::Uninitialize(v15);
    IoDeleteDevice(v10);
    goto LABEL_16;
  }
  v8 = 0;
  *((_QWORD *)vemgr::g_pDeviceExtn + 1) = v10;
LABEL_16:
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v14, VEMGR_Driver_Load_Finish, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015fa4  mov     [rsp+arg_0], rbx
0x180015fa9  mov     [rsp+arg_10], rsi
0x180015fae  mov     [rsp+arg_8], rdx
0x180015fb3  push    rdi
0x180015fb4  sub     rsp, 70h
0x180015fb8  mov     rsi, rcx
0x180015fbb  call    LogInitialize
0x180015fc0  lea     r8, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x180015fc7  mov     r9, r8
0x180015fca  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT
0x180015fd1  call    McGenEventRegister_EtwRegister
0x180015fd6  lea     r8, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x180015fdd  mov     r9, r8
0x180015fe0  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS
0x180015fe7  call    McGenEventRegister_EtwRegister
0x180015fec  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x180015ff3  jz      short loc_180016004
0x180015ff5  xor     r8d, r8d
0x180015ff8  lea     rdx, VEMGR_Driver_Load_Start
0x180015fff  call    McTemplateK0_EtwWriteTransfer
0x180016004  xorps   xmm0, xmm0
0x180016007  mov     [rsp+78h+arg_8], 0
0x180016013  xorps   xmm1, xmm1
0x180016016  lea     rdx, aDeviceAppvvemg; "\\Device\\AppvVemgr"
0x18001601d  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180016022  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x180016027  movups  xmmword ptr [rsp+78h+SymbolicLinkName.Length], xmm1
0x18001602c  call    cs:__imp_RtlInitUnicodeString
0x180016033  nop     dword ptr [rax+rax+00h]
0x180016038  lea     rdx, aDosdevicesAppv; "\\DosDevices\\AppvVemgr"
0x18001603f  lea     rcx, [rsp+78h+SymbolicLinkName]; DestinationString
0x180016044  call    cs:__imp_RtlInitUnicodeString
0x18001604b  nop     dword ptr [rax+rax+00h]
0x180016050  lea     rax, [rsp+78h+arg_8]
0x180016058  mov     rcx, rsi; DriverObject
0x18001605b  lea     r8, [rsp+78h+DestinationString]; DeviceName
0x180016060  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x180016065  call    WdmlibIoCreateDeviceSecure
0x18001606a  mov     ebx, eax
0x18001606c  test    eax, eax
0x18001606e  js      short loc_1800160A5
0x180016070  lea     rdx, [rsp+78h+DestinationString]; DeviceName
0x180016075  lea     rcx, [rsp+78h+SymbolicLinkName]; SymbolicLinkName
0x18001607a  call    cs:__imp_IoCreateSymbolicLink
0x180016081  nop     dword ptr [rax+rax+00h]
0x180016086  mov     ebx, eax
0x180016088  test    eax, eax
0x18001608a  jns     short loc_1800160CE
0x18001608c  mov     rcx, [rsp+78h+arg_8]; DeviceObject
0x180016094  test    rcx, rcx
0x180016097  jz      short loc_1800160A5
0x180016099  call    cs:__imp_IoDeleteDevice
0x1800160a0  nop     dword ptr [rax+rax+00h]
0x1800160a5  xor     edx, edx
0x1800160a7  lea     r8, aDriverinitiali; "DriverInitialize() - AppvVemgr.sys fail"...
0x1800160ae  mov     r9d, ebx
0x1800160b1  lea     ecx, [rdx+1]
0x1800160b4  call    LogWrite
0x1800160b9  lea     r11, [rsp+78h+var_8]
0x1800160be  mov     eax, ebx
0x1800160c0  mov     rbx, [r11+10h]
0x1800160c4  mov     rsi, [r11+20h]
0x1800160c8  mov     rsp, r11
0x1800160cb  pop     rdi
0x1800160cc  retn
0x1800160ce  mov     rdi, [rsp+78h+arg_8]
0x1800160d6  lea     rax, ?VEManagerShutdown@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; VEManagerShutdown(_DEVICE_OBJECT *,_IRP *)
0x1800160dd  mov     [rsi+0F0h], rax
0x1800160e4  mov     rcx, rsi; Driver
0x1800160e7  lea     rax, ?VEManagerCreate@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; VEManagerCreate(_DEVICE_OBJECT *,_IRP *)
0x1800160ee  mov     cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA, 0; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x1800160f9  mov     [rsi+70h], rax
0x1800160fd  lea     rax, ?VEManagerClose@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; VEManagerClose(_DEVICE_OBJECT *,_IRP *)
0x180016104  mov     [rsi+80h], rax
0x18001610b  lea     rax, ?VEManagerDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; VEManagerDispatch(_DEVICE_OBJECT *,_IRP *)
0x180016112  mov     [rsi+0E0h], rax
0x180016119  call    ?VeMgrFilterStart@@YAJPEAU_DRIVER_OBJECT@@@Z; VeMgrFilterStart(_DRIVER_OBJECT *)
0x18001611e  mov     ebx, eax
0x180016120  test    eax, eax
0x180016122  jns     short loc_180016151
0x180016124  xor     edx, edx
0x180016126  lea     r8, aDriverinitiali; "DriverInitialize() - AppvVemgr.sys fail"...
0x18001612d  mov     r9d, eax
0x180016130  lea     ecx, [rdx+1]
0x180016133  call    LogWrite
0x180016138  call    ?VeMgrFilterCleanup@@YAXXZ; VeMgrFilterCleanup(void)
0x18001613d  mov     rcx, rdi; DeviceObject
0x180016140  call    cs:__imp_IoDeleteDevice
0x180016147  nop     dword ptr [rax+rax+00h]
0x18001614c  jmp     loc_1800160B9
0x180016151  mov     rax, [rdi+40h]
0x180016155  mov     cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA, rax; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x18001615c  mov     qword ptr [rax+8], 0
0x180016164  call    ?DevExtnInit@vemgr@@YAJXZ; vemgr::DevExtnInit(void)
0x180016169  mov     ebx, eax
0x18001616b  test    eax, eax
0x18001616d  js      short loc_18001619F
0x18001616f  xor     edx, edx; Remove
0x180016171  lea     rcx, ?ProcessNotifyCallbackEx@vemgr@@YAXPEAU_KPROCESS@@PEAXPEAU_PS_CREATE_NOTIFY_INFO@@@Z; NotifyRoutine
0x180016178  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx
0x18001617f  nop     dword ptr [rax+rax+00h]
0x180016184  mov     ebx, eax
0x180016186  test    eax, eax
0x180016188  jns     short loc_1800161CE
0x18001618a  mov     edx, eax
0x18001618c  lea     rcx, Format; "PsSetCreateProcessNotifyRoutine failed "...
0x180016193  call    cs:__imp_DbgPrint
0x18001619a  nop     dword ptr [rax+rax+00h]
0x18001619f  xor     edx, edx
0x1800161a1  lea     r8, aDriverinitiali; "DriverInitialize() - AppvVemgr.sys fail"...
0x1800161a8  mov     r9d, ebx
0x1800161ab  lea     ecx, [rdx+1]
0x1800161ae  call    LogWrite
0x1800161b3  call    ?VeMgrFilterCleanup@@YAXXZ; VeMgrFilterCleanup(void)
0x1800161b8  call    ?Uninitialize@vemgr@@YAJXZ; vemgr::Uninitialize(void)
0x1800161bd  mov     rcx, rdi; DeviceObject
0x1800161c0  call    cs:__imp_IoDeleteDevice
0x1800161c7  nop     dword ptr [rax+rax+00h]
0x1800161cc  jmp     short loc_1800161DB
0x1800161ce  mov     rax, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x1800161d5  xor     ebx, ebx
0x1800161d7  mov     [rax+8], rdi
0x1800161db  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x1800161e2  jz      loc_1800160B9
0x1800161e8  xor     r8d, r8d
0x1800161eb  lea     rdx, VEMGR_Driver_Load_Finish
0x1800161f2  call    McTemplateK0_EtwWriteTransfer
0x1800161f7  jmp     loc_1800160B9
```
