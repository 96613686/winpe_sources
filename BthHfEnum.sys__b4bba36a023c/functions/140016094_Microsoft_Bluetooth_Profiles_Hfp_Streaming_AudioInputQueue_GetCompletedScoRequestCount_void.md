# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::GetCompletedScoRequestCount(void)

- ea: `0x140016094`
- end: `0x140016111`
- name: `?GetCompletedScoRequestCount@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAKXZ`
- size: `125`
- prototype: `unsigned int __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002db70`

## callees

- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::GetCompletedScoRequestCount(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *this)
{
  unsigned int v2; // ebx

  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2528))(
    WdfDriverGlobals,
    *((_QWORD *)this + 29));
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 112))(
         WdfDriverGlobals,
         *((_QWORD *)this + 30));
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2536))(
    WdfDriverGlobals,
    *((_QWORD *)this + 29));
  return v2;
}

```

## disassembly

```asm
0x140016094  mov     [rsp+arg_0], rbx
0x140016099  push    rdi
0x14001609a  sub     rsp, 20h
0x14001609e  mov     rax, cs:WdfFunctions_01015
0x1400160a5  mov     rdi, rcx
0x1400160a8  mov     rdx, [rcx+0E8h]
0x1400160af  mov     rcx, cs:WdfDriverGlobals
0x1400160b6  mov     rax, [rax+9E0h]
0x1400160bd  call    _guard_dispatch_icall
0x1400160c2  mov     rax, cs:WdfFunctions_01015
0x1400160c9  mov     rdx, [rdi+0F0h]
0x1400160d0  mov     rcx, cs:WdfDriverGlobals
0x1400160d7  mov     rax, [rax+70h]
0x1400160db  call    _guard_dispatch_icall
0x1400160e0  mov     rcx, cs:WdfFunctions_01015
0x1400160e7  mov     ebx, eax
0x1400160e9  mov     rdx, [rdi+0E8h]
0x1400160f0  mov     rax, [rcx+9E8h]
0x1400160f7  mov     rcx, cs:WdfDriverGlobals
0x1400160fe  call    _guard_dispatch_icall
0x140016103  mov     eax, ebx
0x140016105  mov     rbx, [rsp+28h+arg_0]
0x14001610a  add     rsp, 20h
0x14001610e  pop     rdi
0x14001610f  retn
```
