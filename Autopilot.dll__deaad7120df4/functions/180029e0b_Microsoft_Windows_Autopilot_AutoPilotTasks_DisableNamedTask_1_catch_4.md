# _Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask_::_1_::catch$4

- ea: `0x180029e0b`
- end: `0x180029e41`
- name: `_Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask_::_1_::catch$4`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x180029e1c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x84,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029e0b  mov     [rsp+arg_8], rdx
0x180029e10  push    rbp
0x180029e11  sub     rsp, 20h
0x180029e15  mov     rbp, rdx
0x180029e18  mov     rcx, [rbp+28h]; this
0x180029e1c  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x180029e23  mov     edx, 84h; void *
0x180029e28  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029e2d  mov     [rbp+38h], eax
0x180029e30  mov     rax, 0
0x180029e3a  add     rsp, 20h
0x180029e3e  pop     rbp
0x180029e3f  retn
```
