# SidebandAudioWdmDevice::SidebandAudioWdmDevice(ushort const *,ushort const *)

- ea: `0x140086800`
- end: `0x140086940`
- name: `??0SidebandAudioWdmDevice@@QEAA@PEBG0@Z`
- size: `320`
- prototype: `SidebandAudioWdmDevice *__fastcall(SidebandAudioWdmDevice *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14007d3b8`

## callees

- `0x140037714`
- `0x1400891ec`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14008690b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086925`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008690b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086925`
- `ntoskrnl!KeInitializeEvent` at `0x140086853`
- `ntoskrnl!KeInitializeEvent` at `0x1400868e3`
- `ntoskrnl!KeInitializeEvent` at `0x140086853`
- `ntoskrnl!KeInitializeEvent` at `0x1400868e3`
- `ntoskrnl!KeInitializeSpinLock` at `0x140086826`
- `ntoskrnl!KeInitializeSpinLock` at `0x140086826`

## string_xrefs

- `0x140086904`: `A2DP_SIDEBAND_INTERFACE`
- `0x14008691e`: `\A2DP_SIDEBAND_INTERFACE`

## pseudocode

```c
SidebandAudioWdmDevice *__fastcall SidebandAudioWdmDevice::SidebandAudioWdmDevice(
        SidebandAudioWdmDevice *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  *(_QWORD *)this = &SidebandAudioWdmDevice::`vftable'{for `IrpDispatcher'};
  *((_QWORD *)this + 1) = &SidebandAudioWdmDevice::`vftable'{for `SidebandAudioDevice'};
  KeInitializeSpinLock((PKSPIN_LOCK)this + 2);
  *((_DWORD *)this + 6) = 1;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  KeInitializeEvent((PRKEVENT)this + 2, SynchronizationEvent, 0);
  *((_BYTE *)this + 80) = 1;
  *((_QWORD *)this + 11) = -1;
  *((_QWORD *)this + 12) = -1;
  *((_QWORD *)this + 13) = -1;
  *((_QWORD *)this + 14) = (char *)this + 112;
  *((_QWORD *)this + 15) = (char *)this + 112;
  *((_QWORD *)this + 16) = 0;
  CsQueue::CsQueue((SidebandAudioWdmDevice *)((char *)this + 136));
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 17) = &CsDispatchQueue::`vftable';
  wil::details::kernel_event_t<1>::kernel_event_t<1>((char *)this + 280);
  *((_DWORD *)this + 84) = 1;
  *((_QWORD *)this + 43) = 0;
  *((_DWORD *)this + 88) = 0;
  KeInitializeEvent((PRKEVENT)this + 15, SynchronizationEvent, 0);
  *((_QWORD *)this + 49) = &utl::_FuncEmpty<void,_IRP *>::`vftable';
  RtlInitUnicodeString((PUNICODE_STRING)((char *)this + 424), L"A2DP_SIDEBAND_INTERFACE");
  RtlInitUnicodeString((PUNICODE_STRING)((char *)this + 440), L"\\A2DP_SIDEBAND_INTERFACE");
  return this;
}

```

## disassembly

```asm
0x140086800  mov     [rsp+arg_0], rbx
0x140086805  push    rdi
0x140086806  sub     rsp, 20h
0x14008680a  lea     rax, ??_7SidebandAudioWdmDevice@@6BIrpDispatcher@@@; const SidebandAudioWdmDevice::`vftable'{for `IrpDispatcher'}
0x140086811  mov     rdi, rcx
0x140086814  mov     [rcx], rax
0x140086817  lea     rax, ??_7SidebandAudioWdmDevice@@6BSidebandAudioDevice@@@; const SidebandAudioWdmDevice::`vftable'{for `SidebandAudioDevice'}
0x14008681e  mov     [rcx+8], rax
0x140086822  add     rcx, 10h; SpinLock
0x140086826  call    cs:__imp_KeInitializeSpinLock
0x14008682d  nop     dword ptr [rax+rax+00h]
0x140086832  xor     r8d, r8d; State
0x140086835  mov     dword ptr [rdi+18h], 1
0x14008683c  lea     rcx, [rdi+30h]; Event
0x140086840  mov     qword ptr [rdi+20h], 0
0x140086848  mov     dword ptr [rdi+28h], 0
0x14008684f  lea     edx, [r8+1]; Type
0x140086853  call    cs:__imp_KeInitializeEvent
0x14008685a  nop     dword ptr [rax+rax+00h]
0x14008685f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140086863  mov     byte ptr [rdi+50h], 1
0x140086867  mov     [rdi+58h], rax
0x14008686b  lea     rbx, [rdi+88h]
0x140086872  mov     [rdi+60h], rax
0x140086876  mov     rcx, rbx; this
0x140086879  mov     [rdi+68h], rax
0x14008687d  lea     rax, [rdi+70h]
0x140086881  mov     [rax], rax
0x140086884  mov     [rax+8], rax
0x140086888  mov     qword ptr [rax+10h], 0
0x140086890  call    ??0CsQueue@@QEAA@XZ; CsQueue::CsQueue(void)
0x140086895  lea     rax, ??_7CsDispatchQueue@@6B@; const CsDispatchQueue::`vftable'
0x14008689c  mov     qword ptr [rbx+88h], 0
0x1400868a7  lea     rcx, [rbx+90h]
0x1400868ae  mov     [rbx], rax
0x1400868b1  call    ??0?$kernel_event_t@$00@details@wil@@QEAA@_N@Z; wil::details::kernel_event_t<1>::kernel_event_t<1>(bool)
0x1400868b6  xor     r8d, r8d; State
0x1400868b9  mov     dword ptr [rbx+0C8h], 1
0x1400868c3  lea     rcx, [rbx+0E0h]; Event
0x1400868ca  mov     qword ptr [rbx+0D0h], 0
0x1400868d5  mov     dword ptr [rbx+0D8h], 0
0x1400868df  lea     edx, [r8+1]; Type
0x1400868e3  call    cs:__imp_KeInitializeEvent
0x1400868ea  nop     dword ptr [rax+rax+00h]
0x1400868ef  lea     rax, ??_7?$_FuncEmpty@XPEAU_IRP@@@utl@@6B@; const utl::_FuncEmpty<void,_IRP *>::`vftable'
0x1400868f6  lea     rcx, [rdi+1A8h]; DestinationString
0x1400868fd  mov     [rbx+100h], rax
0x140086904  lea     rdx, aA2dpSidebandIn_0; "A2DP_SIDEBAND_INTERFACE"
0x14008690b  call    cs:__imp_RtlInitUnicodeString
0x140086912  nop     dword ptr [rax+rax+00h]
0x140086917  lea     rcx, [rdi+1B8h]; DestinationString
0x14008691e  lea     rdx, aA2dpSidebandIn; "\\A2DP_SIDEBAND_INTERFACE"
0x140086925  call    cs:__imp_RtlInitUnicodeString
0x14008692c  nop     dword ptr [rax+rax+00h]
0x140086931  mov     rbx, [rsp+28h+arg_0]
0x140086936  mov     rax, rdi
0x140086939  add     rsp, 20h
0x14008693d  pop     rdi
0x14008693e  retn
```
