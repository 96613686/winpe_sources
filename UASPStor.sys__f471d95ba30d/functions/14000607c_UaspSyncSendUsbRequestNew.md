# UaspSyncSendUsbRequestNew

- ea: `0x14000607c`
- end: `0x1400061ec`
- name: `UaspSyncSendUsbRequestNew`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001154`
- `0x140002130`
- `0x140005944`
- `0x1400061f4`
- `0x140006690`

## callees

- `0x14000607c`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1400061c8`
- `ntoskrnl!IoFreeIrp` at `0x1400061c8`
- `ntoskrnl!KeInitializeEvent` at `0x1400060b3`
- `ntoskrnl!KeInitializeEvent` at `0x1400060b3`
- `ntoskrnl!IofCallDriver` at `0x140006142`
- `ntoskrnl!IofCallDriver` at `0x140006142`
- `ntoskrnl!IoCancelIrp` at `0x140006192`
- `ntoskrnl!IoCancelIrp` at `0x140006192`
- `ntoskrnl!IoAllocateIrp` at `0x1400060c5`
- `ntoskrnl!IoAllocateIrp` at `0x1400060c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006177`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400061b4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006177`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400061b4`

## pseudocode

```c
__int64 __fastcall UaspSyncSendUsbRequestNew(__int64 a1, struct _DEVICE_OBJECT *a2, struct _FILE_OBJECT *a3, char a4)
{
  PIRP Irp; // rax
  IRP *v9; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _IO_STACK_LOCATION *v12; // rax
  unsigned int Status; // edi
  struct _KEVENT Object; // [rsp+30h] [rbp-38h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+78h] [rbp+10h] BYREF

  memset(&Object, 0, sizeof(Object));
  KeInitializeEvent(&Object, SynchronizationEvent, 0);
  Irp = IoAllocateIrp(a2->StackSize, 0);
  v9 = Irp;
  if ( !Irp )
    return 3221225626LL;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
  if ( a4 && (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 1272) + 216LL) - 1538) <= 0xFFFFF9FC )
    CurrentStackLocation[-1].FileObject = a3;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)a3;
  v12 = Irp->Tail.Overlay.CurrentStackLocation;
  v12[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)USBD_SyncCompletionRoutine;
  v12[-1].Context = &Object;
  v12[-1].Control = -32;
  Status = IofCallDriver(a2, v9);
  if ( Status == 259 )
  {
    Timeout.QuadPart = -50000000;
    if ( KeWaitForSingleObject(&Object, Executive, 0, 0, &Timeout) == 258 )
    {
      Status = -1073741643;
      IoCancelIrp(v9);
      KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
    }
    else
    {
      Status = v9->IoStatus.Status;
    }
  }
  IoFreeIrp(v9);
  return Status;
}

```

## disassembly

