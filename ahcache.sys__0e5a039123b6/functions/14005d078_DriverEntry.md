# DriverEntry

- ea: `0x14005d078`
- end: `0x14005d317`
- name: `DriverEntry`
- size: `671`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x14005d010`

## callees

- `0x140007854`
- `0x1400079f0`
- `0x140028fec`
- `0x140036ee8`
- `0x14003e364`
- `0x140049ba0`
- `0x14004af80`
- `0x14005d078`
- `0x14005d320`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x14005d199`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14005d199`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x14005d1f9`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x14005d1f9`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14005d224`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14005d224`
- `ntoskrnl!PsStartSiloMonitor` at `0x14005d23d`
- `ntoskrnl!PsStartSiloMonitor` at `0x14005d23d`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x14005d278`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x14005d2ca`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x14005d278`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x14005d2ca`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x14005d28a`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x14005d28a`

## string_xrefs

- `0x14005d0c3`: `\Device\ahcache`
- `0x14005d0eb`: `\DosDevices\ahcache`
- `0x14005d17f`: `Failed to create device [%x]`
- `0x14005d1ab`: `Failed to create symbolic link [%x]`
- `0x14005d24f`: `The driver failed the create infrastructure silo state: 0x%x\n`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS inited; // eax
  NTSTATUS v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  ULONG v7; // edx
  ULONG v8; // r9d
  int started; // eax
  __int64 v11; // [rsp+20h] [rbp-29h]
  BOOLEAN v12; // [rsp+28h] [rbp-21h]
  const UNICODE_STRING *v13; // [rsp+30h] [rbp-19h]
  const GUID *v14; // [rsp+38h] [rbp-11h]
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp+Fh] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+68h] [rbp+1Fh] BYREF
  __int128 v18; // [rsp+78h] [rbp+2Fh] BYREF
  __int128 v19; // [rsp+88h] [rbp+3Fh]

  DeviceObject = 0;
  DestinationString = 0;
  SymbolicLinkName = 0;
  v18 = 0;
  v19 = 0;
  wil_InitializeFeatureStaging(DriverObject, RegistryPath);
  inited = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"\\Device\\ahcache");
  v4 = inited;
  if ( inited >= 0 )
  {
    inited = WdmlibRtlInitUnicodeStringEx(&SymbolicLinkName, L"\\DosDevices\\ahcache");
    v4 = inited;
    if ( inited >= 0 )
    {
      AhcTraceStart();
      PerfScenarioStart(&CompatCacheInitializeStart);
      DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&AhcDriverDispatchCreate;
      DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&AhcDriverDispatchCreate;
      DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&AhcDriverDispatchDeviceControl;
      DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)&AhcDriverDispatchShutdown;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)AhcDriverUnload;
      inited = WdmlibIoCreateDeviceSecure(DriverObject, v7, &DestinationString, v8, v11, v12, v13, v14, &DeviceObject);
      v4 = inited;
      if ( inited >= 0 )
      {
        inited = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
        v4 = inited;
        if ( inited >= 0 )
        {
          *(_DWORD *)((char *)&v18 + 2) = 0;
          WORD3(v18) = 0;
          LOWORD(v18) = 257;
          *((_QWORD *)&v18 + 1) = &DriverObject->DriverName;
          *(_QWORD *)&v19 = AhcacheCreateSiloNotification;
          *((_QWORD *)&v19 + 1) = AhcacheTerminateSiloNotification;
          inited = PsRegisterSiloMonitor(&v18, &g_AhcacheSiloMonitor);
          v4 = inited;
          if ( inited >= 0 )
          {
            g_AhcacheSiloContextSlot = PsGetSiloMonitorContextSlot(g_AhcacheSiloMonitor);
            started = PsStartSiloMonitor(g_AhcacheSiloMonitor);
            v4 = started;
            if ( started < 0 )
            {
              AslLogCallPrintf(
                1,
                "DriverEntry",
                227,
                "The driver failed the create infrastructure silo state: 0x%x\n",
                started);
              PsUnregisterSiloMonitor(g_AhcacheSiloMonitor);
              goto LABEL_16;
            }
            inited = IoRegisterShutdownNotification(DeviceObject);
            v4 = inited;
            if ( inited >= 0 )
            {
              v4 = 0;
              goto LABEL_19;
            }
            v5 = "Failed to register shutdown notification [%x]";
            v6 = 239;
          }
          else
          {
            v5 = "The driver failed the register for silo notifications: 0x%x\n";
            v6 = 213;
          }
        }
        else
        {
          v5 = "Failed to create symbolic link [%x]";
          v6 = 194;
        }
      }
      else
      {
        v5 = "Failed to create device [%x]";
        v6 = 183;
      }
    }
    else
    {
      v5 = "Failed to initialize dos device name [%x]";
      v6 = 150;
    }
  }
  else
  {
    v5 = "Failed to initialize device name [%x]";
    v6 = 144;
  }
  LODWORD(v11) = inited;
  AslLogCallPrintf(1, "DriverEntry", v6, v5, v11);
LABEL_16:
  if ( g_AhcacheSiloMonitor )
  {
    PsUnregisterSiloMonitor(g_AhcacheSiloMonitor);
    g_AhcacheSiloMonitor = 0;
  }
LABEL_19:
  PerfScenarioStop(&CompatCacheInitializeStop);
  return v4;
}

```

