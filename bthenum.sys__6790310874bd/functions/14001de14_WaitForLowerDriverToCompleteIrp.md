# WaitForLowerDriverToCompleteIrp

- ea: `0x14001de14`
- end: `0x14001df23`
- name: `WaitForLowerDriverToCompleteIrp`
- size: `271`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018964`
- `0x140019058`
- `0x14001cf90`
- `0x14001d4fc`

## callees

- `0x140001328`
- `0x14001de14`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14001dea4`
- `ntoskrnl!IofCallDriver` at `0x14001dea4`
- `ntoskrnl!KeInitializeEvent` at `0x14001de44`
- `ntoskrnl!KeInitializeEvent` at `0x14001de44`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001df03`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001df03`

## pseudocode

```c
__int64 __fastcall WaitForLowerDriverToCompleteIrp(PDEVICE_OBJECT DeviceObject, PIRP Irp, char a3)
{
  $77775CA9583EF2DE25120AC31E027D8D *v6; // r8
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v8; // rax
  int v9; // edx
  struct _KEVENT Object; // [rsp+30h] [rbp-28h] BYREF

  memset(&Object, 0, sizeof(Object));
  KeInitializeEvent(&Object, NotificationEvent, 0);
  v6 = &Irp->Tail.Overlay.64;
  if ( a3 )
  {
    CurrentStackLocation = v6->CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&v6->CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
  }
  v8 = v6->CurrentStackLocation;
  v8[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&IoCompletionSetEvent;
  v8[-1].Context = &Object;
  v8[-1].Control = -32;
  if ( IofCallDriver(DeviceObject, Irp) == 259 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        17,
        (__int64)WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids);
    KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
  }
  return (unsigned int)Irp->IoStatus.Status;
}

```

## disassembly

```asm
0x14001de14  mov     r11, rsp
0x14001de17  mov     [r11+8], rbx
0x14001de1b  mov     [r11+10h], rsi
0x14001de1f  push    rdi
0x14001de20  sub     rsp, 50h
0x14001de24  xorps   xmm0, xmm0
0x14001de27  mov     bl, r8b
0x14001de2a  mov     rdi, rdx
0x14001de2d  mov     rsi, rcx
0x14001de30  xor     eax, eax
0x14001de32  lea     rcx, [r11-28h]; Event
0x14001de36  movups  xmmword ptr [rsp+58h+Object.Header.___u0], xmm0
0x14001de3b  xor     r8d, r8d; State
0x14001de3e  mov     [r11-18h], rax
0x14001de42  xor     edx, edx; Type
0x14001de44  call    cs:__imp_KeInitializeEvent
0x14001de4b  nop     dword ptr [rax+rax+00h]
0x14001de50  lea     r8, [rdi+0B8h]
0x14001de57  test    bl, bl
0x14001de59  jz      short loc_14001DE83
0x14001de5b  mov     rax, [r8]
0x14001de5e  movups  xmm0, xmmword ptr [rax]
0x14001de61  movups  xmmword ptr [rax-48h], xmm0
0x14001de65  movups  xmm1, xmmword ptr [rax+10h]
0x14001de69  movups  xmmword ptr [rax-38h], xmm1
0x14001de6d  movups  xmm0, xmmword ptr [rax+20h]
0x14001de71  movups  xmmword ptr [rax-28h], xmm0
0x14001de75  movsd   xmm1, qword ptr [rax+30h]
0x14001de7a  movsd   qword ptr [rax-18h], xmm1
0x14001de7f  mov     byte ptr [rax-45h], 0
0x14001de83  mov     rax, [r8]
0x14001de86  lea     rcx, IoCompletionSetEvent
0x14001de8d  mov     rdx, rdi; Irp
0x14001de90  mov     [rax-10h], rcx
0x14001de94  lea     rcx, [rsp+58h+Object]
0x14001de99  mov     [rax-8], rcx
0x14001de9d  mov     rcx, rsi; DeviceObject
0x14001dea0  mov     byte ptr [rax-45h], 0E0h
0x14001dea4  call    cs:__imp_IofCallDriver
0x14001deab  nop     dword ptr [rax+rax+00h]
0x14001deb0  cmp     eax, 103h
0x14001deb5  jnz     short loc_14001DF0F
0x14001deb7  lea     rax, WPP_RECORDER_INITIALIZED
0x14001debe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dec5  jz      short loc_14001DEED
0x14001dec7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dece  lea     rax, WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids
0x14001ded5  mov     r9d, 11h
0x14001dedb  mov     [rsp+58h+Timeout], rax
0x14001dee0  mov     rcx, [rcx+40h]
0x14001dee4  lea     r8d, [r9-10h]
0x14001dee8  call    WPP_RECORDER_SF_
0x14001deed  xor     r9d, r9d; Alertable
0x14001def0  mov     [rsp+58h+Timeout], 0; Timeout
0x14001def9  xor     r8d, r8d; WaitMode
0x14001defc  lea     rcx, [rsp+58h+Object]; Object
0x14001df01  xor     edx, edx; WaitReason
0x14001df03  call    cs:__imp_KeWaitForSingleObject
0x14001df0a  nop     dword ptr [rax+rax+00h]
0x14001df0f  mov     eax, [rdi+30h]
0x14001df12  mov     rbx, [rsp+58h+arg_0]
0x14001df17  mov     rsi, [rsp+58h+arg_8]
0x14001df1c  add     rsp, 50h
0x14001df20  pop     rdi
0x14001df21  retn
```
