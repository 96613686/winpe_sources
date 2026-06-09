# _Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask_::_1_::catch$10

- ea: `0x180028cb9`
- end: `0x180028cef`
- name: `_Microsoft::Windows::Autopilot::AutoPilotTasks::RunTask_::_1_::catch$10`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180028cca`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

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
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180028cb9  mov     [rsp+arg_8], rdx
0x180028cbe  push    rbp
0x180028cbf  sub     rsp, 20h
0x180028cc3  mov     rbp, rdx
0x180028cc6  mov     rcx, [rbp+68h]; this
0x180028cca  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028cd1  mov     edx, 0C6h; void *
0x180028cd6  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028cdb  mov     [rbp+78h], eax
0x180028cde  mov     rax, 0
0x180028ce8  add     rsp, 20h
0x180028cec  pop     rbp
0x180028ced  retn
```
