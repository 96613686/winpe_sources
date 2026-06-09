# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::GetFirstCompletedScoRequest(void)

- ea: `0x14001614c`
- end: `0x1400161f2`
- name: `?GetFirstCompletedScoRequest@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAPEAVRequestContext@23456@XZ`
- size: `166`
- prototype: `struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *__fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002db70`

## callees

- `0x14001ae00`

## pseudocode

```c
struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *__fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::GetFirstCompletedScoRequest(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *this)
{
  __int64 v2; // rax
  __int64 v3; // rbx

  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2528))(
    WdfDriverGlobals,
    *((_QWORD *)this + 29));
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 152))(
         WdfDriverGlobals,
         *((_QWORD *)this + 30));
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         v2,
         off_140022500);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2536))(
    WdfDriverGlobals,
    *((_QWORD *)this + 29));
  return (struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *)v3;
}

```

## disassembly

```asm
0x14001614c  mov     [rsp+arg_0], rbx
0x140016151  push    rdi
0x140016152  sub     rsp, 20h
0x140016156  mov     rax, cs:WdfFunctions_01015
0x14001615d  mov     rdi, rcx
0x140016160  mov     rdx, [rcx+0E8h]
0x140016167  mov     rcx, cs:WdfDriverGlobals
0x14001616e  mov     rax, [rax+9E0h]
0x140016175  call    _guard_dispatch_icall
0x14001617a  mov     rax, cs:WdfFunctions_01015
0x140016181  mov     rdx, [rdi+0F0h]
0x140016188  mov     rcx, cs:WdfDriverGlobals
0x14001618f  mov     rax, [rax+98h]
0x140016196  call    _guard_dispatch_icall
0x14001619b  mov     rcx, cs:WdfFunctions_01015
0x1400161a2  mov     rdx, rax
0x1400161a5  mov     r8, cs:off_140022500
0x1400161ac  mov     rax, [rcx+650h]
0x1400161b3  mov     rcx, cs:WdfDriverGlobals
0x1400161ba  call    _guard_dispatch_icall
0x1400161bf  mov     rcx, cs:WdfFunctions_01015
0x1400161c6  mov     rbx, rax
0x1400161c9  mov     rdx, [rdi+0E8h]
0x1400161d0  mov     rax, [rcx+9E8h]
0x1400161d7  mov     rcx, cs:WdfDriverGlobals
0x1400161de  call    _guard_dispatch_icall
0x1400161e3  mov     rax, rbx
0x1400161e6  mov     rbx, [rsp+28h+arg_0]
0x1400161eb  add     rsp, 20h
0x1400161ef  pop     rdi
0x1400161f0  retn
```
