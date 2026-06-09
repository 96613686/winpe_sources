# SrpInitialize

- ea: `0x1400387a4`
- end: `0x140038a4d`
- name: `SrpInitialize`
- size: `681`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003825c`

## callees

- `0x1400016d8`
- `0x140006f40`
- `0x14002318c`
- `0x140023e00`
- `0x140023ee8`
- `0x140036e80`
- `0x1400387a4`

## import_xrefs

- `ntoskrnl!ExCreateCallback` at `0x1400388dd`
- `ntoskrnl!ExCreateCallback` at `0x1400388dd`
- `ntoskrnl!ExRegisterCallback` at `0x140038904`
- `ntoskrnl!ExRegisterCallback` at `0x140038904`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400389e2`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400389e2`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14003899c`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14003899c`
- `ntoskrnl!IoCreateDevice` at `0x14003894b`
- `ntoskrnl!IoCreateDevice` at `0x14003894b`
- `ntoskrnl!EtwRegister` at `0x140038829`
- `ntoskrnl!EtwRegister` at `0x140038829`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003889a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003889a`

## pseudocode

```c
__int64 __fastcall SrpInitialize(PDRIVER_OBJECT DriverObject)
{
  NTSTATUS v2; // ebx
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  struct _UNICODE_STRING DeviceName; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF

  *(_QWORD *)&DeviceName.Length = 2359330;
  *(_QWORD *)&SymbolicLinkName.Length = 1835034;
  DeviceName.Buffer = L"\\Device\\SrpDevice";
  SymbolicLinkName.Buffer = L"\\??\\SrpDevice";
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  memset(&g_Srp, 0, 0x50u);
  g_Srp = 1;
  v2 = EtwRegister(&SrpEventProviderId, 0, 0, &qword_1400196F8);
  if ( v2 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) == 0 )
      goto LABEL_6;
    v4 = 10;
    goto LABEL_5;
  }
  SrppPolicyChangeCallback(0, 0, 0);
  RtlInitUnicodeString(&DestinationString, L"\\Callback\\LicensingData");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 80;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ExCreateCallback((PCALLBACK_OBJECT *)&CallbackObject, &ObjectAttributes, 0, 1u);
  if ( v2 < 0 )
    goto LABEL_6;
  CallbackRegistration = ExRegisterCallback((PCALLBACK_OBJECT)CallbackObject, SrppPolicyChangeCallback, 0);
  if ( !CallbackRegistration )
  {
    v2 = -1073741823;
    goto LABEL_6;
  }
  v2 = IoCreateDevice(DriverObject, 0, &DeviceName, 0x22u, 0x100u, 0, &DeviceObject);
  if ( v2 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_6;
    v4 = 11;
    goto LABEL_5;
  }
  v2 = ObSetSecurityObjectByPointer(DeviceObject, 4, qword_14000C050);
  if ( v2 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_6;
    v4 = 12;
    goto LABEL_5;
  }
  v2 = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
  if ( v2 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_6;
    v4 = 13;
LABEL_5:
    WPP_SF_D(v3->AttachedDevice, v4, WPP_fc098aeb1105362a6314aedfc5617165_Traceguids);
    goto LABEL_6;
  }
  v2 = AipForEachPlugin(AipInitializePluginsCallback, DriverObject);
  if ( v2 >= 0 )
  {
    SrppReadNoPropogtionLogOption();
    dword_1400196F0 = 1;
    return (unsigned int)v2;
  }
LABEL_6:
  SrpCleanup();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400387a4  push    rbp
0x1400387a6  push    rbx
0x1400387a7  push    rdi
0x1400387a8  push    r14
0x1400387aa  lea     rbp, [rsp-3Fh]
0x1400387af  sub     rsp, 0A8h
0x1400387b6  xorps   xmm0, xmm0
0x1400387b9  mov     qword ptr [rbp+57h+DeviceName.Length], 240022h
0x1400387c1  lea     rax, aDeviceSrpdevic; "\\Device\\SrpDevice"
0x1400387c8  mov     qword ptr [rbp+57h+SymbolicLinkName.Length], 1C001Ah
0x1400387d0  mov     [rbp+57h+DeviceName.Buffer], rax
0x1400387d4  mov     rdi, rcx
0x1400387d7  lea     rax, aSrpdevice; "\\??\\SrpDevice"
0x1400387de  mov     r14d, 22h ; '"'
0x1400387e4  mov     [rbp+57h+SymbolicLinkName.Buffer], rax
0x1400387e8  lea     rcx, g_Srp; void *
0x1400387ef  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400387f3  xor     eax, eax
0x1400387f5  xor     edx, edx; Val
0x1400387f7  lea     r8d, [r14+2Eh]; Size
0x1400387fb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400387ff  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140038803  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140038807  call    memset
0x14003880c  lea     r9, qword_1400196F8; RegHandle
0x140038813  mov     cs:g_Srp, 1
0x14003881d  xor     r8d, r8d; CallbackContext
0x140038820  lea     rcx, SrpEventProviderId; ProviderId
0x140038827  xor     edx, edx; EnableCallback
0x140038829  call    cs:__imp_EtwRegister
0x140038830  nop     dword ptr [rax+rax+00h]
0x140038835  mov     ebx, eax
0x140038837  test    eax, eax
0x140038839  jns     short loc_140038883
0x14003883b  mov     rcx, cs:WPP_GLOBAL_Control
0x140038842  lea     rax, WPP_GLOBAL_Control
0x140038849  cmp     rcx, rax
0x14003884c  jz      short loc_14003886E
0x14003884e  test    dword ptr [rcx+2Ch], 200h
0x140038855  jz      short loc_14003886E
0x140038857  lea     edx, [r14-18h]
0x14003885b  mov     rcx, [rcx+18h]
0x14003885f  lea     r8, WPP_fc098aeb1105362a6314aedfc5617165_Traceguids
0x140038866  mov     r9d, ebx
0x140038869  call    WPP_SF_D
0x14003886e  call    SrpCleanup
0x140038873  mov     eax, ebx
0x140038875  add     rsp, 0A8h
0x14003887c  pop     r14
0x14003887e  pop     rdi
0x14003887f  pop     rbx
0x140038880  pop     rbp
0x140038881  retn
0x140038883  xor     r8d, r8d; Argument2
0x140038886  xor     edx, edx; Argument1
0x140038888  xor     ecx, ecx; CallbackContext
0x14003888a  call    SrppPolicyChangeCallback
0x14003888f  lea     rdx, aCallbackLicens; "\\Callback\\LicensingData"
0x140038896  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003889a  call    cs:__imp_RtlInitUnicodeString
0x1400388a1  nop     dword ptr [rax+rax+00h]
0x1400388a6  lea     rax, [rbp+57h+DestinationString]
0x1400388aa  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400388b1  xorps   xmm0, xmm0
0x1400388b4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400388b8  mov     r9b, 1; AllowMultipleCallbacks
0x1400388bb  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400388c3  xor     r8d, r8d; Create
0x1400388c6  mov     [rbp+57h+ObjectAttributes.Attributes], 50h ; 'P'
0x1400388cd  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400388d1  lea     rcx, CallbackObject; CallbackObject
0x1400388d8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400388dd  call    cs:__imp_ExCreateCallback
0x1400388e4  nop     dword ptr [rax+rax+00h]
0x1400388e9  mov     ebx, eax
0x1400388eb  test    eax, eax
0x1400388ed  js      loc_14003886E
0x1400388f3  mov     rcx, cs:CallbackObject; CallbackObject
0x1400388fa  lea     rdx, SrppPolicyChangeCallback; CallbackFunction
0x140038901  xor     r8d, r8d; CallbackContext
0x140038904  call    cs:__imp_ExRegisterCallback
0x14003890b  nop     dword ptr [rax+rax+00h]
0x140038910  mov     cs:CallbackRegistration, rax
0x140038917  test    rax, rax
0x14003891a  jnz     short loc_140038926
0x14003891c  mov     ebx, 0C0000001h
0x140038921  jmp     loc_14003886E
0x140038926  lea     rax, DeviceObject
0x14003892d  mov     r9d, r14d; DeviceType
0x140038930  mov     [rsp+0C0h+DeviceObject], rax; DeviceObject
0x140038935  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x140038939  mov     [rsp+0C0h+Exclusive], 0; Exclusive
0x14003893e  xor     edx, edx; DeviceExtensionSize
0x140038940  mov     rcx, rdi; DriverObject
0x140038943  mov     [rsp+0C0h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14003894b  call    cs:__imp_IoCreateDevice
0x140038952  nop     dword ptr [rax+rax+00h]
0x140038957  mov     ebx, eax
0x140038959  test    eax, eax
0x14003895b  jns     short loc_140038989
0x14003895d  mov     rcx, cs:WPP_GLOBAL_Control
0x140038964  lea     rax, WPP_GLOBAL_Control
0x14003896b  cmp     rcx, rax
0x14003896e  jz      loc_14003886E
0x140038974  mov     eax, [rcx+2Ch]
0x140038977  test    al, 1
0x140038979  jz      loc_14003886E
0x14003897f  mov     edx, 0Bh
0x140038984  jmp     loc_14003885B
0x140038989  mov     rcx, cs:DeviceObject
0x140038990  lea     r8, qword_14000C050
0x140038997  mov     edx, 4
0x14003899c  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400389a3  nop     dword ptr [rax+rax+00h]
0x1400389a8  mov     ebx, eax
0x1400389aa  test    eax, eax
0x1400389ac  jns     short loc_1400389DA
0x1400389ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400389b5  lea     rax, WPP_GLOBAL_Control
0x1400389bc  cmp     rcx, rax
0x1400389bf  jz      loc_14003886E
0x1400389c5  mov     eax, [rcx+2Ch]
0x1400389c8  test    al, 1
0x1400389ca  jz      loc_14003886E
0x1400389d0  mov     edx, 0Ch
0x1400389d5  jmp     loc_14003885B
0x1400389da  lea     rdx, [rbp+57h+DeviceName]; DeviceName
0x1400389de  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x1400389e2  call    cs:__imp_IoCreateSymbolicLink
0x1400389e9  nop     dword ptr [rax+rax+00h]
0x1400389ee  mov     ebx, eax
0x1400389f0  test    eax, eax
0x1400389f2  jns     short loc_140038A20
0x1400389f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400389fb  lea     rax, WPP_GLOBAL_Control
0x140038a02  cmp     rcx, rax
0x140038a05  jz      loc_14003886E
0x140038a0b  mov     eax, [rcx+2Ch]
0x140038a0e  test    al, 1
0x140038a10  jz      loc_14003886E
0x140038a16  mov     edx, 0Dh
0x140038a1b  jmp     loc_14003885B
0x140038a20  mov     rdx, rdi
0x140038a23  lea     rcx, AipInitializePluginsCallback
0x140038a2a  call    AipForEachPlugin
0x140038a2f  mov     ebx, eax
0x140038a31  test    eax, eax
0x140038a33  js      loc_14003886E
0x140038a39  call    SrppReadNoPropogtionLogOption
0x140038a3e  mov     cs:dword_1400196F0, 1
0x140038a48  jmp     loc_140038873
```
