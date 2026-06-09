# EdpPluginInit

- ea: `0x140038c60`
- end: `0x140038e20`
- name: `EdpPluginInit`
- size: `448`
- prototype: `int __fastcall(struct _DRIVER_OBJECT **)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400293ac`
- `0x140038c60`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x140038e02`
- `ntoskrnl!PsCreateSystemThread` at `0x140038e02`
- `ntoskrnl!ZwCreateEvent` at `0x140038dc2`
- `ntoskrnl!ZwCreateEvent` at `0x140038dc2`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140038d3f`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140038d3f`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x140038d23`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x140038d23`
- `ntoskrnl!IoCreateDevice` at `0x140038d00`
- `ntoskrnl!IoCreateDevice` at `0x140038d00`

## string_xrefs

- `0x140038c88`: `\Device\AppidEDPPlugin`
- `0x140038c9c`: `\??\AppidEDPPlugin`
- `0x140038caf`: `\REGISTRY\MACHINE\System\CurrentControlSet\control\session manager\kernel`
- `0x140038cba`: `SeTokenSingletonAttributesConfig`

## pseudocode

```c
int __fastcall EdpPluginInit(struct _DRIVER_OBJECT **a1)
{
  _QWORD *v1; // rbx
  struct _DRIVER_OBJECT *v2; // rcx
  int result; // eax
  __int64 v4; // rcx
  ULONG DeviceCharacteristics[2]; // [rsp+20h] [rbp-39h]
  BOOLEAN Exclusive[8]; // [rsp+28h] [rbp-31h]
  PDEVICE_OBJECT *DeviceObjecta; // [rsp+30h] [rbp-29h]
  PDEVICE_OBJECT *DeviceObject; // [rsp+30h] [rbp-29h]
  struct _UNICODE_STRING DeviceName; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v11[2]; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v12[2]; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  int v14; // [rsp+C0h] [rbp+67h] BYREF

  v14 = 0;
  v1 = a1 + 1;
  *(_QWORD *)&DeviceName.Length = 3014700;
  DeviceObjecta = (PDEVICE_OBJECT *)(a1 + 1);
  DeviceName.Buffer = L"\\Device\\AppidEDPPlugin";
  *(_QWORD *)&SymbolicLinkName.Length = 2490404;
  SymbolicLinkName.Buffer = L"\\??\\AppidEDPPlugin";
  v12[1] = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\control\\session manager\\kernel";
  v11[1] = L"SeTokenSingletonAttributesConfig";
  EdppAuditSessionLock = 0;
  v2 = *a1;
  v12[0] = 9699474;
  v11[0] = 4325440;
  memset(&ObjectAttributes, 0, 44);
  result = IoCreateDevice(v2, 1u, &DeviceName, 0x22u, 0x100u, 0, DeviceObjecta);
  if ( result >= 0 )
  {
    result = ObSetSecurityObjectByPointer(*v1, 4, qword_14000DC88);
    if ( result >= 0 )
    {
      result = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
      if ( result >= 0 )
      {
        *(_BYTE *)(*v1 + 64LL) = 1;
        AiRegReadDwordValue(v4, v12, v11, &v14, *(_QWORD *)DeviceCharacteristics, *(_QWORD *)Exclusive, DeviceObject);
        EdppRuntimeConfig = 0;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        EdppSingleInstanceAttributes = v14 != 0;
        ObjectAttributes.ObjectName = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        result = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
        if ( result >= 0 )
          return PsCreateSystemThread(&qword_1400194D8, 0x1FFFFFu, 0, 0, 0, EdppPolicyUpdateSystemThread, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140038c60  mov     [rsp-8+arg_8], rbx
0x140038c65  push    rbp
0x140038c66  lea     rbp, [rsp-57h]
0x140038c6b  sub     rsp, 0B0h
0x140038c72  xorps   xmm0, xmm0
0x140038c75  mov     [rbp+57h+arg_0], 0
0x140038c7c  lea     rbx, [rcx+8]
0x140038c80  mov     qword ptr [rbp+57h+DeviceName.Length], 2E002Ch
0x140038c88  lea     rax, aDeviceAppidedp; "\\Device\\AppidEDPPlugin"
0x140038c8f  mov     [rsp+0B0h+DeviceObject], rbx; DeviceObject
0x140038c94  mov     [rbp+57h+DeviceName.Buffer], rax
0x140038c98  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x140038c9c  lea     rax, aAppidedpplugin; "\\??\\AppidEDPPlugin"
0x140038ca3  mov     qword ptr [rbp+57h+SymbolicLinkName.Length], 260024h
0x140038cab  mov     [rbp+57h+SymbolicLinkName.Buffer], rax
0x140038caf  lea     rax, aRegistryMachin_7; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x140038cb6  mov     [rbp+57h+var_38], rax
0x140038cba  lea     rax, aSetokensinglet; "SeTokenSingletonAttributesConfig"
0x140038cc1  mov     [rbp+57h+var_48], rax
0x140038cc5  xor     eax, eax
0x140038cc7  mov     cs:EdppAuditSessionLock, rax
0x140038cce  mov     rcx, [rcx]; DriverObject
0x140038cd1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140038cd5  mov     [rsp+0B0h+Exclusive], al; Exclusive
0x140038cd9  lea     r9d, [rax+22h]; DeviceType
0x140038cdd  lea     edx, [rax+1]; DeviceExtensionSize
0x140038ce0  mov     [rbp+57h+var_40], 940092h
0x140038ce8  mov     [rbp+57h+var_50], 420040h
0x140038cf0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140038cf4  mov     [rsp+0B0h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140038cfc  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140038d00  call    cs:__imp_IoCreateDevice
0x140038d07  nop     dword ptr [rax+rax+00h]
0x140038d0c  test    eax, eax
0x140038d0e  js      loc_140038E0E
0x140038d14  mov     rcx, [rbx]
0x140038d17  lea     r8, qword_14000DC88
0x140038d1e  mov     edx, 4
0x140038d23  call    cs:__imp_ObSetSecurityObjectByPointer
0x140038d2a  nop     dword ptr [rax+rax+00h]
0x140038d2f  test    eax, eax
0x140038d31  js      loc_140038E0E
0x140038d37  lea     rdx, [rbp+57h+DeviceName]; DeviceName
0x140038d3b  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x140038d3f  call    cs:__imp_IoCreateSymbolicLink
0x140038d46  nop     dword ptr [rax+rax+00h]
0x140038d4b  test    eax, eax
0x140038d4d  js      loc_140038E0E
0x140038d53  mov     rax, [rbx]
0x140038d56  lea     r9, [rbp+57h+arg_0]
0x140038d5a  lea     r8, [rbp+57h+var_50]
0x140038d5e  lea     rdx, [rbp+57h+var_40]
0x140038d62  mov     byte ptr [rax+40h], 1
0x140038d66  call    AiRegReadDwordValue
0x140038d6b  cmp     [rbp+57h+arg_0], 0
0x140038d6f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140038d73  xorps   xmm0, xmm0
0x140038d76  mov     cs:EdppRuntimeConfig, 0
0x140038d81  mov     r9d, 1; EventType
0x140038d87  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140038d8e  mov     edx, 1F0003h; DesiredAccess
0x140038d93  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140038d9b  lea     rcx, EventHandle; EventHandle
0x140038da2  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140038da9  setnz   cs:EdppSingleInstanceAttributes
0x140038db0  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140038db8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140038dbd  mov     byte ptr [rsp+0B0h+DeviceCharacteristics], 0; InitialState
0x140038dc2  call    cs:__imp_ZwCreateEvent
0x140038dc9  nop     dword ptr [rax+rax+00h]
0x140038dce  test    eax, eax
0x140038dd0  js      short loc_140038E0E
0x140038dd2  lea     rax, EdppPolicyUpdateSystemThread
0x140038dd9  mov     [rsp+0B0h+DeviceObject], 0; StartContext
0x140038de2  mov     qword ptr [rsp+0B0h+Exclusive], rax; StartRoutine
0x140038de7  lea     rcx, qword_1400194D8; ThreadHandle
0x140038dee  xor     r9d, r9d; ProcessHandle
0x140038df1  mov     qword ptr [rsp+0B0h+DeviceCharacteristics], 0; ClientId
0x140038dfa  xor     r8d, r8d; ObjectAttributes
0x140038dfd  mov     edx, 1FFFFFh; DesiredAccess
0x140038e02  call    cs:__imp_PsCreateSystemThread
0x140038e09  nop     dword ptr [rax+rax+00h]
0x140038e0e  mov     rbx, [rsp+0B0h+arg_8]
0x140038e16  add     rsp, 0B0h
0x140038e1d  pop     rbp
0x140038e1e  retn
```