```asm
0x14000607c  mov     r11, rsp
0x14000607f  mov     [r11+8], rbx
0x140006083  mov     [r11+18h], rbp
0x140006087  push    rsi
0x140006088  push    rdi
0x140006089  push    r14
0x14000608b  sub     rsp, 50h
0x14000608f  xor     eax, eax
0x140006091  xorps   xmm0, xmm0
0x140006094  mov     rdi, r8
0x140006097  mov     r14, rdx
0x14000609a  mov     rbp, rcx
0x14000609d  xor     r8d, r8d; State
0x1400060a0  movups  xmmword ptr [rsp+68h+Object.Header], xmm0
0x1400060a5  lea     edx, [rax+1]; Type
0x1400060a8  mov     [r11-28h], rax
0x1400060ac  lea     rcx, [r11-38h]; Event
0x1400060b0  mov     sil, r9b
0x1400060b3  call    cs:__imp_KeInitializeEvent
0x1400060ba  nop     dword ptr [rax+rax+00h]
0x1400060bf  mov     cl, [r14+4Ch]; StackSize
0x1400060c3  xor     edx, edx; ChargeQuota
0x1400060c5  call    cs:__imp_IoAllocateIrp
0x1400060cc  nop     dword ptr [rax+rax+00h]
0x1400060d1  mov     rbx, rax
0x1400060d4  test    rax, rax
0x1400060d7  jnz     short loc_1400060E3
0x1400060d9  mov     eax, 0C000009Ah
0x1400060de  jmp     loc_1400061D6
0x1400060e3  mov     rdx, [rax+0B8h]
0x1400060ea  mov     byte ptr [rdx-48h], 0Fh
0x1400060ee  mov     dword ptr [rdx-30h], 220003h
0x1400060f5  test    sil, sil
0x1400060f8  jz      short loc_140006119
0x1400060fa  mov     rax, [rbp+4F8h]
0x140006101  mov     ecx, [rax+0D8h]
0x140006107  sub     ecx, 602h
0x14000610d  cmp     ecx, 0FFFFF9FCh
0x140006113  ja      short loc_140006119
0x140006115  mov     [rdx-18h], rdi
0x140006119  mov     [rdx-40h], rdi
0x14000611d  lea     rcx, USBD_SyncCompletionRoutine
0x140006124  mov     rax, [rbx+0B8h]
0x14000612b  mov     rdx, rbx; Irp
0x14000612e  mov     [rax-10h], rcx
0x140006132  lea     rcx, [rsp+68h+Object]
0x140006137  mov     [rax-8], rcx
0x14000613b  mov     rcx, r14; DeviceObject
0x14000613e  mov     byte ptr [rax-45h], 0E0h
0x140006142  call    cs:__imp_IofCallDriver
0x140006149  nop     dword ptr [rax+rax+00h]
0x14000614e  mov     edi, eax
0x140006150  cmp     eax, 103h
0x140006155  jnz     short loc_1400061C5
0x140006157  lea     rax, [rsp+68h+arg_8]
0x14000615c  mov     qword ptr [rsp+68h+arg_8], 0FFFFFFFFFD050F80h
0x140006165  xor     r9d, r9d; Alertable
0x140006168  mov     [rsp+68h+Timeout], rax; Timeout
0x14000616d  xor     r8d, r8d; WaitMode
0x140006170  lea     rcx, [rsp+68h+Object]; Object
0x140006175  xor     edx, edx; WaitReason
0x140006177  call    cs:__imp_KeWaitForSingleObject
0x14000617e  nop     dword ptr [rax+rax+00h]
0x140006183  cmp     eax, 102h
0x140006188  jnz     short loc_1400061C2
0x14000618a  mov     rcx, rbx; Irp
0x14000618d  mov     edi, 0C00000B5h
0x140006192  call    cs:__imp_IoCancelIrp
0x140006199  nop     dword ptr [rax+rax+00h]
0x14000619e  xor     r9d, r9d; Alertable
0x1400061a1  mov     [rsp+68h+Timeout], 0; Timeout
0x1400061aa  xor     r8d, r8d; WaitMode
0x1400061ad  lea     rcx, [rsp+68h+Object]; Object
0x1400061b2  xor     edx, edx; WaitReason
0x1400061b4  call    cs:__imp_KeWaitForSingleObject
0x1400061bb  nop     dword ptr [rax+rax+00h]
0x1400061c0  jmp     short loc_1400061C5
0x1400061c2  mov     edi, [rbx+30h]
0x1400061c5  mov     rcx, rbx; Irp
0x1400061c8  call    cs:__imp_IoFreeIrp
0x1400061cf  nop     dword ptr [rax+rax+00h]
0x1400061d4  mov     eax, edi
0x1400061d6  lea     r11, [rsp+68h+var_18]
0x1400061db  mov     rbx, [r11+20h]
0x1400061df  mov     rbp, [r11+30h]
0x1400061e3  mov     rsp, r11
0x1400061e6  pop     r14
0x1400061e8  pop     rdi
0x1400061e9  pop     rsi
0x1400061ea  retn
```
