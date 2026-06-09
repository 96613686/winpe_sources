# USBSTOR_GetBusInterface

- ea: `0x140028098`
- end: `0x140028251`
- name: `USBSTOR_GetBusInterface`
- size: `441`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008590`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x140013d40`
- `0x140028098`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400281a5`
- `ntoskrnl!IoFreeIrp` at `0x140028201`
- `ntoskrnl!IoFreeIrp` at `0x1400281a5`
- `ntoskrnl!IoFreeIrp` at `0x140028201`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140028192`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140028192`
- `ntoskrnl!IofCallDriver` at `0x1400281c4`
- `ntoskrnl!IofCallDriver` at `0x1400281c4`
- `ntoskrnl!KeInitializeEvent` at `0x14002813a`
- `ntoskrnl!KeInitializeEvent` at `0x14002813a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400281ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400281ef`
- `ntoskrnl!IoAllocateIrp` at `0x140028111`
- `ntoskrnl!IoAllocateIrp` at `0x140028111`

## pseudocode

```c
__int64 __fastcall USBSTOR_GetBusInterface(PDEVICE_OBJECT DeviceObject, void *a2)
{
  PVOID DeviceExtension; // rdi
  PIRP Irp; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int Status; // edi
  struct _KEVENT Event; // [rsp+40h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 170, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  DeviceExtension = DeviceObject->DeviceExtension;
  memset(a2, 0, 0x48u);
  Irp = IoAllocateIrp(*(_BYTE *)(*((_QWORD *)DeviceExtension + 3) + 76LL), 0);
  if ( !Irp )
    return 3221225626LL;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)&USB_BUS_INTERFACE_USBDI_GUID;
  *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 2075;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)a2;
  CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
  CurrentStackLocation[-1].Parameters.Create.Options = 65608;
  if ( IoSetCompletionRoutineEx(DeviceObject, Irp, USBSTOR_SyncCompletionRoutine, &Event, 1u, 1u, 1u) < 0 )
  {
    IoFreeIrp(Irp);
    return 3221225626LL;
  }
  Irp->IoStatus.Status = -1073741637;
  Status = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), Irp);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = Irp->IoStatus.Status;
  }
  IoFreeIrp(Irp);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 171, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  return Status;
}

