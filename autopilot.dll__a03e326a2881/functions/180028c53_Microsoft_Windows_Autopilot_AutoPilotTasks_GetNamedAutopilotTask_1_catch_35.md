# _Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask_::_1_::catch$35

- ea: `0x180028c53`
- end: `0x180028c8f`
- name: `_Microsoft::Windows::Autopilot::AutoPilotTasks::GetNamedAutopilotTask_::_1_::catch$35`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180028c67`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

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
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180028c53  mov     [rsp+arg_8], rdx
0x180028c58  push    rbp
0x180028c59  sub     rsp, 30h
0x180028c5d  mov     rbp, rdx
0x180028c60  mov     rcx, [rbp+1B8h]; this
0x180028c67  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028c6e  mov     edx, 6Ch ; 'l'; void *
0x180028c73  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028c78  mov     [rbp+1D0h], eax
0x180028c7e  mov     rax, 0
0x180028c88  add     rsp, 30h
0x180028c8c  pop     rbp
0x180028c8d  retn
```
