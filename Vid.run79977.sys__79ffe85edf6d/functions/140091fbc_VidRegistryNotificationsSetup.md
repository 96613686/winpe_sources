# VidRegistryNotificationsSetup

- ea: `0x140091fbc`
- end: `0x14009210d`
- name: `VidRegistryNotificationsSetup`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400835f0`

## callees

- `0x140021db0`
- `0x140021e00`
- `0x14002f724`
- `0x140091fbc`
- `0x1400924f4`
- `0x1400f8640`
- `0x1400fd28c`

## import_xrefs

- `ntoskrnl!ZwCreateEvent` at `0x14009201c`
- `ntoskrnl!ZwCreateEvent` at `0x140092055`
- `ntoskrnl!ZwCreateEvent` at `0x14009201c`
- `ntoskrnl!ZwCreateEvent` at `0x140092055`

## string_xrefs

- `0x1400920e9`: `onecore\vm\vid\sys\driver\vidregistry.c`
- `0x1400920f0`: `VidRegistryNotificationsSetup`

## pseudocode

```c
__int64 VidRegistryNotificationsSetup()
{
  NTSTATUS v0; // ebx
  __int64 v1; // r8
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  memset(&gVidRegistryContext, 0, 0xA8u);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( v0 < 0 )
  {
    v1 = 439;
LABEL_9:
    VidTraceErrorStatusInternal0(
      "VidRegistryNotificationsSetup",
      "onecore\\vm\\vid\\sys\\driver\\vidregistry.c",
      v1,
      (unsigned int)v0);
    VidRegistrypNotificationsTeardownInternal();
    return (unsigned int)v0;
  }
  v0 = ZwCreateEvent(&Handle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
  if ( v0 < 0 )
  {
    v1 = 452;
    goto LABEL_9;
  }
  v0 = VidRegistryOpenParametersKey(&qword_1400653B8);
  if ( v0 < 0 )
  {
    v1 = 459;
    goto LABEL_9;
  }
  KeyHandle = (HANDLE)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1856))(
                        WdfDriverGlobals,
                        qword_1400653B8);
  qword_140065330 = 0;
  v0 = VidThreadCreate(VidRegistrypNotificationRoutine, 0, 0, &gVidRegistryContext, 0);
  if ( v0 < 0 )
  {
    v1 = 478;
    goto LABEL_9;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140091fbc  push    rbx
0x140091fbe  sub     rsp, 60h
0x140091fc2  xor     edx, edx; Val
0x140091fc4  mov     qword ptr [rsp+68h+ObjectAttributes.Length], 30h ; '0'
0x140091fcd  mov     r8d, 0A8h; Size
0x140091fd3  mov     qword ptr [rsp+68h+ObjectAttributes.Attributes], 200h
0x140091fdc  lea     rcx, gVidRegistryContext; void *
0x140091fe3  call    memset
0x140091fe8  xorps   xmm0, xmm0
0x140091feb  mov     [rsp+68h+ObjectAttributes.RootDirectory], 0
0x140091ff4  xor     r9d, r9d; EventType
0x140091ff7  mov     [rsp+68h+ObjectAttributes.ObjectName], 0
0x140092000  lea     r8, [rsp+68h+ObjectAttributes]; ObjectAttributes
0x140092005  mov     [rsp+68h+InitialState], 0; InitialState
0x14009200a  mov     edx, 1F0003h; DesiredAccess
0x14009200f  lea     rcx, EventHandle; EventHandle
0x140092016  movdqu  xmmword ptr [rsp+68h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009201c  call    cs:__imp_ZwCreateEvent
0x140092023  nop     dword ptr [rax+rax+00h]
0x140092028  mov     ebx, eax
0x14009202a  test    eax, eax
0x14009202c  jns     short loc_140092039
0x14009202e  mov     r8d, 1B7h
0x140092034  jmp     loc_1400920E9
0x140092039  mov     r9d, 1; EventType
0x14009203f  mov     [rsp+68h+InitialState], 0; InitialState
0x140092044  lea     r8, [rsp+68h+ObjectAttributes]; ObjectAttributes
0x140092049  mov     edx, 1F0003h; DesiredAccess
0x14009204e  lea     rcx, Handle; EventHandle
0x140092055  call    cs:__imp_ZwCreateEvent
0x14009205c  nop     dword ptr [rax+rax+00h]
0x140092061  mov     ebx, eax
0x140092063  test    eax, eax
0x140092065  jns     short loc_14009206F
0x140092067  mov     r8d, 1C4h
0x14009206d  jmp     short loc_1400920E9
0x14009206f  lea     rcx, qword_1400653B8
0x140092076  call    VidRegistryOpenParametersKey
0x14009207b  mov     ebx, eax
0x14009207d  test    eax, eax
0x14009207f  jns     short loc_140092089
0x140092081  mov     r8d, 1CBh
0x140092087  jmp     short loc_1400920E9
0x140092089  mov     rax, cs:WdfFunctions_01015
0x140092090  mov     rdx, cs:qword_1400653B8
0x140092097  mov     rcx, cs:WdfDriverGlobals
0x14009209e  mov     rax, [rax+740h]
0x1400920a5  call    _guard_dispatch_icall
0x1400920aa  lea     r9, gVidRegistryContext
0x1400920b1  mov     cs:KeyHandle, rax
0x1400920b8  xor     r8d, r8d
0x1400920bb  mov     cs:qword_140065330, 0
0x1400920c6  xor     edx, edx
0x1400920c8  mov     qword ptr [rsp+68h+InitialState], 0
0x1400920d1  lea     rcx, VidRegistrypNotificationRoutine
0x1400920d8  call    VidThreadCreate
0x1400920dd  mov     ebx, eax
0x1400920df  test    eax, eax
0x1400920e1  jns     short loc_140092104
0x1400920e3  mov     r8d, 1DEh
0x1400920e9  lea     rdx, aOnecoreVmVidSy_74; "onecore\\vm\\vid\\sys\\driver\\vidregis"...
0x1400920f0  lea     rcx, aVidregistrynot; "VidRegistryNotificationsSetup"
0x1400920f7  mov     r9d, ebx
0x1400920fa  call    VidTraceErrorStatusInternal0
0x1400920ff  call    VidRegistrypNotificationsTeardownInternal
0x140092104  mov     eax, ebx
0x140092106  add     rsp, 60h
0x14009210a  pop     rbx
0x14009210b  retn
```