```

## disassembly

```asm
0x140028098  push    rbx
0x14002809a  push    rbp
0x14002809b  push    rsi
0x14002809c  push    rdi
0x14002809d  push    r12
0x14002809f  push    r14
0x1400280a1  push    r15
0x1400280a3  sub     rsp, 60h
0x1400280a7  xorps   xmm0, xmm0
0x1400280aa  xor     eax, eax
0x1400280ac  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x1400280b1  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x1400280b6  mov     rsi, rdx
0x1400280b9  mov     rbp, rcx
0x1400280bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400280c3  lea     r15, WPP_GLOBAL_Control
0x1400280ca  lea     r14d, [rax+1]
0x1400280ce  cmp     rcx, r15
0x1400280d1  jz      short loc_1400280F6
0x1400280d3  mov     eax, [rcx+2Ch]
0x1400280d6  test    r14b, al
0x1400280d9  jz      short loc_1400280F6
0x1400280db  cmp     byte ptr [rcx+29h], 4
0x1400280df  jb      short loc_1400280F6
0x1400280e1  mov     rcx, [rcx+18h]
0x1400280e5  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400280ec  mov     edx, 0AAh
0x1400280f1  call    WPP_SF_
0x1400280f6  mov     rdi, [rbp+40h]
0x1400280fa  xor     edx, edx; Val
0x1400280fc  mov     rcx, rsi; void *
0x1400280ff  lea     r8d, [rdx+48h]; Size
0x140028103  call    memset
0x140028108  mov     rcx, [rdi+18h]
0x14002810c  xor     edx, edx; ChargeQuota
0x14002810e  mov     cl, [rcx+4Ch]; StackSize
0x140028111  call    cs:__imp_IoAllocateIrp
0x140028118  nop     dword ptr [rax+rax+00h]
0x14002811d  mov     rbx, rax
0x140028120  test    rax, rax
0x140028123  jnz     short loc_14002812F
0x140028125  mov     eax, 0C000009Ah
0x14002812a  jmp     loc_140028241
0x14002812f  xor     r8d, r8d; State
0x140028132  lea     rcx, [rsp+98h+Event]; Event
0x140028137  mov     edx, r14d; Type
0x14002813a  call    cs:__imp_KeInitializeEvent
0x140028141  nop     dword ptr [rax+rax+00h]
0x140028146  mov     rax, [rbx+0B8h]
0x14002814d  lea     rcx, USB_BUS_INTERFACE_USBDI_GUID
0x140028154  mov     [rsp+98h+InvokeOnCancel], r14b; InvokeOnCancel
0x140028159  lea     r9, [rsp+98h+Event]; Context
0x14002815e  mov     [rsp+98h+InvokeOnError], r14b; InvokeOnError
0x140028163  lea     r8, USBSTOR_SyncCompletionRoutine; CompletionRoutine
0x14002816a  mov     rdx, rbx; Irp
0x14002816d  mov     [rsp+98h+InvokeOnSuccess], r14b; InvokeOnSuccess
0x140028172  mov     [rax-40h], rcx
0x140028176  mov     rcx, rbp; DeviceObject
0x140028179  mov     word ptr [rax-48h], 81Bh
0x14002817f  mov     [rax-30h], rsi
0x140028183  mov     qword ptr [rax-28h], 0
0x14002818b  mov     dword ptr [rax-38h], 10048h
0x140028192  call    cs:__imp_IoSetCompletionRoutineEx
0x140028199  nop     dword ptr [rax+rax+00h]
0x14002819e  test    eax, eax
0x1400281a0  jns     short loc_1400281B6
0x1400281a2  mov     rcx, rbx; Irp
0x1400281a5  call    cs:__imp_IoFreeIrp
0x1400281ac  nop     dword ptr [rax+rax+00h]
0x1400281b1  jmp     loc_140028125
0x1400281b6  mov     dword ptr [rbx+30h], 0C00000BBh
0x1400281bd  mov     rdx, rbx; Irp
0x1400281c0  mov     rcx, [rdi+18h]; DeviceObject
0x1400281c4  call    cs:__imp_IofCallDriver
0x1400281cb  nop     dword ptr [rax+rax+00h]
0x1400281d0  mov     edi, eax
0x1400281d2  cmp     eax, 103h
0x1400281d7  jnz     short loc_1400281FE
0x1400281d9  xor     r9d, r9d; Alertable
0x1400281dc  mov     qword ptr [rsp+98h+InvokeOnSuccess], 0; Timeout
0x1400281e5  xor     r8d, r8d; WaitMode
0x1400281e8  lea     rcx, [rsp+98h+Event]; Object
0x1400281ed  xor     edx, edx; WaitReason
0x1400281ef  call    cs:__imp_KeWaitForSingleObject
0x1400281f6  nop     dword ptr [rax+rax+00h]
0x1400281fb  mov     edi, [rbx+30h]
0x1400281fe  mov     rcx, rbx; Irp
0x140028201  call    cs:__imp_IoFreeIrp
0x140028208  nop     dword ptr [rax+rax+00h]
0x14002820d  mov     rcx, cs:WPP_GLOBAL_Control
0x140028214  cmp     rcx, r15
0x140028217  jz      short loc_14002823F
0x140028219  mov     eax, [rcx+2Ch]
0x14002821c  test    r14b, al
0x14002821f  jz      short loc_14002823F
0x140028221  cmp     byte ptr [rcx+29h], 4
0x140028225  jb      short loc_14002823F
0x140028227  mov     rcx, [rcx+18h]
0x14002822b  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140028232  mov     edx, 0ABh
0x140028237  mov     r9d, edi
0x14002823a  call    WPP_SF_d
0x14002823f  mov     eax, edi
0x140028241  add     rsp, 60h
0x140028245  pop     r15
0x140028247  pop     r14
0x140028249  pop     r12
0x14002824b  pop     rdi
0x14002824c  pop     rsi
0x14002824d  pop     rbp
0x14002824e  pop     rbx
0x14002824f  retn
```
