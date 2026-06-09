# _Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask_::_1_::catch$35

- ea: `0x180029f25`
- end: `0x180029f61`
- name: `_Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask_::_1_::catch$35`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x180029f39`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask_::_1_::catch_35(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 464) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 440),
                            (void *)0x6C,
                            (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180029f25  mov     [rsp+arg_8], rdx
0x180029f2a  push    rbp
0x180029f2b  sub     rsp, 30h
0x180029f2f  mov     rbp, rdx
0x180029f32  mov     rcx, [rbp+1B8h]; this
0x180029f39  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x180029f40  mov     edx, 6Ch ; 'l'; void *
0x180029f45  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029f4a  mov     [rbp+1D0h], eax
0x180029f50  mov     rax, 0
0x180029f5a  add     rsp, 30h
0x180029f5e  pop     rbp
0x180029f5f  retn
```
