# _Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask_::_1_::catch$10

- ea: `0x180029f8b`
- end: `0x180029fc1`
- name: `_Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask_::_1_::catch$10`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x180029f9c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 120) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 104),
                            (void *)0xC6,
                            (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180029f8b  mov     [rsp+arg_8], rdx
0x180029f90  push    rbp
0x180029f91  sub     rsp, 20h
0x180029f95  mov     rbp, rdx
0x180029f98  mov     rcx, [rbp+68h]; this
0x180029f9c  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x180029fa3  mov     edx, 0C6h; void *
0x180029fa8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029fad  mov     [rbp+78h], eax
0x180029fb0  mov     rax, 0
0x180029fba  add     rsp, 20h
0x180029fbe  pop     rbp
0x180029fbf  retn
```
