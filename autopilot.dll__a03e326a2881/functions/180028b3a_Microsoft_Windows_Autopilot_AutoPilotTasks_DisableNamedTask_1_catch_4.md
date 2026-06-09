# _Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask_::_1_::catch$4

- ea: `0x180028b3a`
- end: `0x180028b70`
- name: `_Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask_::_1_::catch$4`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180028b4b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

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
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028b3a  mov     [rsp+arg_8], rdx
0x180028b3f  push    rbp
0x180028b40  sub     rsp, 20h
0x180028b44  mov     rbp, rdx
0x180028b47  mov     rcx, [rbp+28h]; this
0x180028b4b  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028b52  mov     edx, 84h; void *
0x180028b57  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028b5c  mov     [rbp+38h], eax
0x180028b5f  mov     rax, 0
0x180028b69  add     rsp, 20h
0x180028b6d  pop     rbp
0x180028b6e  retn
```