## disassembly

```asm
0x14005d078  mov     [rsp-8+arg_8], rbx
0x14005d07d  mov     [rsp-8+arg_10], rdi
0x14005d082  push    rbp
0x14005d083  lea     rbp, [rsp-57h]
0x14005d088  sub     rsp, 0A0h
0x14005d08f  mov     rax, cs:__security_cookie
0x14005d096  xor     rax, rsp
0x14005d099  mov     [rbp+57h+var_8], rax
0x14005d09d  xorps   xmm0, xmm0
0x14005d0a0  mov     [rbp+57h+var_50], 0
0x14005d0a8  xorps   xmm1, xmm1
0x14005d0ab  mov     rdi, rcx
0x14005d0ae  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005d0b2  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm1
0x14005d0b6  movups  [rbp+57h+var_28], xmm0
0x14005d0ba  movups  [rbp+57h+var_18], xmm0
0x14005d0be  call    wil_InitializeFeatureStaging
0x14005d0c3  lea     rdx, aDeviceAhcache; "\\Device\\ahcache"
0x14005d0ca  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005d0ce  call    WdmlibRtlInitUnicodeStringEx
0x14005d0d3  mov     ebx, eax
0x14005d0d5  test    eax, eax
0x14005d0d7  jns     short loc_14005D0EB
0x14005d0d9  lea     r9, aFailedToInitia_0; "Failed to initialize device name [%x]"
0x14005d0e0  mov     r8d, 90h
0x14005d0e6  jmp     loc_14005D2A9
0x14005d0eb  lea     rdx, aDosdevicesAhca; "\\DosDevices\\ahcache"
0x14005d0f2  lea     rcx, [rbp+57h+SymbolicLinkName]; DestinationString
0x14005d0f6  call    WdmlibRtlInitUnicodeStringEx
0x14005d0fb  mov     ebx, eax
0x14005d0fd  test    eax, eax
0x14005d0ff  jns     short loc_14005D113
0x14005d101  lea     r9, aFailedToInitia_3; "Failed to initialize dos device name [%"...
0x14005d108  mov     r8d, 96h
0x14005d10e  jmp     loc_14005D2A9
0x14005d113  call    AhcTraceStart
0x14005d118  lea     rcx, CompatCacheInitializeStart; EventDescriptor
0x14005d11f  call    PerfScenarioStart
0x14005d124  lea     rax, AhcDriverDispatchCreate
0x14005d12b  mov     rcx, rdi; DriverObject
0x14005d12e  mov     [rdi+70h], rax
0x14005d132  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x14005d136  lea     rax, AhcDriverDispatchCreate
0x14005d13d  mov     [rdi+80h], rax
0x14005d144  lea     rax, AhcDriverDispatchDeviceControl
0x14005d14b  mov     [rdi+0E0h], rax
0x14005d152  lea     rax, AhcDriverDispatchShutdown
0x14005d159  mov     [rdi+0F0h], rax
0x14005d160  lea     rax, AhcDriverUnload
0x14005d167  mov     [rdi+68h], rax
0x14005d16b  lea     rax, [rbp+57h+var_50]
0x14005d16f  mov     [rsp+0A0h+DeviceObject], rax; DeviceObject
0x14005d174  call    WdmlibIoCreateDeviceSecure
0x14005d179  mov     ebx, eax
0x14005d17b  test    eax, eax
0x14005d17d  jns     short loc_14005D191
0x14005d17f  lea     r9, aFailedToCreate_14; "Failed to create device [%x]"
0x14005d186  mov     r8d, 0B7h
0x14005d18c  jmp     loc_14005D2A9
0x14005d191  lea     rdx, [rbp+57h+DestinationString]; DeviceName
0x14005d195  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x14005d199  call    cs:__imp_IoCreateSymbolicLink
0x14005d1a0  nop     dword ptr [rax+rax+00h]
0x14005d1a5  mov     ebx, eax
0x14005d1a7  test    eax, eax
0x14005d1a9  jns     short loc_14005D1BD
0x14005d1ab  lea     r9, aFailedToCreate_2; "Failed to create symbolic link [%x]"
0x14005d1b2  mov     r8d, 0C2h
0x14005d1b8  jmp     loc_14005D2A9
0x14005d1bd  xor     eax, eax
0x14005d1bf  mov     dword ptr [rbp+57h+var_28+2], 0
0x14005d1c6  mov     word ptr [rbp+57h+var_28+6], ax
0x14005d1ca  lea     rdx, g_AhcacheSiloMonitor
0x14005d1d1  lea     rax, [rdi+38h]
0x14005d1d5  mov     word ptr [rbp+57h+var_28], 101h
0x14005d1db  mov     qword ptr [rbp+57h+var_28+8], rax
0x14005d1df  lea     rcx, [rbp+57h+var_28]
0x14005d1e3  lea     rax, AhcacheCreateSiloNotification
0x14005d1ea  mov     qword ptr [rbp+57h+var_18], rax
0x14005d1ee  lea     rax, AhcacheTerminateSiloNotification
0x14005d1f5  mov     qword ptr [rbp+57h+var_18+8], rax
0x14005d1f9  call    cs:__imp_PsRegisterSiloMonitor
0x14005d200  nop     dword ptr [rax+rax+00h]
0x14005d205  mov     ebx, eax
0x14005d207  test    eax, eax
0x14005d209  jns     short loc_14005D21D
0x14005d20b  lea     r9, aTheDriverFaile_0; "The driver failed the register for silo"...
0x14005d212  mov     r8d, 0D5h
0x14005d218  jmp     loc_14005D2A9
0x14005d21d  mov     rcx, cs:g_AhcacheSiloMonitor
0x14005d224  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14005d22b  nop     dword ptr [rax+rax+00h]
0x14005d230  mov     rcx, cs:g_AhcacheSiloMonitor
0x14005d237  mov     cs:g_AhcacheSiloContextSlot, eax
0x14005d23d  call    cs:__imp_PsStartSiloMonitor
0x14005d244  nop     dword ptr [rax+rax+00h]
0x14005d249  mov     ebx, eax
0x14005d24b  test    eax, eax
0x14005d24d  jns     short loc_14005D286
0x14005d24f  lea     r9, aTheDriverFaile; "The driver failed the create infrastruc"...
0x14005d256  mov     dword ptr [rsp+0A0h+var_80], eax
0x14005d25a  mov     r8d, 0E3h
0x14005d260  lea     rdx, aDriverentry; "DriverEntry"
0x14005d267  mov     ecx, 1
0x14005d26c  call    AslLogCallPrintf
0x14005d271  mov     rcx, cs:g_AhcacheSiloMonitor
0x14005d278  call    cs:__imp_PsUnregisterSiloMonitor
0x14005d27f  nop     dword ptr [rax+rax+00h]
0x14005d284  jmp     short loc_14005D2BE
0x14005d286  mov     rcx, [rbp+57h+var_50]; DeviceObject
0x14005d28a  call    cs:__imp_IoRegisterShutdownNotification
0x14005d291  nop     dword ptr [rax+rax+00h]
0x14005d296  mov     ebx, eax
0x14005d298  test    eax, eax
0x14005d29a  jns     short loc_14005D2E3
0x14005d29c  lea     r9, aFailedToRegist_0; "Failed to register shutdown notificatio"...
0x14005d2a3  mov     r8d, 0EFh
0x14005d2a9  lea     rdx, aDriverentry; "DriverEntry"
0x14005d2b0  mov     dword ptr [rsp+0A0h+var_80], eax
0x14005d2b4  mov     ecx, 1
0x14005d2b9  call    AslLogCallPrintf
0x14005d2be  mov     rcx, cs:g_AhcacheSiloMonitor
0x14005d2c5  test    rcx, rcx
0x14005d2c8  jz      short loc_14005D2E5
0x14005d2ca  call    cs:__imp_PsUnregisterSiloMonitor
0x14005d2d1  nop     dword ptr [rax+rax+00h]
0x14005d2d6  mov     cs:g_AhcacheSiloMonitor, 0
0x14005d2e1  jmp     short loc_14005D2E5
0x14005d2e3  xor     ebx, ebx
0x14005d2e5  mov     edx, ebx
0x14005d2e7  lea     rcx, CompatCacheInitializeStop; EventDescriptor
0x14005d2ee  call    PerfScenarioStop
0x14005d2f3  mov     eax, ebx
0x14005d2f5  mov     rcx, [rbp+57h+var_8]
0x14005d2f9  xor     rcx, rsp; StackCookie
0x14005d2fc  call    __security_check_cookie
0x14005d301  lea     r11, [rsp+0A0h+var_s0]
0x14005d309  mov     rbx, [r11+18h]
0x14005d30d  mov     rdi, [r11+20h]
0x14005d311  mov     rsp, r11
0x14005d314  pop     rbp
0x14005d315  retn
```
