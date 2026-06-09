# NsiContainerTerminateCallback

- ea: `0x1400a9e30`
- end: `0x1400a9f0d`
- name: `NsiContainerTerminateCallback`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14005edec`
- `0x1400a9e30`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400a9eb9`
- `ntoskrnl!KeInitializeEvent` at `0x1400a9eb9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a9efa`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a9efa`
- `ntoskrnl!PsRemoveSiloContext` at `0x1400a9e5f`
- `ntoskrnl!PsRemoveSiloContext` at `0x1400a9e5f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400a9e85`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400a9e85`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x1400a9e49`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x1400a9e49`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400a9ea1`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400a9ea1`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400a9ed8`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400a9ed8`

## pseudocode

```c
NTSTATUS __fastcall NsiContainerTerminateCallback(__int64 a1)
{
  unsigned int SiloMonitorContextSlot; // eax
  NTSTATUS result; // eax
  __int64 v4; // rbx
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF
  __int64 v6; // [rsp+68h] [rbp+10h] BYREF

  v6 = 0;
  SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(NsiContainerMonitor);
  result = PsRemoveSiloContext(a1, SiloMonitorContextSlot, &v6);
  if ( result >= 0 )
  {
    memset(&Event, 0, sizeof(Event));
    v4 = PsAttachSiloToCurrentThread(a1);
    NsipRpcDisconnect(v6);
    PsDetachSiloFromCurrentThread(v4);
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    *(_QWORD *)(v6 + 48) = &Event;
    PsDereferenceSiloContext(v6);
    return KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1400a9e30  push    rbx
0x1400a9e32  sub     rsp, 50h
0x1400a9e36  mov     rbx, rcx
0x1400a9e39  mov     [rsp+58h+arg_8], 0
0x1400a9e42  mov     rcx, cs:NsiContainerMonitor
0x1400a9e49  call    cs:__imp_PsGetSiloMonitorContextSlot
0x1400a9e50  nop     dword ptr [rax+rax+00h]
0x1400a9e55  lea     r8, [rsp+58h+arg_8]
0x1400a9e5a  mov     rcx, rbx
0x1400a9e5d  mov     edx, eax
0x1400a9e5f  call    cs:__imp_PsRemoveSiloContext
0x1400a9e66  nop     dword ptr [rax+rax+00h]
0x1400a9e6b  test    eax, eax
0x1400a9e6d  js      loc_1400A9F06
0x1400a9e73  xorps   xmm0, xmm0
0x1400a9e76  xor     eax, eax
0x1400a9e78  mov     rcx, rbx
0x1400a9e7b  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x1400a9e80  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x1400a9e85  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400a9e8c  nop     dword ptr [rax+rax+00h]
0x1400a9e91  mov     rcx, [rsp+58h+arg_8]
0x1400a9e96  mov     rbx, rax
0x1400a9e99  call    NsipRpcDisconnect
0x1400a9e9e  mov     rcx, rbx
0x1400a9ea1  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400a9ea8  nop     dword ptr [rax+rax+00h]
0x1400a9ead  xor     r8d, r8d; State
0x1400a9eb0  lea     rcx, [rsp+58h+Event]; Event
0x1400a9eb5  lea     edx, [r8+1]; Type
0x1400a9eb9  call    cs:__imp_KeInitializeEvent
0x1400a9ec0  nop     dword ptr [rax+rax+00h]
0x1400a9ec5  mov     rax, [rsp+58h+arg_8]
0x1400a9eca  lea     rcx, [rsp+58h+Event]
0x1400a9ecf  mov     [rax+30h], rcx
0x1400a9ed3  mov     rcx, [rsp+58h+arg_8]
0x1400a9ed8  call    cs:__imp_PsDereferenceSiloContext
0x1400a9edf  nop     dword ptr [rax+rax+00h]
0x1400a9ee4  xor     r9d, r9d; Alertable
0x1400a9ee7  mov     [rsp+58h+Timeout], 0; Timeout
0x1400a9ef0  xor     r8d, r8d; WaitMode
0x1400a9ef3  lea     rcx, [rsp+58h+Event]; Object
0x1400a9ef8  xor     edx, edx; WaitReason
0x1400a9efa  call    cs:__imp_KeWaitForSingleObject
0x1400a9f01  nop     dword ptr [rax+rax+00h]
0x1400a9f06  add     rsp, 50h
0x1400a9f0a  pop     rbx
0x1400a9f0b  retn
```
