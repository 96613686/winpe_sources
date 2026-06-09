# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::RemoveCompletedScoRequest(Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *)

- ea: `0x140016294`
- end: `0x140016316`
- name: `?RemoveCompletedScoRequest@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXPEAVRequestContext@23456@@Z`
- size: `130`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *__hidden this, struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002db70`

## callees

- `0x14001ae00`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::RemoveCompletedScoRequest(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *this,
        struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *a2)
{
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2528))(
    WdfDriverGlobals,
    *((_QWORD *)this + 29));
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 128))(
    WdfDriverGlobals,
    *((_QWORD *)this + 30),
    *(_QWORD *)a2);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2536))(
    WdfDriverGlobals,
    *((_QWORD *)this + 29));
}

```

## disassembly

```asm
0x140016294  mov     [rsp+arg_0], rbx
0x140016299  push    rdi
0x14001629a  sub     rsp, 20h
0x14001629e  mov     rax, cs:WdfFunctions_01015
0x1400162a5  mov     rbx, rdx
0x1400162a8  mov     rdx, [rcx+0E8h]
0x1400162af  mov     rdi, rcx
0x1400162b2  mov     rcx, cs:WdfDriverGlobals
0x1400162b9  mov     rax, [rax+9E0h]
0x1400162c0  call    _guard_dispatch_icall
0x1400162c5  mov     rax, cs:WdfFunctions_01015
0x1400162cc  mov     r8, [rbx]
0x1400162cf  mov     rdx, [rdi+0F0h]
0x1400162d6  mov     rcx, cs:WdfDriverGlobals
0x1400162dd  mov     rax, [rax+80h]
0x1400162e4  call    _guard_dispatch_icall
0x1400162e9  mov     rax, cs:WdfFunctions_01015
0x1400162f0  mov     rdx, [rdi+0E8h]
0x1400162f7  mov     rcx, cs:WdfDriverGlobals
0x1400162fe  mov     rax, [rax+9E8h]
0x140016305  call    _guard_dispatch_icall
0x14001630a  mov     rbx, [rsp+28h+arg_0]
0x14001630f  add     rsp, 20h
0x140016313  pop     rdi
0x140016314  retn
```
