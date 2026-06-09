# DriverEntry

- ea: `0x140016078`
- end: `0x1400161e4`
- name: `DriverEntry`
- size: `364`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140016010`

## callees

- `0x140001814`
- `0x14000b008`
- `0x14000b360`
- `0x14000b4d4`
- `0x14000c474`
- `0x14000c83c`
- `0x14000ce58`
- `0x14000d00c`
- `0x14000d224`
- `0x14000ef90`
- `0x14000f0c0`
- `0x140016078`
- `0x1400161ec`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140016132`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016132`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140016179`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140016179`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS started; // edi
  ULONG v4; // edx
  ULONG v5; // r9d
  ULONG Handle; // [rsp+20h] [rbp-58h]
  BOOLEAN v8; // [rsp+28h] [rbp-50h]
  const UNICODE_STRING *v9; // [rsp+30h] [rbp-48h]
  const GUID *v10; // [rsp+38h] [rbp-40h]
  PDEVICE_OBJECT *v11; // [rsp+40h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF
  __int64 v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = 0;
  DestinationString = 0;
  started = wil_InitializeFeatureStaging(DriverObject, RegistryPath);
  if ( started < 0 )
    goto LABEL_9;
  TlgRegisterAggregateProviderEx();
  BamDriverObject = (__int64)DriverObject;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)BamDriverUnload;
  BampThrottlingInitializeModule();
  started = BampThrottlingStartModule();
  if ( started >= 0 )
  {
    started = BamUserSettingsInitialize(DriverObject);
    if ( started >= 0 )
    {
      started = BampRegisterKernelExtension((__int64)&v13);
      if ( started >= 0 )
      {
        DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&BamControlDispatch;
        DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&BamControlDispatch;
        DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&BamControlDispatch;
        DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&BamControlDispatch;
        RtlInitUnicodeString(&DestinationString, L"\\Device\\Bam");
        started = WdmlibIoCreateDeviceSecure(DriverObject, v4, &DestinationString, v5, Handle, v8, v9, v10, v11);
        if ( started >= 0 )
        {
          if ( !(unsigned int)Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline()
            || (started = PoRegisterPowerSettingCallback(
                            0,
                            &GUID_GLOBAL_USER_PRESENCE,
                            BamIdleGlobalUserPresenceCallback,
                            0,
                            &PoPowerSettingCallbackHandle),
                started >= 0) )
          {
            BampKernelExtensionRegistration = v13;
            v13 = 0;
            WilInitialized = 1;
LABEL_9:
            Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline();
            return started;
          }
        }
      }
      BamUserSettingsShutdown();
    }
  }
  BampThrottlingShutdownModule();
  TlgUnregisterAggregateProvider();
  Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline();
  wil_UninitializeFeatureStaging();
  return started;
}

```

## disassembly

```asm
0x140016078  mov     rax, rsp
0x14001607b  mov     [rax+8], rbx
0x14001607f  push    rbp
0x140016080  push    rsi
0x140016081  push    rdi
0x140016082  sub     rsp, 60h
0x140016086  xorps   xmm0, xmm0
0x140016089  mov     qword ptr [rax+20h], 0
0x140016091  movups  xmmword ptr [rax-28h], xmm0
0x140016095  mov     rsi, rcx
0x140016098  call    wil_InitializeFeatureStaging
0x14001609d  mov     edi, eax
0x14001609f  test    eax, eax
0x1400160a1  js      loc_1400161AC
0x1400160a7  mov     ebp, 1
0x1400160ac  call    TlgRegisterAggregateProviderEx
0x1400160b1  lea     rax, BamDriverUnload
0x1400160b8  mov     cs:BamDriverObject, rsi
0x1400160bf  mov     [rsi+68h], rax
0x1400160c3  call    BampThrottlingInitializeModule
0x1400160c8  lea     ebx, [rbp+4]
0x1400160cb  call    BampThrottlingStartModule
0x1400160d0  mov     edi, eax
0x1400160d2  test    eax, eax
0x1400160d4  js      loc_1400161C9
0x1400160da  mov     rcx, rsi
0x1400160dd  call    BamUserSettingsInitialize
0x1400160e2  mov     edi, eax
0x1400160e4  test    eax, eax
0x1400160e6  js      loc_1400161C9
0x1400160ec  lea     rcx, [rsp+78h+arg_18]
0x1400160f4  lea     ebx, [rbp+6]
0x1400160f7  call    BampRegisterKernelExtension
0x1400160fc  mov     edi, eax
0x1400160fe  test    eax, eax
0x140016100  js      loc_1400161C4
0x140016106  lea     rax, BamControlDispatch
0x14001610d  lea     rdx, aDeviceBam; "\\Device\\Bam"
0x140016114  mov     [rsi+70h], rax
0x140016118  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14001611d  mov     [rsi+100h], rax
0x140016124  mov     [rsi+80h], rax
0x14001612b  mov     [rsi+0E0h], rax
0x140016132  call    cs:__imp_RtlInitUnicodeString
0x140016139  nop     dword ptr [rax+rax+00h]
0x14001613e  lea     r8, [rsp+78h+DestinationString]; DeviceName
0x140016143  mov     rcx, rsi; DriverObject
0x140016146  call    WdmlibIoCreateDeviceSecure
0x14001614b  mov     edi, eax
0x14001614d  test    eax, eax
0x14001614f  js      short loc_1400161C4
0x140016151  call    Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline
0x140016156  test    eax, eax
0x140016158  jz      short loc_14001618B
0x14001615a  lea     rax, PoPowerSettingCallbackHandle
0x140016161  xor     r9d, r9d; Context
0x140016164  lea     r8, BamIdleGlobalUserPresenceCallback; Callback
0x14001616b  mov     [rsp+78h+Handle], rax; Handle
0x140016170  lea     rdx, GUID_GLOBAL_USER_PRESENCE; SettingGuid
0x140016177  xor     ecx, ecx; DeviceObject
0x140016179  call    cs:__imp_PoRegisterPowerSettingCallback
0x140016180  nop     dword ptr [rax+rax+00h]
0x140016185  mov     edi, eax
0x140016187  test    eax, eax
0x140016189  js      short loc_1400161C4
0x14001618b  mov     rax, [rsp+78h+arg_18]
0x140016193  mov     cs:BampKernelExtensionRegistration, rax
0x14001619a  mov     [rsp+78h+arg_18], 0
0x1400161a6  mov     cs:WilInitialized, ebp
0x1400161ac  call    Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline
0x1400161b1  mov     rbx, [rsp+78h+arg_0]
0x1400161b9  mov     eax, edi
0x1400161bb  add     rsp, 60h
0x1400161bf  pop     rdi
0x1400161c0  pop     rsi
0x1400161c1  pop     rbp
0x1400161c2  retn
0x1400161c4  call    BamUserSettingsShutdown
0x1400161c9  call    BampThrottlingShutdownModule
0x1400161ce  cmp     ebx, 4
0x1400161d1  jb      short loc_1400161D8
0x1400161d3  call    TlgUnregisterAggregateProvider
0x1400161d8  call    Feature_UserPresenceThrottling__private_IsEnabledDeviceUsageNoInline
0x1400161dd  call    wil_UninitializeFeatureStaging
0x1400161e2  jmp     short loc_1400161B1
```
